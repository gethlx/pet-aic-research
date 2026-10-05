# research updates-log · 每周增量日志

> 倒序追加；执行字段与成功水位按[AUTOMATION](../AUTOMATION.md)。纠错记录与定时扫描分开，初始盘点不计完整扫描。

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
