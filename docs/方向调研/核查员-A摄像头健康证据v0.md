# 家用摄像头能否检出犬猫缓慢身体/健康变化：六类同行评审证据

**核心判断（有出处）：** 固定摄像头在实验室/犬舍/诊所条件下，已经能识别若干离散行为（进食、饮水、部分临床观察、睡眠姿势、急性疼痛面容），也能把无标记关节点跟踪到与标记软件相近的水平。把这些能力接到「家中单机、跨周/跨月、看出慢性疼痛或认知障碍」上，目前几乎没有对个体纵向、对照金标准的视频研究。

---

## 1. 视频/计算机视觉步态与跛行

### 1.1 无标记姿态：猫跑台 DeepLabCut

**Lecomte CG, Audet J, Harnie J, Frigon A.** A Validation of Supervised Deep Learning for Gait Analysis in the Cat. *Frontiers in Neuroinformatics* 2021. DOI: [10.3389/fninf.2021.712623](https://doi.org/10.3389/fninf.2021.712623). PMC8417424.

- **样本：** 4 只成年猫；2500 个步态周期 / 177 次试验。
- **拍摄：** 实验室分带跑台；双侧 Basler 相机 60 fps、640×480；皮肤上有反光标记（对照软件 Expresso 用标记，DLC 可无标记）。
- **方法：** DLC 2.1 vs Expresso；ICC / Lin CCC / Pearson。
- **原文数字：** 步长 ICC 0.997；髋–趾接触距离 ICC 0.987；离地距离 ICC 0.998；跨步长 CCC 1.000。膝接触 ICC 0.870、离地 0.891；踝接触 0.919；MTP 离地 0.879。12 项中 9 项协议「优秀」（>0.9）。
- **局限：** n=4；跑台、剃毛、侧视 2D；对照是标记软件，不是测力台或兽医跛行分级。

### 1.2 SuperAnimal-Quadruped（含犬）

**Ye S, Filippova A, Lauer J, Schneider S, Vidal M, Qiu T, Mathis A, Mathis MW.** SuperAnimal pretrained pose estimation models for behavioral analysis. *Nature Communications* 2024. DOI: [10.1038/s41467-024-48792-2](https://doi.org/10.1038/s41467-024-48792-2). PMC11192880.

- **样本：** Quadruped-80K（>45 种，含犬）；OOD 基准 AnimalPose / AP-10K / Horse-10 等。
- **拍摄：** 实验室 + 野外图像，非家用 CCTV。
- **方法：** 泛化姿态预训练；零样本 / 微调。
- **原文数字：** SA-Q HRNet-w32 在 AnimalPose 零样本 mAP **84.639**、RMSE 4.884（相对 AP-10K 预训练 79.447 / 5.774）。AP-10K 零样本 mAP 68.038。
- **局限：** 关键点定位基准，**未做跛行分类**，未对测力台。

### 1.3 诊所智能手机 ViTPose（犬关节点）

**Pahk 等.** A deep learning–based markerless gait analysis model for dogs… *American Journal of Veterinary Research* 2026. DOI: [10.2460/ajvr.25.09.0337](https://doi.org/10.2460/ajvr.25.09.0337). PMID 41490686。全文付费，数字取自摘要。

- **样本：** 408 只客户犬、>30 品种；训练 374 只约 20,000 张无标记图；验证/测试 34 只（兽医贴标记作 2D 真值）。
- **拍摄：** 诊所 3.3 m 直线走道；**单侧智能手机** 1080p / 30 fps。
- **方法：** ViTPose-L 从头训练；对照 2D 标记。
- **原文数字：** mAP **96.6%**；mean NKE **2.29**；PCK@0.05 **92.62%**。
- **局限：** 作者写「early-stage」；**关节点定位，不是跛行诊断**；走道侧视，非家中自由活动。

### 1.4 实验室多品种 DLC 步态参数（Gill 2025，全文已核）

**Gill H, Charles J, Grant R, Gardiner J, Bates K, Brassey C.** Gait tracking in dogs using DeepLabCut… *Applied Animal Behaviour Science* 2025;292:106769. DOI: [10.1016/j.applanim.2025.106769](https://doi.org/10.1016/j.applanim.2025.106769). 作者稿 PDF。

- **样本：** 8 品种（训练含 Collie、Spaniel、GSD、Labrador、Dachshund、French Bulldog、WHWT；**Deerhound 留作未见品种**）；2100 训练帧；224 次通过、32 个体、33238 观测。
- **拍摄：** 实验室走道；侧视固定相机约 1.8 m、1920×1080。
- **方法：** 定制 DLC；p-cutoff 0.6；半自动提取 duty factor、关节 ROM。
- **原文数字：** 训练误差 **2.84 px**（帧最大距离的 0.13%），测试 **12.22 px**（0.55%）。品种间 MedAED **0.14–0.24**。部位主效应 p=0.003，品种主效应 p=0.828。Labrador 前肢 duty factor **0.586±0.039**（文献 Labrador 0.60±0.03；混种 0.57±0.05）；stifle ROM **46.3°±5.5°**（混种文献 46.8°±2.2°）。肘角自动识别 257/273（94%），人工筛后 196（76%）。未见品种 Deerhound 无法自动提参数。
- **局限：** 髋/肩跟踪弱；**未训练跛行**；对照是文献值，不是同期测力台。

### 1.5 RGB-D + 动作捕捉（实验室）

**Kearney S, Li W, Parsons M, Kim KI, Cosker D.** RGBD-Dog: Predicting Canine Pose from RGBD Sensors. CVPR 2020 / arXiv:2004.07788.

- **样本：** 训练 5 犬 + 测试 2 犬；合成约 65–83 万帧（文中 830,000 synthetic）。
- **拍摄：** 实验室 Kinect v2 + Vicon 标记 mocap。
- **方法：** stacked hourglass；PA-MPJPE / PA-PCK 3D。
- **原文数字：** Table 1 中 PA-PCK 3D 多数序列约 **0.66–1.00**；PA-MPJPE 多在 **0.3–1.0**（单位似为归一化，**毫米换算待核**）。2D MPJPE 约 6–30（像素量级）。
- **局限：** 深度相机 + mocap 房；n 极小；非家用 RGB。

### 1.6 2D 视频 Kinovea vs 3D mocap

**Winkler EV, Lauer SK, Steigmeier-Raith SI, Zablotski Y, Mille MA.** Accuracy of Kinovea-based kinematic gait analysis… *AJVR* 2024. DOI: [10.2460/ajvr.24.05.0128](https://doi.org/10.2460/ajvr.24.05.0128).

- **样本：** 34 只健康犬（体重 ≥20 kg，肩高 >50 cm）。
- **拍摄：** 跑台；2D 视频（文中为智能手机/视频）+ 同步 VICON 3D 标记。
- **原文数字：** 肩、肘全程增量角差 **<2°**；腕/髋/膝/跗在 10 个步态增量中角差 <2° 的分别是 **9 / 5 / 4 / 4**。续篇 DOI 10.2460/ajvr.24.10.0290：推荐 **90° 侧视**。
- **局限：** 健康犬、跑台、**人工数字化标记**，不是自动 CV 跛行器。

### 1.7 测力/压力走道（金标准，非家用摄像头）

**Nielsen MBM 等.** Kinetic gait analysis in healthy dogs and dogs with osteoarthritis… *PLoS ONE* 2020. DOI: [10.1371/journal.pone.0243819](https://doi.org/10.1371/journal.pone.0243819). PMC7737891.

- **样本：** 健康 41、OA 21。
- **拍摄：** 诊所压力走道（Tekscan），无家用摄像头。
- **原文：** 重复测量精度可接受；OA 与健康的 **重叠（overlap）不足以作诊断**。
- **用途：** 说明即使用金标准 GRF，单次过道仍难把 OA 与健康分开。

### 1.8 跛行检测所需最少步数（高速相机 + 人工）

**Marrero I, Santana A, Vilar JM, Phillips CJC.** Determining Minimum Trial Numbers… *Animals* 2026. DOI: [10.3390/ani16040624](https://doi.org/10.3390/ani16040624). PMC12937312.

- **样本：** 6 犬，诱发轻度前肢跛行。
- **拍摄：** 高速相机 120 fps，距跑道 140 cm 垂直；Kinovea 提 2D。
- **原文：** 所需有效步数 **高度参数依赖**，不是一个万能数字。
- **局限：** 人工标记，非自动 CV。

### 1.9 猫髋 OA：透视而非 RGB

**Guillot M 等.** Coxofemoral joint kinematics using video fluoroscopic images… *JFMS* 2015;17:134–143. DOI: [10.1177/1098612X14537261](https://doi.org/10.1177/1098612X14537261).

- **样本：** 非 OA 2 + 髋 OA 4。
- **拍摄：** 跑台 0.4 m/s；C 臂透视 120 fps。
- **原文：** OA 猫步幅/周期变异更大；3/4 OA 猫髋角左右不对称（2 只 95%CI 不重叠）；角测量绝对变异 **2°–6°**。
- **局限：** X 线透视，**不能外推家用摄像头**。

### 1.10 被综述引用、但是 IMU 的「96%/82%」

**Palez N, Straß L, Meller S, Volk H, Zamansky A, Klein I.** Canine gait analysis using inertial sensors… *Scientific Reports* 2026. DOI: [10.1038/s41598-026-40717-x](https://doi.org/10.1038/s41598-026-40717-x). PMC13133112.

- **样本：** 29 犬（健康 17、骨科 6、神经 6）；部分有 MRI / 压力走道作临床标签。
- **传感器：** **可穿戴 IMU**，不是视频。
- **原文：** 多类（健康/骨科/神经）准确率 **0.96**；泛化到未见犬时二分类 **0.85**、多类约 **0.82**（摘要 0.96 多类 / 0.85 二分类）。
- **Phelan 综述 Table 8 把 Palez 写成 vision-based：** 与原文不符，应以 IMU 论文为准。

**Liu 跛行 2D precision >0.95：** 仅见 Phelan 综述 Table 8 二次引用，**原文未核到，待核**。

**OpenPose 用于犬步态：** Europe PMC 标题检索 `TITLE:"OpenPose" AND (dog OR canine) AND (gait OR pose)` **hit=0**。

### 1.11 综述对「临床可用」的门槛

**Phelan B, Mc Nally T, Cuddy L, Lacey G.** Automatic gait analysis in canines using computer vision. *Frontiers in Veterinary Science* 2026. DOI: [10.3389/fvets.2026.1729697](https://doi.org/10.3389/fvets.2026.1729697). PMC13185694.

- 单目 3D 要进入可解释运动学，关节中心误差需约 **10–20 mm**（皮肤伪影量级）；现有管线很少用 mocap/压力/透视做生物力学验证。
- 引用 Gill MedAED 0.14–0.24；Feuser 马：前肢 SE 100%、后肢 88.9%（**马，不是犬猫家用**）。

---

## 2. 视频评估疼痛表情

### 2.1 Feline Grimace Scale 建立（笼内视频截图）

**Evangelista MC, Watanabe R, Leung VSY, Monteiro BP, O’Toole E, Pang DSJ, Steagall PV.** Facial expressions of pain in cats… *Scientific Reports* 2019. DOI: [10.1038/s41598-019-55693-8](https://doi.org/10.1038/s41598-019-55693-8). PMC6911058.

- **样本：** 客户猫 35 + 对照 20；110 张图像。
- **拍摄：** 诊所笼内、**未打扰视频**后截图。
- **原文：** vs rCMPS-F Spearman **ρ=0.86**（p<0.001）；FGS 总分 ICC_single **0.89**（0.85–0.92）；截断 >0.39：灵敏度 **90.7%**、特异度 **86.6%**、AUC **0.94**（0.89–0.98）。
- **局限：** 急性痛；人工评分；笼内近距离脸。

### 2.2 FGS 实时 vs 图像；主人/护理者可靠性

**Evangelista 等.** Clinical applicability of the FGS… *PeerJ* 2020. DOI: [10.7717/peerj.8967](https://doi.org/10.7717/peerj.8967). PMC7164424. n=65 母猫 OVH；实时略高于图像，临床差异小。

**Evangelista 等.** Agreement and reliability… *Sci Rep* 2021. DOI: [10.1038/s41598-021-84696-7](https://doi.org/10.1038/s41598-021-84696-7). PMC7933168. 每组 5 人评 100 图；总分 ICC 主人 0.80、学生 0.88；胡须/口吻较差。

**Monteiro BP, Lee NHY, Steagall PV.** Can cat caregivers reliably assess… *JFMS* 2023. DOI: [10.1177/1098612X221145499](https://doi.org/10.1177/1098612X221145499). PMC10812049. 护理者 n=1540（ICC 分析问卷 1262）+ 兽医 8，10 张图；护理者总分 ICC **0.65**（Good），兽医 **0.85**。

### 2.3 几何形态测量（OHE 图像）

**Finka LR 等.** Geometric morphometrics… *Sci Rep* 2019. DOI: [10.1038/s41598-019-46330-5](https://doi.org/10.1038/s41598-019-46330-5). PMC6614427. n=29 短毛猫 OHE 四时点；PC 与 UNESP-Botucatu 量表相关。分类准确率本文未作为主终点报告。

### 2.4 自动化猫痛脸（图像）

**Feighelstein M 等.** Automated recognition of pain in cats. *Sci Rep* 2022. DOI: [10.1038/s41598-022-13348-1](https://doi.org/10.1038/s41598-022-13348-1). PMC9187730.

- n=29 OHE；**个体外**交叉验证。
- ResNet50 准确率 **0.7239±0.1837**（文称 >72%）；landmark 路径同类。

**Feighelstein M 等.** Explainable automated pain recognition in cats. *Sci Rep* 2023. DOI: [10.1038/s41598-023-35846-6](https://doi.org/10.1038/s41598-023-35846-6). PMC10238514.

- n=**84** 客户猫（TiHo 多品种诊所）。
- landmark **>77%**，深度学习 **>65%**（个体外）。

**Steagall PV, Monteiro BP, Marangoni S, Moussa M, Sautié M.** Fully automated deep learning models… FGS. *Sci Rep* 2023. DOI: [10.1038/s41598-023-49031-2](https://doi.org/10.1038/s41598-023-49031-2). PMC10703818.

- 3447 张脸图、37 点；ShuffleNetV2 NRMSE **16.76%**；XGBoost 准确率 **95.5%**、MSE **0.0096**、AUROC **0.97**。
- **智能手机静帧**，面向 App，不是家用 CCTV 连续视频。

### 2.5 视频级猫痛识别

**Martvel G 等.** Automated video-based pain recognition in cats using facial landmarks. *Sci Rep* 2024. DOI: [10.1038/s41598-024-78406-2](https://doi.org/10.1038/s41598-024-78406-2). PMC11564822.

- 数据集：Finka OHE 视频 + TiHo 诊所视频。
- **6 FPS：** Finka 准确率 **0.70**、F1 **0.73**；TiHo **0.66**。跨数据集约 **0.53 / 0.63**。
- **局限：** 跨采集条件掉点；急性手术/诊所痛。

### 2.6 犬痛视频（预印本，同行评审状态待核）

**Zhu H, Salgırlı Y, Can P, Atılgan D, Salah AA.** Video-based estimation of pain indicators in dogs. arXiv:2209.13296 (2022).

- 61 段兽医标注视频，>6 h；8 帧 clip，双流关键点+RGB。
- C-LSTM+LSTM128：平均 F1 **76.3%±4.4**，准确率 **77.0%±4.6**。
- **局限：** 预印本；诊所/手术场景；n 视频级。

### 2.7 家中主人识别急性痛（问卷，非算法）

**Gardeweg S 等.** Acute pain sign recognition by dog owners in a home setting. *PLOS One* 2026. DOI: [10.1371/journal.pone.0345418](https://doi.org/10.1371/journal.pone.0345418). PMC13082587. 问卷 n=103（出院日 n=61）；行为变化自报，**无 CV 模型**。

### 2.8 诊所 vs 家中疼痛量表（环境效应）

**Rega V 等.** Comparison of feline Glasgow CMPS-f at home and in hospital. *JFMS* 2025. DOI: [10.1177/1098612X251385847](https://doi.org/10.1177/1098612X251385847). PMC12618839.

- 健康无痛猫；家中 → 到院 → 体检。
- 到 C2 时 CMPS-f 升幅约 **5.8 / 4.1**；**11/17** 达到干预阈值 ≥5/20。
- **含义：** 环境应激会把「无痛」打成「像痛」；家用视频若在诊所训练，外推家中会偏。

**Marangoni S, Steagall PV.** Video-based compilation of acute pain behaviours in cats. *JFMS* 2024. DOI: [10.1177/1098612X241260712](https://doi.org/10.1177/1098612X241260712). PMC11418623. 60 h 视频库做教学 ethogram，24 个行为，**无分类器指标**。

---

## 3. 认知障碍、夜间不安、踱步、睡眠（含红外）

### 3.1 红外 CCTV 自动睡眠（犬舍，最接近「夜视摄像头」）

**Schork I, Zamansky A, Farhat N, de Azevedo CS, Young RJ.** Automated Observations of Dogs’ Resting Behaviour Patterns Using Artificial Intelligence… *Animals* 2024. DOI: [10.3390/ani14071109](https://doi.org/10.3390/ani14071109). PMC11011086. 系统名 **BlyzerDS**。

- **样本：** 13 只混种实验室/犬舍犬；训练用 13,668–13,688 段视频；测试 6000 帧；15 天中 3 天因天气相机移位剔除。
- **拍摄：** 犬舍固定 **Swann SWDVK-845504 CCTV**，1280×720，**红外夜视自动切换**。
- **方法：** CNN 休息/睡眠 vs 人工 ethogram。
- **原文：** 与人工 **89% similarity**；时间百分比无显著差异；系统记录的总睡眠时间更长（p=0.019，时长转换后）。睡眠操作定义：休息姿势 + 闭眼。
- **局限：** 犬舍非家庭；暗角识别难；**不是 CCD 诊断**，是睡眠时长/碎片化。

### 3.2 家犬 PSG（实验室，有人在场）

**Baranyai L 等.** Family Dogs’ Sleep Macrostructure… *Animals* 2025. DOI: [10.3390/ani15213182](https://doi.org/10.3390/ani15213182). PMC12608857. 非侵入 PSG：主人在场时入睡更快、睡眠效率更高、深睡更多。**电极，不是摄像头算法**。

### 3.3 夜间不安 × OA：加速度计（视频只作日志）

**Knazovicky D, Tomas A, Motsinger-Reif A, Lascelles BDX.** Initial evaluation of nighttime restlessness… *PeerJ* 2015. DOI: [10.7717/peerj.772](https://doi.org/10.7717/peerj.772). PMC4340376.

- Part A n=60，Part B n=19，自然发生 OA。
- 项圈 Actical；主人 SNoRE 睡眠问卷。
- 夜间活动 NSAID 后 vs 基线 **无显著下降**（例：均值 4642 vs 5414，p=0.5976）；SNoRE 主观睡眠改善。
- **无非 OA 对照**；**无红外视频分类器**。

### 3.4 CCD 活动节律：加速度计

**Mondino A 等.** Activity patterns are associated with fractional lifespan, memory, and gait speed in aged dogs. *Sci Rep* 2023. DOI: [10.1038/s41598-023-29181-z](https://doi.org/10.1038/s41598-023-29181-z). PMC9929073.

- n=27 老年犬；**PAM 加速度计**，CADES 问卷。
- CADES 高分犬在工作日/周末 **凌晨 3–5 点更活跃**。
- **视频未做自动踱步检测**。

### 3.5 项圈 Actical「睡眠」vs 家中人工观察

**Straube-Koegler S 等.** Actical Accelerometers as a Clinical Tool… *Animals* 2025. DOI: [10.3390/ani15172571](https://doi.org/10.3390/ani15172571). PMC12427222.

- n=10 大型家养犬；家中项圈；人工逐分钟（闭眼规则呼吸=睡）。
- **0 cpm** 识别睡眠+休息：灵敏度 **94.0%**、特异度 **96.1%**、AUC **0.950**（2617 min）。
- 睡眠 vs 睁眼休息：特异度 **0.273**（分不开）。
- **金标准是人看视频/现场，分类器是加速度计。**

**检索结论：** 未找到「家用红外摄像头自动识别 CCD 踱步/夜间不安、并对照 DISHAA/CADES/PSG」的同行评审原文。

---

## 4. 呕吐、咳嗽、抓挠、舔舐、进食饮水

### 4.1 实验室天花板 CCTV（2 犬）

**Atif O, Lee J, Park D, Chung Y.** Behavior-Based Video Summarization… *Sensors* 2023. DOI: [10.3390/s23062892](https://doi.org/10.3390/s23062892). PMC10054391.

- **样本：** 2 只小型犬（8 岁什犬 + 另 1 只）。
- **拍摄：** 实验室房间 **天花板 Hikvision** 俯视。
- **方法：** YOLO 检索「狗单独在场」→ EfficientNetV2-LSTM。
- **原文：** 行为识别 F1 **0.955**。分行为 F1 例：Barking 0.970，Door biting 0.960，Grooming 0.995。
- **局限：** n=2；分离焦虑类行为（门咬/抓）为主；idle 易混。

### 4.2 毒理实验室固定摄像头管线（最完整的「视频临床观察」）

**Eberhardt E 等.** Appearance-based computer vision pipeline… *Frontiers in Toxicology* 2026. DOI: [10.3389/ftox.2026.1758963](https://doi.org/10.3389/ftox.2026.1758963). PMC12957207.

- **拍摄：** 实验室犬舍固定 **AXIS P3235/P3245** 正视，**日+夜视**；彩色/反光胸带做个体 ID。
- **原文数字：**
  - 检测 F1 **94.8%**（昼 96.1%，夜 **91.1%**）
  - 仅靠毛色 ID：**63.7%** top-1，不够用
  - 胸带 3-ID top-1 **80.3%**；跟踪 MOTA **85.1%**、IDF1 **93.0%**
  - 姿态 95.2%；吃/喝 top-1 **94.0%**、类准确率 92.7%
  - 11 类 ClinObs：top-1 **79.0%**，**类准确率 47.9%**（不平衡）
  - 分项：drink **93.2%**，none 90.8%，eating 87.3%，circling **86.6%**，convulsion **43.2%**，ataxia **40.4%**，head shaking 40.1%，limping 35.%（原文截断），**呕吐弱**
  - AI 活动量 vs Actiwatch **r=0.965**
- **局限：** GLP 犬舍、胸带、正视固定机位；**不是家庭客厅**。

配套人工视频观察可靠性：

**Eberhardt E 等.** Application of video surveillance in preclinical safety studies… *PLOS One* 2025. DOI: [10.1371/journal.pone.0326916](https://doi.org/10.1371/journal.pone.0326916). PMC12204552.

- 23 名观察者，70 段视频，13 类临床观察。
- 总体 Fleiss κ **0.70**（加评论 0.72）。
- **效度 ≥90%：** 流涎、攻击、转圈、**呕吐**、摇头、抽搐。
- 肢体僵硬/肌张力高、兴奋较差；「正常」更难。
- **人看固定摄像头**，证明这些行为**在视频上可见**；算法对呕吐仍弱。

### 4.3 家庭风格短视频「异常行为」（独处破坏/焦虑）

**Guo X 等.** TP-CanineNet… *Animals* 2026. DOI: [10.3390/ani16131997](https://doi.org/10.3390/ani16131997). PMC13360469.

- 抖音收集 642 段（异常 366 / 正常 276），约 89% <1 min；家中监控风格。
- AUC **85.19%**、AP **72.55%**、FAR 0.00%（9 帧窗）。
- **弱监督「异常」**（独处破坏/焦虑），**不是医疗诊断**。文中引用 Schork BlyzerDS 红外睡眠 89%。

### 4.4 加速度计行为分类（视频只做标注金标准）

**Chambers RD 等.** Deep Learning Classification of Canine Behavior Using a Single Collar-Mounted Accelerometer. *Animals* 2021. DOI: [10.3390/ani11061549](https://doi.org/10.3390/ani11061549). PMC8228965.

- 众包 5063 视频 / 2217 犬；吃喝子集 262 视频 / 149 犬。**分类器是项圈加速度计。**
- Table 6 灵敏度/特异度：DRINK 0.874/0.995，EAT 0.902/0.967，LICKSELF 0.772/0.990，SCRATCH 0.870/0.997，SHAKE 0.916/1.00。吃喝集：DRINK 0.949/0.999，EAT 0.988/0.983。
- **不能当成摄像头分类器性能。**

**Smit M 等.** 猫三轴加速度计. *Sensors* 2023. DOI: [10.3390/s23167165](https://doi.org/10.3390/s23167165). PMC10458840.

- n=12 猫，7 天；**红外 CCTV 连续**作行为金标准（24 类）；项圈/胸带 ActiGraph。
- RF/SOM 在 15 类时仍有准确率 ≥0.70；**3 类（active/inactive/maintenance）最高**。饮/滚/跑观察很少。
- 视频=标注，模型=加速度计。

**Redmond C / Smit 等.** 犬. *Sensors* 2024. DOI: [10.3390/s24185955](https://doi.org/10.3390/s24185955). PMC11435861.

- n=6 犬，约 36.7 h 视频标注；ActiGraph RF **9 类总体准确率 74%**（各行为 54–93%）。

### 4.5 收容所进食饮水：需要 fiducial 项圈

**BeRSTID.** *Sci Rep* 2022. DOI: [10.1038/s41598-022-22167-3](https://doi.org/10.1038/s41598-022-22167-3). PMC9584257. n=6 收容猫，2D fiducial 项圈。吃 κ=**0.86**，喝 κ=**0.91**。**有标记可穿戴，非纯外观。**

### 4.6 非接触心率（面部视频，实验室）

**Hu R 等.** Contactless heart rate from pet facial videos (iPPG). *Front Vet Sci* 2024. DOI: [10.3389/fvets.2024.1495109](https://doi.org/10.3389/fvets.2024.1495109). PMC11647959. 自然光下犬 MAE 约 3.xx BPM、猫 3.33 BPM（原文 2.94–3.33 因光照条件）；Bland–Altman 约 −5.2 至 7.7 BPM。近距离脸部视频，非全屋监控。

**咳嗽：** 本次检索未找到犬猫家用/诊所 RGB 视频自动咳嗽检测的同行评审原文。

---

## 5. 视频长期纵向追踪个体行为或活动变化

检索到的「纵向」多数是：问卷 CMI、加速度计、或**人看视频访视**，很少是算法自动跨月。

**Boone G 等.** Incorporating video telehealth… feline chronic mobility. *Front Vet Sci* 2025. DOI: [10.3389/fvets.2025.1510006](https://doi.org/10.3389/fvets.2025.1510006). PMC11997976.

- 护理者 N=106；干预 n=63（约 4 个月、每 3 周 1 次视频访视）vs 对照 n=43。
- **同步视频问诊 + 教育**，提高护理者对活动障碍的知识；**无 CV 自动量化步态/疼痛**。

**Walton MB 等.** LOAD 效度. *PLoS ONE* 2013. DOI: [10.1371/journal.pone.0058125](https://doi.org/10.1371/journal.pone.0058125). PMC3591443.

- n=222 OA 犬。LOAD 与测力台 SI-PVF Spearman **r_s=0.232**（弱）。说明主人问卷与力学金标准相关有限。

**未核到：** 家用固定单摄像头、同一只犬/猫、数周至数月、算法输出行为频率/活动量、并对照兽医评分或加速度计的 SCI 论文。韩语非 SCI 家用 CCTV 猫研究不纳入。

---

## 6. 视频 vs 加速度计（家中/笼中）

这里的典型设计是：**视频当金标准，加速度计当产品**。

| 研究 | 对象 | 视频角色 | 加速度计结果 |
|---|---|---|---|
| Hansen 2007 *AJVR* DOI 10.2460/ajvr.68.5.468 | 4 健康犬 | 计算机视频：距离、走速>20 cm/s、面积变化；4 天×7 h；439 个 15 min 窗 | 摘要：各佩戴位置与视频「可接受相关」；项圈腹侧最方便。Colpoys 2021 引用为 **r=0.89**（**Hansen 摘要未写 r，待核全文**） |
| Lascelles 2008 *Vet Anaesth Analg* DOI 10.1111/j.1467-2995.2007.00367.x | 3 研究猫 | 432 h 同步视频距离 | 计数 vs 距离 **r=0.82**；吃/梳/抓产生高计数、位移小 |
| Colpoys 等 2021 FitBark PMC7999242 | 26 犬 | 745 min 人工数步 | 总体 r=**0.65**；自由探索 0.795；互动 0.758；牵引走 0.498 |
| Smit 2023 猫 PMC10458840 | 12 猫，家/笼 7 天红外 CCTV | 24 类人工 | RF/SOM 行为分类 ≥0.70；3 类最高 |
| Smit 2024 犬 PMC11435861 | 6 犬 | 36.7 h 人工 | 9 类 74%（54–93%） |
| Eberhardt 2026 PMC12957207 | 实验室犬 | AI 视频活动 | vs Actiwatch **r=0.965** |
| Straube-Koegler 2025 睡眠 PMC12427222 | 10 家养犬 | 人工分钟观察 | 0 cpm Se 94.0 Sp 96.1；分不开睡 vs 睁眼休息 |
| Montout 2025 *Vet J* DOI 10.1016/j.tvjl.2025.106352 | 51 猫（24 健康/27 早期 DJD 主诉） | 无视频分类器 | 项圈 14 天 SVM **AUC 78%**（0.65–0.88），Se 68% @ Sp 75% |
| Whistle 瘙痒 PMC10445133 | 1042 家诊所回顾 | 无 | 可穿戴瘙痒警报 → 就诊/治疗；**视频未分类** |

**可支撑的比较句：** 加速度计与「视频测得的位移/步数」中等相关到强相关（猫 r=0.82；犬 FitBark 总体 0.65）。视频能看见吃/梳/抓，这些会让加速度计「看起来很忙」。实验室固定摄像头活动量可与 Actiwatch 达到 r=0.965（胸带 ID、正视机位）。

---

## 判断：摄像头撑得起什么、撑不起什么

### 撑得起（有原文数字）

1. **实验室/诊所侧视短距离走道上的关节点跟踪**  
   猫 DLC vs 标记软件 ICC 多在 0.87–1.00（Lecomte）。犬诊所手机 ViTPose mAP 96.6%（Pahk 摘要）。实验室 DLC 测试误差 12.22 px，Labrador duty factor 与文献重叠（Gill）。

2. **近距离、正面/笼内的急性痛脸（猫）**  
   人工 FGS：ρ=0.86、截断灵敏度 90.7%。自动静帧约 72–95%（视数据集与是否个体外）。视频级约 0.66–0.70，跨数据集下降。

3. **固定机位、白天、目标大且少遮挡时的若干行为**  
   吃/喝在毒理犬舍视频 top-1 94%；人工视频对呕吐/抽搐效度 ≥90%。2 犬实验室俯视 F1 0.955（分离焦虑类）。犬舍红外睡眠 vs 人工 89%。

4. **「视频当尺子、加速度计当表」**  
   视频位移与猫 Actical r=0.82；实验室视频活动 vs Actiwatch r=0.965。

5. **跨天对比「摄像头看得到的事件频率」——仅在标注可靠、机位不变时原则上可行。** 现有自动系统（Eberhardt、Atif、Blyzer）都是短周期方法学验证，**没有发表「同一只宠物家中 30 天频率变化 vs 临床转归」**。

### 撑不起（缺金标准对照或条件完全不同）

1. **诊断 OA / 髋发育不良 / 猫 DJD / CCD。** 压力走道本身 overlap 已不足诊断（Nielsen）。LOAD 与 PVF 仅 r_s=0.232。Palez 96% 是 **IMU**。Montout AUC 78% 是 **项圈加速度计**。无家用 RGB 视频诊断试验。

2. **「看出慢性疼痛」。** FGS/自动痛脸几乎全是 **急性手术或诊所痛**；Martvel 跨数据集掉到 ~0.5–0.6。CMPS-f 在医院应激下 11/17 无痛猫过干预线。慢性 OA 夜间不安的视频证据空缺（Knazovicky 是加速度计，且 NSAID 未降夜间活动）。

3. **单目家用摄像头做临床级运动学。** Phelan：需 ~10–20 mm 关节中心保真；Gill 髋/肩差；Kinovea 膝/髋/跗与 3D 差；RGBD-Dog 要深度相机。OpenPose 犬步态论文未找到。

4. **无辅助标记的多宠物家中身份保持。** Eberhardt：毛色 ID 63.7% 失败，必须胸带。BeRSTID 用 fiducial。

5. **咳嗽自动识别；家用红外 CCD 踱步检测。** 本次检索无原文。

---

## 家用固定单摄像头的证据缺口

| 缺口 | 现有证据停在 |
|---|---|
| 机位 | 侧视走道 / 跑台 / 笼正视 / 天花板俯视；客厅斜角、遮挡、多房间未验证 |
| 夜间 | 仅犬舍 Blyzer 89%；家中夜视+CCD 无 |
| 个体 ID | 实验室要胸带；家中多猫多犬无 |
| 时间尺度 | 秒–分钟 clip 或数天方法学；无数周算法纵向 |
| 对照 | 少与测力台/兽医 NRS/CBPI/FGS 慢性评分同步 |
| 品种/毛发 | Gill：未见巨型品种参数提取失败；长毛标记可见性差（Pahk 剔除 6 只） |
| 猫 OA 步态 | 透视 n=6；无 RGB 家用 |
| 外推 | 诊所痛脸 ≠ 家中慢性痛脸（CMPS 环境效应） |

---

## 接上「B：夜间健康」需要补的研究

按现有空白，最小可发表、可产品化的补强是：

1. **家中固定红外摄像头 vs 同步金标准（同一批夜）**  
   - 睡眠/休息：对照项圈 Actical 的 0 cpm 规则 **以及** 人工闭眼编码（Straube-Koegler 已证明 0 cpm 分不开睁眼休息）。  
   - 可选子集做 PSG（Baranyai 协议）。  
   终点：夜视条件下睡眠片段的 Se/Sp、κ，**按小时输出**。

2. **夜间踱步/不安 vs CCD 量表**  
   设计对齐 Mondino：CADES/DISHAA 高分组是否在 **3–5 AM** 视频位移/转圈次数更高。需要个体 re-ID、全夜连续、至少 7–14 夜。

3. **OA 夜间不安的视频终点**  
   重复 Knazovicky：NSAID 交叉，**视频夜醒次数/踱步** 与 SNoRE、CBPI 对照。现有加速度计夜间计数未随 NSAID 下降，视频终点是否更敏感是开放问题。

4. **无胸带的家中 re-ID**  
   Eberhardt 已定量：外观 63.7% 不够。需要单摄像头外观+时空的家中基准。

5. **吃/喝/吐/咳/抓/舔的夜视版本**  
   白天 ClinObs：吐在人工视频上效度高、算法弱。夜视+远距离+侧面会更差，必须单独测 Se/Sp。

6. **纵向最小可检测变化（MDC）**  
   同一机位连续 ≥4 周，报告行为频率的个体内 SD，才能谈「这周抓挠比上周多」。Phelan 已指出：误差若与 MDC 同量级，病理变化会被噪声淹没。

**在补齐 1–3 之前，产品表述宜限制为：**  
「在固定机位、目标可见时，可统计进食/饮水/休息时段，并与前几日同一机位比较」；  
「夜间睡眠时长与人工 ethogram 在犬舍红外下约 89% 相似（Schork 2024）」——外推家庭与 CCD 诊断均需新试验。

---

### 检索备注

- 全文 XML/PDF 已核：Lecomte、Ye/SuperAnimal、Gill 作者稿、Evangelista FGS 系列、Feighelstein、Steagall、Martvel、Atif、Eberhardt 两篇、Schork Blyzer、Smit 猫/犬、Chambers、Knazovicky、Mondino、Actical sleep、TP-CanineNet、Palez IMU、Phelan 综述、Nielsen 压力走道、LOAD、FitBark、telehealth 等。
- 仅摘要：Pahk ViTPose、Winkler Kinovea、Guillot 透视、Hansen 2007、Lascelles 2008、Montout 2025、Zhu arXiv。
- **待核：** Liu limp 原文与模态；Hansen 全文 r=0.89；RGBD-Dog MPJPE 物理单位；Pahk/Kinovea 全文细节；OpenPose 犬步态（标题检索 0）。
