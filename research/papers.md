# papers · 论文与研究线索

> 2026-10-01纠正；路线标签保留，发表状态、原文结果和产品可用性分别记录。未知不补造。核验方法见[VETTING](../VETTING.md)。

## ① 感知

| 研究 | 发表／来源 | 结果及证据边界 | 可用性 |
|---|---|---|---|
| Towards Dog Bark Decoding（Abzaliev等） | ✅[LREC-COLING 2024原文](https://aclanthology.org/2024.lrec-main.1432.pdf)，核查2026-10-01 | 74犬、主要三犬种；个体49.95%、品种62.28%；四类情境62.18%（基线56.37%）；按犬分组十折；不是约70%的情绪识别 | 方法可借鉴，数据申请／许可待核 |
| Deep Learning Classification of Canine Behavior（Pet Insight） | [Animals 2021](https://doi.org/10.3390/ani11061549)，核查2026-10-01 | 原记录抓挠87／99.7、进食98.8／98.3（灵敏度／特异性）；生产数据规模不等于全部有独立真值验证。对应任务、验证集和利益关系须在使用前细读 | 方法可借鉴，无官方开源实现，不是直接可部署 |
| Accelerometers monitor canine pruritus treatment | [AJVR 2025建仓线索](../docs/04-references.md)，原记录DOI后缀ajvr.24.09.0269；解析入口及全文待核 | 病历联动／皮炎治疗响应线索；实际分析样本、对照和局限待核，不能把项目全部犬数当研究样本 | 临床方法候选 |
| 米兰大学猫叫三情境分类 | ❓原论文待追溯；[建仓媒体线索](../docs/04-references.md)，核查2026-10-01 | 原记录21猫／最高96%，任务划分、个体隔离及泛化待核 | 待核，不作性能锚点 |
| Duzce ViT猫叫分类 | ❓题名、venue和原文待核；[建仓线索](../docs/04-references.md) | 原媒体称2024–25；不以报道推定发表或可解释性效果 | 待核 |
| Feline／Canine Grimace及ML系列 | ❓逐篇题名、物种与原文待拆分；[建仓线索](../docs/04-references.md) | 量表研究与App识别分开；CatsMe!95%+为来源口径⚠️ | 方法线索 |
| 犬语音素字母表发现（Wang等，UT Arlington ACL2组） | ✅[ACL 2025原文页](https://aclanthology.org/2025.acl-long.451/)，Outstanding Paper，核查2026-10-05 | 最小对启发的迭代算法发现犬音位类单元与重复声学单元；摘要页未给数据规模、个体划分与跨犬泛化，待读全文；同组另有Dog2vec（Interspeech 2025）与词法发现论文线索待核 | 方法可借鉴；代码/数据链接见[实验室页](https://uta-acl2.github.io/research.html)，许可待核 |
| CREMD犬情绪标注研究 | ⚠️[arXiv 2602.15349](https://arxiv.org/abs/2602.15349)，2026-02-17预印本待评审，核查2026-10-05 | 923视频片段×三呈现模式众包标注研究：视觉上下文显著提高标注一致性；音频线索因设计限制结论不确定；音频显著提高标注者对愤怒/恐惧的信心。是标注方法与偏差研究，非识别模型结果；数据公开与许可待核 | 标注偏差方法参照（主人/外行标注差异证据） |

## ② 表达

| 研究 | 发表／来源 | 结果及证据边界 | 可用性 |
|---|---|---|---|
| Soundboard-trained dogs produce non-accidental…two-button combinations | ✅[Scientific Reports 2024-12-09](https://www.nature.com/articles/s41598-024-79517-6)，核查2026-10-01 | 152犬、26万+按压，组合非随机／非简单模仿；主人记录和选择偏差、词义对应及个体差异仍需检验 | 方法可借鉴，不是直接可用意图标签 |
| How do soundboard-trained dogs respond to human button presses? | ✅[PLOS ONE 2024-08-28](https://doi.org/10.1371/journal.pone.0307189)，核查2026-10-01 | 30入户＋29远程，部分词／结果关联；作者披露FluentPet咨询／雇佣关系，非完全利益无关 | 方法可借鉴 |
| 四按钮计算机化游戏系统评估 | ⚠️[Learning & Behavior 2025-11-04](https://doi.org/10.3758/s13420-025-00692-1)，未读全文，核查2026-10-05 | 按钮论文后续：犬认知参与的四按钮系统；任务、样本与结果待读原文 | 按钮/ACI线索 |
| 播放词音质影响犬识别与响应 | ⚠️[Scientific Reports 2025-04-28](https://doi.org/10.1038/s41598-025-96824-8)，未读全文，核查2026-10-05 | 声板播放音质影响犬对词的识别与响应；细节待读原文 | 声板硬件设计线索 |
| "Talking dogs"科学综述 | ⚠️[Biologia Futura 2025-06-01](https://doi.org/10.1007/s42977-025-00276-0)，未读全文，核查2026-10-05 | 声板研究现状综述；结论待读原文 | 背景综述线索 |

## ③ 推理

| 研究 | 发表／来源 | 结果及证据边界 | 可用性 |
|---|---|---|---|
| NatureLM-audio | ✅[ICLR 2025正式发表](https://openreview.net/forum?id=hJVdwBpWjt)；[arXiv 2411.07186](https://arxiv.org/abs/2411.07186)；[官方指南](https://projects.earthspecies.org/naturelm-audio/latest/quick_start.html)，核查2026-10-05 | 生物声学基准／跨物种任务；鸟类表现最强，犬猫家庭意图待测；权重许可见tooling，2026-10-05确认ICLR 2025发表 | 研究候选；不认定直接商用 |
| NatureLM模型合并零样本泛化（Marincione等） | ⚠️[arXiv 2511.05171 v2](https://arxiv.org/abs/2511.05171)，2025-11-19待评审；[官方repo已引用](https://github.com/earthspecies/NatureLM-audio)，核查2026-10-05 | NatureLM与基座Llama插值合并恢复指令遵循，自称未见物种闭集零样本分类相对提升200%+；仅闭集零样本，非犬猫家庭任务；merging_alpha 0.4–0.6任务相关 | 部署候选路径；独立复现待核 |
| Rossano／UCSD Today评估讨论 | ⚠️2025访谈线索，[建仓参考](../docs/04-references.md) | 访谈不是论文；“主人反馈唯一可规模化真值”是原仓库推断，已撤回 | 仅背景，访谈原文待核 |

## ④ 反向

| 研究 | 发表／来源 | 结果及证据边界 | 可用性 |
|---|---|---|---|
| Neural mechanisms for lexical processing in dogs（Andics等） | Science 2016，原文待补；[建仓线索](../docs/04-references.md) | 犬听觉词／语调背景；具体脑区表述及后续修正待核，不能推定工程干预有效 | 方法背景 |
| 犬跟随屏幕／录像指令（Pongrácz、Péter等） | 2003+，逐篇原文待拆分；[建仓线索](../docs/04-references.md) | 远程信号研究线索，不当通用产品证明 | 背景／方法待核 |

## 新条目的必要笔记

至少写来源、发表与核查日期、任务／物种／动物数量、标签和指标、基线、按个体划分、外部验证、利益关系、使用边界。缺失写未知。健康预警补每宠每日误报、漏报、提前量和后续行动。允许追溯关键旧文献和负面结果；代码／数据／权重许可到对应资源表分别核查。
