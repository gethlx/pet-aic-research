# datasets · 数据库与数据集指引

> 硬字段：license 与商用可行性。研究可用 ≠ 产品可用。无明确 license 标 ❓。每周增量。

## 生物声学数据集

| 数据集 | 模态 | 规模/覆盖 | License 与商用可行性 | 获取 |
|---|---|---|---|---|
| Xeno-canto | 鸟类等音频 | 全球众包，数十万条 | CC 系（逐条确认，部分禁商用） | xeno-canto.org |
| Watkins Marine Mammal Sound Database | 海洋哺乳动物 | 1700+ 录音 | 学术使用为主，商用需确认 ❓ | Watkins 库 |
| Animal Sound Archive（MfN Berlin） | 多物种 | 历史档案级 | 学术使用 ❓商用 | 動物音檔庫 |
| ESP alp-data | 统一接口 | 35+ 生物声学数据集（鸟/鲸/灵长/昆虫/无尾目） | 开源 Python 包，随源数据 license | github.com/earthspecies/alp |
| U-M 犬吠数据集（74 只，14 情境，墨西哥采集） | 犬吠音频 | 论文配套 | 论文公开但数据集获取方式需确认 ❓ | arXiv:2404.18739 联系作者 |

## 行为与生理数据

| 资源 | 模态 | 说明 | License |
|---|---|---|---|
| BEANS benchmark | 音频分类 | 生物声学分类标准基准（ESP 维护） | 开源 |
| BEBE benchmark | IMU/ movement | 动物运动 bio-logger 基准 | 开源 |
| Banfield/Pet Insight 模式参照 | EHR + IMU | 10 万+ 犬病历与加速度计联动——**数据不公开，模式可参照**（自建数据飞轮的行业标杆） | 私有（模式参照） |

## 关键缺口（招新数据的方向）

- 犬/猫**家庭真实场景**多模态数据（音频+视频+IMU 同步、带主人标注）——公开数据集几乎空白，是自建护城河
- 猫叫意图的**中文家庭环境**数据——现有研究均为欧美语境外家庭
- 中老年犬/短鼻犬夜间生理基线数据（ Moonback、PetPace 在做但不开源）

## 每周增量说明

新数据集追加到对应表尾；license 变更在原条目顶部加更新标记，并同步 updates-log。
