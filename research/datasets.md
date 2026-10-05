# datasets · 数据资产与获取条件

> 2026-10-01纠正。数据许可、接口代码许可、模型权重分别核验；没有明确条款不推定商用。规模和训练标签不是独立真值。

| 资源 | 模态／范围 | 获取与规模 | 数据许可／商用条件 | 核查状态 |
|---|---|---|---|---|
| Xeno-canto | 生物声学，以鸟类等为方法参照 | [官方入口](https://xeno-canto.org)，当前规模待核 | 原记录CC系，逐录音条款与署名要求待核；不整库认定商用 | ❓本轮未逐条审许可 |
| Watkins Marine Mammal Sound Database | 海洋哺乳动物声学 | [数据库入口](https://cis.whoi.edu/science/B/whalesounds/index.cfm)，当前规模待核；撤回未核实1700+数量 | 具体许可／授权待核 | 方法参照，不当犬猫数据 |
| Animal Sound Archive | 多物种声音 | [MfN入口](https://www.tierstimmenarchiv.de)，规模／获取待核 | 数据许可和商用待核 | ❓待读条款 |
| ESP alp接口 | 多数据集统一接口 | [repo](https://github.com/earthspecies/alp)，原35+规模待版本核对 | 包代码不授权子数据；逐源许可核对 | ❓不能当现成可商用数据 |
| U-M犬吠数据 | 74犬、主要三犬种；音频 | ✅[原论文末尾](https://aclanthology.org/2024.lrec-main.1432.pdf)说明数据和基线可向作者申请；非直接公开下载 | 分发、训练及商用授权待核 | 核查2026-10-01；不是“论文未说明获取” |
| DogSpeak | 犬吠音频，社交媒体in-the-wild | ✅[官方repo README](https://github.com/Lekhak123/A-Data-driven-Approach-to-the-Longitudinal-Study-of-Canine-Vocal-Pattern-Development)自述：77,202 Barkseqs、33.162小时、156犬、5品种，含犬ID/性别/品种标签；[HF数据集](https://huggingface.co/datasets/ArlingtonCL2/DogSpeak_Dataset)页面条款待复核 | 官方自述CC BY-NC-SA 4.0；HF页待复核；不可商用 | 核查2026-10-05；[ACM MM 2025论文](https://doi.org/10.1145/3746027.3758298)未读全文，跨犬划分待核 |
| EmotionalCanines | 犬吠情绪（arousal/valence） | 官方称1,400段、仅哈士奇/柴犬；[repo](https://github.com/tmdang1101/EmotionalCanines)；标签框架自述可规模化 | 许可待核 | ⚠️[ACM MM 2025论文](https://doi.org/10.1145/3746027.3758286)未读全文，核查2026-10-05 |
| Canine Age Transition | 犬吠纵向（幼犬→成犬） | ✅[官方repo README](https://github.com/Lekhak123/A-Data-driven-Approach-to-the-Longitudinal-Study-of-Canine-Vocal-Pattern-Development)自述：79,142 Bark Units／55,718 seqs／11.4小时／125犬／6品种，含月龄纵向元数据；[HF数据集](https://huggingface.co/datasets/ArlingtonCL2/Canine-Age-Transition-Vocalization-Dataset) | ✅README自述CC BY-NC-SA 4.0，不可商用；HF页待复核 | 核查2026-10-05；⚠️官方明示与DogSpeak存在重叠个体，联合使用须查个体泄漏；[论文](https://doi.org/10.1145/3746027.3758175)未读全文 |
| BEANS | 生物声学基准 | [ESP组织](https://github.com/earthspecies)，具体版本与子集待核 | 评测代码与每个子数据许可分开，不能只写开源 | ❓待核 |
| BEBE | 动物运动／bio-logger基准 | [ESP组织](https://github.com/earthspecies)，具体版本与物种待核 | 同上，商用待核 | ❓待核 |
| Banfield／Pet Insight模式 | EHR＋IMU | [行为论文入口](https://doi.org/10.3390/ani11061549)，项目规模与单篇分析样本分开 | 数据非公开获取，模式参照；合作授权未知 | 不作为可下载资源 |
| NatureLM训练数据 | 音频／文本，多类群 | ✅[官方数据说明](https://projects.earthspecies.org/naturelm-audio/datasets.html) | 含逐记录CC BY-NC、个人／学术用途或unknown等标签；不能整库推定商用 | 核查2026-10-01；宠物标签和训练适用性另评估 |

## 待调查缺口

- 家庭音频、视频、IMU同步数据的可取得性、宠物数量、跨家庭划分和标注成本，不能未穷尽检索就称“几乎空白／护城河”。
- 中国家庭环境的噪声、主人语言和使用习惯可能影响泛化；不能据此认定猫叫存在“中文意图体系”，也不认定现有研究全为欧美家庭。
- 中老年／短鼻犬静息生理数据的设备、姿态和专业参考标准；具体公司是否持有数据须核查。
- 按钮、主人反馈和自动事件标签的偏差与独立复核方法。记录动物数、事件数、标签来源及一致性，不只记录音频条数。
