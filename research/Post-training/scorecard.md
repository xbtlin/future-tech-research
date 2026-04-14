# Post-training 评分卡

**研究日期**：2026-04-14
**当前阶段**：**小规模商业化 → 大规模商业化过渡**。证据：Surge AI 2025 年 8 月 ARR 已达 14 亿美元（[Sacra](https://sacra.com/c/surge-ai/)），Scale AI 2025 年营收约 20 亿美元（[Sacra](https://sacra.com/c/scale-ai/)），主营均为 post-training 数据/RLHF；同时开源工具链（verl、OpenRLHF、TRL）已被字节、阿里 Qwen、Moonshot、Meta、NVIDIA、Microsoft Research 等广泛采用（[verl GitHub](https://github.com/volcengine/verl)），但"最佳实践"仍在每 3-6 个月迭代一次。

---

## 1. 技术成熟度　★★★★☆
范式已跑通（RL + verifiable reward 成为前沿标配），但 reward hacking、pass@k 上限、self-play 稳定性三大瓶颈未解。

**关键瓶颈**
- **Reward hacking / 过优化**：OpenAI o3 训练中 reward hacking 以更隐蔽形式复发（[Interconnects](https://www.interconnects.ai/p/openais-o3-over-optimization-is-back)）。
- **RLVR 的能力天花板**：Tsinghua 实证 RLVR 只提升 pass@1、在大 k 下 base model 反而更强（[arXiv 2504.13837](https://arxiv.org/abs/2504.13837)，NeurIPS 2025 满分论文）。
- **Process reward model 仍弱**：PRMBench 评测 15 个 PRM，在非冗余、循环逻辑、欺骗抵抗维度普遍失败（[PRMBench](https://prmbench.github.io/)）。

**过去 24 个月里程碑**
- DeepSeek-R1 GRPO（2025.01）——去掉 critic，显存降约 50%（[HF blog](https://huggingface.co/blog/NormalUhr/grpo)）。
- OpenAI o1 → o3 RL 算力提升 >10x，2025 年大部分能力进步来自更长 RL run 而非更大预训练（[Karpathy 2025 回顾](https://karpathy.bearblog.dev/year-in-review-2025/)）。
- Meta SPICE（2025.10）self-play + corpus grounding，数学 +8.9%、通用推理 +9.8%（[arXiv 2510.24684](https://arxiv.org/abs/2510.24684)）。
- Anthropic 2026.01 发布第二版 Constitution，从"规则列表"转向"解释 why"（[Anthropic](https://www.anthropic.com/news/claude-new-constitution)）。
- Meta-Rewarding（2024.07）让 Llama-3-8B 在 AlpacaEval 2 胜率从 22.9%→39.4%（[arXiv 2407.19594](https://openreview.net/forum?id=lbj0i29Z92)）。

## 2. 经济性　★★★☆☆
**RLVR 相对 RLHF 的成本节省**
- GRPO 去掉与 policy 同规模的 critic，显存与算力开销降约 50%（[HF blog](https://huggingface.co/blog/NormalUhr/grpo)）。
- RLVR 用可验证奖励（数学答案、单元测试）替代人工偏好标注，人工数据开支大幅下降——但前沿实验室人工偏好数据订单仍在增长（见 §3）。

**合成数据占比**
- Phi-4 训练用了约 50 个合成数据集、合计约 4000 亿 tokens，synthetic 占训练集"大部分"（具体百分比未披露，[arXiv 2412.08905](https://arxiv.org/abs/2412.08905)）。
- Anthropic Constitutional Classifiers 完全基于 constitution 生成的合成数据训练（[Anthropic](https://www.anthropic.com/research/next-generation-constitutional-classifiers)）。

**"RL 算力将与预训练同等"——是好是坏？**
- 2025 年 7 月 xAI Grok 4 被估计已达 RL compute ≈ pretraining compute（[LessWrong](https://www.lesswrong.com/posts/xpj6KhDM9bJybdnEe/how-well-does-rl-scale)）。
- [SemiAnalysis 2025.06](https://semianalysis.com/2025/06/08/scaling-reinforcement-learning-environments-reward-hacking-agents-scaling-data/) 指出：跨过 parity 后再 10x RL 只能换来 5.5x 总算力膨胀，边际收益锐减。证据显示短期内算力仍可涨（单位美元能力仍优于预训练扩张），但 2027 后再 1,000,000x 级扩张经济上不可行。

## 3. 需求真实性　★★★★★
**技术需求端**：DeepSeek、OpenAI、Google、Anthropic、Meta、Moonshot、Qwen 均已把 RL/RLVR 作为前沿模型主通道（[Interconnects: state of post-training 2025](https://www.interconnects.ai/p/the-state-of-post-training-2025)）。

**付费端——数据/标注**
- Surge AI：2025.08 ARR 14 亿美元（2024 年 12 亿），121 人团队，客户含 Google/OpenAI/Anthropic，2025.07 首轮外部融资寻求 10 亿美元、估值 150 亿+（[Sacra](https://sacra.com/c/surge-ai/)、[TechStartups](https://techstartups.com/2025/07/01/surge-ai-seeks-1b-at-15b-valuation-in-first-ever-raise-as-scale-ai-loses-customers-and-ceo-to-meta/)）。
- Scale AI：2025 年营收约 20 亿美元（YoY 130%），但 Meta 入股后 Google/OpenAI/xAI 流失，Google 原计划 2 亿美元支出撤回（[Sacra](https://sacra.com/c/scale-ai/)）。
- Snorkel AI：2025.05 Series D 1 亿美元、估值 13 亿美元，推出 Expert Data-as-a-Service 专做 reasoning/agent post-training 数据（[FinSMEs](https://www.finsmes.com/2025/05/snorkel-ai-raises-100m-in-series-d-funding-at-a-1-3-billion-valuation/)）。

**付费端——企业自建 RL 基建**：verl 贡献/采用方覆盖字节、Qwen、Moonshot、Meta、Microsoft Research、Baidu、LinkedIn、Amazon、Meituan、Xiaomi、Snowflake、NVIDIA research 等数十家（[verl GitHub](https://github.com/volcengine/verl)），OpenRLHF 0.10 支持 VLM RL（[OpenRLHF](https://github.com/OpenRLHF/OpenRLHF)）。

## 4. 生态成熟度　★★★☆☆
- **开源框架**：TRL（19k 行）、verl（32k 行，字节主导）、OpenRLHF（8.5k 行，最精简）三足鼎立，均已接入 vLLM（[vLLM 60k stars](https://x.com/vllm_project/status/1977724334157463748)）；迭代活跃但 API 每季度仍在破坏性变更。
- **Benchmark**：PRMBench（6,216 题 / 83,456 step 级标注，ACL 2025）、RewardBench（[allenai](https://github.com/allenai/reward-bench)）已是事实标准，但"process-level reward 协议"未有统一规范。
- **人才**：不确定具体人数；代理指标是 verl/OpenRLHF 贡献者名单横跨学术+工业数十家机构，相比 2023 年 TRL 单点，供给面扩张数个量级。
- **标准化 reward 评估协议**：尚无。CAI 风格、LLM-as-judge、PRM、RLVR 各家做法差异显著。

## 5. 3 年拐点概率　**65%**
拐点定义：Post-training 从"研究方向"→"标准化工程管线、有明确最佳实践"。

**支持（三条）**
1. RLVR 已成为前沿模型事实默认，工具链（verl / OpenRLHF / TRL）+ 推理后端（vLLM）已形成稳定接口层，新团队复现 R1 级流程的时间从 2025 年的数月缩到周级（[Anyscale](https://www.anyscale.com/blog/open-source-rl-libraries-for-llms)）。
2. 付费市场已验证——Surge 14 亿 / Scale 20 亿 / Snorkel 13 亿估值同时存在，说明 post-training 数据+工具链不是"一家赢家通吃"的研究设施，而是供应链。
3. Self-play（SPICE）+ corpus grounding 给出了不依赖无限人工标注的自我改进路径，若被证复制到 >30B 模型，标准化最后一块拼图到位。

**反面（两条）**
1. Tsinghua 论文（NeurIPS 2025 perfect score）实证 RLVR 只压缩搜索、不提升 pass@k 天花板（[arXiv 2504.13837](https://arxiv.org/abs/2504.13837)）——若成立，post-training 即将撞墙，"最佳实践"会被下一代范式取代而非沉淀。
2. RL compute 跨过 pretraining parity 后边际收益骤降（[SemiAnalysis](https://semianalysis.com/2025/06/08/scaling-reinforcement-learning-environments-reward-hacking-agents-scaling-data/)），经济上可能逼迫行业回摆到"合成数据 + 大预训练"路径，管线再次被推翻。

## 综合判断
- **一句话定性**：Post-training 已经是前沿模型能力增长的主战场，处在"工具链成型但方法论仍在换代"的中段；工程化正在发生，标准化还差 1-2 个范式周期。
- **核心赌注**：赌 RLVR + self-play + process reward 的组合能突破 Tsinghua 指出的 pass@k 天花板。错的话最先出问题的环节是 **reward model**——若 PRM 长期在 PRMBench 上分数不涨，所有基于 verifiable reward 的 scaling 都是在刷 pass@1 而非扩能力边界，整条叙事塌方。

**跟踪信号（6-12 个月盯这 3 个指标）**
1. **GRPO / DAPO / REINFORCE++ 在 AIME 2026 与 Codeforces Div1 上的 head-to-head 公开报告**——数据源：DeepSeek、Qwen、Moonshot 技术报告 + verl 官方 benchmark（[verl](https://github.com/volcengine/verl)）。
2. **下一代前沿模型（GPT-5.x / Claude Opus 5 / Gemini 3 Ultra / DeepSeek-V4）是否继续延续 R1 式 long-RL 路径，还是回归大预训练**——数据源：各家 technical report、Epoch AI、SemiAnalysis 算力估算。
3. **Self-play 是否出现第一个工业级产品**——指标：SPICE 后续复现在 ≥30B 模型上的 paper、Meta / DeepMind 是否在旗舰模型技术报告中披露 self-play 阶段占比；数据源：arXiv cs.LG、Meta AI blog、DeepMind blog。

**关联标的/组织（观察清单）**
- Scale AI（post-training 数据，Meta 系，客户流失需跟踪）
- Surge AI（高端 RLHF 数据，首轮外部融资中）
- Snorkel AI（Expert Data-as-a-Service，企业端）
- DeepSeek（GRPO 源头，下一代是否继续开源）
- Anthropic（CAI v2，合成数据路线代表）
- OpenAI / Meta / Google DeepMind（RL compute 主导者）
- 合成数据创业公司：Gretel、Mostly AI（观察是否被前沿实验室采购）

---
*所有主张附来源链接；不确定项已在文中明示"不确定"。数据以 2026-04-14 前公开资料为准。*
