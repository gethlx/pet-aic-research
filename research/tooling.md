# tooling · 开源模型与工程工具包

> 优先收录开源 + 活跃维护。硬字段：repo 活跃度、license、商用可行性。每周增量。

## 模型

| 模型/仓库 | 用途 | 基座与形态 | License | 活跃度 |
|---|---|---|---|---|
| NatureLM-audio（earthspecies） | 动物音频理解/问答 | BEATs 编码器 + Llama 3.1-8B Instruct，LoRA 微调 | 开源（见 repo；Llama 3.1 社区许可之上需注意组合条款） | demo v1.1，2026-04 更新 ✅ |
| AVES / BirdAVES（earthspecies） | 自监督动物声音表征 | 音频编码器，跨物种分类；BirdAVES 鸟类 +20% | 开源 | 稳定 |
| wav2vec2（Meta/fairseq 或 HF） | 语音预训练迁移基座 | 自监督语音模型——U-M 犬吠研究即基于此 | MIT（fairseq）/ HF 实现 | 维护中 |
| BEATs（Microsoft） | 音频预训练 | NatureLM 的音频编码器来源 | 需查 ❓ | 维护中 |
| FilterNet（Mars Pet Insight） | IMU 行为分类参考 | 论文公开方法，无官方开源 repo——需自研复现 | 论文方法可借鉴 | — |

## 工具链

| 工具 | 用途 | 出处 | License |
|---|---|---|---|
| Voxaboxen | 动物叫声标注平台（协作标注） | ESP | 开源 |
| Biodenoising | 生物声学去噪（无需干净训练数据） | ESP | 开源 |
| BEANS/BEBE 评测脚本 | 标准基准评测 | ESP | 开源 |
| Hugging Face Audio 工具栈 | 数据管道与训练 | HF | Apache-2.0 系 |

## 传感器选型笔记（工程向）

| 传感 | 适用层 | 成熟度 | 宠物场景要点 |
|---|---|---|---|
| 三轴加速度计 | ①行为分类 | **最高**（Whistle 已验证量产） | 采样率与功耗平衡；项圈佩戴位置对精度影响小（已验证） |
| PPG 心率/HRV | ①生理 | 中（医疗级项圈已用，毛发/运动伪影是难点） | 短毛部位贴合；夜间静息场景最稳 |
| 毫米波雷达 60GHz | ①呼吸/心率（非接触） | 中（Moonback 窝垫、康波等在用） | 窝垫场景最稳（静息+固定位置）；穿窝垫织物无碍 |
| MEMS 麦克风阵列 | ①③声学 | 高（萌小译、SoundTalks 已量产两极验证） | 项圈形态需处理摩擦/风噪；多宠家庭声源分离是难点 |
| 摄像头 + 视觉 | ①行为/排泄 | 高（PETKIT Purobot 已量产） | 隐私合规是产品红线；夜视红外 |
| GPS/电子围栏 | ①户外 | 成熟 | 续航是主要约束 |

## 每周增量说明

新模型/工具追加表尾，登记 repo 最近 commit 日期；供应链行情变化移步 [supply-chain.md](./supply-chain.md)。
