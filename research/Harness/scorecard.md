# Harness / Scaffolding 评分卡

**研究日期**：2026-04-14
**当前阶段**：从"百花齐放的工程拼装期"进入"标准化运行时雏形期"——MCP 已于 2026-03-20 正式交由 Linux Foundation 旗下 Agentic AI Foundation 治理，LangGraph v1.0（2025-10）完成 durable execution 稳定化，头部 IDE/CLI 产品（Cursor、Claude Code）进入 10 亿美金级 ARR 阶段，但 harness 与底模能力边界仍在剧烈重划。

## 1. 技术成熟度　★★★

- **上下文管理**：Anthropic 2025-10 发布 *Effective Context Engineering for AI Agents*，明确把 "context engineering" 定义为 prompt engineering 的进阶；学术界 ACE 框架（arXiv:2510.04618）在 agent benchmark 上 +10.6%，解决 context rot / 上下文崩塌。([Anthropic](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)，[arXiv](https://arxiv.org/abs/2510.04618))
- **工具调用标准化**：MCP 2025-11 于 Anthropic 内部孵化 → 2025-12-09 捐赠 Linux Foundation → 2026-03-20 完成治理转交，月下载 9700 万、活跃 server 10,000+，Claude/Cursor/Copilot/Gemini/ChatGPT/VS Code 全部接入。([LF 公告](https://www.linuxfoundation.org/press/linux-foundation-announces-the-formation-of-the-agentic-ai-foundation)，[GitHub Blog](https://github.blog/open-source/maintainers/mcp-joins-the-linux-foundation-what-this-means-for-developers-building-the-next-era-of-ai-tools-and-agents/))
- **durable execution**：LangGraph v1.0 于 2025-10 GA，提供 checkpointing、durable state、HITL 原生 API，Uber/LinkedIn/Klarna 在生产环境使用。([LangChain](https://blog.langchain.com/langchain-langgraph-1dot0/))
- **Computer Use / Desktop Agent**：OSWorld 基准从 2024 年 ~12% 提升到 2025 年 CoACT-1 60.76%（相对人类 72% 上限的 84%）；Devin 2.2（2025）获得完整 Linux desktop、自我验证、自我修复、3× 冷启动提速。([Cognition](https://cognition.ai/blog/introducing-devin-2-2)，[XLANG](https://xlang.ai/blog/osworld-verified))
- **瓶颈仍在**：长 horizon 任务（>2h）可靠性、多 agent 协作 UX、HITL 接口缺统一规范、context window 经济学（每 1M token 多少钱仍决定产品形态）。

## 2. 经济性　★★★★

- **Cursor / Anysphere**：ARR 从 2025-01 的 $100M → 2025-06 的 $500M → 2025 底 $1B → 2026-02 突破 $2B；2025-11 Accel/Coatue 领投 $2.3B、估值 $29.3B；2026 初传闻新一轮估值 $50–60B。30× P/S 的 SaaS，远超传统开发者工具。([TechCrunch](https://techcrunch.com/2025/06/05/cursors-anysphere-nabs-9-9b-valuation-soars-past-500m-arr/)，[CNBC](https://www.cnbc.com/2025/11/13/cursor-ai-startup-funding-round-valuation.html))
- **Windsurf 分拆案**：OpenAI 原定 $3B 收购（2025-05）于 2025-07 崩盘，最终 Google 以 $2.4B 拿走技术授权 + 核心团队，Cognition 接手剩余业务——说明 harness 资产在战略层有明确定价。([Bloomberg](https://www.bloomberg.com/news/articles/2025-05-06/openai-reaches-agreement-to-buy-startup-windsurf-for-3-billion)，[TechCrunch](https://techcrunch.com/2025/07/11/windsurfs-ceo-goes-to-google-openais-acquisition-falls-apart/))
- **Claude Code**：内部估计 2026Q1 run-rate ~$2.5B。([VentureBeat](https://venturebeat.com/orchestration/anthropic-says-claude-code-transformed-programming-now-claude-cowork-is))
- **单位经济**：$20–40/月订阅 vs 单开发者节省 5–15 小时/月（按 $100/h 计 = $500–1500/月价值），ROI 10–50×，是 SaaS 历史上最锋利的单位经济之一。

## 3. 需求真实性　★★★★★

- **Uber**：2026-03 时 84% 开发者为 agentic coding 用户，CLI 工具（含 Claude Code）生成代码占比 100%；Claude Code 使用率 3 个月从 32%→63%。([Pragmatic Engineer](https://newsletter.pragmaticengineer.com/p/how-uber-uses-ai-for-development))
- **Shopify**：通过中央代理层同时接入 Cursor、Claude Code、Copilot、Codex、Gemini，整体生产力 +~20%。([Bessemer](https://www.bvp.com/atlas/inside-shopifys-ai-first-engineering-playbook))
- **Goldman Sachs**：Devin 与 12,000 名人类开发者并行，目标 20% 效率提升。([Contrary Research](https://research.contrary.com/company/cognition))
- **Cognizant × Cognition**（2026-01）：企业级部署合同。付费漏斗非常短——试用 1 周即转付费的比例在 Cursor 公开数据里 >25%。

## 4. 生态成熟度　★★★

- **MCP**：月下载 9700 万、server 10,000+、三大厂（Anthropic/OpenAI/Google）+ AWS/Microsoft/Block/Cloudflare/Bloomberg 全部是 AAIF 成员。([AAIF](https://blog.modelcontextprotocol.io/posts/2025-12-09-mcp-joins-agentic-ai-foundation/))
- **Agent 框架**：LangGraph 事实垄断生产级 orchestration；AutoGen/CrewAI/OpenHands 在研究与垂类仍活跃，但企业生产多选 LangGraph + MCP 组合。
- **标准化**：Linux Foundation Agentic AI Foundation（2025-12）+ AGENTS.md + goose 同时入驻——类似 2014 年 CNCF 起步阶段。生态结构清晰但治理机制、互操作基准仍不足。

## 5. 3 年拐点概率　__60%__

**拐点定义**：Harness 从"每家产品一套"变成类似 Kubernetes 的标准化 agent 运行时——MCP 做工具层总线、LangGraph/类 runtime 做执行层、一套统一 HITL/审计/权限接口。

**支持理由**
1. **标准已落地**：MCP 进 Linux Foundation + 三大厂共同治理，网络效应已经起飞（9700 万月下载），这是 Kubernetes 时刻的必要条件。([LF](https://www.linuxfoundation.org/press/linux-foundation-announces-the-formation-of-the-agentic-ai-foundation))
2. **现金流支撑长期投入**：Cursor $2B ARR + Claude Code $2.5B run-rate + Copilot 数十亿，商业飞轮已自持，不依赖融资续命。
3. **企业侧真实需求**：Uber/Shopify/Goldman 的中央代理层已出现——说明企业需要一个"跨 harness 的统一抽象"，正是标准化拐点的先行信号。

**反面证据**
1. **底模吞噬 harness**：Claude 原生 computer use（2024-10）、Operator（2025）、GPT-5 原生 memory + 原生工具调用，使 harness 工程层价值被快速挤压——Devin 1.0 曾被裸 Sonnet 3.5 在 SWE-bench 上反超，Cognition 不得不把 Devin 重构成 Devin 2.x。([OpenAI Operator]、[Cognition Devin 2.0](https://cognition.ai/blog/devin-2))
2. **IDE 绑定风险**：Cursor 30× P/S，若底模厂商（Anthropic Claude Code CLI、OpenAI Codex CLI）继续下沉到 IDE/CLI 形态，第三方 harness 的差异化可能收敛到 UX 薄层。Windsurf 分拆案已经演示了"harness 没有底模就没有议价权"。

## 综合判断

- **一句话定性**：Harness 是 2026 年最赚钱的 AI 应用层，但它的护城河上限由底模厂商的"原生能力边界"决定——短期超额收益确定，长期结构性风险高。
- **核心赌的是什么**：赌"企业侧需要跨模型、跨工具的中性抽象层"这一需求足够强，以至于 MCP + LangGraph 类标准能独立于任何单一底模活下来（类似 Kubernetes 独立于任何单一云）。
- **跟踪信号**
  - MCP 生态规模：月下载、active server 数量、Fortune 500 部署数（当前 9700 万/月、10,000+ server）
  - 头部产品 ARR 与留存：Cursor ARR（$2B→$4B？）、Claude Code run-rate、企业 seat 续费率
  - 底模原生工具能力：GPT-5/Claude 5/Gemini 3 的原生 computer use、原生 memory 是否导致第三方 harness DAU 下滑
  - OSWorld / SWE-bench Verified 的 harness-free vs harness-assisted gap——gap 收窄即 harness 被吃
- **关联标的**
  - **Anysphere (Cursor)**：$29B→潜在 $60B，最纯粹的 harness 标的
  - **Cognition (Devin + Windsurf 残余)**：autonomous agent 赛道
  - **Anthropic**：Claude Code 已是第二增长曲线，harness 与底模一体化打法
  - **GitHub (Microsoft)**：Copilot 基本盘 + Agent Mode
  - **Replit**：面向非开发者的 agent IDE
  - **Google (Windsurf 技术 + Gemini Code Assist)**：收编后的第二梯队
  - **LangChain**（未上市）：生态层，若 IPO 是标准化最大受益者

## Sources

- [Anthropic: Effective Context Engineering](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)
- [arXiv 2510.04618 — Agentic Context Engineering](https://arxiv.org/abs/2510.04618)
- [Linux Foundation: Agentic AI Foundation](https://www.linuxfoundation.org/press/linux-foundation-announces-the-formation-of-the-agentic-ai-foundation)
- [GitHub Blog: MCP joins Linux Foundation](https://github.blog/open-source/maintainers/mcp-joins-the-linux-foundation-what-this-means-for-developers-building-the-next-era-of-ai-tools-and-agents/)
- [MCP Blog: Joins Agentic AI Foundation](https://blog.modelcontextprotocol.io/posts/2025-12-09-mcp-joins-agentic-ai-foundation/)
- [LangChain: LangGraph 1.0 GA](https://blog.langchain.com/langchain-langgraph-1dot0/)
- [Cognition: Introducing Devin 2.2](https://cognition.ai/blog/introducing-devin-2-2)
- [Cognition: Devin 2.0](https://cognition.ai/blog/devin-2)
- [XLANG: OSWorld-Verified](https://xlang.ai/blog/osworld-verified)
- [OSWorld arXiv 2404.07972](https://arxiv.org/abs/2404.07972)
- [TechCrunch: Anysphere $9.9B / $500M ARR](https://techcrunch.com/2025/06/05/cursors-anysphere-nabs-9-9b-valuation-soars-past-500m-arr/)
- [CNBC: Cursor $2.3B 融资 $29.3B 估值](https://www.cnbc.com/2025/11/13/cursor-ai-startup-funding-round-valuation.html)
- [The Information: Cursor $30B 估值讨论](https://www.theinformation.com/articles/cursor-maker-anysphere-considers-investment-offers-30-billion-valuation)
- [Bloomberg: OpenAI–Windsurf $3B](https://www.bloomberg.com/news/articles/2025-05-06/openai-reaches-agreement-to-buy-startup-windsurf-for-3-billion)
- [TechCrunch: Windsurf 分拆至 Google](https://techcrunch.com/2025/07/11/windsurfs-ceo-goes-to-google-openais-acquisition-falls-apart/)
- [VentureBeat: Claude Code / Claude Cowork](https://venturebeat.com/orchestration/anthropic-says-claude-code-transformed-programming-now-claude-cowork-is)
- [Pragmatic Engineer: Uber AI dev 内幕](https://newsletter.pragmaticengineer.com/p/how-uber-uses-ai-for-development)
- [Bessemer: Shopify AI-first engineering](https://www.bvp.com/atlas/inside-shopifys-ai-first-engineering-playbook)
- [Contrary Research: Cognition 业务分析](https://research.contrary.com/company/cognition)
- [Cognizant × Cognition 企业合作 2026-01-28](https://news.cognizant.com/2026-01-28-Cognizant-and-Cognition-Partner-to-Scale-Autonomous-Software-Engineering-and-Deliver-Business-Value-Across-Enterprise-Operations)

---

## 2026-Q3 更新（2026-08-14）

> 详见 [Q3 更新报告](../../reports/2026-Q3-九大方向更新.md)。

### MCP 做了成立以来最大的破坏性改版

[官方博文](https://blog.modelcontextprotocol.io/posts/2026-07-28/)（2026-07-28），新规范版本号即 `2026-07-28`：

- **从"双向有状态"改为"无状态请求/响应"**：原文 *"MCP is transforming from a bidirectional stateful protocol into a request/response stateless protocol"* 。删除 `initialize`/`initialized` 握手与 `Mcp-Session-Id` 头，每个请求在 `_meta` 里自带协议版本、客户端身份与能力
- 新增 `server/discover` RPC（**服务端 MUST 实现**）
- 弃用 Roots / Sampling / Logging 三原语；HTTP+SSE 重新归类为 Deprecated；弃用 DCR 改用 CIMD
- **首次确立"至少 12 个月"的弃用窗口政策**（有加速例外，最短 90 天）

**生态规模（信号 1 更新）**：Tier 1 SDK **月下载近 5 亿次**（Q2 基线 9700 万，约 5 倍），TS 与 Python SDK **各自累计破 10 亿次**。但官方**未**给出 server 数量、registry 条目数——Q2 记的"10,000+ server"本季无更新。限定：包管理器下载量含 CI/镜像重复拉取，不等于活跃用户。

**判断修正**：命题"MCP 成为 agent 界的 USB-C"**仍在轨**，但**新增一个风险变量**：破坏性改版 + 12 个月弃用窗口，可能让存量 server 生态分裂。规范文本只是意图声明，**不证明 SDK / Claude Code / Cursor 或任何 server 群体已实际迁移**。

### 商业侧（信号 2 更新）

| 事件 | 数字 | 日期 | 证据等级 |
|---|---|---|---|
| Cognition Series D | 融资 >$1B、估值 $26B、**run-rate $492M**、企业用量年内 >10× | 2026-05-27 | 一手（[官方](https://cognition.com/blog/series-d)） |
| Sierra 收购 Takeoff | 3 人团队、"接近 8 位数 run rate"、条款未披露、原文用 "is acquiring" | 2026-07-23 | 一手（[官方](https://sierra.ai/blog/sierra-acquires-takeoff)） |
| Cursor / Anysphere 被 SpaceX 以 $60B 收购 | — | 2026-06-16 | **仅二手，无一手证据** |
| Cursor 与 Claude Code 新 ARR | **窗口内无披露** | — | Cursor 官网最新收入口径仍是 Bloomberg 2026-03-02 的 $2B |

Cursor 侧一手可确认的只有：与名为 "SpaceXAI" 的实体**联合训练并联合发布** [Grok 4.5](https://cursor.com/blog/grok-4-5)（07-08，原文 "trained jointly with SpaceXAI"）与 [Grok 4.6](https://cursor.com/blog/grok-4-6)（08-12）。两篇博文无 acquisition/merger 字样、无价格、无交割状态，页脚仍是 "© 2026 Anysphere, Inc."。

**口径纪律**：[TechCrunch 2026-05-22](https://techcrunch.com/2026/05/22/how-vcs-and-founders-use-inflated-arr-to-kingmake-ai-startups/) 记录了业内把 CARR（签约未交付）当 ARR 报的做法（有 VC 称见过 CARR 比 ARR 高 70% 的公司），以及把月收入直接年化。**本仓库此后一律把 Cognition 的 4.92 亿写作"run-rate（公司口径、未审计、Devin+Windsurf 合并）"，不写作 ARR。**

### 信号 3（底模是否吃掉 harness）

本季无新数据。但 MCP 的无状态化 + 弃用政策，是 harness 层向"操作系统原语"收敛的**弱正向**证据。
