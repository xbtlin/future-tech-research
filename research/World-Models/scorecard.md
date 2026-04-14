# World Models 评分卡

**研究日期**：2026-04-14
**当前阶段**：从"视频生成"走向"可交互世界模拟器 + 机器人 Foundation Model"的转折点。视频预测（Sora 2 / Veo 3.1）已商业化，可交互世界模型（Genie 3 / Cosmos Predict 2.5）进入可用但受限阶段（一致性 ~1min），机器人 VLA（π0.5 / Gemini Robotics 1.5 / Helix）开始走出实验室进入工厂小批量部署（Figure 02 @BMW Spartanburg 1250+ 小时）和 C 端早期预购（1X NEO $20k）。

## 1. 技术成熟度 ★★

- **视频一致性**：Genie 3 在 720p/24fps 下仅能维持"几分钟"的世界一致性，视觉记忆窗口约 1 分钟，长时序漂移仍是根本瓶颈（[DeepMind Genie 3](https://deepmind.google/blog/genie-3-a-new-frontier-for-world-models/)）。
- **物理先验**：LeCun 明确批评"用像素预测来做 world model 是糟糕的想法"——Sora 类模型只记住了"球飞行轨迹的概率"而非"力学定律"；V-JEPA 2 / LeWM 尝试在 latent space 解决但仍局限于玩具环境（[MarkTechPost 2026-03](https://www.marktechpost.com/2026/03/23/yann-lecuns-new-leworldmodel-lewm-research-targets-jepa-collapse-in-pixel-based-predictive-world-modeling/)）。
- **VLA sim-to-real**：π0.5 用 400 小时移动操作 + 异构协同训练已能做到"在没见过的家里做 10-15 分钟清洁"（[Physical Intelligence π0.5](https://www.physicalintelligence.company/blog/pi05)）；Dream-VLA 在 LIBERO 97.2%、SimplerEnv-Bridge 71.4%（[ICLR 2026 VLA 综述](https://mbreuss.github.io/blog_post_iclr_26_vla.html)）。
- **数据差距**：机器人真实数据量仍比视频/语言差 4-5 个数量级（Open X-Embodiment 仅 100 万条轨迹 vs LLM 数万亿 token）（[Open X-Embodiment](https://robotics-transformer-x.github.io/)）。

## 2. 经济性 ★

- **硬件报价**：Unitree G1 $13.5k–16k 基础款（[Unitree](https://www.unitree.com/g1/)）、H1 $90k；1X NEO $20k 或 $499/月订阅（[Fortune](https://fortune.com/2025/10/30/1x-neo-household-robot-chores-20k/)）；Tesla Optimus V3 目标 <$20k，但实际制造成本仍在 $50k-100k，初期商用价 $100k-150k（[notateslaapp](https://www.notateslaapp.com/news/3314/tesla-eyes-20k-price-target-for-optimus-extremely-fast-production-ramp)）；Figure 03 通过 BotQ 压低 90% 制造成本（[Figure](https://www.figure.ai/news/introducing-figure-03)）。
- **视频生成推理**：Sora 2 API $0.10/秒（$6/min 720p），Sora 2 Pro $18-30/min；ChatGPT Pro $200/月 10,000 credits（[eesel Sora 2 pricing](https://www.eesel.ai/blog/sora-2-pricing)）。OpenAI Sora 每条 10 秒成本约 $1.3，仍在大幅亏损运营（[Remio](https://www.remio.ai/post/the-real-sora-cost-openai-s-5-billion-ai-video-problem)）。
- **真机数据采集**：SVRC 2026-03 基准 $118/小时（2024 初 $340/小时降下来），商业化 pick-and-place 吞吐 30-60 条/小时（[SVRC](https://www.roboticscenter.ai/blog/robot-data-collection-cost)）。
- **对比工业机器人**：ABB/KUKA/FANUC 单台 $25k-80k 已运行 40 年、MTBF 数万小时；人形目前在结构化任务上还远无法做 ROI 替代。

## 3. 需求真实性 ★★★

- **Figure @ BMW**：Spartanburg 11 个月 1,250+ 小时、参与 30,000 辆 X3 生产；2026 年 2 月宣布 Leipzig 工厂 4 月起欧洲首次部署（[BMW Group](https://www.press.bmwgroup.com/global/article/detail/T0455864EN/bmw-group-to-deploy-humanoid-robots-in-production-in-germany-for-the-first-time?language=en)、[Figure](https://www.figure.ai/news/production-at-bmw)）。
- **1X NEO**：$20k 消费者版 2026 开始交付，OpenAI Startup Fund 投资；2025-12 追加工厂/仓库版本（[TechCrunch](https://techcrunch.com/2025/12/11/1x-struck-a-deal-to-send-its-home-humanoids-to-factories-and-warehouses/)）。
- **π0.5**：2025-11 完成 $600M B 轮，估值 $5.6B；具体家庭清洁付费客户未披露（[研发中]）。
- **Robotaxi**：Waymo 2026-03 已达 50 万次/周（10 城），目标年底 100 万次/周，Magna 工厂年底扩至 2,000 辆（[TechCrunch 2026-03](https://techcrunch.com/2026/03/27/waymo-skyrocketing-ridership-in-one-chart/)）。
- **视频生成商业化**：Sora 2 通过 ChatGPT Plus/Pro 订阅变现，但经济模型尚未跑通（生成成本 > 订阅 ARPU）。

## 4. 生态成熟度 ★★★

- **开源 VLA/数据**：OpenVLA (7B, 970k 轨迹)、LeRobot、Open X-Embodiment (1M 轨迹/22 embodiments/60 数据集)（[OpenVLA](https://github.com/openvla/openvla)）。
- **NVIDIA Cosmos**：下载量突破 200 万+，已迭代至 Predict 2.5 / Transfer 2.5 / Reason 2（[NVIDIA Newsroom](https://nvidianews.nvidia.com/news/nvidia-announces-major-release-of-cosmos-world-foundation-models-and-physical-ai-data-tools)）。
- **硬件供应链**：Figure（BotQ 90min/台，年产能目标 12k→50k）、1X、Tesla、Unitree、Apptronik、Agility、Sanctuary AI 多元竞争；中国玩家（Unitree、小米）打到 $16k 以下。
- **Benchmark**：LIBERO、SimplerEnv、CALVIN、RoboCasa-GR1、BEHAVIOR-1K 已部分接近饱和（LIBERO 99%），但 RoboArena 级真机通用评测尚未形成统一标准（[ICLR 2026](https://mbreuss.github.io/blog_post_iclr_26_vla.html)）。

## 5. 3 年拐点概率 35%

**拐点定义**：通用人形 VLA 在工厂结构化任务上成功率 95%+ 且部署 100+ 工厂；或可交互世界模型一致性窗口从 1min → 30min 成为主流 RL simulator。

**理由三条**
1. Figure 02 @ BMW 已完成 1,250 小时"最后一公里"验证，Figure 03 BotQ 产线 90min/台 + 50k 年产能目标，硬件规模化曲线进入拐点；
2. Waymo 周订单一年翻倍至 50 万，证明大模型 + 大数据 + 硬件闭环的"物理 AI 飞轮"在自驾子领域已跑通，可外推至人形；
3. Cosmos 下载 200 万次、π0.5 异构协同训练 + 开源生态（LeRobot/Open X-Embodiment）把 sim-to-real 成本曲线往下压，GAIA-3 规模放大 2x 参数/10x 数据印证 scaling law。

**反面证据两条**
1. LeCun 对纯像素 world model 的批评（pixel-only 不懂因果）在 2026 仍未被 Sora/Genie 类模型证伪，长时序漂移是架构级而非数据级瓶颈；
2. 机器人真实数据 4-5 数量级缺口是硬约束，$118/hour 遥操作 + Open X-Embodiment 100 万轨迹对比 LLM 数万亿 token，scaling 曲线远未进入"甜蜜区"。

## 综合判断

- **一句话定性**：World Models 是 2026 年最热、但单位经济性最差的 AI 前沿——视频端已商业化但烧钱，机器人端有真实需求但硬件/数据双重瓶颈。
- **核心赌的是什么**：赌"物理 AI 飞轮"启动——硬件产能下降 + 开源数据规模化 + VLA 架构跨 embodiment 泛化三者共振；如果 3 年内 Figure/1X/Tesla 任一家达到 10k+/年交付且 VLA 真机成功率 >95%，就是 AlexNet 时刻。
- **跟踪信号**：
  1. Figure 03 / 1X NEO / Optimus V3 年产能爬坡节奏（关注 Figure BotQ 是否破 12k/年）；
  2. BMW Leipzig 2026 夏季 pilot 后续扩产决定；
  3. RoboArena / SimplerEnv 上头部 VLA（π、Gemini Robotics 1.5、Helix）真机成功率；
  4. Cosmos / Genie 一致性时长演进（1min → 10min 是关键门槛）；
  5. Waymo 100 万/周能否在 2026 年底达成、单位经济性是否转正。
- **关联标的**：
  - 上市：**NVIDIA**（Cosmos + GPU 双受益）、**Tesla**（Optimus + FSD 数据闭环）、**Alphabet**（DeepMind Genie/Gemini Robotics + Waymo）、**Meta**（V-JEPA/LeWM）；
  - 未上市：**Physical Intelligence**（$5.6B 估值，VLA 纯玩家首选）、**1X**（OpenAI 系、C 端独家）、**Figure**（$39B 估值，工厂 B 端龙头）、**Wayve**（GAIA-3，自驾世界模型）、**Apptronik / Agility / Sanctuary AI**（人形第二梯队）、**Unitree**（中国低成本路线）。
