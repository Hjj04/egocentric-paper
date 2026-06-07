# Egocentric & VLA Paper Pipelines

本仓库围绕**第一人称（egocentric）人类视频**与 **Vision-Language-Action（VLA）策略学习**整理学习与调研材料，分为两个独立维护、各自持续更新的分区：

- **基础知识** —— 理解该方向所需的通用概念、参数模型与表示方法。
- **前沿论文** —— 代表性工作从 `数据 → 处理 → 训练 → 推理` 的完整流程拆解（自包含静态 HTML 页面），按发布时间倒序排列。

## 在线访问

GitHub Pages: **https://hjj04.github.io/egocentric-paper/**

首页分区展示，可按需各自扩充。

## 基础知识

| 主题 | 说明 | 链接 |
| --- | --- | --- |
| MANO 手部参数模型 | 面向具身领域讲清 MANO（手部 pose + shape 的可微分参数模型），是双手 MANO 轨迹 / 手部 6-DoF 位姿等动作表示的共同基础 | [打开](https://hjj04.github.io/egocentric-paper/MANO_hand_model_explained.html) |

## 前沿论文（按发布时间倒序）

| 工作 | 发布时间 | 开源状态 | 流程拆解 |
| --- | --- | --- | --- |
| Donk | 2026-06-02 | 未开源 | [打开](https://hjj04.github.io/egocentric-paper/donk-pipeline.html) |
| HARP-VLA | 2026-05-29 | 匿名提交 | [打开](https://hjj04.github.io/egocentric-paper/HARP-VLA-pipeline.html) |
| HumanEgo | 2026-05-28 | 已开源（★234，马里兰大学） | [打开](https://hjj04.github.io/egocentric-paper/humanego_pipeline.html) |
| JoyAI-RA 0.1 | 2026-04-23 | 未开源 | [打开](https://hjj04.github.io/egocentric-paper/joyai-ra-pipeline.html) |
| DreamDojo | 2026-02-06 | 已开源（★913，NVIDIA） | [打开](https://hjj04.github.io/egocentric-paper/DreamDojo_pipeline.html) |

### 论文摘要

- **Donk** — 同一个"视频-动作联合去噪器"：给定观测图像时作为灵巧手动作策略（从图像+语言预测未来双手 MANO 轨迹），不给图像时作为数据引擎（仅凭文本生成成对的交互视频+同步手部动作）。实验未含真机验证。
- **HARP-VLA** — 从大规模无动作标签的人类视频中预训练可泛化 VLA 策略，同时缩小视觉表征 gap 与动作执行 gap。贡献：源相对+配对判别的对齐损失、潜动作学习与人机视觉对齐耦合的三阶段训练、robot-only adapter。
- **HumanEgo** — 仅用几分钟人类第一视角视频即可学出可 zero-shot 迁移真机的双臂操作策略，无需任何机器人数据。核心是 Interaction-Centric Token（ICT）这一本体/视角无关的显式空间表征，辅以 flow matching + 三个 dense 辅助目标，以及抹手臂+渲染虚拟夹爪的视觉预处理。
- **JoyAI-RA 0.1** — 基于 EgoLive 数据集的 VLA 系统，贡献含相机系 6-DoF 统一动作空间、Perceiver+AdaLN 时序条件+future tokens 的 Action Expert 组合，以及一组定量化消融。
- **DreamDojo** — 用 44k 小时人类第一人称视频 + 连续潜动作作为统一动作，把人类交互知识灌进基于 Cosmos-Predict2.5 的视频世界模型，微调后可对未见物体/环境做物理合理、动作可控的实时模拟。

## 本地查看

直接用浏览器打开任意 `.html` 文件即可，所有页面均为自包含（无外部本地依赖）。
