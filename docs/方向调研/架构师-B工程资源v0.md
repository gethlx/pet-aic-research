# 方向 B 工程资源 v0：老年/慢病犬夜间监测（项圈 IMU，仅活动＋夜间休息）

> 架构师，2026-10-13。**所有链接访问日期 2026-10-13。** "最近推送"＝GitHub API `pushed_at`（UTC），这是近似值，不严格等于 main 分支最后一次提交。许可取自 GitHub API `license.spdx_id` 或 LICENSE/README 原文。⚠️＝有争议或只读到摘要；❓＝未核实。价格只抄页面上看到的数字，**全部未核实**。不修改 `market/`、`research/`。
> 复用等级：**直接**／**改造**／**参考**。本轮未做本地安装或复现。

## 1. 加速度数据处理（活动计数、休息/睡眠检测）

| 资源 | 作用 | 许可 | 最近推送 | 复用 | 说明与来源 |
|---|---|---|---|---|---|
| GGIR（R） | 原始加速度预处理、校准、非佩戴检测、睡眠/休息检测 | Apache-2.0 | 2026-10-12 | **改造** | https://github.com/wadpac/GGIR 。人类睡眠算法（如依赖手腕角度的方法）不能直接套到犬项圈上，需要按犬重新设定阈值 |
| GGIRread | 读取 AX3/GENEActiv/ActiGraph 原始文件 | Apache-2.0 | 2026-09-18 | **直接** | https://github.com/wadpac/GGIRread |
| scikit-digital-health（Python） | 预处理、步态、睡眠、活动流水线 | MIT | 2026-10-05 | **改造** | https://github.com/PfizerRD/scikit-digital-health ；商用友好 |
| pyActigraphy | 休息-活动节律指标（IS/IV/RA 等）、Cole-Kripke 等睡眠算法 | GPL-3.0 | 2026-10-09 | 改造（GPL 有传染性，原型可用，产品要隔离） | https://github.com/ghammad/pyActigraphy |
| agcounts | ActiGraph 活动计数复现 | GPL-3.0 | 2025-03-11 | 改造 | https://github.com/actigraph/agcounts |
| actipy / asleep / stepcount（Oxford） | 读取与处理、睡眠/步数模型（人类） | **Oxford 学术使用许可**（非商用） | 2026-10-06 / 10-09 / 10-09 | **参考** | https://github.com/OxWearables/actipy 等；LICENSE 原文为 "Academic Use Licence" |
| openmovement-python | AX3 .cwa 文件读取 | BSD-2-Clause | 2024-01-12 | 直接 | https://github.com/digitalinteraction/openmovement-python |
| 犬专用：CamiloSR/Dog-Behaviour-Analysis | 基于 Tampere 数据的 notebook，做留一犬交叉验证和 1D-CNN-BiLSTM | 无 LICENSE（默认保留所有权利） | 2026-02-16 | **参考** | https://github.com/CamiloSR/Dog-Behaviour-Analysis ；README 自称复现原文 91.4% 并提升到 92–94%，⚠️未核实，非同行评审 |
| Tampere 数据集自带算法 | 原文信号处理与分类代码（MATLAB） | 随数据集许可 | — | 改造 | 见 §2 |

GitHub 关键词检索（"dog accelerometer"、"canine accelerometer"、"dog behaviour IMU" 等）只找到上表这一个犬专用 repo；"GGIR 式"的犬专用开源库**未发现**（检索不穷尽）。

## 2. 预训练模型与数据基线

| 资源 | 内容 | 许可 | 复用 | 来源 |
|---|---|---|---|---|
| Tampere/Vehkaoja 犬运动数据集 | 45 犬（17 犬重复采集）；项圈+胸背带 ActiGraph GT9X，3D 加速度+陀螺仪，100 Hz；7 类行为，每类约 3 分钟；按录像以 1 秒分辨率标注 | ⚠️**许可有争议**：Mendeley v1（2021-07-02）与 v4（2025-11-05）页面 HTML 里都只出现 CC BY 4.0 链接，本轮**未见 CC BY-SA 字样**；但争议来源未定位，使用前须人工确认版本和 LICENSE 文件 | **直接**（基线），许可确认后 | https://data.mendeley.com/datasets/vxhx934tbn/1 ；https://data.mendeley.com/datasets/vxhx934tbn/4 ；https://doi.org/10.1016/j.dib.2022.107822 ；https://researchportal.tuni.fi/en/datasets/movement-sensor-dataset-for-dog-behavior-classification/ |
| Kumpulainen 等 2021 分类基线 | 原文分类结果（具体指标本轮未读全文❓） | 论文 | 参考 | https://doi.org/10.1016/j.applanim.2021.105393 |
| 公开预训练犬活动模型权重 | **本轮未发现**可下载的预训练权重 | — | — | 检索同 §1 |
| FilterNet（Whistle/Pet Insight） | IMU 行为分类方法 | 无官方开源 | 参考 | https://doi.org/10.3390/ani11061549 ；`research/tooling.md` |

注意：Tampere 数据是在实验场地里按指令完成任务采集的，**没有夜间/居家数据**，也没有专门的老年犬；只能用来训练"静止/活动"类基础分类，夜间休息的有效性需要自采验证。

## 3. 个体基线漂移、变点与异常检测（每晚一个点的休息序列）

| 资源 | 方法 | 许可 | 最近推送 | 复用 | 适配说明 |
|---|---|---|---|---|---|
| ruptures | 离线变点（PELT/Binseg 等） | BSD-2-Clause | 2026-10-06 | **直接** | https://github.com/deepcharles/ruptures ；适合回顾性分析"何时变了" |
| bayesian_changepoint_detection | BOCPD（在线/离线） | MIT | 2026-09-24 | 直接 | https://github.com/hildensia/bayesian_changepoint_detection ；可以给出变点概率，便于"不确定"提示 |
| river | 在线学习与漂移检测（ADWIN、Page-Hinkley 等） | BSD-3-Clause | 2026-10-11 | **直接** | https://github.com/online-ml/river ；适合每晚增量更新 |
| Prophet | 带周期的趋势分解 | MIT | 2026-10-05 | 改造 | https://github.com/facebook/prophet ；能处理周末/工作日效应，但短序列（数周）是否稳定❓ |
| sktime / darts | 预测与异常检测框架 | BSD-3 / Apache-2.0 | 2026-10-12 / 10-12 | 参考 | https://github.com/sktime/sktime ；https://github.com/unit8co/darts |
| PyOD | 多变量异常检测 | BSD-2-Clause | 2026-10-12 | 参考 | https://github.com/yzhao062/pyod ；每晚一个点、维度低，可能用不上 |
| 分析方法参照：FLM | 功能线性模型比较夜间活动曲线 | 论文 | — | 参考 | https://www.nature.com/articles/s41598-019-50623-0 |

建议的规则基线（对应 Issue #13 的 A 臂）：用个体自身前 N 晚的中位数加减 k 倍 MAD 判断偏离。N 和 k 都需要实测确定，**不预设数值**。

## 4. 原型硬件

| 选项 | 类型 | 许可/开放性 | 最近推送 | 价格（页面所见，未核实） | 复用 | 来源 |
|---|---|---|---|---|---|---|
| Axivity AX3 | 研究级原始加速度记录仪；软硬件开源 | 软件 BSD-2；硬件 CC BY 3.0（README 原文） | openmovement repo 2026-08-18 | 搜索摘录 £139–149（官方页），未打开页面核实 | **直接** | https://axivity.com/products ；https://github.com/digitalinteraction/openmovement |
| ActiGraph GT9X Link | Tampere 数据集用的设备，可与公开数据同分布 | 商业 | — | ❓ | 改造 | 数据集页 |
| PawPrint | 开源 9 轴项圈 IMU，SD 卡存储，适合中大型犬 | 文件在 OSF，具体许可❓ | — | 作者页称约 £60/台（看元件价） | 改造 | https://josullivan93.github.io/projects/pawprint_project/ ；作者称初始化软件尚未发布 |
| DoggyLogger | Arduino/SparkFun OpenLog Artemis + ICM-20948 生物记录仪（雪橇犬） | 无 LICENSE（API 为空） | 2025-12-05 | ❓ | 参考 | https://github.com/bhamla-lab/DoggyLogger |
| FitBark | 消费级项圈，有开发者 API（OAuth2）；只给聚合数据：小时分辨率最多 7 天、日分辨率最多 42 天；`time_breakdown` 给出休息/活动/玩耍分钟 | 商业 API，条款见官方 | — | ❓ | **改造**（拿不到原始加速度） | https://www.fitbark.com/dev/ ；OpenAPI 摘录 https://apis.io/apis/fitbark/fitbark-activity-api/ ；已用于 OA 犬夜间研究 https://exa.ai/library/publication/1s611hhqsy2 ⚠️摘要级 |
| MbientLab MetaWear | BLE IMU | SDK 许可 NOASSERTION；Python SDK repo **已归档** | 2023-09-01 | ❓ | 不推荐 | https://github.com/mbientlab/MetaWear-SDK-Python |
| 本地处理机 | Raspberry Pi 5 8GB | — | — | CanaKit $125 / Adafruit $200（搜索摘录） | 可选 | https://www.canakit.com/raspberry-pi-5-8gb.html ；https://www.adafruit.com/product/5813 |

## 5. 数据管道与时序存储

| 资源 | 许可 | 最近推送 | 复用 | 说明 |
|---|---|---|---|---|
| Parquet 文件 + DuckDB | DuckDB MIT | 2026-10-13 | **直接** | https://github.com/duckdb/duckdb ；原始 100 Hz 数据按犬/夜分区写成 Parquet；原型阶段不需要服务器 |
| TimescaleDB | Apache-2.0 与 Timescale License 混合（LICENSE 原文） | 2026-10-13 | 改造 | https://github.com/timescale/timescaledb ；部分功能受 TSL 约束，商用前要核 |
| InfluxDB | Apache-2.0 | 2026-10-12 | 改造 | https://github.com/influxdata/influxdb |
| QuestDB | Apache-2.0 | 2026-10-13 | 改造 | https://github.com/questdb/questdb |

建议流程：设备原始文件（.cwa 或 CSV）→ GGIRread 或 openmovement-python 读取 → 校准与非佩戴检测（GGIR 思路）→ 计算每分钟活动量 → 夜间窗口内的休息比例和觉醒次数 → 每晚一行特征写入 DuckDB → 用规则基线、river/BOCPD 判断偏离 → 输出报告。

## 推荐的最小技术栈（v0）
- **硬件**：Axivity AX3 × 5–10 台（开源、能拿到原始数据、GGIR 生态支持）；FitBark 只作对照，或用于验证"聚合数据是否够用"。
- **处理**：GGIRread + scikit-digital-health（MIT）为主，pyActigraphy（GPL）仅在研究中用于节律指标。
- **模型**：用 Tampere 数据训练"静止/活动"基础分类器，按犬分组交叉验证；夜间休息先用阈值规则。
- **偏离检测**：中位数 ± MAD 规则基线 → ruptures（回顾）+ river 或 BOCPD（在线）。
- **存储**：Parquet + DuckDB。
- **许可红线**：不用 OxWearables（学术许可）；Tampere 许可确认前只做内部研究。

## 待核清单
1. Tampere 许可争议的来源，以及 v1–v4 之间的差异。
2. AX3 页面价格与交货期。
3. PawPrint 在 OSF 上的许可。
4. FitBark API 条款中是否允许研究或商用二次使用。
5. Kumpulainen 原文的指标与划分方式。
