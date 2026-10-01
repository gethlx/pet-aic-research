# papers · 论文追踪

> 按四层路线分组，2023–2026 为主。每条：标题 / venue / 年份 / 一句话结论 / 可用性评级（直接可用 · 方法可借鉴 · 仅背景）。preprint 一律标 ⚠️ 待评审。

## ① 感知层

| 论文 | Venue / 年份 | 一句话结论 | 可用性 |
|---|---|---|---|
| Towards Dog Bark Decoding: Leveraging Human Speech Processing for Automated Bark Classification（Abzaliev et al., U-M & INAOE） | arXiv:2404.18739 / LREC-COLING 2024 | 人类语音预训练模型（Wav2Vec2）迁移到犬吠：个体 50%、品种 62%、情境 ~70%，全面优于从零训练 | 方法可借鉴 |
| Deep Learning Classification of Canine Behavior Using a Single Collar-Mounted Accelerometer（Mars Pet Insight） | Animals 2021, 10.3390/ani11061549 | 单加速度计亚秒级行为分类：抓挠 87/99.7、进食 98.8/98.3（灵敏度/特异性），1100 万天生产数据验证 | 直接可用 |
| Retrospective observational study: accelerometers monitor canine pruritus treatment（AJVR 2025, 86(3)） | AJVR 2025 | 加速度计数据与兽医 EHR 联动可监测皮炎疗效——感知层临床价值实证 | 直接可用 |
| 米兰大学猫叫情境分类（喂食/梳毛/独处，21 只猫） | ~2019（SciAm 报道） | 猫叫情境可分类，最高 96%——MeowTalk 科学源头 | 方法可借鉴 |
| Duzce University vision transformer 猫叫分类 | 2024–25（SciAm 报道） | 频谱图进 ViT，定位对分类贡献可解释 | 方法可借鉴 |
| Feline/Canine Grimace Scale 及 ML 自动化系列 | 2019–2024 | 疼痛表情量表已验证，自动化识别 95%+（CatsMe! 口径 ⚠️） | 方法可借鉴 |

## ② 表达层（AIC 与认知）

| 论文 | Venue / 年份 | 一句话结论 | 可用性 |
|---|---|---|---|
| Soundboard-trained dogs produce non-accidental, non-random and non-imitative two-button combinations（Bastos, Rossano et al.） | Scientific Reports 2024, 10.1038/s41598-024-79517-6 | 152 犬 26 万次按压：双词组合非随机非模仿——AIC 意向性最硬证据 | 直接可用 |
| Dogs understand words from soundboard buttons（Rossano 团队） | PLOS ONE 2024 | 预注册实验：狗响应按钮词义本身，非主人线索 | 直接可用 |

## ③ 推理层（融合与评估方法学）

| 论文 | Venue / 年份 | 一句话结论 | 可用性 |
|---|---|---|---|
| Introducing NatureLM-audio（ESP） | 2024-11 发布，v1.1 2026-04 | 首个动物音频-语言基础模型（BEATs+Llama3.1-8B），BEANS-Zero zero-shot SOTA；可自然语言问答、泛化到未见物种 | 直接可用（开源） |
| 动物通信评估方法学讨论（Rossano, UCSD Today 2025 访谈中表述） | 2025 | AI 找模式，意义需 ground truth；主人反馈是唯一可规模化标注源——评估设计的北极星 | 仅背景 |

## ④ 反向层

| 论文 | Venue / 年份 | 一句话结论 | 可用性 |
|---|---|---|---|
| Neural mechanisms for lexical processing in dogs（Andics et al.） | Science 2016 | 犬脑分离处理词义（左）与语调（右），匹配激活奖励中枢——人→宠信号可工程化的神经地基 | 方法可借鉴 |
| 犬跟随 2D 屏幕指向/预录视频（Pongrácz 2003；Péter 后续） | 2003+（Family Dog Project） | 远程人→宠视觉通道存在基础 | 仅背景 |

## 每周增量说明

新论文追加到对应分组表尾，字段齐全并带 ✅/⚠️；每周扫描结果同步登记 [updates-log.md](./updates-log.md)。
