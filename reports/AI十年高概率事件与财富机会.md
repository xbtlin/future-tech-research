# 押注成本曲线，别押替代日期：AI 十年高概率清单

> 编写日期：2026-09-25。底稿为同目录研究笔记 01–06（能力与成本、就业、算力与能源、价值分配、物理 AI、社会与中国语境）。文中所有"概率"均为研究者主观判断，不是来源数据；来源数据均附链接。笔记撰写时检索额度中途耗尽，部分数字只有二手出处，已在最后一节集中标注。

按目前的速度外推，2036 年最确定的不是"AI 取代了谁"，而是四条已经测出来的曲线继续走：固定能力的推理单价每年下降约 13 倍（2023–2026 实测），前沿模型能以五成把握完成的软件任务时长每 3–4 个月翻一倍，全球数据中心用电从 2024 年的 415 太瓦时走向 2035 年约 1200 太瓦时，生成式 AI 三年内渗透到 53% 的人口。由这四条曲线直接推出的事情——2026 年的前沿能力到 2036 年便宜一千倍以上、今天所有静态基准全部饱和、电力与先进制程持续紧缺、可自动验证的文字与代码工作价格腰斩、年轻白领的入职门槛持续抬高——研究者给出的概率都在 80% 以上。与之相反，"某职业几年内被取代""通用人形机器人进家庭""2027 年实现通用人工智能""AI 引发大规模失业"这类判断，过去十年一律错在乐观方向。对普通人，冲击的形态是"少招新人"而不是"裁掉老人"：美国 22–25 岁在高暴露职业的就业已比反事实水平低 19%，在岗者工资基本未受影响，因此个人的关键是站到"责任可归属、需要到场、依赖隐性经验"的位置上。对投资者，过去两轮基础设施狂热的共同结局是建设者和首批债权人承担损失、折价接盘者和重组业务流程的采用者拿走回报；2026 年 AI 利润几乎全部落在芯片与代工层，模型层巨亏且被开源压价。财富机会因此集中在四处：不可替代的制造瓶颈、慢折旧的位置资产（并网点、电力合同、土地）、握有分发与交易数据的平台，以及 2027–2030 年大概率出现的资本开支消化期里的折价资产。

## 预测史给出两条方向相反的偏差

判断 2036 年之前，先看过去十年的预测成绩单，因为它决定了哪些直觉该上调、哪些该下调。第一条偏差是**对可测量的基准进展系统性悲观**。2022 年一场由超级预测员与领域专家参加的预测锦标赛，对四项 AI 基准结果（数学、综合知识、长文阅读、国际数学奥赛金牌）给出的平均概率，超级预测员只有 **9.7%**，领域专家只有 **24.6%**，结果四项全部发生；奥赛金牌在 2025 年 7 月达成，比两组的中位预测分别早 5 年和 10 年 ([预测研究所](https://forecastingresearch.org/research/near-term-xpt-accuracy))。一项覆盖 2778 名顶会作者的调查，一年之内就把"AI 在所有任务上比人更好更便宜"的中位年份从 2060 年提前到 2047 年 ([arXiv 2401.02843](https://arxiv.org/html/2401.02843v3))。基准饱和的速度也在加快："人类最后的考试"2025 年 1 月发布时顶尖模型得分 8.8%，2026 年 9 月最高已到 61.4% ([维基百科](https://en.wikipedia.org/wiki/Humanity%27s_Last_Exam))。

第二条偏差恰好相反：**对"某职业、某场景在几年内被完全替代"系统性乐观**，且乐观者往往有利益关联。特斯拉创始人 2013 年以来关于自动驾驶的 30 余条时间表，只有高速公路辅助驾驶一条部分兑现 ([维基百科](https://en.wikipedia.org/wiki/List_of_predictions_for_autonomous_Tesla_vehicles_by_Elon_Musk))；2016 年"现在就该停止培训放射科医生"的预言发出十年后，英国国民医疗服务体系的放射科医生反而比需求少 **32%** ([The Spectator](https://www.spectator.com.au/2026/09/why-was-the-bbc-so-surprised-to-meet-an-ai-doomer/))。即便是做得最好的 Waymo，从"技术基本解决"到 2026 年 6 月每周 50 万次付费乘车、覆盖 10 个美国都市区，也用了整整十年 ([维基百科](https://en.wikipedia.org/wiki/Waymo))。更长的历史尺度上，自动取款机 1970 年代问世，1990 年代末普及，美国银行柜员数量在 2000 年后仍年增 2.0%（因为网点成本下降，城市网点数量增加 43%），直到 2010 年代手机银行出现才进入长期下降 ([波士顿大学工作论文](https://www.bu.edu/law/files/2015/11/NewTech-2.pdf)；[IMF 期刊](https://www.imf.org/external/pubs/ft/fandd/2015/03/bessen.htm))。从技术可用到职业收缩，间隔三四十年。

两条偏差的共同机理是：把演示能力当成部署能力，忽略了从五成成功率到九成九成功率的尾部可靠性、法律责任和组织采用的摩擦。METR 的测量把这一机理量化了：2026 年 3 月前沿模型五成成功率的任务时长约 12 小时，八成成功率却只有约 1 小时 10 分，差 4–5 倍 ([AI 2027 追踪站](https://ai2027-tracker.com/predictions/metr-doubling/))；2025 年一项随机对照试验里，有经验的开发者在熟悉的代码库上使用 AI 工具反而慢了 19%，而他们事前预期会快 24% ([维基百科转述 METR 试验](https://en.wikipedia.org/wiki/Vibe_coding))。技术成熟度曲线的实证记录同样不乐观：只有约五分之一的突破性技术走完"兴奋—失望—普及"的完整路径，掉进低谷的技术六成再没恢复 ([维基百科](https://en.wikipedia.org/wiki/Gartner_hype_cycle))。

由此得到本报告所有概率背后的校准规则：**对"某个成本阈值或基准分数在 N 年内达到"的判断向上调；对"某职业或场景在 N 年内被完全自主替代"的判断，把利益相关者给出的时间线乘以 2 到 3；对整体采用率相信 S 形曲线，但把起点推后 2–3 年。** 按这条规则，结构化预测给出的"2036 年前实现通用人工智能"大致是抛硬币：预测社区 Metaculus 的五成分位在 2033 年，研究者调查的五成分位在 2047 年，2036 年分别落在约 60–65% 和 30–35% 分位 ([80,000 Hours](https://80000hours.org/2025/03/when-do-experts-expect-agi-to-arrive/)；[arXiv 2401.02843](https://arxiv.org/html/2401.02843v3))。

## 概率超过八成的判断集中在成本、基建和"入口"

下表汇总六份笔记中研究者给出 80% 以上概率的判断。它们有一个共同点：不依赖任何一次能力突破，只依赖已经运行多年的成本、采用或物理约束曲线继续运行；即使斜率减半，结论也成立。

| 到 2036 年的判断 | 研究者概率 | 核心证据 | 什么会证伪它 |
|---|---|---|---|
| 达到 2026 年 9 月前沿水平的文字与代码能力，单价比 2026 年前沿价低至少 1000 倍 | 92% | 芯片每美元性能年增 49%，十年约 54 倍；预训练算法效率每年约 3 倍；"思考的价格"每季度降 47% ([Epoch AI](https://epoch.ai/publications/the-plunging-price-of-thought)；[Epoch 趋势](https://epoch.ai/trends)) | 算法进步停滞且芯片降价放缓到每年 20% 以下 |
| 2026 年存在的所有静态文字、代码、数学基准全部饱和到人类专家水平以上 | 95% | 基准从"顶尖模型不到 10%"到饱和的周期为 2–3 年并在缩短 ([斯坦福 AI 指数 2025](https://hai.stanford.edu/ai-index/2025-ai-index-report)) | 无合理路径 |
| 生成式 AI 人口渗透率超过 80%，组织采用率超过 95% | 90% | 三年达到 53% 人口渗透，快于个人电脑和互联网；2025 年 88% 的组织已采用 ([斯坦福 HAI](https://hai.stanford.edu/news/inside-the-ai-index-12-takeaways-from-the-2026-report)) | 重大安全事故引发全面禁用 |
| 全球数据中心用电 2035 年超过 800 太瓦时（约为 2024 年的两倍） | 90% | 国际能源署基准情景 2035 年约 1200 太瓦时，最低情景 700 太瓦时也接近翻倍 ([IEA](https://www.iea.org/reports/energy-and-ai/executive-summary)) | 能效提升远超预期且需求见顶；谷歌单次提示词能耗一年降 33 倍，但总用电仍增 27% ([Brookings](https://www.brookings.edu/articles/global-energy-demands-within-the-ai-regulatory-landscape/)) |
| 燃气轮机三大厂 2030 年前满产，美国数据中心密集区电价涨幅跑赢全国 | 85–90% | 三家积压合计约 220 吉瓦，行业年产能 60–70 吉瓦，交付槽位排到 2031 年；电网容量拍卖成本从 22 亿美元跳到 160 亿美元以上 ([Utility Dive](https://www.utilitydive.com/news/ge-vernova-gas-turbine-backlog-climbs-to-116-gw/826039/)；[Yahoo Finance](https://finance.yahoo.com/energy/articles/gas-turbine-shortage-just-became-210000180.html)；[维基百科 PJM](https://en.wikipedia.org/wiki/PJM_Interconnection)) | AI 资本开支在 2028 年前断崖式收缩 |
| 小型模块化核反应堆对数据中心供电贡献低于 5% | 80% | 美国首批小堆 2030 年后才投运 ([IEA](https://www.iea.org/reports/energy-and-ai/energy-supply-for-ai)) | 审批与建造速度出现数量级改善 |
| 中国 AI 加速器市场由国产芯片主导，英伟达在华份额回不到 2024 年水平 | 80–85% | 英伟达最新季度指引完全不含中国数据中心收入 ([英伟达财报](https://investor.nvidia.com/news/press-release-details/2026/NVIDIA-Announces-Financial-Results-for-Second-Quarter-Fiscal-2027/default.aspx))；行业机构估计国产份额 2026 年近 90% ([Tom's Hardware](https://www.tomshardware.com/tech-industry/artificial-intelligence/chinas-homegrown-ai-accelerators-to-supply-90-percent-of-the-countrys-domestic-market-analysts-suggest-cambricon-and-huawei-expected-to-be-the-biggest-winners-in-the-shift-away-from-nvidia-and-amd)) | 美国全面放开最新一代芯片对华销售（研究者判断不到 20%） |
| 全球至少 20 个大都市有车内无安全员的商业化无人出租车 | 90% | Waymo 2026 年 9 月已在约 15 个美国都市区运营并宣布伦敦、东京等计划；萝卜快跑、小马智行、文远知行在北上广深、武汉及中东持有全无人牌照 ([维基百科 Waymo](https://en.wikipedia.org/wiki/Waymo)；[维基百科 WeRide](https://en.wikipedia.org/wiki/WeRide)) | 多人死亡事故引发全国性停摆 |
| 主流软件公司新增代码 80% 以上由 AI 生成（按行数） | 90% | 谷歌 2024 年 10 月已超过四分之一 ([谷歌](https://blog.google/inside-google/message-ceo/alphabet-earnings-q3-2024/))；编程是实验室投入最重的领域 | 代码质量与安全问题迫使回退 |
| 中美三级医院普遍用 AI 做影像分诊和病历生成；但美英放射科医生人数不低于 2026 年 | 90% / 80% | 美国食品药品监督管理局已批准约 1247 个 AI 器械，77% 在放射科 ([维基百科](https://en.wikipedia.org/wiki/Artificial_intelligence_in_healthcare))；乳腺筛查 AI 分诊减少初读 44–70%，检出率持平 ([欧洲 PMC](https://www.ebi.ac.uk/europepmc/webservices/rest/search?query=MASAI%20mammography%20screening%20artificial%20intelligence%20randomised&format=json&resultType=core&pageSize=4&sort=P_PDATE_D%20desc)) | 监管允许 AI 大范围独立签发诊断 |
| 中美大企业一线文字客服 70% 以上会话由 AI 端到端处理 | 85% | Klarna 员工从 2022 年约 5527 人降到 2025 年约 2907 人 ([维基百科](https://en.wikipedia.org/wiki/Klarna))；美国劳工统计局预计客服岗位十年减 5% ([BLS](https://www.bls.gov/ooh/office-and-administrative-support/customer-service-representatives.htm)) | 服务质量投诉迫使大规模回到人工 |
| 非人形的工业与仓储机器人成为大型工厂标配，全球年装机超 100 万台 | 85–90% | 2025 年全球装机 60 万台以上，中国 35.4 万台占 59%；行业协会预测 2029 年 80.6 万台 ([IFR](https://ifr.org/ifr-press-releases/news/five-million-robots-now-operate-in-factories-globally)) | 制造业深度衰退 |
| 标准化白领产出（文案、翻译初稿、常规代码、基础分析）市场价比 2022 年跌 50% 以上 | 85% | 自由职业平台写作类从业者在 ChatGPT 发布后月收入降 5.2%，且高质量者受损最大 ([华盛顿大学](https://olin.washu.edu/about/news-and-media/news/2023/08/study-ai-tools-cause-a-decline-in-freelance-work-and-incomeat-least-in-the-short-run.php)) | 需求弹性远超预期，价格下降被数量扩张完全抵消 |
| 发达经济体与中国城市白领入门岗位持续收缩，但美国不出现 AI 驱动的 8% 以上失业率 | 80% / 80% | 22–25 岁高暴露职业就业比反事实低 19%，且缺口从 15% 扩大到 19%；经济范围内无广泛替代 ([斯坦福数字经济实验室](https://digitaleconomy.stanford.edu/app/uploads/2026/08/Canaries_August2026.pdf)) | 生产率大爆发带来招聘潮；或自动化速度远快于新岗位创造 |
| 需要到场、执照或物理资产的服务相对价格上升，可复制的数字服务相对价格下降 | 85% | 劳动份额指数 2025 年二季度到 2026 年二季度下降 3.3 点 ([FRED](https://fred.stlouisfed.org/series/PRS85006173))；护士执业岗位十年预计增 41% ([BLS](https://www.bls.gov/emp/tables/fastest-growing-occupations.htm)) | 通用机器人提前成熟 |
| 中国不出台全国性无条件基本收入 | 95% 以上 | 最大规模随机实验中每月 1000 美元使劳动参与率降 4.2 个百分点、幸福感回落到对照组 ([NBER w32719](https://www.nber.org/papers/w32719))；"十五五"规划更强调支持企业与扩大医护养老供给 ([维基百科](https://en.wikipedia.org/wiki/15th_five-year_plan)) | 失业率失控 |
| 中国境内推理用量中开源权重模型占 70% 以上（2030 年）；模型层在中国不形成独立利润池 | 80% | 开发者平台上中国模型已占约 61% 的词元消耗，千问衍生模型超过谷歌与 Meta 之和 ([datagravity](https://www.datagravity.dev/p/chinas-open-weight-takeover)) | 国内闭源模型拉开一代以上能力差 |

这张表里需要特别说明两件事。其一，**便宜一千倍指的是"2026 年的前沿能力"，不是"2036 年的前沿能力"**。降价最快的阶段是某能力刚成为最强水平后的头两年（每季度降 66%，年化约 75 倍），两年后放缓到年化约 4.7 倍 ([Epoch AI](https://epoch.ai/publications/the-plunging-price-of-thought))；十年后最强模型的单价未必更低，但今天需要付 50 美元每百万词元的能力，届时接近免费。其二，训练端的扩张不可能按现有斜率持续：单次最贵训练 2025 年约 5 亿美元，按每年 2.4 倍增长，2030 年约 400 亿美元、2036 年约 8 万亿美元 ([Epoch AI](https://epoch.ai/data-insights/cost-trend-large-scale))，后者超出任何公司的承受力。研究者判断最可能的放缓来自资本回报周期而非物理极限，形态是"能力前沿放缓、成本曲线继续"——这对"廉价专家级能力普及"的判断有利，对"通用人工智能"的判断不利。

## 被广泛相信但实际接近抛硬币的判断

下列判断在媒体和行业叙事里常被当作定论，但研究者给出的概率在 30–75% 之间。它们要么依赖八成可靠性与真实环境的转移，要么依赖一个尚未证明的商业闭环。

| 判断 | 研究者概率 | 为什么不确定 |
|---|---|---|
| 2033 年前，八成成功率的任务时长达到一周（40 小时） | 75% | 五成口径只需约两次翻倍，但八成口径落后 4–5 倍；METR 任务集在 16 小时以上已接近饱和，届时可能无法测量 ([METR](https://metr.org/blog/2026-1-29-time-horizon-1-1/)) |
| 全球 50 个以上都市区有商业无人出租车 | 70–80% | 两份笔记分歧：能力笔记给 80%，行业笔记因欧洲、日本监管落地慢下调到 70% |
| 至少一款"AI 发现靶点 + AI 设计分子"的新药在中美获批 | 75% | 英矽智能的 rentosertib 二期 a 结果为阳性信号（71 例，12 周）([欧洲 PMC](https://www.ebi.ac.uk/europepmc/webservices/rest/search?query=rentosertib%20TNIK%20phase%202a&format=json&resultType=core&pageSize=3))；AI 分子一期成功率 80–90%，二期约 40%，与历史持平，最贵的"靶点对不对"问题尚未解决 |
| 2027–2032 年美国四大云合计资本开支至少一年同比下降 15% 以上 | 75% | 资本开支已等于经营现金流的 100%，折旧占收入比例从 2022 年 7% 升向 2027 年 12% ([高盛研究](https://www.gspublishing.com/content/research/en/reports/2026/06/12/50f004d3-b246-4366-9d7d-0bc7e845644b.html))；但微软与谷歌现金流仍能自给 |
| 2030 年前至少一家算力租赁商或数据中心表外融资实体发生债务重组 | 75% | CoreWeave 债务约 350 亿美元、季度净利息 6.4 亿美元，调整后经营利润率仅 5% ([CoreWeave 财报](https://www.sec.gov/Archives/edgar/data/0001769628/000176962826000362/coreweave2q26earningspress.htm))；私募信贷违约率 2026 年 4 月达 6.0% 的纪录 ([Startup Fortune](https://startupfortune.com/oracle-and-meta-are-selling-ai-data-center-debt-to-investors-hungry-for-yield/)) |
| 普通本科学历的信号价值显著下降 | 70% | 年轻人就业缺口在控制教育变量后衰减，说明冲击恰恰沿"正规教育传授的编码化知识"展开 ([斯坦福数字经济实验室](https://digitaleconomy.stanford.edu/app/uploads/2026/08/Canaries_August2026.pdf))；但缺少学历工资溢价的直接时间序列 |
| 中国在前沿模型上始终保持在美国 1–2 年以内 | 65–70% | 2026 年 3 月差距仅 2.7% ([斯坦福 AI 指数 2026](https://hai.stanford.edu/ai-index/2026-ai-index-report))；但美国私人 AI 投资是中国的约 23 倍，中芯国际无极紫外光刻，良率未披露 |
| 美国全要素生产率中 AI 贡献每年 0.2–0.7 个百分点 | 60% | 十年全要素生产率增量的主流估计相差约 10 倍：保守派 0.53–0.66%（十年累计）([NBER w32487](https://www.nber.org/papers/w32487))，乐观派每年 1.5 个百分点；核心分歧是"可盈利自动化的任务份额"是 4.6% 还是 25% ([AEI](https://www.aei.org/articles/ais-economic-potential-goldman-sachs-responds-to-daron-acemoglu/)) |
| 闭源前沿实验室到 2036 年仍保有明显定价权 | 60% | 按词元计开源已过半，按支出计 Anthropic 仍占约 64.6%；企业买的是"可靠性 × 工作流集成 × 责任归属" ([MindStudio](https://www.mindstudio.ai/blog/open-vs-closed-weight-model-token-share)) |
| 2036 年前 Metaculus"强通用人工智能"按原标准判定达成 | 55% | 社区五成分位在 2033 年，但"完全自主"类预测历史上系统性偏早 |
| GPU 行业平均经济寿命约 4 年（会计上是 5.5–6 年） | 55% | 若为真，2027–2029 年四大云每年折旧比现有假设多 300–400 亿美元 ([Silicon Analysts](https://siliconanalysts.com/analysis/hyperscaler-ai-capex-depreciation-wall-2026)) |
| AI 技能工资溢价 2030 年前收窄到 20% 以下 | 55% | 招聘广告标价的溢价 2026 年仍在上升（全球 62%，前一年 57%，二手转述）([Outsource Accelerator 转述普华永道](https://news.outsourceaccelerator.com/pwc-ai-labor-split/))；历史上通用工具技能的溢价最终都会消失，但时点难定 |
| 人形机器人在工厂和物流累计部署超过 50 万台 | 50% | 2025 年行业最大出货商宇树约 5500 台，仅为同年工业机器人装机的零头 ([维基百科](https://en.wikipedia.org/wiki/Humanoid_robot))；中国产业政策强推 |
| AI 在真实环境中以八成可靠性自主完成一个月量级项目 | 45% | 五成口径 2028 年前大概率达到，但叠加八成可靠、真实环境、无人纠偏三重折扣 |
| OpenAI 2030 年收入达到 2000 亿美元目标 | 40% | 2026 年 7 月年化收入 400 亿美元，2026 年一季度每 1 美元收入亏 1.22 美元 ([Sacra](https://sacra.com/c/openai/)；[valueaddvc](https://valueaddvc.com/blog/openai-revenue-2026-25b-arr-2b-month-and-the-path-to-profitability))；对甲骨文、微软等的算力承诺合计远超该收入 |
| 主要国家允许 AI 在某一病种独立出具诊断 | 40% | 试验中 AI 单独诊断比医生高 16 个百分点，但"医生 + AI"并不比医生单独好 ([欧洲 PMC](https://www.ebi.ac.uk/europepmc/webservices/rest/search?query=TITLE:%22Large%20Language%20Model%20Influence%20on%20Diagnostic%20Reasoning%22&format=json&resultType=core&pageSize=3))；瓶颈是责任法而非能力 |

笔记之间有一处需要读者自行裁决的分歧："资本开支回撤年"的概率，能力笔记给"2031 年前出现同比削减 30% 以上"45%，基建笔记给"2027–2032 年出现同比下降 15% 以上"75%。两者阈值不同，并不矛盾，但合起来的含义是：**温和回撤大概率会来，深度回撤是抛硬币。**

## 大概率错误的流行说法

第三类是在舆论里声量很大、研究者判断大概率不会在 2036 年前成立的说法。它们的错误来源高度一致：把能力曲线的斜率当成部署完成的日期。

**"AI 会在几年内造成大规模失业"。** 2026 年 1–7 月美国企业自述"因 AI 裁员"11.3 万人，已是 2025 全年的两倍，5 月起连续成为第一位裁员原因；但同期总裁员人数同比下降 41% ([Challenger](https://www.challengergray.com/blog/challenger-report-layoffs-fall-hiring-picks-up-ai-leads-for-fifth-straight-month/))。这说明 AI 目前改变的是裁员的归因结构，不是裁员总量；企业既有把常规降本包装成 AI 的动机，也有隐瞒的动机。历史上没有任何单一技术在十年内把失业率推高数个百分点。

**"学会用 AI 就能长期拿高溢价"。** 2026 年中国 AI 工程师岗位供需比约 1:3、月薪超 2 万元（二手转引智联数据）([太原晚报](http://www.tywbw.com/jjxw/c/2026-03/27/content_192825.htm))，窗口是真实的；但溢价属于早期采用者，不属于"会用"本身。推理单价每年降一个数量级，意味着"会用"很快成为所有人的默认能力。

**"通用人形机器人十年内进入家庭"。** 研究者给出"进入中美 1% 以上家庭并自主完成通用家务"的概率仅 10–15%。家用人形机器人 1X NEO 在 2025 年 10 月开放预订时，大多数任务靠戴虚拟现实头显的人远程操控 ([维基百科](https://en.wikipedia.org/wiki/1X_Technologies))；国际机器人联合会明确表示，人形机器人作为通用工厂帮手或进入家庭"在近中期不会发生" ([IFR](https://ifr.org/ifr-press-releases/news/china-makes-ai-powered-robots-core-of-national-strategy))。2026 年斯坦福 AI 指数测得机器人家务任务成功率只有 12% ([斯坦福 HAI](https://hai.stanford.edu/news/inside-the-ai-index-12-takeaways-from-the-2026-report))。物理操作没有互联网文本那样的现成语料，只能靠部署规模采集，这与自动驾驶"先用安全员车队攒里程"是同一条慢路。研究者同时给出 2036 年前至少一次人形机器人资本泡沫破裂的概率约 70%，依据是 Figure 390 亿美元估值与千台级出货的脱节。

**"放射科医生、司机、教师、程序员会先消失"。** 研究者判断：美英放射科医生人数不低于 2026 年（80%）；美国软件开发者就业不低于 2026 年（70%，美国劳工统计局预测十年增 10%）([BLS](https://www.bls.gov/ooh/computer-and-information-technology/software-developers.htm))；教师岗位下降超过 20% 不到 10%；无人出租车占中美全国网约车里程过半仅 30–35%。真正先收缩的是职业内部的入门台阶，而不是整个职业。

**"模型公司会成为最大赢家"。** 某一家前沿实验室到 2036 年以独立公司身份拿走一半以上模型支出的概率不到 30%；维持今天 50 美元每百万词元级别价差的概率不到 15%。DeepSeek-V4-Pro 在可比基准上与 GPT-5.5 持平，输入价约为后者的 1/12 ([datagravity](https://www.datagravity.dev/p/chinas-open-weight-takeover))，能力领先窗口只有 6–12 个月。

**"AI 独立做出诺奖级发现"与"AI 让新药成功率翻倍"。** 两者分别只有约 30% 和 20%。AI 辅助的诺奖级成果再出现一例的概率在 85% 以上，这条路径已由蛋白质结构预测验证；但"独立"要求实验闭环，而材料领域"220 万种新晶体"的声明已被同行批评为缺乏新颖、可信、有用三者兼备的证据 ([欧洲 PMC](https://www.ebi.ac.uk/europepmc/webservices/rest/search?query=%22Scaling%20deep%20learning%20for%20materials%20discovery%22%20perspective%20OR%20critique&format=json&resultType=core&pageSize=5&sort=CITED%20desc))。

**"AI 辅导会缩小教育差距"。** 概率约 25%。AI 辅导的效果是真实的：尼日利亚 6 周课后项目效应 0.3 个标准差，相当于近两年常规学习 ([世界银行](https://blogs.worldbank.org/en/education/From-chalkboards-to-chatbots-Transforming-learning-in-Nigeria))。但土耳其近千名高中生的试验显示，带学习护栏的辅导工具使用期间成绩提升 127%，而直接给答案的普通聊天界面在撤掉后，学生成绩比从未使用者低 17% ([PNAS，经欧洲 PMC](https://www.ebi.ac.uk/europepmc/webservices/rest/search?query=%22generative%20AI%20without%20guardrails%20can%20harm%20learning%22&format=json&resultType=core&pageSize=3))。用法决定正负号，使用能力本身成为新的分化。

**"AI 基建过剩会像光纤一样闲置多年再被接盘"。** 这个类比只对了一半。光纤铺下去二十年不贬值，GPU 的每美元性能每 1.7 年翻倍，旧卡的经济价值每年被侵蚀约 35–40%。过剩不会以"暗光纤等七年"的形式存在，而会在 2–4 年内以折旧和减值的形式兑现——这对接盘二手 GPU 不利，对接盘土地、电力接入、建筑外壳有利。

## 对普通人：入口在收窄，位置比技能更重要

就业端最硬的实测结论来自美国薪资处理商 ADP 的数据：截至 2026 年 6 月，22–25 岁年轻人在 AI 高暴露职业的就业，比"跟上低暴露同龄人"的水平低 **19%** ，有经验的工人没有类似缺口；调整**主要通过减少招聘而非增加解雇实现，在岗者的基本工资几乎不受影响**；下降集中在 AI 用来替代任务的职业，而 AI 用来辅助的职业就业持平或上升 ([斯坦福数字经济实验室](https://digitaleconomy.stanford.edu/app/uploads/2026/08/Canaries_August2026.pdf))。招聘广告数据指向同一结构：2026 年 5 月美国资深岗位广告同比增 14.7%，入门岗降 7.5% ([Indeed 招聘实验室](https://hiringlab.indeed.com/2026/07/23/the-labor-market-is-tilting-toward-seniority/))；要求 5 年以上经验的岗位占比从 2022 年中的 37% 升到 2025 年中的 42% ([Fortune](https://fortune.com/2026/04/03/experience-creep-jobs-ai-entry-level/))。机制也已被识别：**依赖教科书与书面流程可以传授的"编码化知识"的职业，年轻人就业增长更慢；依赖实践积累的"隐性知识"的职业，有经验者就业增长更快。**

中国的情况更难辨认，但缓冲更薄。2026 年 8 月 16–24 岁（不含在校生）失业率 18.9%，25–29 岁 7.5%，30–59 岁 3.9% ([腾讯新闻转述国家统计局](https://news.qq.com/rain/a/20260918V0948W00))；2026 届高校毕业生 1270 万人，创历史新高 ([新华网](https://www.news.cn/20251120/ead0f25dff2948dfa7f01fa78f207882/c.html))。这 15 个百分点的年龄差距主要来自毕业生供给和总需求疲弱，AI 的贡献目前无法从官方数据中分离；但年轻白领同时承受周期与技术两股下行力量。另一个与美国相反的结构是：中国工业机器人装机占全球 59%，自动化最快的恰恰是制造业流水线 ([IFR](https://ifr.org/ifr-press-releases/news/five-million-robots-now-operate-in-factories-globally))，研究者判断中国制造业工人总量 2036 年比 2025 年下降 15% 以上的概率约 70%。**在中国，流水线体力岗不是安全岗，在场服务与高技能技工才是。** 政策侧，2026 年人社部首次提出制定"应对人工智能影响促就业"专门文件，并建立 AI 就业影响评估制度 ([国家数据局](https://www.nda.gov.cn/sjj/zwgk/zcfb/0708/20260708133949899211227_pc.html))；新就业形态职业伤害保障参保 2510 万人 ([21 世纪经济报道](https://www.21jingji.com/article/20260127/herald/2420f017092efef4d6f999dfd90860d0.html))。安全网的形式是培训补贴、兜底保障和扩大医护养老供给，不是发钱。

把这些证据翻译成个人决策，有五条结论。

**第一，选位置，不选"安全行业"。** 撑住的岗位不是因为"体力"，而是具备三种属性之一：物理在场（护理、安装、维修）、法律或职业责任可归属到具体的人（执业医护、审计签字、工程签字、出庭律师）、依赖隐性经验的判断（资深工程师、管理者）。三者中责任可归属最稳，因为监管变化比技术慢；隐性经验最脆弱，因为入口收窄正在切断新人积累它的路径——有研究模型专门指出，入门任务自动化即使不减少入门就业，也会把新手从最好的导师身边调走 ([arXiv 2507.16078](https://arxiv.org/pdf/2507.16078))。历史也提醒"安全"往往只是延后：柜员在自动取款机普及后又增长了十多年，最终在手机银行时代收缩。

**第二，把自己变成 AI 产出的责任人。** 软件工程是最清楚的样本：代码生成占比快速上升，但 AI 合写代码的严重问题约为人写的 1.7 倍，安全漏洞率 2.74 倍，开发者中 46% 不信任 AI 的准确性 ([维基百科转述 CodeRabbit](https://en.wikipedia.org/wiki/Vibe_coding)；[Stack Overflow 调查](https://survey.stackoverflow.co/2025/ai))。瓶颈从"写"转移到"审查、测试、维护和担责"。对在岗的中年白领，证据显示存量岗位与工资目前安全，风险在于"低招低裁"下跳槽流动性下降；最优动作是在 AI 技能溢价仍高的这几年，把技能兑换成签字权、验收权和对客户负责的位置。

**第三，用 AI 把自己的产出成本压到市场价以下，而不是等市场来压你。** 标准化白领产出的价格下跌是 85% 概率的事，而且历史模板是平面设计师：职业没有消失，但中位工资三十年停滞，前 10% 拿到六位数收入 ([IMF 期刊](https://www.imf.org/external/pubs/ft/fandd/2015/03/bessen.htm))。收入分布从钟形变成长尾，意味着工资的可预测性下降。

**第四，收入方差上升要求更高的储蓄率和资产性收入。** AI 资本的直接所有权高度集中在少数上市公司股东手中（研究者判断 85%），普通人分享 AI 红利的主渠道是股权而不是工资。在工资收入更不确定的十年里，高杠杆与"收入方差上升"是互相冲突的两件事。

**第五，对下一代，"会用 AI 学"是默认项，保底是一项持牌或到场技能。** 到今天的小学生进入职业选择期时，上表中的高概率事件都已兑现。有护栏的 AI 辅导效果显著，直接给答案的聊天工具有害；执业资格保护的领域与"在场 + 隐性知识"的领域溢价最稳；普通文凭作为信号在贬值。中国"十五五"规划把每千人执业医师从 3.2 提到 3.7、注册护士从 3.9 提到 5.1、护理型养老床位占比从 62% 提到 73% ([维基百科](https://en.wikipedia.org/wiki/15th_five-year_plan))，这些是政策明确扩张、且需要人到场的方向。

## 对投资者：过去的基建狂热里，建设者很少是赢家

先看历史给出的价值归属。1996–2001 年光纤建设投入约 1 万亿美元，铺设 8000–9000 万英里，2002 年只有约 2.7% 被点亮；Global Crossing 峰值市值 380 亿美元，2002 年 1 月破产时负债 124 亿美元；Level 3 在 2002–2006 年以极低折价系统性收购破产资产；需求真正到来是 2007–2012 年（智能手机、流媒体、云计算），距建设高峰约 7 年；谷歌 2010 年以 18 亿美元买下纽约第八大道 111 号的数据中心大楼 ([The Timeless Investor](https://thetimelessinvestor.substack.com/p/they-buried-a-trillion-dollars-underground)；[Fabricated Knowledge](https://www.fabricatedknowledge.com/p/lessons-from-history-the-rise-and)；[Technostatecraft](https://www.technostatecraft.com/p/dark-fiberan-archaeology-of-the-dot))。1846 年英国议会一年批准 263 家新铁路公司、规划 9500 英里，约三分之一从未建成，大公司以远低于真实价值的价格收购失败线路 ([维基百科](https://en.wikipedia.org/wiki/Railway_Mania))。电气化的生产率跃升比发电机商业化晚约四十年，赢家是按电力重新设计工厂布局的制造商 ([HNN](https://www.hnn.us/article/paul-david-it-took-decades-for-the-economic-impact))。三段历史的共同结构是：**基础设施最终都被用上了，但滞后建设高峰 5–10 年；损失由首任所有者和首批债权人承担；回报归于折价接盘者、以及利用变便宜的基础设施重组业务流程的采用者；设备商的收入与订单峰值同步见顶。** 在估值层面，即便是有真实利润的基础设施龙头，在狂热顶点的价格买入也需要十五到二十五年才能回本 ([CNBC](https://www.cnbc.com/2025/12/10/ciscos-stock-closes-at-record-for-first-time-since-dot-com-peak-2000.html))。

再看 2026 年的钱在哪一层。**利润几乎全部落在芯片与代工层**：英伟达截至 2026 年 7 月的季度收入 962 亿美元，其中数据中心 890 亿美元，净利润 597 亿美元，毛利率 75% ([英伟达 8-K](https://www.sec.gov/Archives/edgar/data/0001045810/000104581026000073/q2fy27pr.htm))；台积电营业利润率 60.3% ([台积电](https://investor.tsmc.com/english/quarterly-results/2026/q2))；阿斯麦毛利率 54% ([ASML](https://www.asml.com/en/investors/financial-results/q2-2026))。**云层收入高增但资本开支吞掉现金流**：美国四大云 2026 年资本开支指引合计 7200–7450 亿美元，同比约 80% ([Ajussi Guide](https://ajussiguide.com/hyperscaler-capex-tracker/))，已等于其经营现金流的 100%，2025 年初以来净负债增加 1700 亿美元 ([高盛研究](https://www.gspublishing.com/content/research/en/reports/2026/06/12/50f004d3-b246-4366-9d7d-0bc7e845644b.html))；甲骨文 2026 财年自由现金流负 237 亿美元、评级降至投资级最低一档，Meta 把 270 亿美元的数据中心放进外部资本持股 80% 的表外实体 ([Startup Fortune](https://startupfortune.com/oracle-and-meta-are-selling-ai-data-center-debt-to-investors-hungry-for-yield/))。**模型层收入爆发、亏损同步爆发**：OpenAI 2026 年预计现金消耗约 270 亿美元 ([Sacra](https://sacra.com/c/openai/))；xAI 2025 年收入 32 亿美元、营业亏损 64 亿美元 ([TechCrunch](https://techcrunch.com/2026/05/20/xai-burned-6-4b-last-year-spacexs-ipo-filing-shows-why-the-spending-is-far-from-over/))。有估值研究测算，六家公司近年 AI 资本开支合计约 1.7 万亿美元，而宽口径的 AI 产品与服务市场只有约 2500 亿美元 ([估值博客](https://aswathdamodaran.blogspot.com/2026/08/))。**应用层是少数超高速赢家加一批被结构性侵蚀的中介**：Cursor 年化收入三年内从零到 20 亿美元 ([维基百科](https://en.wikipedia.org/wiki/Cursor_(company)))；Chegg 2026 年二季度收入同比降 51% ([Chegg 8-K](https://www.sec.gov/Archives/edgar/data/0001364954/000136495426000085/a9901-financialresultsq220.htm))，Stack Overflow 提问量一年降 78% ([维基百科](https://en.wikipedia.org/wiki/Stack_Overflow))，Infosys 新财年固定汇率收入增长指引仅 1.5–3.5% ([Zee Business](https://www.zeebiz.com/market-news/news-infosys-investors-lose-rs-26-lakh-crore-in-2026-after-ai-rout-what-did-agm-reveal-about-plans-397832))，Atlassian 首次出现企业席位数下降 ([Computing](https://www.computing.co.uk/feature/2026/ai-deconstructing-saas-licencing-model))。

把历史结构套到这张利润图上，可以按"定价权能守多久"把产业链分为三档。**持久档**是没有替代者的瓶颈：光刻机只有一家供应商；台积电同时卡住先进制程与先进封装，2 纳米订单排到 2028 年 ([Silicon Analysts](https://siliconanalysts.com/analysis/foundry-allocation-status-q1-2026))，研究者判断 2030 年前仍是 AI 加速器唯一大规模来源的概率约 85%。还有慢折旧、不可复制的位置资产：并网点、长期电力合同、土地——美国新建大型并网平均等待 7–10 年 ([Brookings](https://www.brookings.edu/articles/global-energy-demands-within-the-ai-regulatory-landscape/))。**有期限档**是燃气轮机与电力设备（2026–2030 年槽位已锁定，2030 年后行业产能从 60–70 吉瓦向 100 吉瓦以上扩张，大概率回到买方市场）和高带宽内存（2027–2029 年新产能集中释放，研究者判断出现 30% 以上价格下跌周期的概率约 80%，SK 海力士自己的招股书也把周期性供过于求列为风险 ([SEC 文件](https://www.sec.gov/Archives/edgar/data/0002120882/000119312526299963/d32785d424b4.htm)))。**商品化档**是 GPU 出租、标准内存和通用推理算力；GPU 本身 75% 的毛利率是历史异常值，研究者判断英伟达 2036 年毛利率低于 65% 的概率约 75%，但绝对收入仍可能增长。

中国市场的结构与美国同一剧本、晚约 12–18 个月，但有三处关键差异。第一，**模型层在中国几乎不可能成为独立利润池**：开源权重由中国实验室主导，同等能力的价格差达 10–30 倍，而开源本身意味着放弃直接变现。第二，**价值流向握有分发与交易数据的平台，但先要经历资本开支压利润**：阿里巴巴 2026 年 6 月季度 AI 云与算力服务收入 484.4 亿元、增长 45%，AI 相关产品收入连续 12 个季度三位数增长，但资本开支 676.8 亿元（增 75%）使调整后息税摊销前利润 下降 30% ([阿里巴巴 6-K](https://www.sec.gov/Archives/edgar/data/0001577552/000110465926099220/tm2623667d1_ex99-1.htm))；腾讯 2026 年二季度总资本开支 528 亿元（增 176%），自由现金流由去年同期的正 430 亿元转为负 138 亿元 ([Long Yield](https://longyield.substack.com/p/chinas-ai-capex-boom-is-becoming))。第三，**算力硬件被政策锁定为国产**：英伟达 H200 虽于 2026 年 1 月获准出口，实际流量约为零 ([Long Yield](https://longyield.substack.com/p/chinas-ai-capex-boom-is-becoming))；寒武纪 2026 年上半年收入 59.96 亿元、净利润 23.11 亿元 ([Big Hat Group](https://www.bighatgroup.com/blog/china-ai-weekly-2026-09-06/))，国产替代在国内是高利润生意，风险在良率与内存供给而不在需求。

落到具体公司上，按上述逻辑可以这样归类（以下为基于笔记证据的研究判断，不构成交易建议）：

| 类别 | 代表公司 | 支持理由 | 需要跟踪的检验点 |
|---|---|---|---|
| 有分发、自研模型与云的中国采用者 | 腾讯、阿里巴巴 | 微信与淘宝的入口、混元与千问、自有云；研究者判断中国头部平台仍是中国 AI 应用价值主要捕获者的概率 80% 以上 | 资本开支压利润预计持续 2026–2028 年；腾讯自由现金流何时转正；阿里云价格战与三年 3800 亿元投资超支幅度 |
| 按交易或广告抽成、不按席位收费的中国平台 | 拼多多、快手、美团 | AI 降低的是商家运营、内容生产和配送调度成本，平台收入不随"人头"减少 | **笔记未覆盖这三家的 AI 数据**，需要单独核对变现率与单位成本；快手可灵的商业化规模 |
| 独立模型公司 | MiniMax，以及计划 2027 年上市、估值 520 亿美元的 DeepSeek ([维基百科](https://en.wikipedia.org/wiki/DeepSeek)) | 增速与生态影响力 | MiniMax 2025 年营收 7904 万美元 ([维基百科](https://en.wikipedia.org/wiki/MiniMax_(company)))；开源环境下没有结构性定价权，"词元份额高"不等于"支出份额高" |
| 中国国产算力链 | 寒武纪、海光，以及电力设备、液冷、光模块 | 份额上升是高确定性的；十五五与国家 AI 产业投资基金（首期 600 亿元）([维基百科](https://en.wikipedia.org/wiki/China_Integrated_Circuit_Industry_Investment_Fund)) 提供需求保障 | 华为不上市，上市标的多为二线；**笔记没有 A 股与港股算力链的估值与业绩数据** |
| 美国有分发的采用者 | Alphabet、微软 | 微软 Azure 增速 43%、商业剩余履约义务 6780 亿美元、Copilot 付费席位超 3000 万 ([微软](https://www.microsoft.com/en-us/investor/earnings/fy-2026-q4/press-release-webcast))；伯克希尔上半年净买入约 116 亿美元股票、Alphabet 进入前五大持仓，同时保留 2103 亿美元现金与短债 ([伯克希尔 10-Q](https://www.berkshirehathaway.com/qtrly/2ndqtr26.pdf)) | 搜索被 AI 助手分流；资本开支已等于经营现金流 |
| 美国基础设施龙头 | 英伟达、台积电、博通、阿斯麦 | 利润真实，远好于 2000 年；台积电与阿斯麦的定价权最持久 | 2027–2029 年的折旧墙与资本开支消化期；定制芯片与国产替代稀释份额 |
| 电力与电网设备 | 燃气轮机、变压器、公用事业 | 需求增量不依赖哪家 AI 公司胜出，研究者判断是 2026–2036 年回报波动最小的 AI 受益链（85%） | 监管要求数据中心自担成本，公用事业股东拿不到超额收益；2028 年前资本开支断崖会让在建电厂成为搁浅资产 |
| 结构性受损 | 按席位收费的企业软件、按人月计费的 IT 服务与业务流程外包、信息中介 | 研究者判断其收入增速系统性低于云基础设施与按结果计费的软件（80%） | 龙头能否转向按结果计费并成为 AI 代理的分发渠道 |

时间维度上最值得关注的是 2027–2030 年财务端的压力。四大云截至 2026 年一季度的过去 12 个月资本开支约为折旧的 3 倍；这一批资产按 6 年直线折旧，投入使用后每年新增折旧 650–750 亿美元，按 4 年则为 950–1100 亿美元 ([Silicon Analysts](https://siliconanalysts.com/analysis/hyperscaler-ai-capex-depreciation-wall-2026))。这会在 2027–2029 年机械性压缩利润率，与收入表现无关；亚马逊 2025 年把部分服务器折旧年限从 6 年回调到 5 年，是行业内部第一个承认信号。与此同时，前沿实验室的上市与大额解禁会带来股票供给冲击 ([GMO](https://www.gmo.com/americas/research-library/a-catalyst-for-the-ai-bubble-break_gmoquarterlyletter/))。历史上的接盘机会，恰恰出现在这类建设者承压的阶段。

## 财富机会落在智能变便宜之后最稀缺的地方

把前面几节合起来，财富机会的判断原则是：**押注"AI 变便宜之后谁受益"，而不是押注"谁把 AI 做出来"。** 当 2026 年的前沿能力在十年内接近免费，稀缺的就不再是智能，而是智能之外的要素：电力与并网指标、先进制程产能、握有用户与交易的分发渠道、可以承担法律责任的执照、需要人到场的服务、客户信任。这份清单同时回答了投资者与普通人的问题。

对资本而言，机会分三种时间尺度。**确定性最高、但已被部分定价的**是不可替代瓶颈与电力链，它们的需求不依赖任何一家 AI 公司胜出。**赔率最好、但需要耐心的**是正处于资本开支压利润阶段的中国平台型采用者：电气化的教训是赢家不是"买了电"的工厂，而是"因为电重新设计生产线"的工厂；对应到中国互联网，赢家是把推荐、广告投放、客服、商家运营、配送调度整条链路按 AI 重构的平台，其收益大概率要到 2028–2030 年才在利润表上与"只是采购了 GPU"的平台分化。研究者判断，2026 年 9 月买入英伟达、台积电、博通的十年回报低于买入 AI 采用型中国互联网平台的概率约 70–80%，理由是前者的价格已计入十年高增长，后者叠加了低估值与资本开支压利润的双重折价——这是一个高度依赖估值起点的判断，只能视为研究者观点。**机会窗口尚未打开的**是折价接盘：若 2027–2030 年出现资本开支消化期、算力租赁商或表外实体重组，历史上的回报就是在这个阶段被"第二任所有者"拿走的；由于 GPU 贬值快，值得接的是土地、电力接入和建筑外壳，不是旧卡。

同样需要说清什么不是机会。纯模型公司的股权在开源环境下没有结构性定价权；人形机器人的估值与出货严重脱节；GPU 出租承担了资产贬值风险却拿不到定价权；互联网泡沫中只有 48% 的公司存活到 2004 年 ([维基百科](https://en.wikipedia.org/wiki/Dot-com_bubble))，对普通家庭而言，研究者判断指数化持有算力链与平台跑赢自选 AI 概念股的比例超过 70%。中国内地个人通过港股通参与需要 50 万元资产门槛 ([维基百科](https://en.wikipedia.org/wiki/Shanghai-Hong_Kong_Stock_Connect))。

对个人而言，机会不在"会用 AI"——那是 85% 以上概率会被拉平的能力——而在 AI 放大之后仍然稀缺的东西。一人加 AI 可以做过去 5–10 人的知识工作，但同样的能力人人可得，护城河只能是客户关系、分销渠道、行业信任与执照。生成成本趋零使内容本身不值钱，而中国自 2025 年 9 月 1 日起强制标识 AI 生成内容 ([网信办](https://www.cac.gov.cn/2025-03/14/c_1743654684782215.htm))，"真人、可验证"本身会成为溢价属性。医护、养老、康复、维修、技工这类政策扩张且需要到场的行业，AI 只做后台增效，却能压低从业者的行政负担，是"原子端"涨价的直接受益者。

## 笔记中的已知缺口与可疑数字

以下条目在笔记中出处存疑、口径冲突或数值异常，本报告已避免把它们当作事实使用，读者引用前需要回查一手来源。

| 项目 | 笔记中的说法 | 问题 |
|---|---|---|
| 中芯国际 2026 年上半年净利润 | 446.7 亿元（增 94.2%） | 与其约 80 亿美元的年营收量级明显不符，疑为单位或口径错误，本报告未采用 |
| Alphabet 2026 年 6 月股权融资 | 847.5 亿美元 | 抓取工具摘录，与其现金流状况矛盾，笔记本身已标注勿引 |
| Anthropic 收入 | 年化 650 亿美元；二季度收入 115 亿美元 | "年化"是当月乘以 12，季度收入乘 4 仅约 460 亿美元；两家实验室口径不同，且无利润数据 |
| OpenAI 2026 年亏损 | 自身预测 140 亿美元（不含股权激励）与另一口径 GAAP 亏损 620 亿美元并存 | 口径差异四倍以上 |
| OpenAI 估值时点 | 8520 亿美元分别标注为 2026 年 3 月与 4 月 | 时点不一致 |
| 四大云 2026 年资本开支分项 | 一处亚马逊约 2200 亿、微软约 1750 亿；另一处亚马逊约 2000 亿、微软约 1900 亿；合计 7200–7450 亿与高盛 7700 亿并存 | 日历年与财年口径、租赁会计重述导致差异 |
| 中国国产 AI 芯片份额 | 研究机构称 2026 年国产近 90%；另一来源称华为约 50%；投行估计 2025 年自给率 41% | 份额口径（出货、金额、自给率）不同，不宜混用 |
| 英伟达估值倍数 | 远期市盈率 41 倍与 24–26 倍两说 | 时点与盈利口径不同，本报告未采用 |
| 燃气轮机价格 | 2027 年底约 600 美元/千瓦（较 2019 年增 195%）与当前分析师估算重型燃机约 790 美元/千瓦并存 | 设备价与联合循环项目造价混用 |
| Epoch 推理降价中位数 | "每年 50 倍，2024 年后 200 倍" | 仅见于搜索摘要，原页只核到"9–900 倍"与"约 40 倍" |
| 2026 年 9 月模型命名与价目 | 两家价格聚合站对 OpenAI 模型命名互相矛盾 | 未核对官方价目 |
| 美国私人 AI 投资 | 2859 亿与 3440 亿美元两个"美国"口径 | 一为私人投资，一为全部投资 |
| METR 最新时间跨度 | 某模型"16 小时" | 仅见社交媒体 |
| 年轻人就业与 AI 使用数据 | Anthropic"49% 职业深度使用""入门招聘放缓 14%"；普华永道"AI 技能溢价 62%"；翻译自由职业者时薪降 20% 以上 | 原始页面无法打开，均为二手转述 |
| 机构暴露度估计 | 国际货币基金组织"40%/60%"、高盛"3 亿岗位" | 笔记注明部分数字来自记忆，未核对原文 |
| 中国白领替代率 | 自媒体流传的"数据录入替代率 95%、客服 90%" | 无出处，不可作为证据 |
| 宇树股东名单含 DeepSeek；Figure 机器人"支持 3 万辆以上汽车生产" | 百科条目原文 | 前者存疑，后者疑为公司口径，与另一条目冲突 |
| rentosertib 进入三期；Klarna 2025 年重新招回人工客服 | 百科与新闻标题 | 均未核实，本报告未采用 |
| 萝卜快跑最新单量、中国网约车司机人数、中国辅助驾驶渗透率、中国人形机器人全行业出货、拼多多与快手与美团的 AI 数据、A 股算力链估值 | 笔记缺失 | 是本报告中国部分最大的空白，相关判断仅为推理 |

此外，笔记中所有概率均为各研究者的主观判断，彼此之间未经统一校准，个别条目（如五十城无人出租车、资本开支回撤年）存在分歧，本报告已并列呈现。

## 结论

这项研究改变的核心认知是：**2036 年的可预测部分与不可预测部分，边界非常清楚。** 可预测的是成本、基准、电力和入口——它们由已运行数年的曲线驱动，历史上这类判断被低估而不是高估；不可预测的是替代的日期、通用人工智能的定义时刻和哪家模型公司胜出——历史上这类判断几乎一律偏早。因此，对个人和资本最稳健的策略，都是把决策建立在"智能会变得极便宜"这一近乎确定的前提上，然后追问：当智能不再稀缺，什么会变得更稀缺。答案是物理约束（电力、制程、土地）、分发与交易数据、可承担责任的执照、需要人到场的服务，以及真实的客户信任。

第二个新认知关于时点。AI 的长期价值与 2027–2030 年的财务压力可以同时成立：折旧墙、表外融资、前沿实验室的巨亏与上市供给，大概率会在能力继续进步的同时制造一次资本开支消化期。按铁路与光纤的经验，那恰恰是价值从建设者手中转移到接盘者和采用者手中的阶段；而与光纤不同，GPU 的快速贬值意味着这次值得接的是慢折旧的位置资产，而不是算力本身。对中国读者，这一逻辑还叠加了一层本地结构：模型层利润被开源压向零、算力被政策锁定为国产，价值将沉淀在少数握有入口的平台上——前提是它们熬过 2026–2028 年资本开支对利润的挤压，这是未来两三年最值得逐季验证的一件事。
