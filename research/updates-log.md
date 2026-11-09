# research updates-log · 每周增量日志

> 倒序追加；执行字段与成功水位按[AUTOMATION](../AUTOMATION.md)。纠错记录与定时扫描分开，初始盘点不计完整扫描。

---

## 2026-11-09 · AIC 学术工程侧每周扫描第七次运行（定时任务）

- 运行：开始 **2026-11-09T10:04:03+0900**（date实测）；写入开始 **2026-11-09T10:20:32+0900**（.weekly-write.lock/owner.txt创建时刻，date＋stat实测；创建时曾误填估计值10:58，与实测冲突当场作废改实测）；Git提交时间戳 **提交后补笔回填**（本行占位，以提交后git log %cI实测为准，防时间戳冲突复发）。
- 采集窗口：**2026-10-31～2026-11-09 10:04**（自上轮完整成功扫描2026-11-02 10:11回溯2天）；成功水位：**不推进（部分完成）**——结转项Sounds of Play全文受SSRN注册墙阻塞（样本量/与17犬关系未取得），按"部分扫描不推进水位"，下轮窗口起点维持**2026-10-31**补扫。
- 轮换主题：**11月第二周「按钮、认知、反向训练与负面结果」**；上轮结转补查：Sounds of Play全文、Pawgaze分数表＋许可、InterPet4D论文定位、K9-Bench 907 vs 923口径、主任务连续监控/自动事件触发专项、合成数据大鼠USV择值。
- 必查项（逐项，禁止先写"全部完成"再列失败）：
  1. NatureLM repo＋权重卡（每周必查）— **完成** — HF API `models/EarthSpeciesProject/NatureLM-audio`＋`github.com/earthspecies/NatureLM-audio/commits/main.atom` — 备用入口：本轮atom主站通道直接可用（连续第6次）— 权重卡无变化（lastModified 2025-09-09、cc-by-nc-sa-4.0、下载650）；main窗口内（10-31起）无新提交（最新#20 v1.1.0系11-01，上轮已定性纯版本号跳变）
  2. 本期主任务：连续事件发现、误报／漏报评估、跨会话／家庭证据、简单基线对照 — **完成（检索覆盖真实，主结果为缺口确认＋1条负面结果）** — OpenAlex×13查询＋arXiv×5＋S2×2（429失败）＋WebSearch×5＋HF API×3 — 入库1条误报/泛化负面结果（Martvel Sci Rep）；**核心四问（连续自动触发/事件区间/注册负担/跨家庭）本轮专项检索仍未定位到覆盖研究**（S2两查询429属通道失败，已换OpenAlex/arXiv同类查询补齐，备用成功）
  3. 结转·Sounds of Play全文获取（样本量、标注、与17犬关系）— **访问失败** — SSRN原文页✅直读（`papers.ssrn.com/sol3/papers.cfm?abstract_id=7612027`，经WebFetch通道得26页/完整作者/摘要全文）；**PDF全文＝注册墙**（"Sign in to Access Cell Press Sneak Peek"；curl的Delivery.cfm与Data_Integrity_Notice均403）— 备用入口两通道均阻塞，按规则不注册绕过；样本量/与17犬关系仍未知
  4. 结转·Pawgaze结果表分数＋许可 — **完成** — [OpenReview PDF](https://openreview.net/attachment?id=6DxxI05WSk&name=pdf)＋HF API＋README — Table 2直读（Gemini-2.0-Flash总分61.07% vs GPT-4o 56.07%，五选一随机20%）；许可双查（cardData空＋README无声明）一致"未见许可声明"
  5. 结转·InterPet4D论文/出处定位 — **完成** — arXiv `abs/2607.10287`＋Google Scholar作者页＋HF README — **ECCV 2026正式发表（437–454）**确认；arXiv摘要直读6.8M帧/13犬/11品种/23人、InterPetMoGen FID 11.21
  6. 结转·K9-Bench 907 vs 923口径 — **完成** — arXiv HTML 2607.02680v1（§3.1＋附录表6/7） — 阶段口径闭合：总挖掘池1,737（＝1,129＋608）→923（498人工＋425 Gemini-2.0-flash代理）→8,263 QA→3模型多数投票去偏滤42.58%→4,744 QA/907视频——与R3阶段分列一致，无冲突
  7. 轮换·按钮线（一般引用）— **完成（无新增）** — OpenAlex `dog button soundboard AAC communication 2026` — 唯一命中Wayenberg框架（已收录）；窗口内无新按钮实验研究
  8. 轮换·认知／反向训练 — **完成（无相关新增）** — OpenAlex `dog reverse training cue control cognition`／`canine cognition inhibitory control transfer` — 命中均旧文献或不相关
  9. 轮换·负面结果 — **完成** — 由Martvel入库覆盖（本轮负面结果主命中）；OpenAlex `dog cognition negative result replication failure`无其他相关
  10. 结转·合成数据跨物种先例（大鼠USV）择值 — **完成（判断）** — 择值＝维持跨物种方法参照、**不升级入库**（非犬、独立真实测试集设计待核）；犬合成实证维持"本轮检索未定位到"
- 预算顺序自检：必查是否全部完成 **否**（10项中9完成、1项Sounds of Play全文受注册墙阻塞）；读原文方法节／表格的条目数 **2**（K9-Bench §3.1＋附录表6/7口径链；Pawgaze Table 2结果表）；深查 **4**/上限5（Martvel、Pawgaze、InterPet4D、Sounds of Play页面级；不凑满）
- 入库 **1**/上限6（只设上限，0–2条亦属正常，未凑数）＋存量行升级4处（Sounds of Play／Pawgaze／K9-Bench／InterPet4D）：
  1. [LVLM零样本犬情绪识别](https://doi.org/10.1038/s41598-025-25199-7)（Martvel等，Scientific Reports 2025-11-21，CC BY 4.0；窗口外补入——负面结果/改变判断条款）— 数字口径：DE网络图4类原始4,000/测试1,000；LRc受控实验（源29犬/248段视频）测试1,000张2类；GPT-4o DE约76.6%、**LRc无一模型>0.6（近随机）**、跨集ΔAcc−0.32～−0.55（McNemar p<0.001）、同数据监督DINO-ViT 89%（正文数字经OA原文页读取，表格未逐项复核）；独立犬数：LRc源29犬、DE未知 — 证据层级：**原文页级** — 为何对本仓库有价值：零样本LVLM犬情绪靠背景捷径、受控标签下去背景近随机的硬负面结果，直接收窄"现成VLM读犬状态"路线，为误报/泛化/标签可靠性问题提供实证
- 判断变化：①**"现成通用模型理解犬状态"负向证据链成形**——图像情绪（Martvel：去背景近随机＋背景捷径实证）、视频QA（K9-Bench约40%量级、Pawgaze 56–61%）三面合围，与"能力有限、尚未证明家庭应用可靠"一致且加强；同数据监督小模型89%说明缺口在零样本通用模型而非面部信息缺失；②InterPet4D升级为**ECCV 2026正式发表**＋摘要级规模（6.8M帧/13犬/11品种/23人、FID 11.21），资源地图该条可信度上升，任务仍限交互运动生成参照（运动生成成绩≠行为解释精度）；③K9-Bench 907/923**阶段口径闭合**（1,737＝1,129＋608），非冲突；④Pawgaze分数表落地，与K9-Bench任务/难度不同，**不作精度差比较**；⑤主任务核心四问缺口维持——按五档用词为"本轮检索未定位到（OpenAlex/arXiv/S2/HF/WebSearch，2025-06起过滤＋窗口内全查）"，不作"领域不存在"外推。
- 筛除／存疑：HF窗口内dog/canine条目全筛除（`BangorAI/dogfennau-llyw-cymru-1`＝威尔士语文档翻译、`PeetPedro/ultrawhale-dogfood`＝软件dogfood语义、`alessandro54/dogs-of-the-world-refined`＝品种图像分类、`ladyfareedah/cats-dogs-classification`＝教程级、doge/dogecoin＝加密行情噪声）；`wewewemoxom/Canine-Age-Transition-Vocalization-Dataset`（2026-10-27）与`SreethanSiddharth/Barkopedia-Dog-Vocal-Detection`（2026-10-20）第三方再上传（窗口外，沿例存疑不入库）；SMARTSENSE PET（CSIT 2025-09-20低层级会刊）仅线索不入库。
- 其他发现（自由填写）：①家庭犬行为连续监测方向存在旧工程文献——2022 Sensors《Multi-level Hierarchical Complex Behavior Monitoring System for Dog Psychological Separation Anxiety》与2023 Sensors《Behavior-Based Video Summarization System for Dog Health and Welfare Monitoring》（本轮仅元数据级命中、全文未读），或部分松动"家庭连续监控研究空白"表述，待精读后判断是否改变主任务缺口口径；②arXiv 2610.14232《Speech event detector》（2026-10-09）时间戳式非言语声音事件检测——人类语音侧方法参照，可借鉴事件区间输出形式；③通道观察：OpenAlex/S2/arXiv今日多轮429（并发即限流），串行＋退避后恢复；SSRN页面可经WebFetch读正文而PDF在注册墙后——**页面级与全文级须分开记**。
- 未入库但值得跟踪的线索：《Unsupervised Canine Emotion Recognition Using Momentum Contrast》（Sensors 2024-11-16）；SMARTSENSE PET；2022分离焦虑监测系统与2023视频摘要系统（见其他发现）；Sounds of Play PDF全文（换浏览器通道或等Cell Press期刊版）；Pawgaze与K9-Bench视频ID重合度。
- 深查证据层级自报：**4**/5；本轮新条目整体层级 **原文页级**（1条）＋存量升级混合（表格级／摘要级／原文页级）。
- 覆盖（逐条；采集段约2026-11-09 10:04–10:20 +09，逐条时刻无独立日志的标未知）：
  - HF API｜`models/EarthSpeciesProject/NatureLM-audio`、`datasets/pawgaze/pawgaze`＋README、`datasets/ohicarip/interpet4d`＋README、`datasets?search=dog／canine／pet behavior&sort=lastModified`（各返回上限12）｜2026-11-09｜发现（NatureLM复查、Pawgaze许可双查、InterPet4D作者列、HF窗口内0入库）
  - GitHub｜`earthspecies/NatureLM-audio/commits/main.atom`｜2026-11-09｜发现（窗口内无新提交）
  - arXiv｜`abs/2607.02680`＋`html/2607.02680v1`（§3.1＋附录表6/7）＋`abs/2607.10287`＋API `all:"InterPet4D"|"InterPetMoGen"`（0命中，与Scholar对照后经作者页定位）｜2026-11-09｜发现（K9口径闭合、InterPet4D摘要）；API曾429×3→退避后成功
  - OpenAlex｜主任务13查询（`dog activity recognition continuous home video`／`pet camera dog event detection`／`dog behavior monitoring household false positive`／`canine behavior recognition cross-subject generalization`／`dog activity recognition continuous video household`／`pet dog behavior detection false alarm wearable`／`dog vocalization event detection home`／`canine behavior cross-household generalization`（429）等）＋轮换5查询（按钮/认知/反向/负面/简单基线）｜2026-11-09｜发现（主任务窗口内无直接新研究＋2条旧工程文献线索；轮换按钮无新增、认知反向无相关）；429×4→串行退避重试
  - Semantic Scholar｜`pet dog event detection camera household`（命中均不相关）；`dog bark detection false positive deep learning`／`pet activity recognition smart home camera dog`／`InterPet4D…`等**429访问失败**→OpenAlex/arXiv/WebSearch备用补齐｜2026-11-09｜部分访问失败（备用成功）
  - WebSearch｜`dog activity recognition continuous video home monitoring automatic event detection 2026`（商业噪音为主）／`"Sounds of Play" …`／`Pawgaze … results`（命中OpenReview PDF）／`"InterPet4D" OR "InterPetMoGen" …`（命中arXivDaily＋Scholar作者页→ECCV 2026落定）／`"Investigating the capabilities…dog emotion recognition" Technion`（命中CRIS＋网易转述）｜2026-11-09｜发现
  - WebFetch｜SSRN `abstract_id=7612027`（页面✅）＋`Data_Integrity_Notice.cfm?abid=7612027`（**注册墙**）＋nature.com `s41598-025-25199-7`（OA全文页✅）＋NeurIPS `virtual/2025/131537`（Pawgaze摘要✅）＋Technion CRIS页（✅）｜2026-11-09｜发现
  - OpenReview｜v1 `notes/search?query=Pawgaze`（空）、api2（400）→经WebSearch命中`openreview.net/attachment?id=6DxxI05WSk` PDF直读｜2026-11-09｜备用成功
  - curl SSRN PDF｜`Delivery.cfm?abid=7612027`＋`Data_Integrity_Notice.cfm`｜2026-11-09｜**访问失败（403/Cloudflare＋注册墙）**
- 未完成与下轮承诺（2026-11-16）：①**Sounds of Play全文**（唯一欠账；SSRN注册墙——换浏览器通道或等Cell Press期刊版；样本量/与17犬关系仍未知）；②主任务核心四问续（连续自动触发/事件区间/注册负担/跨家庭维持重点；2022/2023家庭监测两篇择值精读）；③Salford维持低频观察（预设条款，不再每周挂账）；④Sci Data 17犬描述论文发表随查；⑤合成数据维持方法参照，出现犬实证即改判；⑥窗口起点维持**2026-10-31**补扫。

## 2026-11-02 · GPT 评审纠错落地（R3–R6／R9，非定时扫描）

- 性质：GPT 本期评审列 R3–R6 纠正；军师逐条**直读原文复核**（K9-Bench arXiv 2607.02680v1 §3.1–3.4 与结果表、Pawgaze NeurIPS 页作者对照、InterPet4D arXiv 2607.10287v1 §3.3／§6.1）后落地。历史周记不回改，被本节取代的口径不得继续引用。
- **R3 K9-Bench**：923＝问答筛选前视频数、907／4,744 为问答终集——**按处理阶段分列**，撤"并存待核"；§3.2 任务类别由犬行为专家（expert canine-trainer）参与设计，撤"纯 VLM 流水线"；MC 成绩（Gemini-2.5 Pro 平均约 40.1%、音视频 41.9%）与 GPT-4o 裁判主观分约 70 分**分列**，裁判分≠人工确认正确率；音视频 +1.8pp 不可外推家庭路线不可行；"勉强超随机、远未可用"改为"该论文所测任务和条件下能力有限，尚未证明家庭应用可靠"。
- **R4 Pawgaze**：与 K9-Bench **同团队**（Attarde、Bhutani 作者重合已对照确认）——归并为同团队线索，**不计两次独立验证**；撤"一个纯模型、一个有专家"对比；视频 ID 重合／子集／版本演进待核。
- **R5 InterPet4D**：原文已定位（arXiv 2607.10287v1 全文可读，"论文原文未定位"作废）；§3.3 **All dogs appear in both sets**（200 训练／40 验证 clip）——"per-dog 80:20"是**犬内片段切分、非犬个体隔离**，跨犬结论按此收窄；任务定位为交互运动生成／多模态数据参照。
- **R6 用词与检索范围**：VETTING 新增五档用词行（原文报告／本文未见／本轮未检索到／不适用／尚未验证）；"合成数据仍无犬实证""核心四问全部指向缺口"等全局断言收窄为"本轮检索未定位到＋范围"。
- **R9 水位复核**：11-02 研究轮自登记完整扫描并推进水位——军师复核：覆盖真实（主任务方向有进展、五资源入库属实），方法读取错误已由本轮纠正；**水位维持有效**，以本节更正后的口径为准；不以"10 项已处理"代替验收，11-09 轮按修正后覆盖与交付继续。


## 2026-11-02 · AIC 学术工程侧每周扫描第六次运行（定时任务）

- 运行：开始 **2026-11-02T10:11:31+0900**（date实测；执行环境时区UTC+9，等效+08口径09:11:31）；写入开始 **2026-11-02T10:16:19+0900**（.weekly-write.lock/owner.txt实测，+08口径09:16:19）；Git提交时间戳 **2026-11-02T10:21:03+0900**（1df6089，git log %cI实测；+08口径09:21:03）。
- 采集窗口：**2026-09-29～2026-11-02 10:11（+08/本地口径见上，补扫）**；成功水位：**本轮建立**（计划覆盖完成并收尾，理由见"未完成与下轮承诺"）。窗口起点说明：10-26扫描原登记"建立"后被GPT纠错**回调为未建立**（[纠错节](#2026-10-26--gpt-评审纠错落地非定时扫描)⑥），按AUTOMATION"部分扫描不推进水位"与[计划§2](../reports/2026-10-26-下一期调研方案计划.md)（"11-02增量窗口仍按AUTOMATION与周记有效水位计算"），窗口起点维持**2026-09-29**补扫；automation运行记忆所写"2026-10-24"系纠错前口径，以仓库有效水位为准。
- 轮换主题：**11月第一周「行为／声学及个体外泛化」**（正对本轮主任务的隔离/泛化问题）＋犬吠论文月查（LREC 10.63317增量、ICASSP引用）。上轮结转补查：按钮线月查＋主人确认设计专项（Salford细读）；Mescalina申请条件与许可；Sci Data发表即核——四项均按计划§2预设条款处理完毕（Salford留观察，见必查项与未完成节）。
- 必查项（逐项，禁止先写"全部完成"再列失败）：
  1. NatureLM repo＋权重卡（每周必查）— **完成** — HF API `models/EarthSpeciesProject/NatureLM-audio`＋`github.com/earthspecies/NatureLM-audio/commits/main.atom`＋commit.diff＋tags页 — 备用入口：GitHub REST releases API本轮429限流，改用commit.diff/tags成功 — 权重卡无变化（lastModified 2025-09-09、cc-by-nc-sa-4.0、下载348）；main窗口内两笔：#22（2026-10-29）依赖告警清理（自述lock-only）、**#20（2026-11-01）v1.1.0版本号跳变（diff仅pyproject/uv.lock，非模型/权重/许可变化）**
  2. 本期主任务：家庭视频、时序与多模态能力 — **完成** — 检索组合`dog behavior video recognition`／`canine multimodal behavior dataset`／`dog video temporal analysis cross-subject`＋HF/arXiv/OpenAlex/Scholar（**未只检索dog bark**）— 发现4条直接相关资源（3入库＋1存疑），核心四问（自动触发/事件区间/注册负担/跨会话家庭）均有针对性答案或缺口说明，详见判断变化
  3. 犬吠论文月查·LREC 10.63317/3fjpkdcjtvyx 引用增量 — **完成（无增量）** — OpenAlex `works/https://doi.org/10.63317/3fjpkdcjtvyx`＋`filter=cites:W7131856971` — 仍为2条（ICASSP 2025＋EmotionalCanines ACM MM 2025），与10-19一致
  4. 犬吠论文月查·ICASSP 2025（10.1109/icassp49660.2025.10889684）引用 — **完成** — OpenAlex `filter=cites:W4408355056` — cited_by_count=5、列表得4条（家禽综述Sensors 2025-06、BioSEN与Multi-Layer Attentive Probing两篇ICASSP 2026-04-21、奶牛跨场可靠性SSRN 2026-01）——均为生物声学方法参照，无犬猫家庭任务新增
  5. 按钮线月查 — **完成** — OpenAlex `soundboard dog button`（from 2026-06-01，per-page 10）— 2条命中：Wayenberg框架（已收录）＋《Why Anthropologists Should Study Dogs》（Evolutionary Anthropology 2026-10-14，背景评论，不入库）——窗口内无新按钮实验研究
  6. 主人确认设计专项（Salford论文细读）— **访问失败／未定位** — WebSearch（Salford PhD thesis owner annotations citizen science play）＋OpenAlex `Salford dog owner annotation play pant`（0命中）＋salford-repository.worktribe.com 此前403 — 备用入口EThOS/Scholar本轮换查仍未定位到该博士论文 — **按计划§2预设条款"仍无则继续留观察"执行，降为低频观察**；主人偏差研究方法参照改用CREMD等已可定位文献
  7. Sci Data描述论文发表即核 — **完成（仍未发表）** — OpenAlex `search=dog play pant`（per-page 8）— 前两位仍为Zenodo记录＋OSF项目，无Scientific Data条目；维持"托管页自述在审、OpenAlex未定位到发表条目"两分列
  8. Mescalina申请条件与许可 — **完成（公开渠道无条款）** — crossref `10.3233/JIFS-169509`（Mescalina原文＝Pérez-Espinosa等"Automatic individual dog recognition based on the acoustic properties of its barks"，JIFS）— 公开元数据无许可/申请条款；**未联系原作者**（未获授权），维持"可向作者申请"路径标注
  9. 月度轮换「行为／声学及个体外泛化」— **完成** — 由主任务视频基准的隔离设计核查（K9-Bench/Pawgaze均无犬ID→无个体隔离）＋ICASSP引用中的跨场/迁移方法文献（奶牛跨场可靠性、Attentive Probing）覆盖
  10. 晶晶追加重点余量快扫（①可采购意图数据②合成数据实证）— **完成（维持原结论）** — WebSearch `dog intent behavior labeled dataset purchase commercial license owner confirmation`（0相关命中，单查询口径）＋`synthetic dog bark vocalization data augmentation empirical evaluation`（0犬合成实证命中；命中大鼠超声合成训练数据JASA 2024，跨物种方法参照）— 可采购意图标注犬声/行为数据仍**未定位到**；合成数据仍无犬实证研究
- 预算顺序自检：必查是否全部完成 **是**（10项中9完成、1项按预设条款降为留观察）；读原文方法节／表格的条目数 **1**（K9-Bench arXiv HTML §3＋附录A/B＋结果表部分；Pawgaze/InterPet4D无方法节可读——前者workshop摘要级、后者论文未定位）；深查 **5**/上限5（K9-Bench、Pawgaze、InterPet4D、Sounds of Play、DogMo；不超）
- 入库 **5**/上限6（只设上限，宁缺毋滥；5条均为改变主任务资源地图或窗口内新证据，未凑数）：
  1. [K9-Bench](https://arxiv.org/abs/2607.02680)（arXiv 2026-07-02预印本，论文CC BY 4.0；数据HF CC BY-NC 4.0）— 数字口径：**923视频**（附录；摘要另写907待核）／**4,744条QA**（HF实际；摘要"约5,000"）／5类任务；独立犬数未知 — 证据层级：**方法节级** — 为何有价值：家庭视频理解首批公开基准，直接量化"MLLM能看懂多少犬行为视频"（约40%量级），负向结果本身改变"多模态已可用"的任何乐观假设
  2. [Pawgaze](https://neurips.cc/virtual/2025/131537)（NeurIPS 2025 Workshop投稿；HF无许可声明）— 数字口径：1,929收集→**923精选视频**／**7,120 MCQ**（HF卡一致）；独立犬数未知 — 证据层级：摘要＋数据卡级 — 为何有价值：第二个犬视频理解基准，专家参与QA设计（对比K9-Bench纯VLM流水线），workshop层级如实下调
  3. [InterPet4D](https://huggingface.co/datasets/ohicarip/interpet4d)（HF v1.1，2026-10-07，**窗口内**；CC BY-NC 4.0）— 数字口径：**113场次／13犬／约23人／227段ego片段**（HF卡）；媒体稿161场次/683万帧**口径不一致待核** — 证据层级：数据卡级（论文未定位）— 为何有价值：人宠交互4D多模态（音频＋SMPL-X/MANO/SMAL）首个公开规模资源，正对声画对齐与时序交互；13犬受控采集
  4. [The Sounds of Play](https://doi.org/10.2139/ssrn.7612027)（SSRN 2026-10-16登记，**窗口内**；posted-content待评审）— 数字口径：三类人犬游戏发声画像；**样本量/独立犬数未知**（全文未读）— 证据层级：元数据＋摘要级 — 为何有价值：ELTE系play pant线首个发声画像结果（喘气最常见），描述性旁证；与17犬数据集是否同一采集未知
  5. [DogMo](https://arxiv.org/abs/2510.24117)（arXiv 2025-10-28；窗口外补入）— 数字口径：**1.2k运动序列／10只犬**；四设定运动恢复基准 — 证据层级：摘要级 — 为何有价值：犬4D运动恢复多视角RGB-D资源，补上视频/运动地图一角（10犬规模小、无行为标签）
- 判断变化：①**"家庭视频／多模态基准稀缺"判断大幅改写**——已存在两个犬视频MLLM理解基准（K9-Bench／Pawgaze，各约900视频级）＋人宠交互4D数据集（InterPet4D）＋犬运动4D数据集（DogMo），视频侧资源地图由"几乎空白"变为"有基准、但全是YouTube或受控短采集、无家庭连续监控"；②**MLLM犬视频理解能力实测有限**（K9-Bench方法节级：MC约40%量级 vs 五选一随机20%）——"用现成多模态大模型直接理解家庭犬行为"路线短期不可行的硬证据；③**主任务核心四问全部指向缺口**：无一资源测过连续录像自动触发、依赖预先给定区间或QA切片、均无注册负担/跨会话/跨家庭隔离设计（K9-Bench/Pawgaze无犬ID）；④play pant线获得同团队描述性旁证（游戏喘气高频），"play pant"假说仍未获实验验证；⑤NatureLM无模型层变化（v1.1.0纯版本号），权重CC-BY-NC-SA-4.0边界不变。
- 筛除／存疑：①Kaggle"Real-World Dog Behavior Videos"（64段顶置单犬无标签，CC0）——单犬、无标注，对跨犬/家庭问题无判断价值，不入库；其中文镜像7zcode（张家梁/Bob 2026-09-23）为同一数据转传，按镜像筛除；②`hxu028/interpet4d-auto-label`（2026-10-29）第三方衍生再上传、无许可声明——沿Barkopedia再上传先例仅存疑；③UMich AI Lab新闻页提及Mihalcea系"犬吠玩乐/攻击性识别"工具（搜索摘要标6天前）——页面JS渲染未直读正文，疑为既有工作新闻覆盖，存疑不入库；④《Why Anthropologists Should Study Dogs》（2026-10-14）背景评论不入库。
- 其他发现（自由填写）：①**合成训练数据跨物种先例**：大鼠超声发声合成训练数据做监督分类（JASA 2024，Jack/Bilkey）——晶晶"合成数据实证"重点的最接近方法参照（非犬、非独立真实测试集设计待核），值得下轮判断是否升级跟踪；②K9-Bench的VLM视频过滤代理（Gemini-2.0-Flash与人工拒绝一致率84.3%）可借鉴为低标注成本数据筛选手段；③GitHub REST API连续第二轮限流（429/403），主站atom/commit.diff/raw通道依旧可用——依赖备用入口的模式已五轮稳定；④三个新基准/数据集的许可呈现呈三种状态（K9双源NC一致、Pawgaze无声明、InterPet4D卡内一致但无独立LICENSE），印证VETTING双源规则必要性。
- 未入库但值得跟踪的线索：BehaviorVLM（arXiv 2603.12176，VLM引导姿态+行为理解，量子点标注系实验动物，犬适用性未知）；《Learning When to Look》（arXiv 2603.07279，关键点-视频按需融合）；Pawgaze结果表分数与失败案例分析；InterPet4D论文/InterPetMoGen正式出处；Sounds of Play全文（样本量、与17犬数据集关系）；K9-Bench 907 vs 923 视频口径差。
- 深查证据层级自报：**5**/5；本轮新条目整体层级 **混合（1条方法节级、2条数据卡级、1条摘要＋数据卡级、1条摘要级）**。
- 覆盖（逐条；采集段约2026-11-02 10:11–10:18 +09，逐条时刻无独立日志的标未知）：
  - WebSearch｜`dog behavior video recognition dataset 2026`／`canine multimodal behavior dataset dog video audio`／`Pawgaze benchmark canine behavior NeurIPS 2025 arXiv`／`Salford PhD thesis dog owner annotations citizen science`／`synthetic dog bark vocalization data augmentation empirical evaluation`／`dog intent behavior labeled dataset purchase commercial license owner confirmation`｜2026-11-02｜发现（主任务4条＋Salford未定位＋合成/采购无犬命中）
  - arXiv｜`abs/2607.02680`＋`html/2607.02680v1`（§3、附录A/B、结果表）＋`abs/2510.24117`＋`abs/2603.12176`＋export API `all:InterPet4D`／`all:InterPetMoGen`（0命中）｜2026-11-02｜发现（K9方法节级、DogMo/BehaviorVLM摘要级、InterPet4D论文未定位）
  - Hugging Face API｜`models/EarthSpeciesProject/NatureLM-audio`、`datasets/K9Bench/K9Bench`＋README、`datasets/pawgaze/pawgaze`＋README、`datasets/ohicarip/interpet4d`＋README、`datasets/hxu028/interpet4d-auto-label`、`datasets?search=InterPet`｜2026-11-02｜发现（三数据卡＋NatureLM复查）
  - GitHub｜`earthspecies/NatureLM-audio/commits/main.atom`、`commit/a4c65ad.diff`、`tags`页、`releases`页｜2026-11-02｜发现（v1.1.0定性）；REST `releases` API **访问失败（429限流）**→commit.diff＋tags备用成功
  - OpenAlex｜LREC DOI引用（cites:W7131856971）／ICASSP引用（cites:W4408355056）／`search=dog play pant`（per-page 8）／`soundboard dog button`（from 2026-06-01）／`Salford dog owner annotation play pant`（0命中）｜2026-11-02｜发现（LREC无增量、ICASSP 4条引用、Sci Data仍无、按钮2条、Salford未定位）
  - crossref｜`10.2139/ssrn.7612027`（Sounds of Play元数据＋摘要，二次抓取空返回）／`10.3233/JIFS-169509`（Mescalina）｜2026-11-02｜发现
  - NeurIPS virtual｜`virtual/2025/131537`（Pawgaze，经搜索摘要呈现）｜2026-11-02｜发现（workshop投稿页）
  - UMich AI Lab news页｜`ai.engin.umich.edu/news/`｜2026-11-02｜**访问失败（JS渲染无正文）**→不以搜索摘要入库
- 失败项的备用入口与重试：Salford——repository 403（上轮）→本轮EThOS/Scholar/OpenAlex换入口仍未定位，按计划降为留观察；GitHub REST——429→atom/commit.diff/tags成功；crossref SSRN二次抓取空返回→已用首次摘要结果入库并标全文未读。
- 未完成与下轮承诺（2026-11-09）：①Sounds of Play全文获取（样本量、标注、与17犬数据集关系）——SSRN页或期刊后续；②Pawgaze结果表分数直读＋HF许可声明寻找；③InterPet4D论文/项目页定位（作者主页、CMU/Science Tokyo实验室）；④K9-Bench 907 vs 923口径核对（读附录表6/7）；⑤Salford维持低频观察（不再每周挂账，有新入口或直接使用需要时再试）；⑥合成数据跨物种先例（大鼠USV）判断是否升级；⑦主任务续：家庭连续监控/自动事件触发方向的专项检索（本轮四问缺口无人填补，下轮定向搜`dog activity recognition continuous video home`／`pet camera event detection`类）。

## 2026-10-26 · 补做材料校订与计划收拢（GPT/Codex，非扫描）

- 对象：PR #17 `0570222`、main `41c1299`中的资源结论；按用户要求本地修订，不建立成功水位。
- 论文任务纠正：2610.21011原文§3与表3–5输入已给吠声区间，可见／画外分类不得当连续吠声检出；注册式身份识别不得简写为零注册新犬能力。当前任务、指标、条件集中于[papers](papers.md)，旧修补轮“可复现”只表示作者给出材料线索，**本项目未运行或独立复现**。
- Mendeley v2：2026-10-26直读[网页Licence](https://data.mendeley.com/datasets/5g5hg9hrkv/2)及[版本DOI登记](https://api.datacite.org/dois/10.17632/5g5hg9hrkv.2)，均CC BY-NC-ND 4.0，声明展示补核结项。数据页写聚类算法分配情绪，具体算法／人工复核／个体ID未核；不作真值，不把ND直接解释为全面禁止训练。
- OSF：PR #17体裁纠正载入本地；DataCite创作者已独立复核，项目页许可双源一致据核查员报告，尚未取得的数据文件另核。
- Zenodo：多个登记入口不代表独立授权，不采“平台两源胜过README一源”的推断；冲突仍在。idiap的GPL家族与only／or-later的适用范围分列，GPL允许商用，具体分发义务另评估（[GNU官方FAQ](https://www.gnu.org/licenses/gpl-faq.en.html#DoesTheGPLAllowMoney)）。
- 时间纠正：git log确认36f908d提交为13:56:05+09:00；原记owner.txt的13:58晚于提交，不足以定位该次写入开始，改未知，不猜测原因或新时间。
- 后续：已结项项不重查；自动触发、注册负担、跨会话与跨家庭、简单基线／标签成为工程主任务。积压按[统一计划§2](../reports/2026-10-26-下一期调研方案计划.md)收拢。平台配置、扫描水位、Git远端状态均未改；未触发任务、下载数据、运行模型或联系作者。

---

## 2026-10-26 · 临时修补轮（手动触发，非定时）

- 运行：开始 2026-10-26 13:47（系统时间 Asia/Tokyo +09:00；+08 口径 12:47）；写入开始 **未知**（原记owner.txt的13:58晚于同一时区的提交13:56:05，无法作为该次写入开始；历史原值与原因在本节保留，未猜测替代时间）；Git提交时间戳：**2026-10-26T13:56:05+09:00**（36f908d，git log核对）。
- 采集窗口：不适用（修补轮非增量扫描）；成功水位：**不建立**。
- 轮换主题：无；任务＝修补余项＋主任务第一刀（主公 2026-10-26 裁示："三件事按建议处理，然后临时重跑一轮"）。
- 必查项（逐项）：
  1. Salford 论文定位 — **访问失败**（salford-repository.worktribe.com 403 Cloudflare）— 备用入口下轮换 EThOS／Scholar — 维持待核，不阻塞方向
  2. Zenodo 17 犬许可第三源 — **完成** — DataCite DOI 登记 rightsList＝CC BY 4.0，与 Zenodo API 一致（平台层双源）对 README CC BY-NC 4.0（作者层单源）；**冲突仍在**，重心偏平台层，继续按最保守 NC
  3. Zenodo 归档内 LICENSE 文件 — **完成** — 7 文件清单复核无 LICENSE 文件（README 为归档内唯一许可声明）
  4. OSF 98nhd creators 字段 — **完成** — DataCite 直读：Shelly Volsche、Veronika Keeton、Shea Cobb、Macie Dirickson、Sydney Schultz、**Alexandra Horowitz、Holly Root-Gutteridge**、Vanessa Grenier、Sky Sobol；resourceType＝Project 确认（团队归属由"待核"落定）
  5. 10-26 轮商业数字抽查 — **部分完成** — Kickstarter 原始页 403，HK$1,221,069 维持"扫描自报原始页直读"待独立复核
- 预算顺序自检：修补 5 项中 3 完成／1 访问失败／1 部分；读原文方法节 **1**（arXiv 2610.21011 全文方法节＋结果）；深查 3/上限5（Mendeley 数据卡＋DataCite、arXiv 全文、GitHub repo；不凑满）
- 入库 **2**/上限6（只设上限，0–2 亦属正常，未凑数）：
  1. [Audio-Visual Dog Identification and Tracking in Real-World Videos](https://arxiv.org/abs/2610.21011)（arXiv 2026-10-14 预印本，CC BY-NC-SA 4.0）— 数字口径：46 真实视频／**213 吠声事件**；定位 61.83%（IoU≥0.30）、可见/画外 F1 91.33%、多犬 top-1 73.3%、开放集已知犬 65.36%／EER 12.47%（5 条注册吠声）— 证据层级：**方法节级** — 为何有价值：真实多犬场景个体归因首个基准，开放集未见犬识别直对跨个体问题；能力边界如实偏低恰是"家庭应用尚远"的硬数据
  2. [犬情绪音视频数据集](https://doi.org/10.17632/5g5hg9hrkv)（Mendeley 2026-09-26，v2）— 数字口径：约 **127 条音视频**、4 情绪类、**独立犬数未知** — 证据层级：数据卡＋DataCite 级 — 为何有价值：真实场景音视频犬情绪少数候选；但规模小、无个体标注、许可单源待核
- 判断变化：①"家庭视频／多模态无基准"判断**松动**——存在真实多犬视频个体归因基准（46 视频级，能力有限但可测、可复现）；②音视频犬情绪真实数据存在但规模小（127 条）且许可紧（ND 待核）；③ACL2 组研究面由声音扩展至音视频追踪（Dog2vec／Barkopedia 同门，归并）。
- 筛除／存疑：Mendeley 描述"unlabelled recordings"与"emotions assigned"表述矛盾待核；Kickstarter 金额独立复核未果。
- 其他发现（自由填写）：①GitHub API 本轮 HTTP 000（网络层失败），raw 入口可用但无 LICENSE 文件——**第三处"无根 LICENSE"模式**（idiap、dog_av_id_tracking 同款），考虑在 VETTING 双源行补"无根 LICENSE 时查 LICENSES/ 目录"（待评估）；②下轮视频线候选：SuperAnimal 姿态模型（Nature Comm 2024，10.1038/s41467-024-48792-2）、SyDog-Video（IJCV 2023 合成视频时序姿态）、行为视频摘要（Sensors 2023）。
- 深查证据层级自报：3/5；本轮新条目整体层级 **混合（1 条方法节级、1 条数据卡级）**。
- 覆盖（逐条）：OpenAlex 4 查询｜`dog behavior video recognition`／`canine multimodal behavior dataset`／`dog video temporal behavior analysis`／`dog pose estimation behavior video`（filter from 2019，per-page 8）｜发现（19227/1551/12629/3655 命中，筛后 2 入库）；DataCite｜`dois/10.5281/zenodo.18972388`、`dois/10.17632/5g5hg9hrkv`、`dois/10.17605/osf.io/98nhd`｜发现（许可双源＋creators）；Mendeley API｜`datasets/5g5hg9hrkv`＋`/files`｜发现；arXiv｜`abs/2610.21011`＋`html/2610.21011v1`｜发现（方法节级）；GitHub API｜`repos/UTA-ACL2/dog_av_id_tracking`＋`contents/`｜**访问失败（HTTP 000）**→raw 备用入口成功但 `LICENSE` 404、README 无许可行→**许可待核**；Salford repository｜**访问失败（403）**；Kickstarter｜**访问失败（403）**
- 未完成与下轮承诺（2026-11-02）：Salford 原文定位（换 EThOS／Scholar 入口）；Kickstarter 金额独立复核；dog_av_id_tracking 许可（查 LICENSES/ 目录或 README 更新）；Mendeley 数据卡页面许可行第二源；SuperAnimal／SyDog-Video 候选读方法节；市场侧主任务（国内狗主真实事件）按计划 §3 执行。

---

## 2026-10-26 · GPT 评审纠错落地（非定时扫描）

- 性质：GPT（Codex）本期评审报告（[reports/2026-10-26-本期调研评审报告.md](../reports/2026-10-26-本期调研评审报告.md)）列五条纠正＋完成状态复核；军师对三条优先项**独立复核属实**（Zenodo API 双字段＋README 原文、DataCite 体裁、ElevenLabs 原文日期与措辞）后落地。历史周记不回改，被本节取代的口径不得继续引用。
- ① **Zenodo 许可冲突恢复"待核"**（纠 10-26 扫描"告破／NC 胜出"）：API 实测 `metadata.license.id=cc-by-4.0`（**根层 `license` 为 null**，扫描误读根层为空），README 原文 CC BY-NC 4.0，冲突仍在；不得认定可商用或不可商用，不得外推"受控采集犬声数据均无商用许可"。
- ② **Text to Bark 撤回**：ElevenLabs 官方文章发布于 **2025-04-01**（愚人节），含"2-Factor Pawthentication""cloud barkitecture"等玩笑措辞，无可核样本与测试——撤回"首个商用合成信号"与"95% 犬不可区分"，降为营销线索，不支持合成训练有效性。
- ③ **OSF 98nhd 体裁纠正**：项目记录、非预印本；53 场音视频、17 只犬拒绝参与、分析进行中；结果与数据取得待核；已补入 datasets.md（原周记记"入库 papers"但表内无行）。
- ④ Salford"98.1%"降级：无可定位出处（缺题名／作者／年份／链接／页码），移出确定性判断，待补原文方法。
- ⑤ "公开渠道无"收窄为"本轮检索未定位到"；OpenAlex 未见 Sci Data 条目≠证明仍在审，两者分列。
- ⑥ **成功水位回调**：10-26 研究扫描登记"本轮建立"，不符合 AUTOMATION"完成全部计划覆盖并收尾"之条件（关键结论出错、体裁误判、家庭视频／时序／多模态主任务覆盖不足）——**回调为未建立（部分完成）**，下轮窗口起点仍 2026-09-29。
- ⑦ 存量收窄：市场 10-19 判断变化①"资本背书使提价压力只增不减"收窄为"观察到伯克希尔追加投资事实，服务生命周期风险观察继续，不推定特定产品未来提价"。
- ⑧ idiap 许可纠错：实为 `LICENSES/GPL-3.0-only.txt`（10-22"无声明"系根目录无 LICENSE 致 API 字段为 null 之误）。

---

## 2026-10-26 · 学术工程侧每周扫描第五次运行（定时任务）

- 运行：开始 2026-10-26 10:06（任务触发后实测；系统时钟 11:06+09:00，等效 +08 口径）；写入开始 **2026-10-26 10:18:32（.weekly-write.lock/owner.txt mtime 实测）**——初记"10:32"为未实测估计值、与提交时间戳冲突，按规则作废改记实测；Git 提交时间戳：**2026-10-26T10:22:31+08:00（2793778，git log %cI 原值 11:22:31+09:00，同一时刻的执行环境时区偏移）**。
- 采集窗口：2026-09-29～2026-10-26 10:06（补扫；前四轮均部分完成、成功水位未建立）；成功水位：**本轮建立**（计划覆盖完成，理由见"未完成与下轮承诺"）。
- 轮换主题：10 月第四/五周「可取得数据／权重、相关硬件供给和法规」——本轮积压四项正对该主题（数据许可与可取得性）；硬件供给与法规按频率表"仅与当前具体任务直接相关时查"，本轮主任务为数据/模型边界，**未触发（非未覆盖）**。上轮结转补查：17 犬 Zenodo 条款细读（必做）、Sci Data 描述论文查证、ICASSP 全文顺延、《Bark and Howl 1D-CNN》择价值——**四项全部完成**。
- 必查项（逐项）：
  1. NatureLM repo＋权重卡 — **完成** — HF API `models/EarthSpeciesProject/NatureLM-audio` ＋ `github.com/earthspecies/NatureLM-audio/commits/main.atom` — 无需备用；权重卡无变化（lastModified 2025-09-09、cc-by-nc-sa-4.0、下载245）；**main 新提交 #21（2026-10-23T07:59Z）"Import docs site and add MkDocs tooling"——文档工具类，非模型行为或条款变化**
  2. （sources.md 降频后本周仅此一条每周必查；积压四项按"待补积压（2026-10-26 优先）"逐项执行如下）
- 积压四项（逐项）：
  1. 17 犬 Zenodo 许可冲突 — **完成（告破）** — Zenodo API `records/18972388`（记录级 license 字段实测为空）＋归档内 `06 Readme.txt`（7,021字节直读）— README 原文明写 **CC BY-NC 4.0**，与预印本 crossref 一致；冲突解决＝**NC 胜出，不可商用**
  2. idiap/ssl-human-animal 可用性 — **完成** — GitHub 主站页面＋raw＋LICENSES 目录＋commits atom — 根目录无 LICENSE 文件（raw 404 属事实记录非通道失败），实际为 `LICENSES/GPL-3.0-only.txt`（SPDX 风格）；README badge GPLv3 属实；最新提交 2026-02-03（99ae454，加演示材料）
  3. 17 犬 Sci Data 描述论文 — **完成（维持"在审"）** — OpenAlex `works?title.search:dog play pant`（per-page 5）— 仅 2 命中（Zenodo 记录本身＋OSF 预印本），无 Scientific Data 条目
  4. ICASSP 2025 全文与作者代码 — **完成（超预期）** — arXiv 2501.05987 HTML 全文直读（§II＋表I–III）＋ idiap repo README — 方法节级证据到手
- 预算顺序自检：必查是否全部完成 **是**（每周必查 1/1＋积压 4/4＋晶晶追加重点 4/4）；读原文方法节／表格的条目数 **1**（ICASSP arXiv 全文方法节＋表I/II/III；另 17 犬 Zenodo README 原文全文直读属数据卡级）；深查 **4**/上限5（ICASSP 全文、17犬 Zenodo 数据卡＋README、idiap repo、OSF 预印本元数据；不凑满）
- 入库 **1**/上限6（只设上限，0–2 条亦属正常，未凑数；另 3 处存量行升级/复查不计新增）：
  1. [Dog-human play and the canine play pant in a shelter dog population](https://doi.org/10.17605/osf.io/98nhd)（OSF Preprints，2026-09-07）— ⚠️预印本待评审 — 数字口径：**53 场次音视频（原始采集量）、2022–2023 学年、收容所可领养犬≥6月龄；17 只犬拒绝参与；独立犬数全文未读未知** — 证据层级：OpenAlex 元数据级（摘要经倒排索引重建）— 为何有价值：play pant 受控采集由 ELTE 单一团队扩展出第二团队（Horowitz/Root-Gutteridge 系）＋收容所场景，"犬 dissent"作为同意/退出方法论先例；正对主任务"现有数据能支持什么判断"的资源地图
- 判断变化：①**17 犬数据集"首个可能商用犬声数据集"假设作废**——归档 README 原文 CC BY-NC 4.0 落定，受控采集犬声数据仍无商用许可（datasets 行 10-22 冲突口径关闭）；②ICASSP 论文由摘要级升级**方法节级**——犬任务（Abzaliev 14 类）随机 70:20:10 **段级切分未按犬隔离**，最佳 UAR 54.23%（AVES）对语音预训练 48.95%（+5.28pp，三数据集中动物预训练优势最大但绝对水平低）——其结果不可作跨犬泛化证据，预训练路线旁证的适用边界收窄并具体化；③"可采购意图标注犬声数据"盘点结论：**公开渠道无**——可商用的是媒体 SFX 音效库（无科研标注），科学数据路径＝作者申请（Mescalina/Abzaliev）或开放许可（Barkopedia MIT 但来源再授权未知；17犬 CC-BY-NC 本轮落定）。
- 筛除／存疑：①《A Lightweight 1D-CNN for Bark and Howl Classification》（Applied Sciences 2026-07-07，10.3390/app16136819）——**筛除挂账**：103 段（46 吠＋57 嚎）规模过小、独立个体数未知（规模口径待核）、二分类任务过窄，无噪声 93.40±2.62% 不具判断价值；若未来需边缘部署参数参照（7,130 参数/27.85KB/18.35 MFLOPs）可回溯；②arXiv "synthetic+dog bark" 唯一命中（2608.04072）为 HRI 声音指令识别，非合成数据研究——0 新增仅对该查询成立；③IPFS 托管"DogBridge"项目文档（2026-06-03，主人确认/纠正回路 MVP 设计）——出处不明无法定归属，疑似与已作废旧 MVP 相关，不入库仅存疑。
- 其他发现（自由填写）：①**ElevenLabs Text to Bark**（文字转犬吠商用合成，官方 blog；经网易转述"独立测试 95% 犬不可区分"⚠️厂商转述级、测试设计未核）——合成数据重点的首个商用信号，实证缺失；②可商用犬声音效库盘点：Pro Sound Effects Canines（648 文件/10.11GB/24bit-192kHz/royalty-free 商用）、Sound Ideas Canine（750 条）等——媒体许可清晰但**无意图/情绪科研标注、个体与情境元数据不齐**；③Mescalina Bark ID 数据库（10.3233/JIFS-169509）可向原作者申请取得——"可取得"科学犬声数据的具体入口（ICASSP 用其 v2017 版 8,034 段）；④Zenodo 记录级 license 字段现状为空——10-22 轮"记录 CC-BY-4.0"应是当时记录元数据，现已无该字段，冲突解决以归档内 README 为准；⑤Salford 博士论文（citizen science 主人拍摄＋主人标注，研究者-主人标签一致度 **98.1%**、不一致项经回看全部修正，方法承 Horowitz & Hecht 2016）——主人确认标注设计的直接先例，全文 PDF 在 Salford repository，值得细读。
- 未入库但值得跟踪的线索：Salford 博士论文主人标注设计（98.1% 一致度先例）；ElevenLabs Text to Bark 实证状态；DogBridge IPFS 文档归属；ICASSP 论文 5 条引用追踪（归犬吠月查 2026-11 第一周）；Mescalina 申请条件与许可（须联系原作者，本轮未联系）。
- 深查证据层级自报：4/5；本轮新条目整体层级 **元数据级**（OSF 预印本为 OpenAlex 摘要重建；ICASSP 升级方法节级属存量行升级非新增）。
- 覆盖（逐条，采集段 2026-10-26 10:06–10:18 +08；逐条时刻无独立日志可验证、一律标未知，仅按先后排序）：
  - Zenodo API｜records/18972388＋files/06 Readme.txt/content（7,021B）｜未知｜发现（许可冲突解决）
  - GitHub 主站＋raw｜idiap/ssl-human-animal 页面、LICENSE（404）、LICENSES/、README、CITATION.cff｜未知｜发现（GPL-3.0-only 落定）
  - GitHub atom｜idiap/ssl-human-animal/commits/main.atom｜未知｜发现（最新提交 2026-02-03）
  - arXiv｜export.arxiv.org id_list=2501.05987＋arxiv.org/html/2501.05987v1（HTTP 200，94KB）｜未知｜发现（方法节级直读；v2 同存未用）
  - OpenAlex｜works?title.search:dog play pant（per-page 5）＋works/doi:10.17605/osf.io/98nhd｜未知｜发现（Sci Data 无条目；OSF 预印本新发现）
  - HF API｜models/EarthSpeciesProject/NatureLM-audio｜未知｜发现（无变化）
  - GitHub atom｜earthspecies/NatureLM-audio/commits/main.atom（9 条目）｜未知｜发现（#21 新提交）
  - arXiv API｜all:"synthetic"+all:"dog bark"（max_results 8，submittedDate desc）｜未知｜1 命中不相关→0 新增（单查询口径）
  - crossref API｜10.3390/app16136819｜未知｜发现（1D-CNN 摘要→筛除）
  - WebSearch｜synthetic dog bark audio generation training data augmentation empirical study bioacoustics｜未知｜发现（ElevenLabs 信号；无实证研究）
  - WebSearch｜dog vocalization dataset commercial license purchase bark database｜未知｜发现（SFX 库盘点）
  - WebSearch｜pet owner confirmation correction labeling animal behavior data collection design citizen science dog｜未知｜发现（Salford 论文线索＋DogBridge 存疑）
  - 失败通道：本轮无（GitHub api 未用直接走主站；arXiv https 直连无 301）。
- 未完成与下轮承诺（2026-11-02）：①**成功水位建立依据**：每周必查 1/1、积压 4/4、追加重点 4/4（①可采购②开源许可③合成数据④主人确认均以实际查询覆盖）、轮换主题按频率表执行完毕；前四轮外因阻塞项按 2026-10-22 频率表重划——17 犬资源边界已由 Zenodo 原档＋README 原文补齐（预印本全文仅剩背景价值）、JAVMA 全文归疼痛线月查、bioRxiv 全文不再单列——**此为按规则降频，非临时缩减**。下轮采集窗口改为 **2026-10-24～运行时刻**（回溯 2 天），不再补扫 09-29。②轮换回月度第一周「行为／声学及个体外泛化」＋犬吠关键论文月查（含 ICASSP 5 条引用、LREC 10.63317 引用增量）。③按钮线月查＋主人确认与纠正设计专项（Salford 论文细读优先，正对晶晶追加重点④）。④Mescalina 申请条件与许可（须联系原作者，安排在按钮线轮次）。⑤Sci Data 描述论文发表即核（不挂账）。

---

## 2026-10-22 · 规则采纳与内容补强（非定时扫描）

- 性质：主公采纳《2026-10-22 下一期调研改动建议》（三项授权：改规则、修合并 PR #16、报告入库），军师落地；另补两处内容。
- 规则（AUTOMATION 第3步＋两侧 sources.md）：每轮顺序＝本侧核心问题及重大纠错 → 相关变化检查 → 余量低频轮换；频率表落地（犬吠关键论文月查、融资细节降级、猫／畜牧低频、硬件按需）；**降频≠删除，不得事后缩减计划以宣布完整成功**；本期主任务＝国内家庭需求证据＋不自采数据下的能力边界。
- 体裁边界（docs/方向调研/README.md）：讨论结论／决策记录≠已验证证据；与主分支已核实记录冲突时以已核实记录为准并回头修订。
- 内容补强：①CREMD 行补全文直读（arXiv 2602.15349v1 §III–IV、表 V–VI、表 X，2026-10-22）：402 基础视频含 **351 只独立犬**、单元均长 15.8 秒、23 名标注者（16 主人／7 非主人、8 专业）、12,794 条标注／15,195 票、**非主人一致度高于主人**（多数票占比中位 0.80 vs 0.69）；②17 犬数据集托管纠正：Zenodo 18972387 实际跳转至 **18972388**（规范 DOI 10.5281/zenodo.18972388），**许可声明冲突待核**——Zenodo 记录 CC-BY-4.0 vs 预印本 crossref CC-BY-NC-4.0，若 CC-BY-4.0 成立即为本表首个可能商用的犬声数据集。
- PR #16 已按主公授权修订两处回归（犬吠"约 70%"、CREMD"923 段"）后合并（86f2062），细节见 PR #16 评论。

---

## 2026-10-19 · 学术工程侧每周扫描第四次运行（定时任务）

- 运行：开始 2026-10-19 10:07（任务触发，系统时间）；写入开始 2026-10-19 10:20（锁 owner.txt 实测）；Git 提交时间戳：**2026-10-19T10:24:33+08:00（06c9d67，实测）**。
- 采集窗口：2026-09-29～2026-10-19 10:07（补扫；前三轮均部分完成，成功水位未建立，下轮窗口起点仍 2026-09-29）。
- 轮换主题：10 月第三周「疼痛／生理／健康预警的外部与纵向验证」；上轮结转补查：犬吠 LREC 引用重挖（必做）、17 犬游戏数据集全文与数据托管、AAC §6／§9–11、JAVMA 短头颅猫个体隔离与外测、Barkopedia 任务区别复核、Multi-QuadEmoNet 方法节确认。
- 必查项（逐项）：
  1. 犬吠 LREC 论文引用重挖 — **完成（连续两周失败后告破）** — `api.openalex.org/works/doi:10.63317/3fjpkdcjtvyx` — 失败根因定位：前两轮查的 `10.18653/v1/2024.lrec-main.1432` 是 ACL 内部标识、未在 OpenAlex/S2 注册；OpenAlex 实际收录该论文于 DataCite 前缀 DOI **10.63317/3fjpkdcjtvyx**（W7131856971，正名《Towards Dog Bark Decoding》）。引用共 2 条（见下），窗口内 0 新增；S2 DOI 端点本轮仍查无此文（404 而非 429）
  2. 按钮论文（PLOS ONE）引用 — **完成** — `api.openalex.org/works?filter=cites:W4401948191` — 总 11 条，窗口内 0 新增
  3. 组合论文（Sci Rep）引用 — **完成** — `api.openalex.org/works?filter=cites:W4405168186` — 总 26 条，窗口内 0 新增
  4. NatureLM repo＋权重卡 — **完成** — HF API `models/EarthSpeciesProject/NatureLM-audio`（无变化：lastModified 2025-09-09、cc-by-nc-sa-4.0）＋ `github.com/earthspecies/NatureLM-audio/commits/main.atom`（api.github.com 整站 403 限流，主站 atom 备用成功）— **main 新提交 d95b645（2026-10-13T08:12Z）"Clear Dependabot vulnerabilities: dependency bumps, torch 2.6 on CUDA…"，依赖修补类，非模型行为或条款变化**
- 预算顺序自检：必查是否全部完成 **是**（4/4）；读原文方法节／表格的条目数 **1**（AAC 框架全文 §6–§11 直读）；深查 **5**/上限5（AAC 全文、JAVMA 摘要复读、JFMS 摘要、17 犬 Zenodo 数据卡、ICASSP 摘要）
- 入库 **2**/上限6（只设上限，0–2 条亦属正常，未凑数；均为窗口外补入——依"允许补入改变判断的旧文献"条款）：
  1. [Challenges using the Feline Grimace Scale in brachycephalic cats](https://doi.org/10.1177/1098612x251401338)（J Feline Med Surg，2025-11-18）— ✅摘要级 — 数字口径：**28 只猫**（前瞻随机盲法、95 张图像、4 评分者）；口鼻张力 ICC 0.47、胡须变化 0.34（差），耳位 0.81、眼位 0.84（良好），FGS 总分 0.76；LoA −0.37～0.22 — 证据层级：摘要级，全文未读 — 为何有价值：人工评分可靠性在短头颅猫**分动作单元不均**，直接解释同团队 JAVMA 自动管线为何"去口鼻＋胡须"配置最佳——把"需构型专门数据集"的失效机制从模型层下沉到量表动作单元层；Steagall 系归并
  2. [Comparing Self-Supervised Learning Models Pre-Trained on Human Speech vs Animal Vocalizations](https://doi.org/10.1109/icassp49660.2025.10889684)（ICASSP 2025，2025-03-12）— ✅摘要级 — 数字口径：3 个生物声学数据集×2 类任务（样本量摘要未给，待全文）；动物声预训练仅**边际优于**人类语音预训练、ASR 微调结果混合 — 证据层级：摘要级 — 为何有价值：为 LREC 犬吠论文"借人类语音处理"路线提供旁证（非劣势选择）；亦是 LREC 引用重挖命中之一
- 判断变化：①AAC 框架由"摘要级候选观察方案"升级为**方法节级直读**——§6 六类编码＋成对反类目＋非对称重分类＋20% 盲外编、§10 八条可证伪模式、§11 作者自认非实证；仍非经验验证，但操作化路径与可证伪条件已具体化；作者利益关系（CCR—Haverim 私营犬交流实验室）明记；②FGS 自动管线失效获机制解释（人工评分在口鼻/胡须单元本就不可靠）——"需构型专门数据集"判断**加强**；③预训练路线判断获旁证：动物域预训练非必需，人类语音 SSL 表征已够用——不改变犬吠精度结论本身；④17 犬数据集托管由"未知"落定为 Zenodo＋Sci Data 在审；⑤JAVMA 摘要复读后明确**未见个体隔离与外测描述**（维持未知，不作已核陈述）。
- 筛除／存疑：Europe PMC 窗口查询（grimace scale/pain face/pain recognition＋cat/dog）6 命中全不相关（浆细胞瘤、镇痛 RCT、非动物通信）——**0 新增仅对该查询成立**；arXiv "dog bark"／"cat meow" 窗口内 0 新增（该查询口径）；HF datasets dog bark/cat meow 无窗口内新条目（Barkopedia 第三方再上传 PuneettArora 09-06、hlx1021 07-08 维持 10-13 存疑挂账）。
- 其他发现（自由填写）：①OpenAlex 对 LREC 论文的收录 DOI 是 **10.63317 DataCite 前缀**而非 ACL 的 10.18653 内部标识——后续引用追踪一律以 10.63317 为准，避免重蹈两轮失败；②api.github.com 整站 403 时 `github.com/<owner>/<repo>/commits/main.atom` 主站 atom 仍可用（连续第三次验证）；③Europe PMC 出现一次 503（10:14 前后）数分钟内自行恢复，重试即可，无需换通道；④17 犬 Zenodo 描述披露多机位视频＋同步音结构——对"声学×视觉多模态对齐"研究是额外素材，超出纯音频价值；⑤ICASSP 论文自身有 5 条引用，可作下轮引用追踪起点。
- 未入库但值得跟踪的线索：**Scientific Data 在审**的 17 犬数据描述论文（发表即核方法节，替换摘要级）；ICASSP 2025 的 5 条引用；《A Lightweight 1D-CNN for Bark and Howl Classification》（Applied Sciences 2026-07-08，10.3390/app16136819，标题含 howl 疑似犬狼声分类，未核）；JFMS 论文同团队其余 FGS 外部验证工作。
- 深查证据层级自报：5/5；本轮新条目整体层级 **摘要级**（2 条新入库均未读全文；AAC 框架为本轮唯一方法节级直读对象，属存量行升级非新增）。
- 覆盖（逐条，访问时间 2026-10-19 上午）：
  - OpenAlex works/DOI｜`10.63317/3fjpkdcjtvyx`、`cites:W7131856971`｜10:10｜发现（2 引用，窗口内 0 新增）
  - OpenAlex works/DOI｜`10.1371/journal.pone.0307189`→cites、`10.1038/s41598-024-79517-6`→cites（per-page 50）｜10:12｜发现（11/26 条总量，窗口内 0 新增）
  - HF API models｜NatureLM-audio｜10:11｜发现（无条款变化）
  - GitHub API repos＋atom｜`api.github.com` 403｜10:12｜**访问失败**→备用 `github.com/.../commits/main.atom` 成功（发现 d95b645 新提交）
  - S2 API｜DOI 端点×2、search 端点×2｜10:10–10:14｜**访问失败**（404 查无此文，非限流）→OpenAlex 已补齐，不再重试 S2
  - Europe PMC search｜grimace scale 窗口查询（FIRST_PDATE 2026-09-29 TO 2026-10-19）｜10:16｜发现 6 命中全不相关→0 新增；另 DOI 查询 2 次（JAVMA/JFMS）｜10:24｜发现
  - Europe PMC search｜brachycephalic＋grimace 标题检索｜10:24｜发现（JAVMA 正确 DOI＋JFMS 新条目）
  - Frontiers 官网 HTML｜`fanim.2026.1907975/full`（curl 直抓 575KB）｜10:19｜发现（§6–§11 全文）
  - bioRxiv 全文/PDF/Highwire｜10.64898/2026.04.20.719471 三通道｜10:14–10:17｜**访问失败**（17 bytes／403）→bioRxiv API＋crossref＋Zenodo 记录补齐元数据；全文仍不可得
  - Zenodo API＋WebSearch｜Dog play pant 托管定位｜10:29｜发现（10.5281/zenodo.18972387）
  - arXiv API｜"dog bark"、"cat meow"（sortBy submittedDate，max_results 8）｜10:36｜窗口内 0 新增（http 301→https 重试成功）
  - HF API datasets｜dog bark／cat meow（limit 12，createdAt desc）｜10:37｜无窗口内新条目
- 未完成与下轮承诺（2026-10-26）：①轮换 10 月第四/五周「可取得数据／权重、相关硬件供给和法规」（正对 17 犬 Zenodo 条款细读与 Barkopedia 系数据许可核对）——必做；②Scientific Data 数据描述论文在审，发表即核（下轮查证是否已发表）；③ICASSP 全文与 5 条引用追踪——顺延不挂账；④《Bark and Howl 1D-CNN》候选——下轮判断价值；⑤窗口起点：本轮仍无"全部计划覆盖"的完整收尾（bioRxiv 全文与 JAVMA 全文持续付费墙/反爬不可得属外因），维持部分完成口径，窗口起点 2026-09-29；若下轮无新增外因阻塞且覆盖完成，可考虑登记成功水位。

---

## 2026-10-14 · Barkopedia任务口径纠正（非扫描）

- 原口径：10月13日周记／账本及datasets将其称为“个体隔离／跨犬泛化公开基准”。此口径作废，历史记录保留但不得继续引用。
- 依据：[官方HF数据卡](https://huggingface.co/datasets/ArlingtonCL2/Barkopedia_Individual_Dog_Recognition_Dataset)，2026-10-14读回：训练／测试均约每个60犬ID取片段；任务是已知犬身份分类，不是留出未见犬的泛化。标签隐藏不等于按犬分组。
- 修改：datasets当前行纠正，规模与MIT卡片标签保留，来源再授权仍未知。未下载数据、未运行模型，不推进扫描成功水位。

## 2026-10-13 · issue #9/#10/#11 事实核查落地（非定时扫描）

- 性质：协作方（老邪，云端）以 issue 形式提交三组事实核查；军师逐项**直读原始来源独立复核**后落正文，不照抄 issue。复核通道：猫叫论文全文（Europe PMC PMC6719916 XML）、犬吠论文表格（arXiv:2404.18739 HTML 版，与 ACL Anthology 同版）、四条元数据（Crossref API）。
- 更正（#9）：猫叫「96%」追溯到 **Ntalampiras 等，Animals 2019, 9(8):543**（CC BY，PMC6719916）——21 只成年猫（10 只 Maine Coon 同一主人＋11 只 European Shorthair 不同主人）、448 段（196＋252，均长 1.82s、约 1s 背景噪声）、DAG-HMM **95.94%**（对照：类别专用 HMM 80.95%、通用 HMM 76.19%、SVM 78.51%、ESN 68.9%）；**十折交叉验证未说明按猫隔离**；三情境为实验诱发（等食／陌生环境隔离／梳毛）。README「仍待追溯」、02 表 ❓、papers ❓ 三处同步升级；并明确与犬吠 62.18%（按犬分组）**口径不可比**。
- 更正（#10）：犬吠论文补四个口径——①四类情境**全部为陌生人在场**，"袭击主人"类因早期实验发现与很凶吠不可区分而**被剔除**；②情境增益仅 **+5.81pp**（56.37→62.18），各类 F1 45–91%；③品种 62.28% 的多数类基线为 **58.76%**（仅 +3.5pp）；④性别 68.90%／70.07% 的多数类基线为 **68.70%**，**未明显超基线**；个体识别 49.95%（基线 5.03%）。README／02／04-F／papers 四处同步。
- 更正（#11）：04-references A 节五条元数据经 Crossref 补全——Bastos 等 13 位作者（PLOS ONE 19(8):e0307189, 2024-08-28）；Chambers 等 10 位作者（Animals 11(6):1549, 2021-05-25）；O'Rourke 等（AJVR 86(3), 2025-03, DOI 10.2460/ajvr.24.09.0269）；Andics 等 6 位作者（Science 353(6303):1030–1032, 2016-09-02）；Abzaliev 等确认为 LREC-COLING 2024 正式会议论文（ACL 2024.lrec-main.1432, pp.16480–16486）。Andics 2016 脑图标注更正讨论**标待核**，未定性。
- 影响：犬吠「62.18%」由"接近六成的情境理解"收窄为"陌生人在场四分类、增益 5.8pp、性别任务未超基线"——对"家庭日常意图不可直接翻译"判断是**加强**；猫叫 95.94% 由媒体口径升级为论文报告，但按猫隔离缺失使其同样不能作泛化锚点。两篇口径不可比已写入正文。

---

## 2026-10-13 · 学术工程侧每周扫描（新规则测试运行，非定时触发）

- 运行：开始 2026-10-13 07:50（系统时间 Asia/Shanghai）；写入开始 2026-10-13 07:56（系统时间实测）；Git 提交时间戳：**2026-10-13T07:59:37+08:00**（477cdce，实测）。
- 采集窗口：2026-09-29～2026-10-13 07:50（补扫；前两轮均部分完成，成功水位仍未建立）。
- 轮换主题：无（本轮为手动触发的新规则测试运行）；上轮结转补查：NatureLM 权重卡与 repo 状态、犬吠 LREC 引用重挖、按钮／组合论文后续、HF 新条目、bioRxiv、Xeno-canto 条款。
- 必查项（逐项）：
  1. NatureLM HF 权重卡 — **完成** — `huggingface.co/api/models/EarthSpeciesProject/NatureLM-audio` — license 仍 cc-by-nc-sa-4.0、lastModified 2025-09-09、文件含 model.safetensors（连续两周挂账项本轮清除）
  2. NatureLM repo 版本／条款 — **完成** — GitHub REST API 空返回→备用入口 `commits/main.atom` 成功 — main 最新提交仍 2026-04-16（#18）、v1.0.2，本轮无新提交
  3. 犬吠 LREC 论文（Abzaliev 等，2024.lrec-main.1432）引用重挖 — **访问失败** — OpenAlex 无收录（DOI 与标题检索均无）、S2 DOI 端点 404、S2 search 端点 429 — 三个备用入口均失败，**不计无新增**，下轮 2026-10-19 继续
  4. 按钮论文／组合论文后续 — **完成** — `api.openalex.org/works?filter=cites:W4405168186` — 引用 26 条，最新 2025-11-04，窗口内 0 新增（仅对该查询成立）
- 预算顺序自检：必查是否全部完成 **否**（第3项访问失败）；读原文方法节／表格的条目数 **1**（Barkopedia 个体犬识别 HF 数据卡：训练／测试划分与每犬片段数，属方法级）；深查 2/上限5（不必凑满）
- 入库 **2**/上限6（只设上限，宁缺毋滥）：
  1. [Barkopedia 个体犬识别数据集](https://huggingface.co/datasets/ArlingtonCL2/Barkopedia_Individual_Dog_Recognition_Dataset) — 核查 2026-10-13 — ✅MIT — 数字口径：8,924 片段／训练 7,137＋测试 1,787／**60 只犬**（原始采集量未知，来源音频再授权待核） — 证据层级：数据卡方法级 — 为何有价值：首个可直接用于**个体隔离与跨犬泛化**检验的公开犬吠基准，且许可为 MIT（比既有 CC-BY-NC 系宽松），正对"跨数据集个体泄漏"判断缺口
  2. [犬-人社交游戏犬声数据集](https://doi.org/10.64898/2026.04.20.719471) — 2026-04-23 预印本 — ⚠️CC-BY-NC-4.0 不可商用 — 数字口径：30 场／**17 只犬**／6–24 月龄 — 证据层级：**摘要级，全文未读** — 为何有价值：正对"公开犬声数据多为社媒来源、缺家庭／交互场景受控采集"这一核心缺口，含视频上下文与跨个体泛化的初步证据
- 判断变化：①犬声数据格局再更新——除三个社媒来源大规模集外，新增**受控采集**（17 犬实验室游戏）与**个体识别基准**（60 犬）两类资源；"家庭／交互场景受控数据缺口"由"几乎空白"改为"已有首个受控公开候选，但规模小、许可不可商用、全文未核"；②出现首个 MIT 许可的犬吠公开基准（Barkopedia 个体识别），商用可行性须与来源音频再授权分开核，暂不改写"多数犬声数据不可商用"的整体结论。
- 筛除／存疑：组合论文引用中的《Home Ranges of Animals》书章节系列（5 条）为引用解析噪音，筛除；HF 上 Barkopedia 第三方再上传条目（PuneettArora 2026-09-06、hlx1021 2026-07-08）许可与来源再授权未核，存疑不入库；cat meow 各 HF 集（liladhii/isolated-cat-meows 等）规模与许可未核，存疑；Research Square《Adaptation of Speech and Bioacoustics Models》（2026-07-14）未核，列下轮候选。
- 其他发现（自由填写）：①Barkopedia 在 HF 上另有 breed／age／sex 三个分类子集（ArlingtonCL2，2025-04-15），可用于"同批数据多任务"对照；②Europe PMC 的 `SRC:PPR` 通道可稳定检索预印本（本轮 74 命中），可作 bioRxiv 官网之外的备用入口。
- 未入库但值得跟踪的线索：Barkopedia 挑战页其余任务子集；犬-人游戏数据集的数据托管仓库（定位后即核许可与规模）；cat meow 各 HF 集。
- 深查证据层级自报：2/5；本轮新条目整体层级 **混合（1 条数据卡方法级、1 条摘要级）**
- 覆盖（逐条）：HF models API｜`api/models/EarthSpeciesProject/NatureLM-audio`｜07:52｜发现（无条款变化）；GitHub REST repos｜`api.github.com/repos/earthspecies/NatureLM-audio`｜07:52｜**访问失败（空返回）**→备用入口 ATOM feed 成功；HF datasets API｜search=dog+bark／cat+meow／animal+vocalization，limit 6，sort createdAt desc｜07:53｜发现 4 条候选、2 条入库；OpenAlex｜`works/doi:10.1038/s41598-024-79517-6`、`works?filter=cites:W4405168186&per-page=25&sort=publication_date:desc`｜07:52｜发现 26 条引用、窗口内 0 新增；ACL Anthology｜`2024.lrec-main.1432.bib`｜07:53｜发现（论文正名）；OpenAlex｜`works/doi:10.18653/v1/2024.lrec-main.1432` 与标题检索｜07:54｜**无收录**；S2｜DOI 端点、search 端点｜07:56｜**404／429 访问失败**；Europe PMC｜`SRC:PPR AND (cat OR dog) AND (vocalization OR bark OR meow)`，pageSize 15，sort P_PDATE_D desc｜07:54｜74 命中、1 条入库；crossref｜`works/10.64898/2026.04.20.719471`｜07:55｜发现（许可 CC-BY-NC-4.0）；bioRxiv 全文｜`biorxiv.org/content/10.64898/2026.04.20.719471v1.full`｜07:56｜**访问失败**（返回长度 17，被拒）
- 未完成与下轮承诺（2026-10-19）：①犬吠 LREC 引用重挖——**必做**，换 OpenAlex 收录恢复／S2 限流解除，不得再挂账；②犬-人游戏数据集全文与数据托管位置——必做；③Xeno-canto 条款——**本轮给结论：降级为季度核查（下次 2027-01 首周）**，理由鸟类为主、非四线重点；④AAC 框架 §6／§9–11 全文、JAVMA 短头颅猫全文——顺延；⑤bioRxiv、NatureLM 权重卡两项挂账本轮已清除。

---

## 2026-10-13 · issue #2 复核纠正（非定时扫描）

- 性质：针对第二次扫描（f658358）的正文纠正，由 [issue #2](https://github.com/gethlx/pet-aic-research/issues/2)（R1–R8）驱动；papers 原文已改、规则已补，历史周记不回改，被本节取代的口径不得继续引用。证据见 [复核报告](../reports/2026-10-13-research-周更新复核.md)；关键项由我方直读原文独立复核（Europe PMC 全文 XML、PubMed 官方摘要、crossref 参考书目），未直读者已标待核。
- 更正（R1）：Multi-QuadEmoNet **规模三分写**——原始每情绪类别 100 条、取自 YouTube／Kaggle／GitHub；增强（加噪／变调／高通）至每类 1,000（犬 2,000／猫 6,000）。摘要"自收集 6000 猫＋2000 犬"是**增强后计数**，非独立采集量，**独立个体数未知**；标签为公开来源自带、经一名兽医博士验证（无多标注者一致性报告）；80:20 未说明按个体／源录音隔离及增强与划分先后，增强泄漏风险待核。
- 更正（R2）：JAVMA 短头颅猫条目**补回核心负面结果**——关键点定位精度下降（NRMSE 19.96% vs 中头型为主 16.76%）、**疼痛预测泛化差**（最佳配置 MAE 0.168／R² 0.115／Pearson 0.374）、明确"需构型专门数据集"；200 张**图像**≠200 只猫。原"可行性评估含局限"的弱化表述作废。
- 更正（R5）：Kuhlmeier 评论——crossref 参考书目 6 条中**无四按钮计算机游戏系统论文**，删除该错误引用关系；保留在线 2025-07-22／期次 2026-06 区别。
- 收窄（R3／R4）：FGS chatbot——原文明称重测**同一 chatbot 版本**，两月间一致性变化**不得归因版本漂移**；无规则对照，**不得外推"LLM 相对规则也无增益"**；参考标准单一专家、图像取自其本人数据库；LoA 跨阈值是一致性差值范围，不等于临床误诊率。AAC 框架——未经经验验证（待核），由"方法论升级"降为**候选观察方案**。
- 更正（R8）：周记"写入开始约 10:25"与 Git 提交时间戳 10:20:01 直接冲突（提交早于所记写入开始）→ 该估计值作废、改标**未知**；规则收紧为"凡与可验证时间戳冲突的记忆估计一律标未知"。
- 流程（R6／R7）：周记"必查三件完成"与同条所列"LREC 引用重挖因限流失败"自相矛盾，改为逐项标注完成／失败；AUTOMATION 补预算优先级（必查→1–2 篇读方法节→再找新文献；深查配额不必凑满）、必查项连续两周挂账须给轮次承诺或缩减计划、查询记录补日期与返回上限字段。
- **复发提示**：R1（规模口径）与 R8（时间源）与 issue #1 同类，上周所加规则未被执行到位——单纯"写进规则"不够，本轮改为可勾选字段与冲突即作废的硬口径。

---

## 2026-10-12 · 学术工程侧每周扫描第二次运行（定时任务）

- 运行：开始 2026-10-12 10:07、写入开始约 10:25（Asia/Shanghai，内存估计）；Git 收尾时间以提交时间戳为准。
- 采集窗口：2026-09-29～2026-10-12 10:07（补扫；上轮部分完成不推进水位，成功水位仍未建立）。
- 轮换主题：10 月第二周「按钮、认知、反向训练与负面结果」＋ issue #1 R7 补查（猫声、临床/疼痛与负面结果、覆盖记录字段、同团队引用偏差控制）。
- 完整性：**部分完成**——必查三件完成（NatureLM 状态复查、按钮两论文引用重挖；犬吠 LREC 论文引用重挖因 S2 search 限流未完成，计访问失败）；R7 四项补查中猫声与临床/疼痛完成、覆盖字段已记、团队归并已执行（Steagall FGS 系、VIT 计算机系单条目归并）；bioRxiv、ESP 其余 repo、HF 新条目、Xeno-canto 条款、NatureLM HF 权重卡复查未覆盖（连续第二周）。不登记成功水位。
- 入库（papers，7 处）：①Multi-QuadEmoNet 猫犬叫声情绪分类（✅Front Vet Sci 2026-06-22 正式发表 CC BY；摘要级数字犬 95%/猫 90% 待原文复核；标签来源与个体划分未知；数据自收集未公开——补上 R7-①猫声覆盖缺口首篇正式发表参照）；②Longhitano Springer 章节（⚠️摘要级，Beti 85%/Kisha 91.8% 待复核）；③LLM chatbot 评 FGS 一致性（✅Sci Rep 2025-12-09，50 图×4 chatbot×2 轮 Bland-Altman，多数一致性不可接受、LoA 跨镇痛阈值 0.39——**负面结果入库**，LLM 不能直接当兽医疼痛评估器）；④短头颅猫眼痛 FGS 自动管线（✅JAVMA 2026-07-22 摘要级，Steagall 系按团队归并）；⑤按钮 AAC"情境化交流事件"方法论框架（⚠️Frontiers in Animal Science 2026-08-26 摘要级，分析单元从孤立按键转向事件——与既有主人偏差判断一致）；⑥声板评论 Kuhlmeier（✅L&B 2025-07-22 元数据级，评论无摘要）；⑦AI 伴侣动物交互综述（✅ACM TOMM 2026-06-09 摘要级）。另 Grimace ML 系列行改"部分拆分"并挂 Animals 2026-08-18 micro-expression 综述（明示尚无已验证通用跨物种框架）。
- 入库（tooling）：NatureLM 行补 2026-10-12 复查注记（main 最新提交仍 2026-04-16 #18、MIT 未变；repo pushed_at 2026-09-21 属元数据/旁支动静，非 main 新提交——GitHub REST commits 限流后经 commits ATOM feed 核实）。
- 判断变化：①按钮线方法论升级——从"是否理解词义"转向"情境化交流事件"单元，操作化路径与既有偏差判断兼容；②LLM 疼痛评估获具体负面证据，支撑"LLM 相对规则/专家无免费增益"边界；③猫声情绪分类出现正式发表可及文献，但标签方法与个体划分仍未知，不改变"猫声标签质量未知"判断；④**窗口内按发表日期 0 新增**——本轮入库全部为引用追踪与补查命中的窗口外文献（依"允许补入改变判断的旧文献"条款），不得表述为"窗口内新增"。
- 筛除／存疑：arXiv 犬吠（cs.SD/eess.AS/cs.LG）与猫叫（全字段）查询窗口内 0 新增——**仅对该查询成立**，8+4 条命中均为语音/视听/艺术类误匹配；S2 PLOS ONE 引用列表中两条巴西 Saúde em Debate（青春期物质滥用）与一条 Physics of Life Reviews 内心语音评论为引用解析噪音，筛除；theherd.news 对 Multi-QuadEmoNet 的二手批评仅作线索，不入库。
- 深查配额：3/5（chatbot-FGS 原文页、Frontiers AAC crossref 摘要、Multi-QuadEmoNet 原文页+PDF 摘要）；Longhitano、JAVMA、micro-expression 综述、ACM TOMM、Kuhlmeier 为摘要/元数据级。均未读方法节全文——**本轮新条目整体仍为摘要级，非方法核验**。
- 覆盖（访问时间均为 2026-10-12 上午）：S2 citations API×2（PLOS ONE 按钮 9 条→1 条新增分析、组合论文 7 条→3 条新发现）访问成功；arXiv API×3（"cat meow"+eess.AS；"cat meow"OR"cat vocalization"全字段；"dog bark"+三分类）访问成功；GitHub API repos 成功、REST commits 429 失败→commits ATOM feed 成功；PubMed 网页 **reCAPTCHA 拦截**→Europe PMC API 成功（hitCount 36，窗口内按发表日期 0 新增；关键词 feline grimace scale machine learning）；crossref API×5 DOI 成功（摘要 5/5，Kuhlmeier 无摘要属实）；WebSearch 猫声关键词检索成功；Frontiers 官网直抓 JS 渲染摘要不可得→crossref 补齐；S2 search 端点 **429×3**（10:12/10:15/10:19）→犬吠 LREC 引用更新**访问失败未完成**，不计无新增。精确查询词与调用记录：S2 `graph/v1/paper/DOI:{doi}/citations`（fields=title,year,externalIds,publicationDate,venue）、arXiv `export.arxiv.org/api/query`（上述查询串，sortBy=submittedDate）、Europe PMC `webservices/rest/search?query=feline%20grimace%20scale%20machine%20learning`、crossref `api.crossref.org/works/{doi}`。
- 下轮（2026-10-19）：轮换第三周「疼痛／生理／健康预警的外部与纵向验证」正对本轮 JAVMA/chatbot-FGS 延伸；补犬吠 LREC 引用重挖（S2 search 限流恢复后）；HF 新条目与 bioRxiv 仍挂账；窗口起点按水位规则仍为 2026-09-29。

---

## 2026-10-05 · issue #1 复核纠正（非定时扫描）

- 性质：针对本周首次扫描（7ca2433）的正文纠正，由 [issue #1](https://github.com/gethlx/pet-aic-research/issues/1)（R1–R9）驱动；papers／datasets／tooling／AUTOMATION 原文已改，历史周记不回改，被本节取代的口径不得继续引用。证据详见 [复核报告](../reports/2026-10-05-research-周更新复核.md)。
- 更正（R1）：CREMD 样本单位为**呈现条目合计 923**（402＋402＋119，23 标注者，缺"无上下文有音频"条件），非"923 片段×3 模式"；标注一致性／信心≠真实情绪准确性。
- 更正（R2）：Dog2vec **收集 6000+ 小时在线视频，清洗后约 150 小时犬吠用于训练**，两者勿混；分任务 F1（吠声类型 macro-F1 0.7138、事件检测 0.8287）代替摘要相对增益表述。
- 更正（R3）：Biologia Futura 综述 Version of record 2025-07-29（2025-06 为期次），内容为犬发声多面向综述、非仅声板。
- 更正（R8）：本周周记"写入完成约 10:45"为运行记忆估计、时间源不可靠——Git 作者／提交时间实测 10:22:20／10:22:36；主提交实为 4 个 research 文件＋账本共 5 文件，"6 文件"口径作废。
- 补强（R4/R5/R6）：EmotionalCanines 官方 LICENSE 为 CC-BY-NC-SA-4.0（2026-10-05 直读核查）；四按钮研究为 1 犬 PoC 且披露作者产品公司利益关系，音质研究 17 普通犬＋7 GWL 犬、FluentPet Classic 条件最差（负面结果保留）；模型合并增益为闭集 40 标签／425 样本 F1 0.09→0.28；NatureLM 边界收窄为"尚无犬猫家庭意图验证"。
- 流程（R7/R9）：AUTOMATION 增覆盖记录字段（访问失败与无新增分开记、API 失败换官方网页／期刊备用入口重试、单查询 0 新增不得外推）与下轮（2026-10-12）补查重点（猫声、临床／疼痛、负面结果、同团队引用偏差控制）；`.workbuddy/`（本地运行数据，仅含记忆日志）加入 .gitignore。

---

## 2026-10-05 · 学术工程侧每周扫描首次实际运行（定时任务）

- 运行：开始 2026-10-05 10:08、写入完成约 10:45（Asia/Shanghai）；Git 收尾结果见导航账本。
- 采集窗口：2026-09-29～2026-10-05 10:08（首次规则：自 2026-10-01 回溯 2 天）；关注对象当前状态与旧事实纠错不受窗口限制。
- 轮换主题：每月第一周「行为／声学及个体外泛化」。
- 完整性：**部分完成**——必查三件与定向检索在预算内完成；bioRxiv、ESP 其余 repo release、HF 新条目、Xeno-canto 条款、Google Scholar Alerts 未覆盖；PubMed 访问失败。不登记成功水位，下轮补扫。
- 入库（papers）：①犬语音素字母表（Wang等，✅ACL 2025 杰出论文，摘要页已核、全文待读）；①CREMD 标注研究（⚠️预印本，923片段×3模式，标注偏差证据）；②按钮后续三条（四按钮游戏系统 Learning & Behavior 2025-11-04、播放音质 Sci Rep 2025-04-28、Biologia Futura 综述 2025-06-01，均元数据级未读全文）；③NatureLM 模型合并论文（⚠️arXiv 2511.05171，官方 README 已引用）。
- 入库（datasets）：DogSpeak（✅官方 README 自述 77,202 seqs/156犬/33.16h，HF 公开）；EmotionalCanines（⚠️1,400 段 arousal/valence，仅哈士奇/柴犬）；Canine Age Transition（✅79,142 BUs/125犬/11.4h 纵向，CC BY-NC-SA 4.0）。
- 入库（tooling）：Dog2vec 线索（⚠️Interspeech 2025 自述，repo/许可待核）；NatureLM 行状态更新。
- 判断变化：①NatureLM-audio 发表状态由「预印本待核」改为「ICLR 2025 已发表」，权重 CC-BY-NC-SA-4.0 未变；②犬吠公开数据格局更新：出现三个大规模公开数据集，均为社交媒体来源、非家庭受控采集，许可均 CC BY-NC-SA 系（不可商用）——不改变「家庭多模态受控数据缺口」判断；③跨数据集个体泄漏风险获官方自述证实（Age Transition×DogSpeak 重叠个体警告），按个体隔离测试的必要性有新证据。
- 筛除／存疑：arXiv「dog bark」「cat meow」窗口内 0 新增；arXiv 2609.33458（音频 LLM「狗」概念定位，2026-09-27，窗口外且边缘）记观察不入库；Barkopedia 犬情绪数据集仅第三方 HF space 转述，未核，存疑；「Phonetic and Lexical Discovery of Canine Vocalization」与 Dog2vec 详情并入音素字母表条与 tooling 行待核。
- 深查配额：5/5（模型合并、CREMD、DogSpeak、EmotionalCanines、音素字母表）。
- 覆盖（均 2026-10-05 上午）：NatureLM repo（github）访问成功——ICLR 2025/v1.0.2/最后提交 2026-04-16；NatureLM HF 权重卡访问成功——许可与 out-of-scope 边界；PLOS ONE 按钮论文引用（Semantic Scholar API）访问成功——3 条后续；犬吠 LREC 论文（Semantic Scholar 检索＋引用）访问成功——12 条引用；arXiv API「dog bark」「cat meow」访问成功——窗口内 0 新增；arXiv CREMD 页、ACL Anthology 音素页、ACM MM 两条目（S2 API）访问成功——深查通过；WebSearch（数据集仓库）访问成功——HF 与官方 repo 线索；PubMed E-utilities **访问失败**（NCBI 反滥用屏蔽）——兽医临床窗口内增量未知，下轮补查，不计为无新增。

---

## 2026-10-01 · 审核纠正（非定时扫描）

- 采集性质：针对既有错误核对原论文、官方模型卡和监管说明；未全扫四线，不登记成功扫描水位。
- 更正：犬吠四类情境62.18%、多数类基线56.37%；近70%是另一性别任务。数据可向作者申请，商用许可未知。NatureLM代码MIT与所列权重CC-BY-NC-SA-4.0分开；犬猫家庭任务未验证。
- 更正：按钮词／结果有限关联及利益关系、PetPace声学机制、兽用法规边界；论文报告不替代部署验证。
- 更新：papers、datasets、tooling、supply-chain、README、sources；补测试划分、基线、负面结果、标签偏差、逐项许可和版本。
- 存疑／筛除：撤销NatureLM“开源可直接商用”、主人反馈唯一真值、硬件参数普遍已核实；猫叫96%、部分旧题名与样本继续待核。原papers实有12条候选记录，包含访谈／系列线索，不是13篇已核论文。
- 核验依据：[原始来源](../docs/04-references.md#f-2026-10-01-原始来源复核与纠正)；[报告](../reports/2026-10-01-审核与纠正报告.md)。配置和Git结果见报告／导航账本。


## 2026-09-30 ~ 10-01（建仓历史原记录，非完整周扫描）

> 以下保留当时记录供追溯，其✅和结论不代表当前核验状态；被上方纠错记录取代的口径不得继续引用。

- ✅ 论文线：初始收录 13 条（四层分组，见 papers.md），含 UCSD 两篇 2024、U-M 2024、Mars 系列期刊、NatureLM-audio。
- ✅ 数据集线：初始收录生物声学 5 库 + 基准 2 项；识别三大数据缺口（家庭多模态、中文环境猫叫、老年犬夜间基线）。
- ✅ 工具线：NatureLM-audio v1.1 demo（2026-04-09 更新）确认开源可用；FilterNet 无官方开源，列为复现项。
- ✅ 供应链线：传感器五类格局 + 代工产业带 + 认证四项完成初始盘点；重点标记「健康宣称的医疗器械监管边界」为产品级风险。

### 存疑区

- ❓ BEATs（Microsoft）license 条款待确认，影响 NatureLM 衍生商用链路。
- ❓ U-M 犬吠数据集是否公开分发（论文未附公开链接）。
- ❓ Watkins/Animal Sound Archive 的商用条款原文未逐条核对，暂标学术使用。
