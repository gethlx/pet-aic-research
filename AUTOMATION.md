# AUTOMATION · 每周自动化执行指令

> 本文档是两条每周自动化的**执行指令原文镜像**（人读版）。修改本文档必须同步修改对应自动化指令，反之亦然；不一致时以本文档为准并立即修正自动化。
>
> 依据文件：收集章程 `market/README.md`、`research/README.md`；信源清单 `market/sources.md`、`research/sources.md`；入库闸门 `VETTING.md`；技术框架 `docs/03-roadmap.md`（四层路线）。

## 调度总览

| 任务 | 自动化名称 | 时间（Asia/Shanghai） | 产出 | 提交信息格式 |
|---|---|---|---|---|
| 任务一 | AIC 市场侧每周扫描 | 每周一 09:00 | `market/` 增量 | `weekly-market: <YYYY-MM-DD>` |
| 任务二 | AIC 学术工程侧每周扫描 | 每周一 10:00 | `research/` 增量 | `weekly-research: <YYYY-MM-DD>` |

两任务独立运行、独立提交、互不阻塞；任一失败不影响另一条。工作目录均为 `/Users/larry/PET/pet-aic-research`，远程 `origin = git@github.com:gethlx/pet-aic-research.git`，主分支 `main`。

## 共同规矩（两任务均适用）

1. **先读规矩再干活**：依次读 `VETTING.md`（闸门）→ 对应章程 README → 对应 `sources.md`（信源清单）。
2. **入库必过闸门**：溯源 → 交叉验证（2 个独立来源，同稿转载不算）→ 真伪判定（✅/⚠️/❓）→ 价值评分（新颖性/可比性/信号强度/决策相关性，4 项×0–2 分）。**≥5 分入库，3–4 分观察名单，≤2 分丢弃留痕。**
3. **标注铁律**：所有入库条目附来源链接、日期、✅⚠️❓ 标注；不可溯源的爆料一律 ❓，不进主表。
4. **只做增量**：不改写 `docs/` 与 `README.md` 中的历史结论；与既有条目矛盾时走原条目顶部 `> [!UPDATE]` 标记 + 存疑区，不静默覆盖。
5. **周记三段式**：`updates-log.md` 顶部追加 ① 入库清单（条目+来源+日期+标注）② 筛掉清单（筛了什么、为什么）③ 存疑区。**扫描无实质新增也必须记录**，并列出本轮扫描过的信源清单——审计轨迹不可断。
6. **新信源**：发现新信源加入对应 `sources.md` 的「候选信源」小节并注明理由，验证一轮后转正。
7. **收尾**：`git status` 确认无遗漏 → `git add -A` → 按上表格式 commit → `git push origin main`。

---

## 任务一 · AIC 市场侧每周扫描

**目标**：追踪五类市场主体的产品、商业与口碑动态，维护可比的竞品矩阵，识别宣传-实测落差与可借鉴/可避坑信号。

**扫描范围（按 `market/sources.md` 逐源执行，中英文关键词分别检索）**：

| 品类圈 | 内容 |
|---|---|
| M1 | AI 宠物翻译/交互硬件 |
| M2 | 宠物健康监测硬件（穿戴/窝垫/摄像头/猫砂盆） |
| M3 | 宠物声学/视觉 AI 软件 App |
| M4 | AIC 按钮板与训练生态 |
| M5 | 畜牧声学/行为监测（**对照系**，只记里程碑） |

**信息源**：行业媒体（36氪、猎云网、宠业家、PetAge、PET NEWS 等）→ 融资工商库（企查查、亿欧、Crunchbase）→ 电商与口碑（Amazon 类目榜、小红书/抖音、Reddit、Trustpilot）→ 展会众筹（CES、亚宠展、Interzoo、Kickstarter）→ 官方渠道（一律 ⚠️ 自报）。公司监测名单与关键词见 `market/sources.md`。

**输出**：
1. `market/products-matrix.md`：新增行或修订字段（七维度：路线归属/传感器方案/AI 方案/精度口径官方 vs 实测/落差/价格与商业模式/销量渠道融资）。
2. 重大变化的新产品：`market/profiles/` 新建拆解文件。
3. 精度落差 > 20 个百分点：同步登记 `market/insights.md` 落差榜。
4. `market/updates-log.md`：三段式周记 + 存疑区 + 新信源候选。

---

## 任务二 · AIC 学术工程侧每周扫描

**目标**：追踪四层技术路线（①感知②表达③推理④反向）的学术证据与工程资源更新，维护论文、数据集、开源工具、供应链四条资源线。

**扫描范围（按 `research/sources.md` 逐源执行）**：

| 线 | 信源 | 关注点 |
|---|---|---|
| 论文 | arXiv cs.SD/eess.AS/q-bio.NC、bioRxiv、ACM ACI/CHI/IMWUT、兽医期刊（AJVR/JAVMA/Vet Dermatology）、Science/Nature/PLOS 系 | 按四层路线归类；preprint 一律 ⚠️ 待评审 |
| 数据集 | Xeno-canto、Hugging Face datasets、ESP alp/BEANS/BEBE | **license 与商用可行性是硬字段**；license 变更走原条目顶部更新标记 |
| 代码与模型 | GitHub（topic: animal-bioacoustics 等）、ESP 仓库、Hugging Face models | 新 release、repo 活跃度（最近 commit）、license |
| 供应链 | Bosch/ADI/TDK/Infineon/TI/Calterah newsroom、Digi-Key/Mouser 新品、EE Times、FCC/CE 认证记录 | 传感器新品、涨价/缺货、国产替代、法规变化（健康宣称的医疗器械边界为常设风险项） |

**输出**：
1. `research/papers.md`：新论文追加至对应四层分组表尾（标题/venue/年份/一句话结论/可用性评级）。
2. `research/datasets.md` / `tooling.md` / `supply-chain.md`：按各自硬字段增量更新。
3. `research/updates-log.md`：三段式周记 + 存疑区 + 新信源候选。

---

## 变更记录

- 2026-10-01：拆分原单条自动化为两条独立任务（市场侧 09:00 / 学术侧 10:00），执行指令落成本文档。
