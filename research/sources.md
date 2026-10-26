# research/sources · 学术与工程侧信源清单

> 按下方分级与轮换执行。新信源先加入末尾「候选信源」小节并注明理由，验证一轮后转正。所有候选信息入库前必须过 [VETTING.md](../VETTING.md)。

## A. 论文预印本与索引（按分类页订阅式扫描）

| 信源 | 扫描范围 |
|---|---|
| arXiv cs.SD / eess.AS / q-bio.NC | 每周新 Submission，关键词过滤（见 F） |
| bioRxiv（zoology / neuroscience） | 动物通信与认知 preprint（标 ⚠️ 待评审） |
| Semantic Scholar / Google Scholar Alerts | 竞品论文引用追踪（如 Wav2Vec2-dog、Feline Grimace ML） |

## B. 会议与期刊

| 信源 | 关注点 |
|---|---|
| ACM ACI（Animal-Computer Interaction） | 领域主场（一年一届，ACM DL） |
| CHI / UbiComp(IMWUT) | 宠物 HCI、可穿戴系统 |
| LREC / Interspeech / ICASSP | 动物声学建模方法 |
| NeurIPS / ICLR | 基础模型在生物声学的应用（NatureLM 系） |
| Animals / Applied Animal Behaviour Science | 行为分类与应用动物行为 |
| J Vet Intern Med / AJVR / Veterinary Dermatology | 临床验证类（行为-健康关联） |
| Scientific Reports / PLOS ONE / Science / Nature 系 | 跨物种认知与通信重磅 |

## C. 机构与实验室（官方 blog / 发布页）

| 机构 | 看什么 |
|---|---|
| Earth Species Project | NatureLM 更新、新数据集/基准、Decode 实验 |
| UCSD Comparative Cognition Lab（Rossano） | AIC 纵向研究新论文 |
| Family Dog Project（ELTE Budapest） | 犬认知与交流实验 |
| Open University ACI Lab（Mancini） | 犬用界面与 ACI 方法论 |
| Project CETI / Interspecies Internet | 方法学外溢（鲸类/基础设施） |

## D. 代码与数据

| 信源 | 关注点 |
|---|---|
| GitHub Trending + Topic: animal-bioacoustics / bioacoustics | 新模型新工具 |
| earthspecies org 的 repo（NatureLM-audio、alp、BEBE） | release 与 license 变更 |
| Hugging Face（models + datasets） | animal vocalization / dog bark / cat meow 相关新条目 |
| Xeno-canto / iNaturalist | 数据集规模与条款变化 |

## E. 工程与供应链

| 信源 | 关注点 |
|---|---|
| Bosch / ADI / TDK / Infineon / TI / Calterah Newsroom | 传感器新品（毫米波、IMU、PPG） |
| Digi-Key / Mouser 新品目录 | 传感器与低功耗 SoC 量产信号 |
| EE Times / IEEE Spectrum | 传感与边缘 AI 产业动态 |
| FCC设备授权 / 厂商欧盟符合性声明 | 竞品认证入网记录（新品先于新闻出现） |

## F. 标准检索关键词

- **英文**：dog bark classification / cat meow classification / animal vocalization foundation model / bioacoustics deep learning / pet wearable health / mmWave vital signs animal / soundboard dog AIC / feline pain recognition
- **中文**：宠物大模型 / 动物声纹 / 宠物健康监测算法 / 毫米波 宠物

## 候选信源（待验证，暂不作为常规扫描源）

- （空——每周扫描发现新信源时填入此处并注明理由）

## 每周重点与轮换（执行方法以AUTOMATION为准）

- **本期主任务（2026-11-02 起，采纳[下一期调研方案计划](../reports/2026-10-26-下一期调研方案计划.md) §4）**：**家庭视频、时序与多模态能力**——犬类家庭场景的视频行为、姿态、活动变化、声画对齐与时序理解研究；核心问题＝不自采训练数据时，现有视频／声音／多模态方法分别支持什么可验证能力、距离家庭应用还缺哪些证据。检索组合（计划 §4.1）：`dog behavior video recognition`、`canine multimodal behavior dataset`、`dog video temporal analysis cross-subject`；**只检索 `dog bark` 不算完成本项**。重点核对输出层级（动作/声音/事件/情境/情绪/意图）、前后文与个体历史的对照增益、按犬/家庭/源录像隔离、与规则/单模态基线对照、家庭条件（夜视/遮挡/多犬/背景声/机位）是否测过、代码权重数据可取得性。
- **11-02收拢补充（2026-10-26）**：主任务先问连续录像能否自动触发、是否已给事件区间、每犬注册负担及跨会话／家庭效果，再比较简单聚合与复杂时序方法。2610.21011的可见／画外分类成绩不是连续吠声检出；按犬隔离只支持相应跨犬主张，跨家庭另需家庭隔离；不满足者可作方法参照。Mendeley v2网页＋版本DOI的许可展示已核，下一步只随主任务查聚类标签与独立犬元数据；不重复查许可。Zenodo冲突、OSF数据发布、代码许可、Salford出处等留资源观察，有新信息或直接使用需要时再核；Salford若11-02有余量可换一次入口，仍无则继续留未知。具体结项见[统一计划§2](../reports/2026-10-26-下一期调研方案计划.md#2-先结项与降频再开始主任务)，不追加宠物组平行清单。
- **频率表（降频≠删除，旧积压保留出处与状态，不得事后缩减计划以宣布完整成功）**：犬吠关键论文与相关开源模型——初次方法核清优先，此后一般引用与维护状态**月查**（2026-10-19 已逐项核；引用追踪 DOI 以 OpenAlex 收录的 10.63317/3fjpkdcjtvyx 为准）；按钮论文一般引用、长期停服产品——月度或明确新事件时查；融资、股权、招股书细枝末节——降级；猫健康、畜牧及其他物种——低频轮换；硬件供给与认证——仅在与当前具体任务直接相关时查。
- **每周必查（按上表降频后保留）**：[NatureLM repo](https://github.com/earthspecies/NatureLM-audio)与[权重卡](https://huggingface.co/EarthSpeciesProject/NatureLM-audio)的版本、条款与限制变化（轻量周查：API＋commits ATOM feed，GitHub API 限流时走 ATOM）；与主任务直接相关的重大纠错与负面结果（随时，不等轮换）。查具体发布／版本，不用Trending代替资源核验。
- **待补积压（2026-10-26 已执行，状态更新）**：17 犬数据集 Zenodo 许可冲突——**仍未解决**（Zenodo `metadata.license.id`＝CC-BY-4.0 vs 归档 README＝CC BY-NC 4.0；10-26 扫描误判"已解决"已纠错，待核项＝作者书面澄清或归档内独立 LICENSE 文件，落定前按最保守 NC 方式使用）；idiap/ssl-human-animal 的GPLv3家族声明已核（`LICENSES/GPL-3.0-only.txt`＋README徽章）；具体only／or-later适用范围待核，根目录无LICENSE不等于无声明。GPL允许商用，实际分发、组合义务另评估；17 犬 Sci Data 描述论文＝托管页自述在审、OpenAlex 未定位到发表条目（两者分列）；ICASSP 2025 全文与作者代码任务／切分已核（方法节级，见 10-26 纠错节）。
- 2026-10-22 起追加重点（晶晶已确认，细节见 [下周调研要求](../docs/方向调研/2026-10-22-宠物组讨论结论与下周调研要求.md#四下周调研重点2026-10-26-那一轮起执行)）：可采购的家庭场景狗狗意图数据（内容、规模、标注、价格或待询价、授权范围）；开源数据持续观察并记许可和「商用前要处理的点」，不因许可剔除；有实证的合成数据研究；主人确认与纠正的设计。
- 定向增量检索：犬／猫＋具体任务；arXiv关键词检索不能只限三个分类，兽医研究补[PubMed](https://pubmed.ncbi.nlm.nih.gov)，数据或代码到原文所链资源。预印本和正式论文去重并记录发表状态。
- 海外开源项目线索从原论文、作者／机构仓库及官方模型卡追踪；结合姿态、声音、时序视频理解和评估工具。检查固定提交／权重、数据切分、可运行示例、基线、许可及维护状态；仅收藏链接或README阅读不能记作本地复现。地域权重与当前阶段按AUTOMATION及根README执行。
- 每月第一周：行为／声学及个体外泛化；第二周：按钮、认知、反向训练与负面结果；第三周：疼痛／生理／健康预警的外部与纵向验证；第四／第五周：可取得数据／权重、相关硬件供给和法规。撤稿、许可或停产变化不等轮换才处理。
- 硬件只查当前路线相关型号；FCC按设备标识，欧盟查符合性声明及适用规则，不假设存在通用“CE竞品认证库”。
- 野生物种研究记为方法参照，不凭跨物种成绩写犬猫意图可用。允许追溯关键旧论文，不排除与既有路线冲突的结果。
- 重点检索问题：误报／漏报、按动物和家庭隔离测试、独立标签、主人暗示／选择偏差、LLM相对规则增益、代码／权重／数据许可。每项实际覆盖、访问失败和未读全文均写周记。
