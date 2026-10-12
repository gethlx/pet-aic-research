# research updates-log · 每周增量日志

> 倒序追加；执行字段与成功水位按[AUTOMATION](../AUTOMATION.md)。纠错记录与定时扫描分开，初始盘点不计完整扫描。

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
