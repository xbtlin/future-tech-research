# Long-context / Memory 评分卡

**研究日期**：2026-04-14
**当前阶段**：技术路线之争进行时——"原生超长上下文"（Gemini 2.5 Pro 2M、Claude Opus 4.6 1M、Grok 4 2M）与"短上下文 + 强检索 + 结构化记忆"（Letta、Mem0、Zep、HippoRAG 2）并存。上下文窗口名义长度（1M-10M）已远超有效长度，Chroma 2025 年 *Context Rot* 研究成为行业共识参考。

---

## 1. 技术成熟度　★★

**数据**：
- Chroma 2025 年 *Context Rot* 对 18 个 frontier 模型（GPT-4.1、Claude Opus 4、Gemini 2.5）测试：从 10K→100K tokens 准确率下降 20-50%，Claude 退化最慢但仍未免疫；"lost-in-the-middle"造成中段 30%+ 准确率跌幅；semantically similar distractor 额外恶化；有序文档反而比乱序 haystack 表现更差。([Chroma](https://research.trychroma.com/context-rot))
- MRCR v2 8-needle @ 1M tokens：Claude Opus 4.6 76%（较 Sonnet 4.5 的 18.5% 翻 4 倍），Gemini 3 Pro 77%；但 LongBench v2 @128K 为 68.2%，@1M 骤降到 26.3%。([MRCR v2 Leaderboard](https://llm-stats.com/benchmarks/mrcr-v2-\(8-needle\)))
- 基准本身仍滞后：RULER、LongBench v2、MRCR 均设计于 128K 时代。([Awesome Agents](https://awesomeagents.ai/leaderboards/long-context-benchmarks-leaderboard/))

**瓶颈**：context rot、深度推理 vs 召回的权衡、跨 session 记忆一致性、unlearning、多 agent 共享记忆标准缺失。

## 2. 经济性　★★

**长上下文推理单价**（2026-04）：
- Claude Opus 4.6（1M context）：$5 / $25 per 1M tokens，较上代降价 67%；prompt cache 9 折后 $0.50 / 1M，batch 叠加可至 ~$0.25 / 1M（-95%）。([TLDL](https://www.tldl.io/resources/llm-api-pricing-2026))
- Gemini 2.5 Pro（2M context）：$1.25 / $10，cache 后 $0.13 / 1M。([Gemini pricing](https://ai.google.dev/gemini-api/docs/pricing))
- KV cache：Transformer 的 KV 内存随 context 线性增长，1M context 单会话 GPU 内存占用数十 GB；Jamba 混合 SSM 架构 KV 占用小 1-2 数量级，256K context 可在单卡推理。([AI21 Jamba](https://www.ai21.com/blog/announcing-jamba/))
- 开源 memory 系统：Letta / Mem0 自托管 + 向量 DB，Chroma Cloud 最低 $0.02/GB/月；成本远低于往 1M 原生 context 硬塞。

## 3. 需求真实性　★★★

- MongoDB Atlas Vector Search 成为 Q4 2025 最快增长产品线；MongoDB FY26 Q3 收入指引 $587-592M，全年 $2.34-2.36B，Atlas YoY 加速到 30%+；企业 RAG 部署 2025 年增长 280%。([SaaStr](https://www.saastr.com/mongodb-the-great-ai-turnaround-story-of-2025/))、([MongoDB IR](https://investors.mongodb.com/news-releases/news-release-details/mongodb-inc-announces-third-quarter-fiscal-2026-financial))
- Pinecone：2026-03 付费客户突破 4,000；累计融资 $138M，估值未最新披露。([PitchBook](https://pitchbook.com/profiles/company/431647-21))
- Qdrant 2026-03 完成 Series B $50M；Chroma 种子轮 $18M、Cloud 已上线。
- Agent memory 商业化：Letta V1 runtime、Mem0 SDK 接入 LangChain/CrewAI/AutoGen 均已产生付费用户。([Vectorize](https://vectorize.io/articles/mem0-vs-letta))
- 长文档/法律/科研场景：Gemini 2M、Claude 1M 被大量用于合同分析、整卷病历、代码仓库级问答。

## 4. 生态成熟度　★★★

- 开源 memory 框架：Letta（MemGPT 演进版，LLM-as-OS 范式）、Mem0（框架无关三层 scope：user/session/agent）、Zep、HippoRAG 2、MemOS 均在 2026 维持活跃更新。([Atlan](https://atlan.com/know/best-ai-agent-memory-frameworks-2026/))
- 向量 DB：Pinecone、Weaviate、Chroma、Qdrant、Milvus、pgvector、MongoDB Atlas 并存；企业集成度高。
- SSM / 混合架构：AI21 Jamba（Transformer+Mamba+MoE 首个 production-grade 混合模型，256K context，12B/52B active params）；Mamba-3 已在 OpenReview；但尚无 SSM-based frontier 模型登顶 MRCR/RULER。([AI21](https://www.ai21.com/blog/rise-of-hybrid-llms/))

## 5. 3 年拐点概率　35%

**拐点定义**：1M+ context 在 MRCR v2 8-needle / BABILong 深度推理上错误率降到 <10%，或 memory agent 成为主流 API（Claude/GPT/Gemini）原生能力。

**理由三条**：
1. Opus 4.6 单代把 8-needle MRCR v2 从 18.5%→76%，边际进步巨大，再两代线性外推即可破 90%。
2. 长上下文 caching 单价 1 年降 90%+，经济门槛已不是瓶颈。
3. Letta、Mem0 付费客户与 MongoDB Vector Search 收入侧数据验证需求真实。

**反面证据两条**：
1. Chroma *Context Rot*、BABILong 的核心结论：长 context 退化是 transformer 注意力机制的结构性问题，不会被规模 scaling 自动解决；"短 context + 强检索 + 结构化记忆"才是未来生产架构。([Chroma](https://www.trychroma.com/research/context-rot))、([Understanding AI](https://www.understandingai.org/p/context-rot-the-emerging-challenge))
2. LongBench v2 @1M 仅 26.3%，而 @128K 68.2%——在真正需要推理（非纯召回）任务上，1M context 仍基本不可用。

## 综合判断

- **一句话定性**：长上下文是"看起来已解决、实际远未解决"的赛道；memory 系统是更确定的工程红利。
- **核心赌的是什么**：赌 transformer 架构在长 context 深度推理上存在结构性天花板，因此中期最大价值沉淀在"memory layer + 向量 DB + 混合架构"——不是卖更长 context 的模型厂，而是围绕 context 做工程的基础设施。
- **跟踪信号**：
  1. 下一代模型在 MRCR v2 8-needle @1M、BABILong、LongBench v2 @1M 的数字（目前 26-77% 区间）；
  2. 是否出现 SSM / Mamba / Jamba 架构的 frontier 模型（当前 Jamba 仍是中型模型）；
  3. Memory agent 是否被集成进 Claude / GPT / Gemini 原生 API（而非 SDK 层 Letta/Mem0）；
  4. Anthropic / OpenAI prompt caching 定价曲线（进一步降价=长 context 胜出；停滞=memory 系统胜出）。
- **关联标的**：
  - 上市：**MongoDB**（Atlas Vector Search 加速，最干净的 picks-and-shovels）、**Anthropic / OpenAI / Google**（原生长 context 方代言人，未上市或嵌于大厂）。
  - 未上市：**Pinecone**（$138M 累计融资，4,000+ 付费客户）、**Chroma**（研究 + Cloud 双品牌）、**Weaviate**、**Qdrant**（Series B $50M）、**Letta**、**Mem0**、**AI21**（Jamba，押注混合架构）。

## 来源汇总

- [Chroma Context Rot 研究](https://research.trychroma.com/context-rot)
- [Chroma Research 官网](https://www.trychroma.com/research/context-rot)
- [Understanding AI: Context rot](https://www.understandingai.org/p/context-rot-the-emerging-challenge)
- [MRCR v2 Leaderboard](https://llm-stats.com/benchmarks/mrcr-v2-\(8-needle\))
- [Long-context benchmarks leaderboard](https://awesomeagents.ai/leaderboards/long-context-benchmarks-leaderboard/)
- [BenchLM Reasoning 2026](https://benchlm.ai/reasoning)
- [LLM API Pricing 2026 (TLDL)](https://www.tldl.io/resources/llm-api-pricing-2026)
- [Gemini API pricing](https://ai.google.dev/gemini-api/docs/pricing)
- [Letta GitHub](https://github.com/letta-ai/letta)
- [Mem0 vs Letta (Vectorize)](https://vectorize.io/articles/mem0-vs-letta)
- [Atlan: Best AI Agent Memory Frameworks 2026](https://atlan.com/know/best-ai-agent-memory-frameworks-2026/)
- [AI21 Jamba 发布](https://www.ai21.com/blog/announcing-jamba/)
- [AI21: Rise of hybrid LLMs](https://www.ai21.com/blog/rise-of-hybrid-llms/)
- [MongoDB FY26 Q3 财报](https://investors.mongodb.com/news-releases/news-release-details/mongodb-inc-announces-third-quarter-fiscal-2026-financial)
- [SaaStr: MongoDB AI turnaround](https://www.saastr.com/mongodb-the-great-ai-turnaround-story-of-2025/)
- [Pinecone PitchBook](https://pitchbook.com/profiles/company/431647-21)
- [Lost in the Middle (arxiv)](https://arxiv.org/abs/2307.03172)
- [LongBench v2](https://longbench2.github.io/)
- [Epoch AI context windows](https://epoch.ai/data-insights/context-windows/)
