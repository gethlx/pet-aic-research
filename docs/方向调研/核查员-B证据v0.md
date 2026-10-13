# 一、Tampere 大学犬只加速度计/陀螺仪行为识别数据集

## 1. 官方发布页（以这个为准）

**唯一官方数据仓：Mendeley Data**（Tampere University + University of Helsinki）。本次检索 **未找到** Fairdata / IDA 或 Zenodo 上的同一数据集镜像（待核：若日后补存，以原作者 DOI 为准）。

| 项目 | 内容 |
|---|---|
| 标题 | Movement Sensor Dataset for Dog Behavior Classification |
| 官方页 | https://data.mendeley.com/datasets/vxhx934tbn |
| 当前版本 DOI | [10.17632/vxhx934tbn.4](https://doi.org/10.17632/vxhx934tbn.4)（Version 4，2025-11-05） |
| 数据论文引用的版本 | [10.17632/vxhx934tbn.2](http://dx.doi.org/10.17632/vxhx934tbn.2) |
| 机构 | Tampereen yliopisto（Tampere University）、Helsingin Yliopisto（University of Helsinki） |
| 贡献者 | Antti Vehkaoja, Sanni Somppi, Heini Törnqvist, Anna Valldeoriola Cardó, Pekka Kumpulainen, Heli Väätäjä, Päivi Majaranta, Veikko Surakka, Miiamaaria Kujala, Outi Vainio |
| 资助 | Business Finland 1665/31/2016, 1894/31/2016, 7244/31/2016（Buddy and the Smiths 2.0） |

**官方许可证（Mendeley 页面原样标注）：CC BY 4.0**

数据描述论文版权页原文：

> © 2022 The Author(s). Published by Elsevier Inc. This is an open access article under the **CC BY license** (http://creativecommons.org/licenses/by/4.0/)  
> 来源：Vehkaoja et al., *Data in Brief* 40 (2022) 107822, https://doi.org/10.1016/j.dib.2022.107822

行为分类论文同样为 CC BY 4.0：Kumpulainen et al., *Applied Animal Behaviour Science* 241 (2021) 105393, https://doi.org/10.1016/j.applanim.2021.105393

作者额外请求（非法律强制，但是官方页原文）：使用数据并发表结果时，引用上述两篇论文。

## 2. CC BY 4.0 条款原文（Creative Commons 官方 deed）

来源：https://creativecommons.org/licenses/by/4.0/deed.en

**You are free to:**

1. **Share** — copy and redistribute the material in any medium or format **for any purpose, even commercially**.
2. **Adapt** — remix, transform, and build upon the material **for any purpose, even commercially**.
3. The licensor cannot revoke these freedoms as long as you follow the license terms.

**Under the following terms:**

1. **Attribution** — You must give appropriate credit, provide a link to the license, and indicate if changes were made. You may do so in any reasonable manner, but not in any way that suggests the licensor endorses you or your use.
2. **No additional restrictions** — You may not apply legal terms or technological measures that legally restrict others from doing anything the license permits.

**appropriate credit** 脚注原文：If supplied, you must provide the name of the creator and attribution parties, a copyright notice, a license notice, a disclaimer notice, and a link to the material.

法律文本（https://creativecommons.org/licenses/by/4.0/legalcode.en）第 2 节授权范围：worldwide, royalty-free, non-sublicensable, non-exclusive, irrevocable license，包括 reproduce and Share the Licensed Material，以及 produce, reproduce, and Share Adapted Material。

**没有 ShareAlike，没有 NonCommercial，没有 NoDerivatives。**

## 3. 样本规模与采集参数（数据论文 + 官方仓描述）

来源：Vehkaoja et al., *Data in Brief* 2022；Mendeley 描述页。

| 项目 | 官方数字 |
|---|---|
| 犬数 | **45** 只中大型宠物犬；**17** 只做了重复采集 |
| 品种/体型 | 27 个品种；平均年龄 4.9 岁、平均体重 24.5 kg；无重大影响运动的健康问题 |
| 传感器 | ActiGraph GT9X Link（ActiGraph LLC, Florida, USA），6 自由度：**3 轴加速度计 + 3 轴陀螺仪** |
| 佩戴位置 | **项圈腹侧**（胶带固定）+ **胸背背带**（neoprene 口袋） |
| 采样率 | **100 Hz / 通道** |
| 场景 | 犬运动馆 10 m × 18 m 人工草皮；主人引导的半控制任务 |
| 任务（约各 3 分钟） | 坐、站、卧、快步 trotting、走 walking、玩耍 playing、寻零食/嗅 sniffing |
| 视频标注标签（1 秒分辨率） | **Galloping, Lying on chest, Sitting, Sniffing, Standing, Trotting, Walking**（玩耍任务中才标 galloping；寻零食任务中才标 sniffing） |
| 数据量 | CSV 约 10,611,068 行 × 20 列；`DogMoveData.mat` 约 431 MB |

分类论文结果（Kumpulainen et al. 2021，同一数据）：2 秒窗、54 个特征、4 种分类器。**背部最高约 91% 准确率，项圈最高约 75%。** 加入陀螺仪特征使准确率提高 **0.7–2.6%**。嗅探最易分；静姿（卧/坐/站）最难，尤其项圈。

## 4. 版本一览

| 版本 | DOI | 日期（来源） | 说明 |
|---|---|---|---|
| v1 | 10.17632/vxhx934tbn.1 | 2021-07-02（Tampere Research Portal） | 分类论文引用的首发 |
| v2 | 10.17632/vxhx934tbn.2 | 数据论文 2022 引用 | *Data in Brief* 指定 URL |
| v3 | 10.17632/vxhx934tbn.3 | 2022-04-19（Tampere Research Portal） | 门户登记 |
| v4 | 10.17632/vxhx934tbn.4 | **2025-11-05**（当前官方页） | 许可证仍标 **CC BY 4.0** |

许可证在各版本页面均为 CC BY 4.0，未见改为 CC BY-SA。

## 5. 相关 Tampere 研究，但不是第二个公开数据集

Kumpulainen 等，ACI 2018（https://doi.org/10.1145/3295598.3295602）：**24 只犬、仅项圈 3D 加速度计、七类行为、最高总体准确率 76%**。这是同一课题组的前期会议论文，**未检索到单独的 Fairdata/Zenodo/Mendeley 数据发布**。

University College Cork / Tyndall 的 “Inertial sensor dataset for Dog Posture Recognition”（Mendeley 10.17632/mpph6bmn7g.1，42 犬，CC BY 4.0）**不是 Tampere 数据集**。

## 6. Kaggle 转载 vs 官方许可

检索到两份转载：

**A. Möbius（arashnic）**  
https://www.kaggle.com/datasets/arashnic/animal-behavior-analysis  
页面明确写：**License: CC BY-SA 4.0**。内容是 Tampere 45 犬、双传感器、100 Hz 的同一套数据。

**B. Benjamin Gray（benjamingray44）**  
https://www.kaggle.com/datasets/benjamingray44/inertial-data-for-dog-behaviour-classification  
正文写：Data downloaded from https://data.mendeley.com/datasets/vxhx934tbn/2，并写 **CC BY 4.0**；同一页又出现 “License: Attribution-NoDerivatives 4.0 International (CC BY-ND 4.0)”。**Kaggle 页内部自相矛盾。**

### 是否冲突、以哪个为准

**以官方 Mendeley 的 CC BY 4.0 为准。**

理由（均有出处）：

1. 原权利人在 Mendeley 与两篇 OA 论文中授予的是 **CC BY 4.0**。
2. CC BY 4.0 deed 明确：**No additional restrictions**——转载者不得对同一材料附加法律条款，限制他人做许可证已允许的事。
3. 第三方把同一文件标成 **CC BY-SA** 或 **CC BY-ND**，是**错误收紧**，不能覆盖原许可。ShareAlike 要求“改编后必须以同类许可证再分发”；NoDerivatives 禁止改编。二者都**不是**原作者授予的条件。

Kaggle 的 CC BY-SA 与官方 **有标签冲突，没有法律效力上的覆盖关系**。从 Kaggle 下载的仍是 CC BY 作品。若只使用 Kaggle 上传者自己写的说明文字/整理方式，那些附加内容可能另有版权，但**原始传感器文件**仍受 CC BY 4.0 约束。

### 商用训练模型是否允许

**允许。** CC BY 4.0 deed 原文两次写 “for any purpose, even commercially”（Share 与 Adapt）。

署名要求（最低实务清单，对应 deed + legal code §3(a)）：

- 标明创作者：Vehkaoja, Somppi, Törnqvist, Valldeoriola Cardó, Kumpulainen, Väätäjä, Majaranta, Surakka, Kujala, Vainio 等
- 标明来源与 DOI（建议同时给 Mendeley DOI 与两篇论文 DOI）
- 提供许可证链接：https://creativecommons.org/licenses/by/4.0/
- 说明是否做了修改（清洗、重标注、子集等）
- 不得暗示原作者或 Tampere 大学为你的产品背书

作者“请引用两篇论文”是学术惯例请求，建议遵守；法律强制项是 CC BY 的 Attribution。

**待核（法律灰色带，不是许可禁止）：** 训练得到的模型权重是否构成 CC 意义上的 “Adapted Material”，各司法辖区与律师意见不一。CC BY **没有** ShareAlike，因此即便把权重视为改编物，也**不必**把模型开源为 CC BY-SA；仍须在合理处署名数据集。这不影响“可以用该数据做商用训练”这一条——deed 已写明 commercially。

---

# 二、犬只夜间活动/休息与健康：同行评审原文要点

说明：下列每条都来自论文摘要/正文/表格。未找到加速度计原文数字的，标 **待核** 或写明“本文未报该指标”。

## A. 骨关节炎、夜间不安、NSAID / 抗 NGF

### A1. Knazovicky, Tomas, Motsinger-Reif, Lascelles, 2015

- **标题：** Initial evaluation of nighttime restlessness in a naturally occurring canine model of osteoarthritis pain  
- **期刊 / 年：** *PeerJ* 3:e772, 2015  
- **DOI：** https://doi.org/10.7717/peerj.772  
- **设计：** 前瞻、设盲。Part A：60 只 OA 犬，2 周无药基线 → 2 周 meloxicam（个体内前后）。Part B：19 只 OA 犬，meloxicam/安慰剂交叉，各 2 周 + 1 周洗脱。  
- **设备 / 位置：** 项圈加速度计（后续文献明确为 **Actical**；Smith et al. 2022 写明 “Knazovicky et al. 2015 used Actical Activity monitors”）。夜间为主要终点。  
- **主要结果（原文数字）：**  
  - Part A 夜间活动：基线 mean **4,642 ± 2,052** vs NSAID **5,414 ± 2,020**，差值 −772 ± 2,931，**p = 0.5976**（未校正）。  
  - Part B：安慰剂减 NSAID 的每小时活动变化 mean **121 ± 963**，**p = 0.2645**。  
  - **加速度计夜间活动无显著治疗效应。**  
  - SNoRE 总分：NSAID vs 基线 **−6.00，p = 0.0012**；NSAID vs 安慰剂 **−4.73，p = 0.0496**。改善主要在“不明显大动作”的睡眠质量条目。  
- **局限：** 作者结论写 “Although accelerometry does not appear to be useful”；把多小时均值当终点会抹掉短时翻身；无健康对照；Part B 为预试验。

### A2. Gruen, Samson, Lascelles, 2019（对 A1 Part B 的 FLM 再分析）

- **标题：** Functional linear modeling of activity data shows analgesic-mediated improved sleep in dogs with spontaneous osteoarthritis pain  
- **期刊 / 年：** *Scientific Reports* 9:14192, 2019  
- **DOI：** https://doi.org/10.1038/s41598-019-50623-0  
- **设计：** 随机交叉 NSAID（meloxicam）vs 安慰剂的 **个体内纵向再分析**。  
- **样本量：** 完整活动数据 **n = 15**（10 母 / 5 公；年龄 10.29 ± 2.48 岁；体重 31.53 ± 5.39 kg）。  
- **设备：** 与 SNoRE 试验相同的项圈加速度计；**每分钟**采样后做 24 小时功能线性模型（FLM）。夜间窗口与主人定义的夜间重叠，约 **23:00–06:00**。  
- **主要结果：**  
  - 传统混合模型：治疗对夜间活动 **无效应**（Treatment estimate −0.022，p = 0.580）；周末夜间活动更高（p = 0.006）。  
  - **FLM：** meloxicam vs 安慰剂在 **23:00–06:00、07:00–12:00、21:00–22:00** 曲线分离。用药后 **23:00–06:00 夜间活动下降**（更好休息），白天活动上升。  
  - SNoRE：NSAID vs 基线总分（5 题）**−6.20，p = 0.001**；NSAID vs 安慰剂 **−4.93，p = 0.029**。Q2 twitching −1.40，p = 0.012；Q3 dreaming −1.40，p < 0.001。  
- **局限：** n = 15；同一批 OA 犬再分析；FLM 给出时段显著性而非单一效应量（如 Cohen’s d）；“睡眠”由低活动代理，无 EEG。

### A3. Smith, Mendl, Murrell, 2022

- **标题：** Associations between osteoarthritis and duration and quality of night-time rest in dogs  
- **期刊 / 年：** *Applied Animal Behaviour Science* 253:105661, 2022  
- **DOI：** https://doi.org/10.1016/j.applanim.2022.105661  
- **设计：** **群体比较**，OA **n = 20** vs 健康对照 **n = 21**，家中 **28 天**。  
- **设备 / 位置：** **FitBark** 项圈；主人每 7 天填 SNoRE。  
- **主要结果：**  
  - OA 组夜间休息比例更低（即夜间更活跃）：稳健混合模型 Group 系数 **0.9760**（95% CI **0.9540–0.9970**），**z = 2.214，P = 0.0268**（对照为参照；系数 < 1 表示 OA 休息比例约为对照的 97.6%）。  
  - SNoRE：**z = −1.01，p = 0.312**（组间无显著差）。  
- **局限：** 非随机、非纵向治疗；FitBark 专有“休息”算法；SNoRE 与客观指标不一致；样本小、品种/家庭作息未充分分层。

### A4. bedinvetmab / Librela 与夜间活动

**本次检索未找到**以夜间加速度计为主要终点、专门报告 bedinvetmab 改变夜间活动的同行评审全文。

已找到的相邻证据：

- **Enomoto, Buslinger, Thonen-Fleck 等, 2026**，*Scientific Reports*，https://doi.org/10.1038/s41598-026-37626-4：bedinvetmab vs grapiprant 非劣效，**测力台**为主；**SNoRE 3.0** 为病人报告结局，两组治疗后均改善。作者写：今后可用加速度计客观看对睡眠质量的影响。**无夜间加速度计数字。**
- **Veterinary World, 2026**（肥胖 OA 犬 RCT）：FitBark 项圈，**日均** MAC/day 至 Day 56 升 **25.6%（p = 0.032）**，疼痛分降 1.95（p < 0.001）。**不是夜间分层。**
- 注册试验（Michels et al. 2023, *Vet Anaesth Analg*，https://doi.org/10.1016/j.vaa.2023.06.003）：n = 272，CBPI，无加速度计睡眠终点。

**结论：抗 NGF 改变夜间活动 = 待核 / 证据缺口。** NSAID 的夜间证据来自 Gruen 2019 的 FLM，不是 Librela。

### A5. 其他 OA 24 小时活动（夜间片段）

- **Stevens, Kawecki-Wright, Gruen, Lascelles 等, 2025**，*Front. Vet. Sci.* https://doi.org/10.3389/fvets.2025.1503009：**99** 只 OA 犬，**Actigraph GT3X 项圈**，FLM。后肢 OA、高龄、高 CMI、高关节痛、高 BCS、肌萎缩均压低高峰活动。引用 Gruen 2019 的夜间/清晨差异。  
- **Kawecki-Wright 等, ACR 2025 摘要**（非全文）：89 只有足够数据的犬，MJOA 与 3 am–2 pm、6 pm–11 pm 活动更低；高龄/MJOA 在午夜后有短暂活动升高，作者解释为疼痛相关睡眠干扰。**待核：会议摘要，非正式发表全文。**

---

## B. 老年犬认知功能障碍（CCD）与夜间/睡眠

### B1. Woods, Li, Patel, Lascelles, Samson, Gruen, 2020

- **标题：** A functional linear modeling approach to sleep–wake cycles in dogs  
- **期刊 / 年：** *Scientific Reports* 10:22233, 2020  
- **DOI：** https://doi.org/10.1038/s41598-020-79274-2  
- **设计：** 健康成年伴侣犬基线描述，**不是 CCD 病例对照**。  
- **样本：** **n = 42**，年龄 2–9 岁，**Actical 项圈 14 天**。  
- **结果：** 双峰活动（晨、晚）；年龄、体质量、性别影响高峰；作者写该基线“makes it possible to characterize deviations from normal patterns, including those associated with chronic pain and **cognitive dysfunction syndrome**”。  
- **局限：** 排除真正老年/CCD 犬；无疾病诊断效能。

### B2. Mondino, Khan, Case, Gruen, Olby 等, 2023（家中加速度计）

- **标题：** Activity patterns are associated with fractional lifespan, memory, and gait speed in aged dogs  
- **期刊 / 年：** *Scientific Reports* 13:2588, 2023  
- **DOI：** https://doi.org/10.1038/s41598-023-29181-z  
- **设计：** 横断面，**27** 只高龄犬（12.9 ± 1.64 岁）。  
- **设备：** **Actical 项圈，2 周**。CADES 问卷 + 认知测试 + 关节/脊柱痛。CADES 中位 10（0–70）：正常 10、轻度 6、中度 7、重度 4。  
- **结果（FLM）：** 年龄/寿命分数：工作日 **17:00–20:00** 活动更低；周末 **14:00–17:00** 更低；周末清晨约 **5:00**（寿命分数约 **4:15–4:45**）更活跃。工作记忆更好的犬傍晚更活跃；周末约 00:00–02:45 更活跃、03:45–05:30 更少活动。作者把主人报告的 CCD 特征写成“白天活动减少、睡眠时过度踱步”。  
- **局限：** n = 27；CCD 例数少（重度仅 4）；相关不是诊断；疼痛与认知共线。

### B3. Mondino, Catanzariti, Mateos, Gruen, Olby 等, 2023（多导睡眠图，非项圈）

- **标题：** Sleep and cognition in aging dogs. A polysomnographic study  
- **期刊 / 年：** *Frontiers in Veterinary Science* 10:1151266, 2023  
- **DOI：** https://doi.org/10.3389/fvets.2023.1151266  
- **样本：** **28** 只老年犬（17 母 11 公），实验室 **下午约 2 小时** 午睡 PSG。  
- **结果：** CADES 更高、绕障任务更差 → **NREM、REM 时间更少**；EEG 显示睡眠更浅。作者明确：尚不知下午记录是否等于夜间家中睡眠。  
- **局限：** 非家中夜间加速度计；环境陌生；非诊断试验。

### B4. Mondino, Ludwig, Lascelles, Gruen, Olby 等, 2023（SNoRE 3.0）

- **标题：** Development and validation of a sleep questionnaire, SNoRE 3.0, to evaluate sleep in companion dogs  
- **期刊 / 年：** *Scientific Reports* 13:13340, 2023  
- **DOI：** https://doi.org/10.1038/s41598-023-40048-1  
- **设计：** 问卷验证。PSG 子集 **n = 38**；另与 PAM 对照。  
- **结果：** SNoRE 3.0 vs NREM 潜伏期 **ρ = 0.507，p < 0.001**；vs **01:00–03:00 PAM 活动 p < 0.05**；vs CADES **ρ = 0.625，p < 0.001**。  
- **意义：** 主人问卷与夜间 1–3 点活动、痴呆量表相关；仍不是疾病诊断器。

### B5. Taylor, Tuke, Hazel, 2026（主人报告，无加速度计）

- **标题：** Sleep–wake disturbance in canine cognitive dysfunction: Guardian-reported patterns and a practical screening tool  
- **期刊 / 年：** *The Veterinary Journal*（文章号 106817）  
- **DOI：** https://doi.org/10.1016/j.tvjl.2026.106817  
- **样本：** ≥8 岁犬主人 **n = 205** 在线调查。  
- **结果：** 入睡/维持睡眠差、夜间排泄与 CCD 严重度相关（adjusted **p < 0.00001**）。最不安时段 **02:00–05:00** 占 **53.7%**。重度 CCD 一夜叫醒主人 ≥4 次：**20.8% vs 轻度 9.3%**。决策树区分轻 vs 更重，**AUC = 0.69**。个体差异大。  
- **局限：** 无传感器；回忆偏倚；AUC 中等。

### B6. Madari 等, 2015（CADES 量表，睡眠–觉醒为症状域）

- **标题：** Assessment of severity and progression of canine cognitive dysfunction syndrome using the CAnine DEmentia Scale (CADES)  
- **期刊 / 年：** *Applied Animal Behaviour Science*, 2015  
- **DOI：** https://doi.org/10.1016/j.applanim.2015.08.034  
- **样本：** 筛选 >300 只，入分析 **215**。睡眠–觉醒是四域之一。中度认知损害中 **67%** 同时有社交与睡眠–觉醒受累。这是 **问卷分期工具**，不是加速度计验证。

---

## C. 加速度计项圈：疼痛/疾病相关验证

### C1. Actical — Hansen, Lascelles 等, 2007

- **标题：** Evaluation of an accelerometer for at-home monitoring of spontaneous activity in dogs  
- **期刊 / 年：** *Am J Vet Res* 68:468–475, 2007  
- **DOI：** https://doi.org/10.2460/ajvr.68.5.468  
- **样本：** **4** 只健康犬；5 台 Actical；8 个位置（项圈/背心/前肢）。  
- **结果：** 各位置与视频移动相关可接受；**项圈腹侧最方便**。最不一致的一对设备中 **96%** 读数在全体均值 ±2 SD 内。  
- **局限：** n = 4；实验室视频，非疾病诊断。

### C2. Actical — Brown, Boston, Farrar, 2010

- **标题：** Use of an activity monitor to detect response to treatment in dogs with osteoarthritis  
- **期刊 / 年：** *JAVMA* 237:66–70, 2010  
- **DOI：** https://doi.org/10.2460/javma.237.1.66  
- **设计：** RCT，OA 犬 **n = 70**（carprofen 35 / 安慰剂 35），项圈 Actical **21 天**（治疗 day 8–21）。  
- **结果：** carprofen 组中位活动计数 1,276,427 → 1,374,133；校正年龄与基线后，相对安慰剂 **+20%（95% CI 10–26%）**。  
- **局限：** 总活动而非夜间；群体治疗效应，非个体报警阈值。

### C3. Actical — 睡眠/休息零计数（2025 预试验）

- **标题：** Actical Accelerometers as a Clinical Tool for the Monitoring of Sleeping and Resting Periods in Individual Dogs  
- **期刊 / 年：** *Animals*（PMC12427222）, 2025  
- **DOI：** 待核页码；PMC：https://pmc.ncbi.nlm.nih.gov/articles/PMC12427222/  
- **样本：** **10** 只大型家犬；项圈 Actical；逐分钟行为观察 2633 分钟、32 段睡眠/休息。  
- **结果：** **0 counts/min** 识别合并睡眠+休息：**灵敏度 94.0%，特异度 96.1%**；**不能**区分闭眼睡与睁眼休息。  
- **局限：** n = 10；零计数 = 静息，不是疾病标签。

### C4. PetPace — Belda, Enomoto, Case, Lascelles, 2018

- **标题：** Initial evaluation of PetPace activity monitor  
- **期刊 / 年：** *The Veterinary Journal* 237:63–68, 2018  
- **DOI：** https://doi.org/10.1016/j.tvjl.2018.05.011  
- **样本：** **10** 只健康家犬；**同一项圈同时** PetPace、Actical、ActiGraph，**7 天**。  
- **结果：** PetPace vs Actical **r² = 0.59**；PetPace vs ActiGraph **r² = 0.85**；Actical vs ActiGraph **r² = 0.72**。Actical <50,000 counts/h 时 PetPace vs Actical **r² = 0.71**。  
- **局限：** 仅健康犬；相关 ≠ 疼痛检测。

### C5. PetPace — Rowlison de Ortiz, Belda, Hash, Enomoto, Robertson, Lascelles, 2022

- **标题：** Initial exploration of the discriminatory ability of the PetPace collar to detect differences in activity and physiological variables between healthy and osteoarthritic dogs  
- **期刊 / 年：** *Frontiers in Pain Research* 3:949877, 2022  
- **DOI：** https://doi.org/10.3389/fpain.2022.949877  
- **设计：** 观察性群体比较；PetPace + Actical 同戴 **14 天**。入组 22 健康 + 23 OA；1 只因项圈不适退出。分析约 **健康 n = 21，OA n = 23**。  
- **结果：**  
  - vs Actical：**R² = 0.56，p < 0.001**（未达作者预设 R² ≥ 0.70）。  
  - 平均每小时活动：健康 **293 ± 76** vs OA **228 ± 43**，**p = 0.005**；OA 低 **22.1%**。  
  - 白天零计数比例：健康 **45.2 ± 9.1%** vs OA **51.6 ± 7.5%，p = 0.029**（OA 白天多约 10% 的零读数）。  
  - OA 站立更少、高强度更少；部分 HRV 更低。  
- **局限：** 横断面；年龄/绝育有协变量效应；**不能诊断 OA**（重叠大）；HRV/体位算法未充分公开验证。

### C6. Whistle — Yashari, Duncan, Duerr, 2015

- **标题：** Evaluation of a novel canine activity monitor for at-home physical activity analysis  
- **期刊 / 年：** *BMC Veterinary Research* 11:146, 2015  
- **DOI：** https://doi.org/10.1186/s12917-015-0457-y  
- **样本：** **11** 只大型家犬；Whistle + Actical 同项圈 **24 h**。  
- **结果：** 3740 个时间点；强度 **Pearson r = 0.81**；总活动 **r = 0.925**（均 p < 0.0001）。  
- **局限：** 1 天；健康/方便样本；非疼痛试验。

### C7. Whistle — Chambers, Yoder, Carson 等（Kinship/Mars）, 2021

- **标题：** Deep Learning Classification of Canine Behavior Using a Single Collar-Mounted Accelerometer: Real-World Validation  
- **期刊 / 年：** *Animals* 11:1549, 2021  
- **DOI：** https://doi.org/10.3390/ani11061549  
- **样本：** 训练库 >**2500** 犬、>5000 段视频；生产数据 >1100 万设备日；用户调查 10,550 犬、163,110 条进食/饮水事件。  
- **设备：** Whistle FIT / Whistle 3 / Whistle GO，项圈。  
- **结果：** 饮水灵敏度/特异度 **0.949 / 0.999**；进食 **0.988 / 0.983**；抓挠等也有报告。作者称可作 OA 等疾病的**行为指标**，但本文验证的是**行为分类**，不是疾病诊断。  
- **局限：** 厂家论文；进食/饮水 ≠ 诊断 OA/CCD。

### C8. FitBark — Colpoys & DeCock, 2021

- **标题：** Evaluation of the FitBark Activity Monitor for Measuring Physical Activity in Dogs  
- **期刊 / 年：** *Animals* 11:781, 2021  
- **DOI：** https://doi.org/10.3390/ani11030781  
- **样本：** **n = 26**，项圈 FitBark，30 分钟三阶段（自由探索、人犬互动、牵引走），视频计步。  
- **结果：** 总体 vs 步数 **r = 0.65**；阶段 1 **r = 0.795**；阶段 2 **r = 0.758**；牵引走 **r = 0.498**。作者：脱牵引活动有效，牵引走需再研究。

### C9. FitBark vs Actical — 2024 预试验（AJVR）

- **标题：** Commercially available wearable health monitors in dogs only had a very strong correlation during longer durations of time: a pilot study  
- **期刊 / 年：** *Am J Vet Res* 85(10), 2024  
- **DOI：** https://doi.org/10.2460/ajvr.24.06.0162  
- **样本：** 入组 20，完整分析约 **15**；FitBark 2 vs Actical，1 周。  
- **结果：** **整周 r = 0.9**（95% CI 0.71–0.97），**r² = 0.85**；1 英里步行日仅 **r = 0.59**；23:00–24:00 **r = 0.78，r² = 0.89**。短窗相关变弱。  
- **局限：** 预试验；相关随时间尺度变。

### C10. 项圈行为分类（非 Whistle/PetPace 商品名，但同类）

**den Uijl 等, 2017**，*PLoS ONE* 12(11):e0188481，https://doi.org/10.1371/journal.pone.0188481  
设备：**PetDialog+ powered by Oggii（Zoetis）**，项圈三轴。**51** 只健康犬。走/小跑/快跑/吃/喝/摇头正确分类 **>95%**；睡眠与静止 **>90%**；PPV 93–100%；静止 NPV 86%（陌生 kennel）。这是行为状态验证，**不是疼痛/CCD 诊断**。

---

# 三、判断：能否支持“个体基线偏移报警”，能否“诊断某病”

## 1. 个体自身基线偏移报警

**现有证据只能提供间接、群体级的机制支持，不能作为已验证的临床报警系统。**

支持“值得做个体基线”的出处：

- 同一只 OA 犬，meloxicam vs 安慰剂，FLM 在 **23:00–06:00** 夜间活动下降（Gruen 2019，交叉设计，n = 15）。这是**个体内治疗对比**，说明夜间活动对镇痛有响应，但用的是组水平曲线，不是每只犬的报警阈值。
- 周末 vs 工作日夜间活动显著不同（Gruen 2019；Woods 2020 也强调作息）。说明必须用**该犬自己的同时段基线**，不能用群体均值。
- Actical 零计数识别休息/睡眠灵敏度 94%、特异度 96%（2025，n = 10），说明“夜间静息时长”可测，但仍是行为状态，不是疾病。
- OA 组夜间休息比例低于对照（Smith 2022，系数 0.976，效应小）。
- 高龄犬周末约 5 点更活跃（Mondino 2023 活动论文），与主人报告的 02:00–05:00 不安（Taylor 2026）方向一致。

**不能声称已验证的原因（均有出处或明确缺口）：**

- Knazovicky 2015 用小时均值时，**夜间加速度计对 NSAID 无显著变化**；同一数据换 FLM 才出现差异。报警算法若用粗糙均值会漏检。
- **没有**检索到：预注册的、以“相对个体基线的偏移”为指数、报告灵敏度/特异度/阳性预测值、并经兽医金标准确认的前瞻报警试验。
- 作息、周末、共病、项圈松紧、设备品牌（FitBark 短窗相关弱）都会驱动偏移。
- 效应量往往小（Smith 的休息比例约 2.4% 相对差；PetPace OA 全天活动低 22%，但分布重叠）。

**更准确的表述：** 证据支持把夜间活动当作**可重复的个体内结局**（尤其配合 FLM 或同时段对照），用于监测镇痛反应或老化趋势；**不支持**把“相对基线偏移”直接做成已验证的疾病报警产品。

## 2. 诊断某病（OA、CCD、疼痛）

**不能支持用加速度计/项圈单独诊断某病。**

| 主张 | 证据地位 |
|---|---|
| OA 犬群体白天活动更低、高强度更少 | 有（PetPace 2022：−22.1%；Brown 2010 治疗 +20%） |
| OA 犬夜间休息略少 | 有（Smith 2022），效应小，SNoRE 不同步 |
| NSAID 改善主人评定的夜间睡眠；FLM 显示夜间活动下降 | 有（Knazovicky SNoRE；Gruen FLM） |
| CCD 与睡眠结构/夜间不安相关 | 有（PSG、CADES、主人调查）；家中加速度计仅为相关（Mondino 2023 n = 27） |
| 项圈能分类走/跑/吃/睡等行为 | 有（Kumpulainen、den Uijl、Chambers） |
| 项圈输出 = OA 或 CCD 诊断 | **无**。无一篇给出诊断灵敏度/特异度达到临床诊断器标准 |
| bedinvetmab 改变夜间加速度计 | **未找到**；仅有 SNoRE/日活动 |

行为标签（嗅、走、卧）≠ 疾病标签。CCD 诊断依赖 DISHAA 多域（JAVMA CCDS Working Group 2026），睡眠只是一域。OA 诊断依赖骨科检查 + 影像。加速度计最多是**辅助监测**。

## 3. 证据缺口（只列检索后仍空缺的）

1. **个体基线报警的前瞻验证**：灵敏度、假阳性、最短基线天数、如何处理周末/旅行。  
2. **bedinvetmab/Librela 的夜间加速度计 RCT**（Enomoto 2026 自己写了这是未来工作）。  
3. **CCD 家中夜间加速度计 vs 临床金标准**的诊断试验（现有 n = 27 相关 + 下午 PSG）。  
4. **疼痛 vs CCD vs 瘙痒 vs 环境**的鉴别：夜间不安多种病共有（文献亦指出）。  
5. **跨设备阈值不可移植**（Actical counts ≠ FitBark BarkPoints ≠ PetPace；短窗相关下降）。  
6. **Tampere 数据集**是半控制、中大型、短任务，**不能**直接当家庭夜间健康模型的训练金标准。  
7. 厂家“疼痛评分”实时报警（如 PetPace 营销页）**不等于**已发表的诊断试验。

---

**检索范围：** Mendeley 官方页、CC 官方 deed/legalcode、Kaggle 两页、*Data in Brief* / *Appl Anim Behav Sci* 全文、PeerJ、*Sci Rep*、*Front Pain Res*、*Front Vet Sci*、PubMed/PMC、Bristol 仓储。Fairdata/Zenodo 无 Tampere 该库。bedinvetmab 夜间加速度计全文未找到。Kawecki-Wright 2025 仅为会议摘要，未当正式论文使用。
