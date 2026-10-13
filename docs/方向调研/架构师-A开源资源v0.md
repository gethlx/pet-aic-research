# 方向 A 开源资源 v0：家用摄像头对宠物犬全生命周期（幼犬→老年犬）的视频理解

> 架构师，2026-10-13。**只做调研，不含方案。** 所有链接访问日期均为 2026-10-13。代码许可取自 GitHub API `license.spdx_id`；模型许可取自 Hugging Face API `cardData.license` 或 LICENSE 原文。"最近维护"＝GitHub `pushed_at` 或 HF `lastModified`（UTC，是近似值）。⚠️＝未核实或只读到摘要。可商用一栏：是 / 否 / 不明。复用等级：直接 / 改造 / 参考。中国市场另行评估。

## 0. 许可陷阱速览（最重要）
| 陷阱 | 说明 | 来源 |
|---|---|---|
| **Ultralytics YOLO = AGPL-3.0** | 网络服务和闭源产品也要开源，否则需要买企业许可；YOLOv10 也是 AGPL-3.0，YOLOv9 是 GPL-3.0 | https://github.com/ultralytics/ultralytics ；https://github.com/THU-MIG/yolov10 ；https://github.com/WongKinYiu/yolov9 |
| **SuperAnimal 权重仅限学术非商用** | 框架 DeepLabCut 是 LGPL-3.0，但权重是 Modified MIT 加上"academic, non-commercial purposes only" | https://huggingface.co/mwmathis/DeepLabCutModelZoo-SuperAnimal-Quadruped |
| **同一模型家族，不同尺寸许可不同** | Qwen2.5-VL-7B 是 apache-2.0；**3B 是 Qwen RESEARCH LICENSE**；72B 是 Qwen LICENSE（月活超过 1 亿要另申请） | https://huggingface.co/Qwen/Qwen2.5-VL-3B-Instruct/raw/main/LICENSE ；https://huggingface.co/Qwen/Qwen2.5-VL-72B-Instruct/raw/main/LICENSE ；https://huggingface.co/Qwen/Qwen2.5-VL-7B-Instruct |
| **标注许可 ≠ 视频版权** | MammalNet 标注是 CC BY，但视频来自 YouTube；AP-10K 的 repo 是 CC-BY-4.0，底图来源条款❓ | https://mammal-net.github.io/ ；https://github.com/AlexTheBad/AP-10K |
| **从短视频平台爬取的数据** | TP-CanineNet 的 Alone-Dog 数据集来自抖音检索下载，商用和再分发风险高 | https://pmc.ncbi.nlm.nih.gov/articles/PMC13360469/ |
| **仓库没写许可 ≠ 可以用** | APT-36K、Animal Kingdom 的 repo 没有 SPDX 许可；核查员记录 Animal Kingdom 申请条款为仅限非商用科研 | https://github.com/pandorgan/APT-36K ；https://github.com/sutdcv/Animal-Kingdom ；`核查员/grok-dataset.md` |
| 权重和代码分开授权 | 例如 InternVL 代码是 MIT、InternVL3-8B 权重是 apache-2.0，但它的 LLM 基座和视觉编码器的许可要逐层查⚠️ | https://github.com/OpenGVLab/InternVL ；https://huggingface.co/OpenGVLab/InternVL3-8B |

## 1. 检测 / 跟踪
| 资源 | 许可 | 可商用 | 最近维护 | 复用 | 说明 |
|---|---|---|---|---|---|
| MegaDetector | MIT | 是 | 2026-10-12 | 改造 | https://github.com/agentmorris/MegaDetector ；训练数据是相机陷阱画面，室内/家居场景的效果⚠️未测 |
| RT-DETR / RT-DETRv2 | Apache-2.0（代码和 HF 权重） | 是 | repo 2026-10-09；HF 2025-02-06 | **直接** | https://github.com/lyuwenyu/RT-DETR ；https://huggingface.co/PekingU/rtdetr_v2_r50vd ；COCO 类别里有 dog，可替代 YOLO |
| YOLOX | Apache-2.0 | 是 | 2025-06-08 | 直接 | https://github.com/Megvii-BaseDetection/YOLOX （旷视，国内） |
| PaddleDetection | Apache-2.0 | 是（单个预训练权重的许可⚠️要另查） | 2026-05-28 | 直接 | https://github.com/PaddlePaddle/PaddleDetection （百度，国内） |
| MMDetection | Apache-2.0 | 是 | 2024-08-21（更新放缓） | 改造 | https://github.com/open-mmlab/mmdetection |
| Ultralytics YOLO / YOLOv10 / YOLOv9 | AGPL / AGPL / GPL | **需商业许可或开源** | 2026-10-13 / 2025-03-14 / 2024-08-09 | 仅限原型 | 见 §0 |
| Grounding DINO / Grounded-SAM-2 | Apache-2.0 | 是（权重⚠️另查） | 2024-08-12 / 2025-11-11 | 改造（开放词表检测，用于辅助标注） | https://github.com/IDEA-Research/GroundingDINO ；https://github.com/IDEA-Research/Grounded-SAM-2 |
| SAM2 | Apache-2.0 | 是 | 2026-05-30 | 改造（分割 / 视频跟踪） | https://github.com/facebookresearch/sam2 |
| supervision | MIT | 是 | 2026-10-13 | 直接（跟踪、区域计数、可视化） | https://github.com/roboflow/supervision |

## 2. 动物姿态
| 资源 | 许可 | 可商用 | 最近维护 | 复用 | 说明 |
|---|---|---|---|---|---|
| MMPose（含 AP-10K / APT-36K 配置） | Apache-2.0 | 代码是；数据集训练出的权重要看数据许可 | 2025-08-04 | 改造 | https://github.com/open-mmlab/mmpose |
| ViTPose | Apache-2.0 | 代码是（权重和预训练数据⚠️另查） | 2025-12-25 | 改造 | https://github.com/ViTAE-Transformer/ViTPose |
| AP-10K | CC-BY-4.0（repo） | 不明（底图来源⚠️） | 2023-01-05 | 改造 | https://github.com/AlexTheBad/AP-10K |
| APT-36K | 无 SPDX | 不明 | 2023-07-06 | 参考 | https://github.com/pandorgan/APT-36K |
| DeepLabCut + SuperAnimal | LGPL-3.0 / 权重非商用 | 框架是，权重**否** | 2026-10-13 | 研究可直接用 | 见 §0 |
| PRS Group28 室内狗骨架与行为（HF） | 许可❓ | 不明 | ⚠️ | 参考 | https://huggingface.co/datasets/melodyyyyy123/PRS-Group28-data ；室内 CCTV、单狗单人，7 类行为 + 17 个关键点，与 APT-36K 对齐；规模未读 |

## 3. 犬行为 / 动作数据集
| 资源 | 内容 | 许可 | 可商用 | 维护 | 复用 | 来源 |
|---|---|---|---|---|---|---|
| Animal Kingdom | 野外多物种，含动作定位、动作识别、姿态 | 申请条款为非商用（核查员） | 否 | 2024-12-07 | 参考 | https://github.com/sutdcv/Animal-Kingdom ；`核查员/grok-dataset.md` |
| MammalNet | 173 类哺乳动物，12 类高层行为 | 标注 CC BY；repo MIT；视频来自 YouTube | 标注可用，视频**不明** | ⚠️ | 参考 | https://mammal-net.github.io/ ；https://github.com/Vision-CAIR/MammalNet |
| EgoPet | 宠物第一人称视角（不是家用摄像头视角） | README 写"MIT licence"；API 为 NOASSERTION；视频来源条款⚠️ | 不明 | 2025-12-15 | 参考 | https://github.com/DannyTran123/egopet |
| Alone-Dog（TP-CanineNet） | 独处犬异常行为，摘要称 430 个样本 + 60 个真值标注样本，来自抖音 | 无许可，平台视频 | **否 / 高风险** | 论文 | 参考（方法：弱监督视频异常检测） | https://pmc.ncbi.nlm.nih.gov/articles/PMC13360469/ |
| Kaggle 室内俯拍单犬视频 | 64 段，1.42 GB，单只犬，**没有标签** | Kaggle 页许可⚠️未读 | 不明 | ⚠️ | 参考（自监督学习） | https://www.kaggle.com/datasets/umuttuygurr/videosdog ；中文转载 https://www.7zcode.com/25386.html |
| Mobiusi 家庭宠物危险行为数据集 | 宣称 500 条、1.5 GB、来自真实家庭摄像头 | 商业数据集，条款❓ | 可买⚠️ | ⚠️ | 参考 / 采购 | https://www.mobiusi.com/datasets/a88c859c10c746df57e12036f0697e02 |
| DogCentric、Stanford Dogs、StanfordExtra | 狗背第一人称 / 只有品种 / 静图姿态 | 非商用或底图受限 | 否 | — | 参考 | `核查员/grok-dataset.md` |
| 方法参照：Atif 2023 视频摘要；分离焦虑可穿戴研究 | — | 论文 | — | — | 参考 | https://doi.org/10.3390/s23062892 ；https://www.mdpi.com/1424-8220/22/4/1556 |

**全生命周期缺口**：本轮没找到按年龄段（幼犬、成犬、老年犬）分层的家用摄像头行为数据集；老年犬步态、起卧困难的视频数据**未发现**（检索不穷尽）。

## 4. 视频-语言 / VLM（用于生成说明）
| 模型 | 权重许可 | 可商用 | HF 最近更新 | 复用 | 来源 |
|---|---|---|---|---|---|
| Qwen2.5-VL-7B-Instruct | apache-2.0 | 是 | 2025-04-06 | 改造 | https://huggingface.co/Qwen/Qwen2.5-VL-7B-Instruct ；代码 https://github.com/QwenLM/Qwen2.5-VL （Apache-2.0） |
| Qwen2.5-VL-3B / 72B | Research 许可 / Qwen 许可（月活超 1 亿另申请） | 3B **否**；72B 有条件 | 2025-04 / 2025-06 | 注意 | 见 §0 |
| Qwen3-VL | 代码 Apache-2.0；各尺寸权重许可⚠️逐个查 | 不明 | repo 2026-01-30 | 改造 | https://github.com/QwenLM/Qwen3-VL |
| InternVL3-8B | apache-2.0（权重）；代码 MIT | 是⚠️（基座许可另查） | 2025-09-11 | 改造 | https://huggingface.co/OpenGVLab/InternVL3-8B （上海 AI 实验室） |
| InternVideo | Apache-2.0（代码） | 权重⚠️ | 2026-07-02 | 参考 | https://github.com/OpenGVLab/InternVideo |
| LLaVA-Video-7B-Qwen2 | apache-2.0 | 是⚠️（训练数据条款另查） | 2024-10-25 | 改造 | https://huggingface.co/lmms-lab/LLaVA-Video-7B-Qwen2 ；https://github.com/LLaVA-VL/LLaVA-NeXT |
| MiniCPM-V 4.5 | apache-2.0（HF 卡片） | 是⚠️（以前的版本有自定义许可，要复核） | 2026-08-18 | 改造（端侧友好） | https://huggingface.co/openbmb/MiniCPM-V-4_5 ；https://github.com/OpenBMB/MiniCPM-V （面壁/清华系） |
| VideoLLaMA3-7B | apache-2.0 | 是⚠️ | 2025-09-02 | 改造 | https://huggingface.co/DAMO-NLP-SG/VideoLLaMA3-7B （阿里达摩院） |
| TimeChat（带时间戳定位） | BSD-3-Clause（代码） | 权重⚠️ | 2025-05-08 | 参考 | https://github.com/RenShuhuai-Andy/TimeChat |
| ModelScope 平台 | Apache-2.0（SDK） | 每个模型单独看 | 2026-10-11 | 国内分发渠道 | https://github.com/modelscope/modelscope |

## 5. VLM 幻觉证据（补充）
- **用户侧**：主人抱怨 Furbo 的 AI 聊天会"编造狗在做什么"。这是父代理转述的，**本轮没找到原帖⚠️**。能找到的是 Furbo 误报的原话：订阅试用结束后，一天最多收到 50 条吠叫误报，主人认为是电视声触发的 https://www.reddit.com/r/Dogowners/comments/1k4fmlf/is_the_furbo_dog_camera_worth_it/ ；Furbo 官方也承认外部噪声会被误判为吠叫（`产品专家-用户证据v0.md` A2）。
- **VideoHallucer**：评测了 11 个视频大模型，结论是"多数模型存在显著幻觉"；扩大数据和参数量对外在事实性幻觉帮助有限；共 948 个视频、1,800 个问答对（检索摘录⚠️）。https://github.com/patrick-tssn/VideoHallucer ；https://huggingface.co/papers/2406.16338
- **EventHallusion**：研究由语言先验导致的事件幻觉，包含 Pet&Animal 领域；400 个视频、711 个问题（摘录⚠️）。https://arxiv.org/abs/2409.16597
- **Animal-Bench（NeurIPS 2024）**：13 项以动物为中心的任务，包括应激/疼痛检测；评测了 8 个视频模型。在**动作定位和动作计数上接近随机猜测**；在"物体是否存在"任务上倾向答"yes"，作者称之为严重幻觉。https://proceedings.neurips.cc/paper_files/paper/2024/file/8fa604a81e5a236e2f38e917109571a3-Paper-Conference.pdf ；代码 https://github.com/PRIS-CV/Animal-Bench （许可❓）
- 仓库已有的负面证据：通用 chatbot 给猫做 FGS 疼痛评分，一致性不可接受（`research/papers.md`；https://doi.org/10.1038/s41598-025-27404-z ）。

## 6. 把说明落到可检验证据上（grounding）的开放工具
| 工具 | 作用 | 许可 | 来源 |
|---|---|---|---|
| supervision | 检测框、跟踪 ID、区域进出事件 → 带时间戳的结构化证据 | MIT | https://github.com/roboflow/supervision |
| Grounding DINO / Grounded-SAM-2 | 用文字描述找框，校验"VLM 说的东西是否真的在画面里" | Apache-2.0 | 同 §1 |
| TimeChat | 输出带时间戳的视频描述 | BSD-3 | https://github.com/RenShuhuai-Andy/TimeChat |
| Qwen2.5-VL | 官方 README 称支持事件时间定位和输出框坐标⚠️（未读原文段落） | Apache-2.0（7B） | https://github.com/QwenLM/Qwen2.5-VL |
| VideoHallucer / EventHallusion | 评测用：衡量说明里的幻觉率 | 见各 repo | 同 §5 |
| MMAction2 | 动作识别、时序定位基线 | Apache-2.0，2026-03-18 | https://github.com/open-mmlab/mmaction2 |

## 7. 夜间 / 红外画面
- 本轮**没找到**犬家庭红外夜视的公开标注数据集；MegaDetector 的相机陷阱数据含夜间红外，可作参考⚠️（未核 MegaDetector 夜间子集的性能报告）。
- 常见检测器（RT-DETR、YOLOX）用 COCO 的 RGB 图训练；在灰度红外画面上的效果⚠️要自测。Animal-Bench 用视频编辑模拟拍摄条件变化，用于测鲁棒性，可参考它的做法（同 §5）。

## 8. 边缘部署
| 选项 | 许可 | 维护 | 说明 |
|---|---|---|---|
| OpenVINO | Apache-2.0 | 2026-10-13 | https://github.com/openvinotoolkit/openvino |
| ncnn（腾讯） | API 为 NOASSERTION（自称 BSD-3 系⚠️） | 2026-10-13 | https://github.com/Tencent/ncnn |
| RKNN Toolkit2（瑞芯微） | NOASSERTION⚠️ | 2026-10-13 | https://github.com/airockchip/rknn-toolkit2 ；国产摄像头常用 SoC |
| Hailo Model Zoo | MIT | 2026-09-18 | https://github.com/hailo-ai/hailo_model_zoo |
| torch2trt（Jetson） | MIT | 2024-08-17 | https://github.com/NVIDIA-AI-IOT/torch2trt |

## 9. 小结
- **可参考的组件线索，尚非已验收组合**：RT-DETR／YOLOX、supervision、MMPose／ViTPose，以及所列视频模型和部署工具。代码、权重、训练数据、依赖及具体版本仍须分别核验；未完成本地运行，不整体认定商用或有效。
- **主要缺口**：本轮未定位到许可及家庭适用性均已核齐的完整数据方案，尤其夜视与跨生命周期。所列视频模型风险仅适用于对应基准及版本；不能扩展为所有当前VLM的统一性能结论。
- **最大的许可陷阱**：Ultralytics/YOLOv10 是 AGPL；SuperAnimal 权重非商用；Qwen2.5-VL-3B 是研究许可；从 YouTube/抖音来的视频数据。
