# tooling · 模型与工程资源

> 2026-10-01纠正。代码、权重、数据及依赖分别核查；当前表中“待核”不能用于商用判断。最新commit日期不是可用性证明。

## 模型

| 资源 | 任务／形态 | 代码许可 | 权重／数据与商用 | 当前证据与可用性 |
|---|---|---|---|---|
| NatureLM-audio | BEATs＋Llama3.1-8B相关生物声学模型 | ✅[当前MIT LICENSE](https://github.com/earthspecies/NatureLM-audio/blob/main/LICENSE) | ✅[所列权重CC-BY-NC-SA-4.0](https://huggingface.co/EarthSpeciesProject/NatureLM-audio)，不据此允许直接商用；[数据逐记录许可](https://projects.earthspecies.org/naturelm-audio/datasets.html)；基座／依赖另查 | 核查2026-10-05：✅论文已发表于[ICLR 2025](https://openreview.net/forum?id=hJVdwBpWjt)；repo v1.0.2、最新提交2026-04-16（#18），窗口内无变化；模型卡明示个体识别未测试、call-type/生活阶段仅鸟类测试过、无犬猫任务；官方README引用合并法（[arXiv 2511.05171](https://arxiv.org/abs/2511.05171)，merging_alpha 0.4–0.6）。未本地复现，犬猫适用性待测 |
| Dog2vec | 犬吠专用SSL表征 | [实验室页](https://uta-acl2.github.io/research.html)称有code链接，repo与许可待核 | 权重／数据待核 | ⚠️[Interspeech 2025](https://uta-acl2.github.io/research.html)（pp.1698–1702）自述6000+小时犬吠视频预训练，bark类型/声音事件任务相对+8.2%；未读全文，未复现，核查2026-10-05 |
| AVES／BirdAVES | 动物声音表征 | [ESP仓库入口](https://github.com/earthspecies)，具体repo／版本许可待核 | 权重和数据待核；撤回“开源即可商用”推定 | 维护日期及原“鸟类+20%”对应任务待核 |
| wav2vec2 | 人类语音预训练迁移 | [fairseq](https://github.com/facebookresearch/fairseq)／[HF模型入口](https://huggingface.co/models?search=wav2vec2)，具体实现许可待核 | 实现许可不覆盖所有checkpoint；具体权重／数据待核 | 犬吠论文方法可借鉴，资源版本和复现待核 |
| BEATs | 音频编码器 | [Microsoft入口](https://github.com/microsoft/unilm/tree/master/beats)，许可待核 | checkpoint及依赖待核 | 不以代码或论文存在推定商业许可 |
| FilterNet | IMU行为分类方法 | [论文](https://doi.org/10.3390/ani11061549)，无已确认官方开源repo | 无可直接取得部署资源证明 | 方法可借鉴，需自研复现；生产规模不是本项目验收 |

## 工具线索

| 工具 | 用途 | 原始入口／许可与版本状态 |
|---|---|---|
| Voxaboxen | 动物声音标注 | [ESP组织](https://github.com/earthspecies)，具体repo、license、维护日期待核 |
| Biodenoising | 生物声学去噪 | [ESP组织](https://github.com/earthspecies)，具体repo、license、维护日期待核 |
| BEANS／BEBE评测脚本 | 基准评估 | [ESP组织](https://github.com/earthspecies)，脚本与子数据许可分开核对 |
| Hugging Face Audio栈 | 数据与训练 | [HF文档](https://huggingface.co/docs)，具体包／版本许可待核，不笼统写Apache-2.0系 |

## 传感器选型问题

| 方案 | 可研究任务 | 必须核验的宠物适配条件 |
|---|---|---|
| IMU | 行为分类 | 位置、项圈松紧、犬种、采样／功耗、人与宠物接触混淆；不能泛称佩戴位置无影响 |
| 声学生理检测 | 脉搏／HRV | PetPace官方机制说明，具体型号和独立性能待核 |
| PPG | 生理候选 | 毛发、贴合、肤色及运动伪影；不能用PetPace当PPG实证 |
| 60GHz雷达 | 静息呼吸／心率候选 | 姿态、遮挡、距离、多宠和织物条件，不能泛称穿织物无碍 |
| 麦克风 | 声学分类 | 风／摩擦／电视人声、多宠声源归属及未见家庭测试 |
| 摄像头 | 行为／如厕 | 夜视、遮挡、多宠识别、人像隐私和数据可导出性 |
| GPS／通信 | 户外定位 | 具体模块、功耗、覆盖与无线规则，不与健康识别性能混用 |

首次复现前固定硬件／软件版本、任务样本、基线与许可。参数或厂商宣传不替代宠物场景实测。
