# research updates-log · 每周增量日志

> 倒序追加；执行字段与成功水位按[AUTOMATION](../AUTOMATION.md)。纠错记录与定时扫描分开，初始盘点不计完整扫描。

---

## 2026-10-19 · 学术工程侧每周扫描第四次运行（定时任务）

- 运行：开始 2026-10-19 10:07（任务触发，系统时间）；写入开始 2026-10-19 10:20（锁 owner.txt 实测）；Git 提交时间戳：待本笔提交后实测补记（补记笔填入）。
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
