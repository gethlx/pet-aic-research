# datasets · 数据资产与获取条件

> 2026-10-01纠正。数据许可、接口代码许可、模型权重分别核验；没有明确条款不推定商用。规模和训练标签不是独立真值。

| 资源 | 模态／范围 | 获取与规模 | 数据许可／商用条件 | 核查状态 |
|---|---|---|---|---|
| Xeno-canto | 生物声学，以鸟类等为方法参照 | [官方入口](https://xeno-canto.org)，当前规模待核 | 原记录CC系，逐录音条款与署名要求待核；不整库认定商用 | ❓未逐条审许可；**2026-10-13 决定**：鸟类为主、非本轮四线重点，降级为**季度核查**（下次 2027-01 首周），不再每周挂账 |
| Watkins Marine Mammal Sound Database | 海洋哺乳动物声学 | [数据库入口](https://cis.whoi.edu/science/B/whalesounds/index.cfm)，当前规模待核；撤回未核实1700+数量 | 具体许可／授权待核 | 方法参照，不当犬猫数据 |
| Animal Sound Archive | 多物种声音 | [MfN入口](https://www.tierstimmenarchiv.de)，规模／获取待核 | 数据许可和商用待核 | ❓待读条款 |
| ESP alp接口 | 多数据集统一接口 | [repo](https://github.com/earthspecies/alp)，原35+规模待版本核对 | 包代码不授权子数据；逐源许可核对 | ❓不能当现成可商用数据 |
| U-M犬吠数据 | 74犬、主要三犬种；音频 | ✅[原论文末尾](https://aclanthology.org/2024.lrec-main.1432.pdf)说明数据和基线可向作者申请；非直接公开下载 | 分发、训练及商用授权待核 | 核查2026-10-01；不是“论文未说明获取” |
| DogSpeak | 犬吠音频，社交媒体in-the-wild | ✅[官方repo README](https://github.com/Lekhak123/A-Data-driven-Approach-to-the-Longitudinal-Study-of-Canine-Vocal-Pattern-Development)自述：77,202 Barkseqs、33.162小时、156犬、5品种，含犬ID/性别/品种标签；[HF数据集](https://huggingface.co/datasets/ArlingtonCL2/DogSpeak_Dataset)页面条款待复核 | 官方自述CC BY-NC-SA 4.0；HF页待复核；不可商用；数据集许可与来源再授权分开核对 | 核查2026-10-05；[ACM MM 2025论文](https://doi.org/10.1145/3746027.3758298)未读全文，跨犬划分待核 |
| EmotionalCanines | 犬吠情绪（arousal/valence） | 官方称1,400段、仅哈士奇/柴犬；[repo](https://github.com/tmdang1101/EmotionalCanines)；标签框架自述可规模化 | ✅[官方LICENSE](https://github.com/tmdang1101/EmotionalCanines/blob/main/LICENSE)为CC-BY-NC-SA-4.0，不可商用（核查2026-10-05）；HF页与来源再授权待核 | ⚠️[ACM MM 2025论文](https://doi.org/10.1145/3746027.3758286)未读全文，核查2026-10-05 |
| Canine Age Transition | 犬吠纵向（幼犬→成犬） | ✅[官方repo README](https://github.com/Lekhak123/A-Data-driven-Approach-to-the-Longitudinal-Study-of-Canine-Vocal-Pattern-Development)自述：79,142 Bark Units／55,718 seqs／11.4小时／125犬／6品种，含月龄纵向元数据；[HF数据集](https://huggingface.co/datasets/ArlingtonCL2/Canine-Age-Transition-Vocalization-Dataset) | ✅README自述CC BY-NC-SA 4.0，不可商用；HF数据卡条款待逐条复核；不把数据集许可与来源再授权混同 | 核查2026-10-05；⚠️官方明示与DogSpeak存在重叠个体，联合使用须查个体泄漏；[论文](https://doi.org/10.1145/3746027.3758175)未读全文 |
| BEANS | 生物声学基准 | [ESP组织](https://github.com/earthspecies)，具体版本与子集待核 | 评测代码与每个子数据许可分开，不能只写开源 | ❓待核 |
| BEBE | 动物运动／bio-logger基准 | [ESP组织](https://github.com/earthspecies)，具体版本与物种待核 | 同上，商用待核 | ❓待核 |
| Barkopedia 个体犬识别数据集 | 犬吠音频，已知个体身份识别（60个犬ID） | ✅[HF数据卡](https://huggingface.co/datasets/ArlingtonCL2/Barkopedia_Individual_Dog_Recognition_Dataset)核查2026-10-14：总计8,924片段，训练7,137、测试1,787（709公开／1,078私有）；**训练和测试均覆盖同一批60个犬ID**；作者自述人工生成并验证标签 | ✅HF数据卡MIT；来源音频再授权仍待核，不能仅凭卡片认定整体商用 | 默认切分不是按犬隔离，也不证明未见犬泛化；隐藏测试标签不改变任务。可作身份识别资源，其他任务须另有合适标签、分组与验证。ACL2同团队归并；未下载或本地复现 |
| 犬-人社交游戏犬声数据集（Cuaya等，Dog play pant） | 犬发声（含非吠叫类）＋视频，实验室标准化采集 | ⚠️[bioRxiv预印本 2026-04-23](https://doi.org/10.64898/2026.04.20.719471)摘要级核对：**30场游戏、17只幼犬（6–24月龄、多品种）**与熟悉人类互动；两层声音标注＋视频上下文＋犬与场次元数据；置换检验显示标注声音类别在**跨个体**上呈高于随机且可泛化的声学差异 | ⚠️crossref许可字段 **CC-BY-NC-4.0，不可商用**；预印本待评审。**数据托管已落定（2026-10-19；2026-10-22 补核）**：[Zenodo 记录 18972387 实际跳转至 18972388](https://doi.org/10.5281/zenodo.18972388)（"Dog play pant"，通讯作者Cuaya，2026-03-12）——**规范 DOI 为 10.5281/zenodo.18972388**；文件清单＝原始录音／会话录音／样本／双层标注／元数据／README／参与者照片；Zoom H4＋2–3外置麦克风、48kHz WAV PCM、多机位原始视频＋同步音；伦理审批ELTE-AWC-003/2026（ASAB/ABS＋ARRIVE合规，饲主明示同意公开可识别音视频）；资助John Templeton基金会（Grant 63138）；**数据描述论文已投Scientific Data在审**（发表即核方法节；2026-10-26 OpenAlex标题检索"dog play pant"仍无Sci Data条目，维持"在审"）。**许可冲突已解决（2026-10-26归档README原文直读）**：数据许可为**CC BY-NC 4.0，不可商用**——[Zenodo归档内Readme.txt（7,021字节全文）](https://zenodo.org/records/18972388)原文明写"Creative Commons Attribution–NonCommercial 4.0 International (CC BY-NC 4.0)"，与预印本crossref口径一致；Zenodo记录级license字段实测为空（2026-10-26 API），此前"记录CC-BY-4.0"不再作口径依据——**10-22"若CC-BY-4.0成立即为首个可能商用犬声数据集"的假设作废**，受控采集犬声数据仍无商用许可。README另核实（2026-10-26）：14类声音字母标签（A Growl/B Whine/C Bark-yelp/D Moan/E Pant/F Cough-woof/G Howl/H Grunts/I Other/J Sneeze/K Shake/L Human vocalizations）；三麦＝Zoom H4＋Rode Wireless Go 2（领夹）＋Sennheiser ME66（枪式）＋ME64（心形）；每犬6–7机位＋双视角同步合成视频；双层标注（Raven Lite三人初标→Praat专家复核）；会话录音30段（多数单声道16bit，P-05/P-06立体声、P-01为32bit） | 核查2026-10-13、托管2026-10-19、许可与README原文2026-10-26；bioRxiv全文直抓仍被挡（正文经搜索引擎缓存部分呈现，背景节与摘要一致）；维也纳大学SCAN单元＋Family Dog Project／Messerli系（Faragó／Huber／Lamm）＋Duke（Winkler）按团队归并；正对"公开数据多为社媒来源、缺家庭／交互受控采集"缺口 |
| Banfield／Pet Insight模式 | EHR＋IMU | [行为论文入口](https://doi.org/10.3390/ani11061549)，项目规模与单篇分析样本分开 | 数据非公开获取，模式参照；合作授权未知 | 不作为可下载资源 |
| NatureLM训练数据 | 音频／文本，多类群 | ✅[官方数据说明](https://projects.earthspecies.org/naturelm-audio/datasets.html) | 含逐记录CC BY-NC、个人／学术用途或unknown等标签；不能整库推定商用 | 核查2026-10-01；宠物标签和训练适用性另评估 |

## 待调查缺口

- 家庭音频、视频、IMU同步数据的可取得性、宠物数量、跨家庭划分和标注成本，不能未穷尽检索就称“几乎空白／护城河”。
- 中国家庭环境的噪声、主人语言和使用习惯可能影响泛化；不能据此认定猫叫存在“中文意图体系”，也不认定现有研究全为欧美家庭。
- 中老年／短鼻犬静息生理数据的设备、姿态和专业参考标准；具体公司是否持有数据须核查。
- 按钮、主人反馈和自动事件标签的偏差与独立复核方法。记录动物数、事件数、标签来源及一致性，不只记录音频条数。
