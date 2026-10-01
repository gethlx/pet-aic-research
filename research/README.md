# research/ · 学术界与工程技术界研究进展与资源包

> 收集章程（charter）。更新频率：每周一次（见仓库根 README）。标注规范沿用全仓约定：✅ 已核实 / ⚠️ 自报 / ❓ 未确认。

## 1. 本文件夹的定位

**research/ 是方法与供给侧。** 它回答的问题是：实现四层路线（感知/表达/推理/反向，见 `docs/03-roadmap.md`）所需的**科学证据、数据资产、工程工具与硬件供给**，各自成熟到什么程度、能不能直接用。

与 `market/` 的分工：market 管「什么被商业验证」，research 管「什么被科学证明、什么资源可拿」。每个市场现象应回溯到这里的文献解释（如翻译器精度翻车 → 个体基线与评估方法学），每个研究进展应前瞻市场机会（如 NatureLM 开源 → 低成本意图引擎）。

## 2. 四条资源线

### 2.1 `papers.md` — 论文追踪

- **分组方式**：按四层路线分组（①感知：声学分类/视觉表情与疼痛/生理监测/行为分类；②表达：AIC 与动物认知；③推理：多模态融合与评估方法学；④反向：犬猫听觉与条件反射）。
- **时间范围**：以 2023–2026 为主；2000 年代奠基文献只收录已进 `docs/04-references.md` 的，不追老。
- **每条字段**：标题 / venue / 年份 / 一句话结论 / 对本项目的可用性评级（直接可用 / 方法可借鉴 / 仅背景）。
- **来源**：arXiv（cs.SD、eess.AS、q-bio.NC）、bioRxiv、ACM ACI/CHI/IMWUT、Nature/Science 系、Veterinary 期刊（AJVR、JAVMA、Veterinary Dermatology）。
- **红线**：未经同行评审的 preprint 必须标 ⚠️，标注「待评审」。

### 2.2 `datasets.md` — 数据库与数据集指引

- **收录对象**：公开生物声学数据集（Xeno-canto、Watkins Marine Mammal、Animal Sound Archive、ESP 的 alp-data 统一接口等）、行为基准（BEANS/BEBE）、犬吠/喵叫专门数据集、可参照的宠物电子病历联动模式（Banfield/Pet Insight）。
- **硬字段：license 与商用可行性**。研究可用 ≠ 产品可用——每个数据集必须标注许可证类型、是否允许商用、引用要求。无明确 license 的标 ❓。
- **格式字段**：模态（audio/video/IMU/生理）、规模、标注质量、获取方式。

### 2.3 `tooling.md` — 工程资源包

- **模型**：优先收录已开源且有活跃维护的（NatureLM-audio、AVES/BirdAVES、wav2vec2、BEATs、FilterNet 类行为分类参考实现）。
- **工具链**：标注（Voxaboxen）、去噪（Biodenoising）、基准（BEANS/BEBE 评测脚本）。
- **传感器选型笔记**：加速度计 / PPG / 毫米波雷达 / 麦克风阵列的技术成熟度、功耗、宠物场景适配要点。
- **硬字段**：repo 活跃度（最近 commit）、license、是否可直接商用。

### 2.4 `supply-chain.md` — 供应链信息

- **范围**：
  - MEMS 加速度计/IMU（Bosch、ADI、TDK/InvenSense 等格局与代表型号）
  - 毫米波雷达（Infineon、TI、Calterah 加特兰等，60GHz 生命体征方案）
  - PPG/体温等生理传感
  - 低功耗通信与电池（BLE SoC、LoRa、纽扣电池/锂聚合物方案）
  - 宠物智能硬件代工产业带（深圳/宁波等，公开报道层面）
  - 认证要求：FCC/CE/UKCA、宠物穿戴材料安全（可舔咬）、无线法规
- **红线**：只收录公开可验证信息（厂商官网、Datasheet、行业报道）；不收录需 NDA 的报价；价格信息只记量级与趋势。
- **更新触发**：新品、涨价/缺货、国产替代进展、法规变化。

## 3. 文件结构

| 文件 | 内容 | 更新方式 |
|---|---|---|
| `papers.md` | 论文追踪（按四层路线分组） | 每周增量 |
| `datasets.md` | 数据集与数据库指引（含 license 硬字段） | 每周增量 |
| `tooling.md` | 开源模型与工程工具包 | 每周增量 |
| `supply-chain.md` | 传感器/代工/认证供应链信息 | 每周增量 |
| `updates-log.md` | 每周增量日志 + 存疑区 | 每周追加，倒序 |

## 4. 更新规则

- 只做增量，新条目必须附来源链接与日期，并按 ✅⚠️❓ 标注。
- 每周扫描为空时，仍在 updates-log 记录「本周扫描无实质新增」，保持审计轨迹。
- 论文被撤稿/数据集改 license 等逆向变化，须在原条目顶部加显眼的更新标记，不静默修改。
