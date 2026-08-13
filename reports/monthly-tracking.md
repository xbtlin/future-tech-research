# 月度跟踪面板

> 每月第一周更新。只记**关键信号**的新数据点与我对此的简短解读（"是否修正了判断"）。冗长分析放到各方向 scorecard。

---

## 跟踪信号总览（从 5 个方向的 scorecard 提取）

| 方向 | 信号 1 | 信号 2 | 信号 3 |
|---|---|---|---|
| **Post-training** | GRPO / DAPO vs PPO 在 AIME / Codeforces 的公开 head-to-head | 下一代前沿模型是否继续 long-RL 路径还是回归大预训练（DeepSeek-R3 / o5 / GPT-6 / Claude Opus 5） | Self-play 是否出现 ≥30B 工业级复现（非学术玩具） |
| **Agentic** | METR 任务时长 doubling 节奏（当前 131 天 / doubling） | SWE-Bench Pro 最高分（当前 46%） | Operator / ChatGPT Agent Mode MAU + 留存 |
| **Harness** | MCP 生态规模（SDK 月下载、server 数量） | Cursor / Claude Code ARR 增速与企业留存 | 底模原生 computer use / memory 是否吃掉第三方 harness（比 SWE-Bench 模型裸跑 vs 带 harness） |
| **Long-context** | 下代模型在 MRCR v2 1M 处 / BABILong qa5 分数 | 混合架构（Mamba/Jamba）是否出现 frontier 级模型 | Memory agent 是否集成进 Claude / GPT / Gemini 原生 API |
| **World Models** | Figure 03 / 1X NEO Gamma / Optimus V3 实际量产节奏 | RoboArena / LIBERO / SimplerEnv 头部 VLA 成功率 | Genie / Cosmos 一致性窗口是否突破 5 分钟 |

---

## 2026-04（baseline，本月是建立基线）

### Post-training
- **基线**：GRPO 已成头部实验室默认（DeepSeek、OpenAI、Anthropic、Qwen、Kimi）；PRM 综述 arXiv 2510.08049；Tsinghua arXiv 2504.13837 对 pass@k 提出实证质疑
- **观察**：——
- **判断修正**：——

### Agentic
- **基线**：METR 任务时长 doubling 131 天；Claude Opus 4.6 14.5h；SWE-Bench Pro 最高 46%；OSWorld 已被 Holo3 10B 开源推到 78.85%；Cognition ARR 约 $150M，Sierra $100M ARR / 21 个月
- **观察**：——
- **判断修正**：——

### Harness
- **基线**：Cursor ARR $2B、估值 $29.3B；MCP SDK 月下载 9700 万 / 10,000+ server；Claude Code 年化 $2.5B run-rate；LangGraph v1.0 GA
- **观察**：——
- **判断修正**：——

### Long-context
- **基线**：Opus 4.6 MRCR v2 8-needle @1M 76%；Gemini 3 Pro 1M MRCR 8-needle 26.3%；LongBench v2 最强 50.1%；MongoDB Vector Search 增长 280%
- **观察**：——
- **判断修正**：——

### World Models
- **基线**：Genie 3 一致性 ~1 分钟；Sora 2 单镜头 25s；Cosmos 下载 200 万+；Figure@BMW 1250+ 工厂小时；1X NEO $20k / 2026 交付；Waymo 50 万 次/周；π0.5 家庭清洁多步成功
- **观察**：——
- **判断修正**：——

---

## 2026-05 ~ 2026-08（合并记录，见 [Q3 更新报告](2026-Q3-九大方向更新.md)）

> 本次未按月拆分：两轮 deep-research 的取证窗口是整个 5—8 月，多数信号无法定位到具体月份。

### Post-training
- **观察**：清华 arXiv 2504.13837 的质疑被两篇独立论文**实证坐实**——arXiv 2607.20543（07-12）命名"pass@k 反转"并给出机制（低频正确解在被强化前先消失）、arXiv 2606.15455（06-13）把它框定为过训练问题。但后者同时给出反证：**有相当一部分初始不可解的问题在标准 RLVR 中变成可解**，且"零成功问题门控"能让 Pass@256 超过基座。self-play ≥30B 工业级复现**仍无信号**（连续两轮）
- **判断修正**：质疑的**现象描述**成立、**推论**（能力边界推不动）被挑战。两篇均为单实验室预印本、无独立复现、未到 30B 规模，暂不改评分卡星级

### Agentic
- **观察**：**量具坏了，不是能力退了**。METR 自曝 TH 1.1 在 16 小时以上不可靠，公开前沿 50% 视野约 12h 但置信区间 [5h–61h] 跨一个数量级；Meta 官方 Gaia2 榜自 2026-05-15 后无新提交，SOTA 仍是 04-13 的 Opus 4.6 (57.0)；Berkeley BenchJack 证明 OSWorld 可用 wget gold 文件刷到 73%
- **判断修正**：**Q2 的 3 年拐点概率 40% 需下调**，但本季数据不足以定新值。"METR 曲线外推到 900h"这条支持理由**失去量具支撑**，暂停使用

### Harness
- **观察**：MCP 2026-07-28 发布同名规范，**协议从双向有状态改为无状态请求/响应**，删握手与 Session-Id，弃用 Roots/Sampling/Logging 与 DCR，首次确立 12 个月弃用窗口；SDK 月下载 9700 万 → **近 5 亿**，TS 与 Python 各破 10 亿累计。Cognition 05-27 融资 >$1B / 估值 $26B、run-rate $492M；Sierra 07-23 收购 Takeoff（3 人、近 8 位数 run rate）。**Cursor 被 SpaceX 以 $60B 收购一事无任何一手证据**，仅确认与 SpaceXAI 联合训练 Grok 4.5/4.6
- **判断修正**：生态规模信号强正向（5 倍），但**新增"迁移成本"风险变量** ——破坏性改版可能让存量 server 分裂。商业口径中断：Cursor / Claude Code 窗口内均无新 ARR

### Long-context
- **观察**：**本轮零取证**。MRCR v2 @1M、LongBench v2、BABILong、混合架构均无数据
- **判断修正**：无。**注意：这是"未取证"不是"无进展"**，Q4 优先补

### World Models
- **观察**：出现专测长时程稳定性的 **WorldRoamBench**（arXiv 2606.31672，06-30），600+ 用例、10—60 秒交互，结论是**没有模型在所有维度可靠达标**；Qwen-VLA（arXiv 2605.30280，05-28）首次给出成套数字：LIBERO 97.9% / 真机 ALOHA 分布外 76.9% / DOMINO 零样本 26.6%；Figure 03 产能**从 1 台/天到 1 台/小时（120 天 24 倍）**、交付 350+ 台、下线首次通过率 >80%
- **判断修正**：一致性窗口命题（1 分钟 → 30 分钟+）**转负向** ——新量具的测试区间只到 60 秒，且此区间内已无模型达标。VLA 的 sim-to-real 缺口首次有了精确数字：仿真到真机掉 21 分，到零样本动态掉 71 分

### 横向（新增跟踪项）
- **观察**：**三把量尺同时出问题** ——FrontierMath 承认 42% 题目有错（06-12 v2）、METR 承认 16h 以上不可靠、Berkeley BenchJack 用零能力 agent 把 10 个 agent 榜单中的 9 个刷到接近满分（8 类漏洞 219 处缺陷）。另有 arXiv 2607.27518（07-29）独立发现 5 个常用 benchmark 存在经人工确认的有效性问题
- **判断修正**：**Q2 所有以 benchmark 分数为唯一依据的拐点判断，置信度下调一档。** 新增常设跟踪信号："benchmark 维护方是否响应 BenchJack 并合并补丁"

---

*模板。每月开新 section，旧 section 保留。连续 3 个月同一信号朝"反面"走 → 触发 scorecard 全面复盘。*
