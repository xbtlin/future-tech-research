# Agentic 评分卡

**研究日期**：2026-04-14
**范围界定**：本评分卡仅评估"大模型自身的 agentic 能力"（长程规划、工具使用、自我纠错、跨 session 记忆等模型内化能力），不含工程层 harness（scaffold、retry、RAG、外部 memory store）。
**当前阶段**：**试点 → 小规模商业化过渡期**。软件工程（Devin/Claude Code/Cursor Agent）和客服（Sierra）两个垂直已跨过 $100M ARR；通用 agent（Operator/Manus）仍停留在 demo 与早期试点。

---

## 1. 技术成熟度　★★★☆☆

**瓶颈**：
- **长程 credit assignment**：模型对"哪一步决定了最终成败"的归因能力弱；TAU-Bench pass^8 相对 pass^1 衰减 60%，GPT-4o 在 τ-retail 从 ~80% → ~25%（[Sierra τ-Bench](https://sierra.ai/blog/benchmarking-ai-agents)）
- **错误累积（17x trap）**：每步 95% 成功率 × 50 步 = 7.7% 端到端；需要 >99% 单步才能做 50 步任务
- **self-correction vs self-delusion**：Manus 案例 14 类失败模式中多次出现"幻觉成功汇报"（[MIT Tech Review](https://www.technologyreview.com/2025/03/11/1113133/manus-ai-review/)）
- **跨 session 记忆一致性**：模型内化记忆仍薄弱，主要靠外部 scaffold，不算模型本征能力

**里程碑**：
- **METR Time Horizon 1.1**：Claude Opus 4.6 在 50% 成功率下 = **14.5 小时**人类任务（2026-02-20 测量），doubling time 从 TH1 的 165 天缩短至 TH1.1 的 **131 天**（[METR TH1.1](https://metr.org/blog/2026-1-29-time-horizon-1-1/)、[LessWrong 估测](https://www.lesswrong.com/posts/WacuyurbABwNv8ziq/estimating-metr-time-horizons-for-claude-opus-4-6-and-gpt-5)）
- **OpenAI Operator / ChatGPT Agent Mode**：2025 年上线，Plus/Pro 全量；Pro 单月 400 任务
- **Gemini 3 Agent、Anthropic Computer Use、Devin 2.2**：computer-use 从 demo 走向 beta 生产
- **Manus 风波**：中国背景 + 过度营销 + 测试失败，成为 "shell wrapping" 反面教材（[CNBC](https://www.cnbc.com/2026/03/27/meta-manus-china-review-singapore-washing-model-regulation-.html)）

**Benchmark 状态**：
| Benchmark | 当前 SOTA | 人类/饱和 | 备注 |
|---|---|---|---|
| SWE-Bench Verified | Claude Opus 4.5 = **80.9%** | 污染严重，OpenAI 已停报 | [CodeSOTA](https://www.codesota.com/news/swe-bench-contamination-debate) |
| SWE-Bench Pro | Claude Opus 4.5 = **45.9%** | 真实难度，抗污染 | [Scale Pro LB](https://labs.scale.com/leaderboard/swe_bench_pro_public) |
| OSWorld-Verified | GPT-5.4 = **75.0%** | 人类基线 72.4% | 首次突破人类（[NxCode](https://www.nxcode.io/resources/news/gpt-5-4-release-date-features-pricing-2026)） |
| GAIA | Claude Sonnet 4.5 = **74.6%** | 人类 92% | [HAL GAIA](https://hal.cs.princeton.edu/gaia) |
| TAU-Bench (pass^8) | ~25-40% | 衰减极快 | 端到端可靠性差 |
| BrowseComp | ~60-89% | 接近饱和 | 基准本身可能退役 |
| MLE-Bench (Kaggle) | o1+AIDE = **16.9%** 铜牌（pass@1）/ 34.1% (pass@8) | 人类金牌 | [OpenAI MLE-bench](https://openai.com/index/mle-bench/) |

**小结**：单一窄域（coding、computer use）已达可用；**跨域通用 agent 仍在 50% 可靠性线以下**。

---

## 2. 经济性　★★☆☆☆

- **ChatGPT**：Plus $20/mo（Agent Mode 每月 ~400 任务上限）、Pro $200/mo（最大额度 + Operator）（[ChatGPT Pricing](https://chatgpt.com/pricing/)）
- **Claude Code**：按 API token 计费或 Claude Max $100-200/mo；Anthropic 分析师估算 Claude Code 年化收入 **$2.5B+**（2026-03，未官方确认）（[The New Stack](https://thenewstack.io/ai-coding-tool-stack/)）
- **Devin**：团队订阅约 $500/mo/seat 起
- **单个 OSWorld 50-step 任务 API 成本**：按 Claude Opus 4.6 ($15/$75 per MTok) 估算，单任务 input+output 约 200-500K tokens → **$5-20/任务**；GPT-5.4 ($2.50/MTok input) 显著更便宜，约 **$1-5/任务**
- **企业 ROI**：Sierra 客服 agent 客单价 $1-5/resolved ticket（vs 人工 $8-15），数学上成立；Devin 替代初级工程师账单时薪 $2-5 vs 外包 $30-80。但**多数企业试点仍未跑出 clean ROI**，主要阻碍是返工、审核、事故成本

**小结**：单位成本已远低于人工，但**端到端可靠性不足导致"隐性 HITL 成本"吞掉毛利**。

---

## 3. 需求真实性　★★★★☆

**公开付费案例**：
- **Cognition (Devin)**：ARR 从 $1M (2024-09) → **$73M** (2025-06) → 收购 Windsurf 后合计 **~$150M**；2025-09 融资 $400M @ $10.2B（[TechCrunch](https://techcrunch.com/2025/09/08/cognition-ai-defies-turbulence-with-a-400m-raise-at-10-2b-valuation/)、[Sacra](https://sacra.com/c/cognition/)）
- **Sierra (Bret Taylor)**：21 个月达 **$100M ARR**（2025-11）；$10B 估值；2026-03 收购 Opera Tech（[TechCrunch](https://techcrunch.com/2025/11/21/bret-taylors-sierra-reaches-100m-arr-in-under-two-years/)）
- **Cursor**：$10B 估值，**Fortune 500 50%** 渗透，企业占比 45-60%（[Panto](https://www.getpanto.ai/blog/cursor-ai-statistics)）
- **Claude Code**：JetBrains 2026-01 调查 **18% 开发者工作中使用**；与 Cursor 并列
- **Replit Agent 3**：自然语言端到端建 web app

**部署行业**：软件工程（最成熟）→ 客服/支持 → 数据分析/BI → 运维（SRE/DevOps 开始）→ 营销 SDR（11x 等）

**失败/回退案例**：
- **Adept**：核心团队被 Amazon acqui-hire（2024），产品实际上搁浅
- **Imbue**：从 agent 公司转向基础研究/教育，战略撤退
- **Manus**：14 类失败 + 中国地缘风险，企业端信任崩坏
- **HITL 回归**：OSWorld 75% 意味着 1/4 失败率 → 写操作场景几乎都回到 human-in-the-loop 审核

**小结**：需求真实且已 PMF，但**集中在 coding 和客服两个 vertical**；通用 agent 需求仍靠 hype 拉动。

---

## 4. 生态成熟度　★★★☆☆

- **开源框架**：LangChain **126k stars**、AutoGen **54k**、CrewAI **44k**（Fortune 500 60%+）、LangGraph **24k**（2026 Q1 增速最快）、OpenHands（原 OpenDevin）持续迭代（[o-mega](https://o-mega.ai/articles/langgraph-vs-crewai-vs-autogen-top-10-agent-frameworks-2026)）
- **评估标准**：HAL (Princeton)、Steel.dev leaderboard（121 reported results × 16 benchmarks）、Scale SWE-Bench Pro、τ-Bench 已成社区共识
- **人才供给**：AI/agent engineer 岗位从 2024 的稀缺到 2026 已有成建制培训；但能 debug 多 agent 系统的仍极少
- **关键研究**：Cemri et al. 2025《Why Do Multi-Agent LLM Systems Fail?》指出 7 个 SOTA 多 agent 系统失败率 **41%-86.7%**，14 类失败模式（[arXiv 2503.13657](https://arxiv.org/abs/2503.13657)）——生态还在"知道哪里坏了"阶段，不是"修好了"阶段

---

## 5. 3 年拐点概率　**40%**

**拐点定义**：Agentic 从"单一窄域演示/试点"变成"跨行业规模化商业部署"（≥1000 家企业在 ≥3 个非 coding vertical 规模化使用，且合同续约率 >70%）。

**支持理由（可证伪）**：
1. **METR 曲线**：若 131 天 doubling 延续 3 年，任务时长从 14.5h → ~900h（约 4 个月人类工作量）；即使减半为 7 个月 doubling，也能到 ~230h → 覆盖大部分"junior analyst 一周任务"
2. **单位经济**：GPT-5.4 级别模型 OSWorld 任务成本已 <$5，低于任何人类时薪；成本曲线继续往下，会强推企业尝试
3. **SOTA 突破人类基线**：OSWorld 75% > 72.4%（2026-03）+ SWE-Bench Pro 从 45.9% 每 6 个月 +10pp → 3 年后跨越 70% 可靠线

**反面证据（两条）**：
1. **HITL 不可绕开**：τ-Bench pass^8 衰减 60%、OSWorld 25% 失败率、多 agent 41-86.7% 失败率（[arXiv 2503.13657](https://arxiv.org/abs/2503.13657)）——写操作场景人工审核无法退场，"agent 只是改名的 copilot"
2. **benchmark 与现实 gap**：SWE-Bench Verified 污染（80%+ → Pro 46%）揭示 benchmark 进步可能虚高；Manus/Adept/Imbue 案例显示"demo to prod"摔跤频繁；多数企业 agent POC 到生产转化率 <20%

---

## 综合判断

- **一句话**：Agentic 是**已被软件工程和客服两个 vertical 证伪证真的真需求**，但"跨域通用 agent"仍被可靠性墙挡在 demo 阶段；3 年内会有 2-3 个新 vertical 跑通，但不会全面商业化。
- **核心赌的是**：**模型本征可靠性能否随 METR 曲线把单步成功率从 95% 推到 99%+**。如果能，50-100 步任务自然打开；如果不能，agentic 永远是"带人 copilot"。
- **跟踪信号**（3 个）：
  1. **METR 任务时长 doubling**：能否继续每 4-7 个月翻倍（2026 年底应达 ~30h，2027 Q2 应达 ~60h）
  2. **SWE-Bench Pro / τ-Bench pass^8**：前者 +10pp/半年、后者衰减收窄到 <30% 是拐点信号
  3. **Operator/Agent Mode MAU 与留存**：OpenAI Agent Mode 付费用户数 + 30 天留存率（目前未披露，但是最诚实的需求真实性指标）
- **关联标的**：
  - 模型层：**Anthropic**（Claude Code 年化 $2.5B 领跑 coding agent）、**OpenAI**（Operator + GPT-5.4 OSWorld 75%）、**Google**（Gemini 3 Agent，追赶中）
  - 应用层：**Cognition/Devin**（$10.2B，coding vertical 龙头）、**Sierra**（$10B，客服 vertical 龙头）、**Cursor**（$10B，IDE agent）、**Replit**（端到端 app agent）
  - 风险/撤退：**11x**（SDR agent，增长放缓）、**Adept**（已 acqui-hire）、**Imbue**（战略转向）、**Manus**（声誉受损）
  - **不确定**：未上市公司真实留存与毛利均无披露，ARR 数字多为 run-rate 不等于 GAAP 收入

**Sources** 已以内联 markdown 链接形式嵌入各条目；关键依据：METR TH1.1、Scale SWE-Bench Pro、Sierra τ-Bench、arXiv 2503.13657、TechCrunch Cognition/Sierra 融资报道、OpenAI MLE-bench、NxCode GPT-5.4 评测。
