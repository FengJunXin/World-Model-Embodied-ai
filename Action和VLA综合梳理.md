Action Model 与 VLA 综合发展路线梳理
======================================

    生成日期：2026-06-23
    文档定位：综合展示 Action Model 与 VLA 两条发展脉络的独立演进、
              汇聚融合与经典论文对照。


一、全景树状图：Action Model → VLA 的发展与汇聚
=================================================

                    ╔═══════════════════════════════════════════╗
                    ║       具身智能动作与VLA发展全景            ║
                    ╚═══════════════════════════════════════════╝

  ─── Action Model 独立演进路线（左侧主干）───      ─── VLA 独立演进路线（右侧主干）───

  ╔═══════════════════════════════════════════════════════════════════════════════╗
  ║  第一层：底层基础（2013-2020）                                              ║
  ║  核心矛盾：如何让神经网络输出动作？                                         ║
  ╚═══════════════════════════════════════════════════════════════════════════════╝
        │
  ① 经典策略学习期 (Action路线)
        │
    GPS (ICML 2013)             —— 引导策略搜索，深度网络策略优化起点
    CNN Visuomotor (JMLR 2016)  —— CNN直接输出关节力矩
    QT-Opt (CoRL 2018)          —— 大规模Q学习连续动作空间
    BC from Obs (IJCAI 2018)    —— 行为克隆标准框架
    Residual RL (ICRA 2019)     —— 基础策略+RL残差修正
        │
        │         此时的Action仅被视为"回归问题"，无VLA概念
        │


  ╔═══════════════════════════════════════════════════════════════════════════════╗
  ║  第二层：表征觉醒 + VLA萌芽（2021-2022）                                    ║
  ║  核心矛盾：如何最好地表征动作？→ 隐式/序列/Token三路线并行                     ║
  ╚═══════════════════════════════════════════════════════════════════════════════╝
        │
  ②Action表征开创期                       ②VLA萌芽与奠基期
        │                                       │
    IBC (CoRL 2021) 隐式能量              CLIPort (CoRL 2021) CLIP+语言条件拾放
        ↓                                       │
    Decision Transformer                  SayCan (arXiv 2022) LLM规划+价值筛选
    (NeurIPS 2021) 序列化RL
        ↓                                       │
    ─────────────  ║  ═══════════════         PerAct (CoRL 2022) 3D体素+Perceiver
                    ║
    RT-1 (arXiv 2022)  ◄═══【共享里程碑】═══► RT-1 (arXiv 2022)
    连续动作→256bin离散Token                 首次Token化Transformer机器人策略
    6Hz机载推理                              VLA的工程原型
                    ║
        │           ║                          │
    Gato (DeepMind 2022)                    （VLA尚未作为统一概念出现）
    统一多任务Transformer策略
        │                                       │


  ╔═══════════════════════════════════════════════════════════════════════════════╗
  ║  第三层：范式革命——动作块+扩散+VLA联合（2023）⚠️ 核心汇聚点                    ║
  ╚═══════════════════════════════════════════════════════════════════════════════╝
        │                                       │
  ③Action革命期                            ③VLA范式确立期
        │                                       │
  ACT (RSS 2023)                           PaLM-E (ICML 2023)
  CVAE+100步动作块                         562B多模态具身LLM
        ║                                       ║
  Diffusion Policy (RSS 2024首发2023) ═══【汇聚】═════════ RT-2 (arXiv 2023) ══════╗
  扩散生成动作轨迹  ◄──── 扩散+动作块 ────►  首个端到端VLA ◄── VLM+动作Token ────╝
        │              共同塑造VLA                                      │
        │                                       │
  IQL (NeurIPS 2021)                       RT-1-X / RT-2-X + OXE (2023)
  CQL (NeurIPS 2020)                       跨22+机器人、1M+轨迹
  离线RL基础框架                            跨具身训练标准确立
        ║                                       ║
  ─────────────  ║  〓〓〓（VLA核心组件已完备）〓〓〓  ║  ─────────────
                  ║   视觉(VLM) + 语言(LLM) + 动作(扩散/Token) ║
                  ║   VLA范式正式确立：互联网预训练→机器人数据共微调


  ╔═══════════════════════════════════════════════════════════════════════════════╗
  ║  第四层：开源爆发 + 工业验证（2024）                                        ║
  ║  核心矛盾：从"是否可行"到"速度和精度的最优权衡"                               ║
  ╚═══════════════════════════════════════════════════════════════════════════════╝
        │                                       │
  ④Action开源工业期                        ④VLA开源生态爆发期
        │                                       │
  OpenVLA (arXiv 2024)  ◄═══【共享里程碑】═══► OpenVLA (arXiv 2024)
  7B VLA，离散Token~6Hz                     首个开源VLA基础模型
        ║                                       ║
  π0 (Physical Intel. 2024) ◄═══【共享里程碑】═══► π0 (Physical Intel. 2024)
  3.3B Flow-Matching ~50Hz                 验证扩散作为VLA动作头
        ║                                       ║
  Octo (arXiv 2024)                        Octo (arXiv 2024)
  27M-93M DDPM轻量通用                      轻量级通用策略验证
        ║                                       ║
  RDT-1B (ICLR 2025)  ◄══【共享里程碑】═══► RDT-1B (ICLR 2025)
  1.2B DiT 381Hz双臂                        双臂扩散VLA里程碑
        ║                                       ║
  TinyVLA (IEEE RA-L 2025)                 TinyVLA (IEEE RA-L 2025)
  40M-1.4B紧凑扩散20×加速                   高效VLA开创
        ║                                       ║
  Diffusion Policy Optimization (2024)     DROID (2024) 数据集
  扩散策略RL理论                             SIMPLER (2024) Real-to-Sim


  ╔═══════════════════════════════════════════════════════════════════════════════╗
  ║  第五层：全面深化——7条主线并行（2025）                                      ║
  ║  VLA与Action Model进入深度融合、正交分化的新阶段                               ║
  ╚═══════════════════════════════════════════════════════════════════════════════╝

   ─── Action Model 路线深化 ───         ─── VLA 系统拓展 ───
        │                                       │
  ⑤-1 扩散+自回归统一                   ⑤-1 统一理解与控制
  DiffusionVLA (ICML 2025) 2B-72B        ChatVLA (EMNLP 2025) MoE分离
  HybridVLA (2025) LLM内协同              ChatVLA-2 (2025) 保持VLM能力
        ║                                       ║
  ⑤-2 离散Token极致                      UniVLA (2025) 共享词表95.5%
  UniVLA(共享词表统一)                     UP-VLA (ICML 2025) 理解+预测
  ChatVLA(MoE分离理解-控制)
        ║                                       ║
  ⑤-3 RL后训练                           ⑤-2 人形全身控制
  SimpleVLA-RL (2025) pushcut发现         Humanoid-VLA (2025) 首个人形VLA
  iRe-VLA (2025) SL+RL迭代               WholeBodyVLA (2025) 潜空间全身
  RIPT-VLA (2025) 稀疏奖励                LeVERB (2025) 零样本Sim2Real
  Beyond Human Demo (2025) 扩散RL         SONIC (2025) 100M帧MoCap
        ║                                       ║
  ⑤-4 潜空间动作                         ⑤-3 3D空间感知
  UniVLA潜动作 (2025)                     3DS-VLA (CoRL 2025) 2D→3D对齐
  PELA潜动作对齐 (2025)                   GraphCoT-VLA (2025) 图谱+CoT
  villa-X潜规划 (2025)                    ActiveVLA (2025) 主动感知
        ║                                       ║
  ⑤-5 层次化动作                         ⑤-4 移动操作
  SayCan→Gemini ER (2025)                EchoVLA (2025) 场景记忆
  LeVERB层次化潜指令                       PosA-VLA (2025) 姿态锚点
  HANDO导航+操作 (IROS 2025)
        ║                                       ║
  ⑤-6 MoE动作架构                        ⑤-5 人类视频学习
  HiMoE-VLA (2025) 双层MoE SOTA           π0.5 (2025) 涌现迁移
  AdaMoE (2025) 解耦选择加权              MimicDreamer (2025) H2R对齐
  ChatVLA MoE (2025) 理解-控制分离         VLA Pretraining (ICML 2026)
        ║                                       ║
  ⑤-7 效率优化                           ⑤-6 后训练与RL
  VLA-Adapter (2025) 500M→97.3%           SimpleVLA-RL (2025) Pushcut
  SwiftVLA (2025) 轻量级                  iRe-VLA (2025) SL+RL迭代
  MoTVLA (2025) Tiny+MoE
        ║                                       ║
  ⑤-8 世界模型融合                       ⑤-7 MoE架构
  FLARE (CoRL 2025) 隐式注入+26%          HiMoE-VLA (2025) AS-MoE+HB-MoE
  IGOR (2024) 原子控制单元                AdaMoE (2025) 解耦选择加权
  Being-H0.7 (2026) 端到端统一
        ║                                       ║
  ⑤-9 安全可解释                         ⑤-8 效率革命
  Mech. Interp. (CoRL 2025) 首个体内解释  VLA-Adapter (2025) 500M→97.3%
  VLA-Fool (2025) 对抗攻击                SwiftVLA (2025)
  BadVLA (2025) 后门攻击


  ╔═══════════════════════════════════════════════════════════════════════════════╗
  ║  第六层：前沿汇聚——潜推理+世界模型+安全体系（2026）                          ║
  ║  Action Model与VLA在最前沿趋于统一：具身推理系统                             ║
  ╚═══════════════════════════════════════════════════════════════════════════════╝

  ⑥Action前沿系统期  ═══════════════════【全面汇聚】═══════════════════ ⑥VLA前沿系统期
        │                                       │
  LaRA-VLA (ICML 2026) ◄═══【共享里程碑】═══► LaRA-VLA (ICML 2026)
  潜空间CoT推理↓90%                         潜空间推理VLA开创
        ║                                       ║
  OneVL (小米 2026) ◄══【共享里程碑】═══► OneVL (小米 2026)
  单步潜推理超越显式CoT                      挑战"推理越长越好"
        ║                                       ║
  MPCoT (2026) ◄════【共享里程碑】════► MPCoT (2026)
  多路径潜推理测试时缩放                     VLA推理Scaling Law
        ║                                       ║
  Being-H0.7 (2026) ◄══【共享里程碑】═══► Being-H0.7 (2026)
  自中心视频世界-动作模型                     世界模型+潜推理融合
        ║                                     ║
  Continuous Reasoning (2026)               Concept Dict. (2026) 攻击↓70%
  高斯潜空间结构化连续思想                     VLA Safety Survey (2026) 首个安全综述
  LARA (2026) 潜动作对齐                     3DThinkVLA (2026) 3D先验+潜推理
  Fast-ThinkAct (2026) 紧凑推理策略
        │                                       │


  ╔═══════════════════════════════════════════════════════════════════════════════╗
  ║  汇聚后的统一趋势（2026+）                                                  ║
  ║  Action Model不再是VLA的一个组件，而是与其在"具身推理系统"中融为一体            ║
  ╚═══════════════════════════════════════════════════════════════════════════════╝

                                     ╔═══════════════════╗
                                     ║  具身推理系统      ║
                                     ║  (VLA = Action)   ║
                                     ╚═══════════════════╝
                                            │
                      ┌─────────────────────┼─────────────────────┐
                      │                     │                     │
                      ▼                     ▼                     ▼
              ╔══════════════╗     ╔══════════════╗     ╔══════════════╗
              ║ 潜推理+动作   ║     ║ 世界模型+动作 ║     ║ 安全可干预    ║
              ║ LaRA-VLA     ║     ║ Being-H0.7   ║     ║ Concept Dict ║
              ║ OneVL        ║     ║ FLARE        ║     ║ Feature Ctrl ║
              ║ MPCoT        ║     ║ UniVLA-WM    ║     ║ EdgeWise     ║
              ╚══════════════╝     ╚══════════════╝     ╚══════════════╝
                      │                     │                     │
                      └─────────────────────┼─────────────────────┘
                                            ▼
                              VLA不再有"独立的Action组件"
                              动作 = 推理 = 理解 = 感知


二、发展阶段的经典论文对照（无重复）
====================================

各阶段论文按归属领域唯一收录——共享里程碑出现在两侧领域交汇处但只计一次。


第一层：底层基础期（2013-2020）
──────────────────────────────

┌───────────┬──────────────────────────────────────────────────────────────────────┐
│ 领域归属   │ 论文（唯一收录，不跨领域重复）                                        │
├───────────┼──────────────────────────────────────────────────────────────────────┤
│ Action    │ GPS (Levine, ICML 2013) - 引导策略搜索                               │
│ Action    │ CNN Visuomotor (Levine, JMLR 2016) - 端到端CNN视觉运动策略           │
│ Action    │ QT-Opt (Kalashnikov, CoRL 2018) - 大规模Q学习连续动作                │
│ Action    │ BC from Observation (Torabi, IJCAI 2018) - 行为克隆框架              │
│ Action    │ Residual RL (Silver, ICRA 2019) - 基础策略+RL残差修正                │
│ Action    │ CQL (Kumar, NeurIPS 2020) - 保守Q学习离线RL                          │
└───────────┴──────────────────────────────────────────────────────────────────────┘

  核心特征：此时期无VLA概念。Action仅是"回归输出"。所有工作归属Action路线。


第二层：表征开创 + VLA萌芽期（2021-2022）
────────────────────────────────────────

┌───────────┬──────────────────────────────────────────────────────────────────────┐
│ 领域归属   │ 论文（唯一收录，不跨领域重复）                                        │
├───────────┼──────────────────────────────────────────────────────────────────────┤
│   Action  │ IBC (Florence, CoRL 2021) - 能量模型隐式策略                        │
│   Action  │ Decision Transformer (Chen, NeurIPS 2021) - 序列化RL                │
│   Action  │ Trajectory Transformer (Janner, NeurIPS 2021) - 轨迹级Transformer   │
│   Action  │ IQL (Kostrikov, NeurIPS 2021) - 隐式Q学习                           │
│   Action  │ Gato (Reed, DeepMind 2022) - 统一多任务Transformer策略              │
├───────────┼──────────────────────────────────────────────────────────────────────┤
│ 【共享】  │ RT-1 (Brohan, arXiv 2022) - 首次连续动作→离散Token，6Hz机载推理     │
│           │ 被Action路线和VLA路线共同使用，因为：                                │
│           │   Action视角：首次有意识的动作表征设计（Token化）                     │
│           │   VLA视角：端到端Transformer机器人策略的工程原型                      │
├───────────┼──────────────────────────────────────────────────────────────────────┤
│   VLA     │ CLIPort (Shridhar, CoRL 2021) - CLIP+语言条件拾放联合              │
│   VLA     │ SayCan (Ahn, arXiv 2022) - LLM规划+价值筛选可执行动作               │
│   VLA     │ PerAct (Shridhar, CoRL 2022) - 3D体素+Perceiver 600+任务SOTA       │
└───────────┴──────────────────────────────────────────────────────────────────────┘

  重要特征：RT-1是两条路线第一次在"动作表征"上相遇。VLA的蒙芽依赖于Action Model的
            Token化创新——VLA尚未独立于 Action。


第三层：范式革命——动作块+扩散+VLA联合（2023）⚠️ 核心汇聚层
─────────────────────────────────────────────────────────────

┌───────────┬──────────────────────────────────────────────────────────────────────┐
│ 领域归属   │ 论文（唯一收录，不跨领域重复）                                        │
├───────────┼──────────────────────────────────────────────────────────────────────┤
│   Action  │ ACT (Zhao, RSS 2023) - CVAE+100步动作块，双臂精细操作              │
│   Action  │ Action Chunking分析 (2024) - 块长度K的系统性研究                    │
│   Action  │ Temporal Action Ensembling (CoRL 2023) - 块间过渡平滑              │
├───────────┼──────────────────────────────────────────────────────────────────────┤
│ 【共享】  │ Diffusion Policy (Chi, RSS 2024首发2023) - 扩散策略奠基              │
│           │ Action视角：扩散生成动作轨迹，多模态分布自然表达                      │
│           │ VLA视角：成为VLA动作头的标准选择（π0 50Hz的基石）                    │
│           │                                                                      │
│ 【共享】  │ RT-2 (Brohan, arXiv 2023) - 首个端到端VLA                           │
│           │ Action视角：动作Token化的极致验证（VLM+动作Token联合训练）            │
│           │ VLA视角：宣告VLA范式正式诞生，VLA术语确立                            │
├───────────┼──────────────────────────────────────────────────────────────────────┤
│   VLA     │ PaLM-E (Driess, ICML 2023) - 562B多模态具身LLM                     │
│   VLA     │ RT-1-X / RT-2-X + OXE (Open X-Embodiment, arXiv 2023)             │
│   VLA     │ RoboFlamingo (ICLR 2024) - VLM+策略头轻量方案                      │
└───────────┴──────────────────────────────────────────────────────────────────────┘

  核心汇聚点分析：
  2023年三条革命性突破中，Diffusion Policy和RT-2同时属于Action和VLA两个领域——
  它们不是在两个领域"各自做自己的事"后再拼接，而是从一开始就在交叉点上：
    → RT-2使得"动作Token"不再是孤立的设计，而是VLM词表的一部分
    → Diffusion Policy使得"扩散动作"不再是策略学习的方法，而是VLA架构的动作头
  因此2023年既是Action的"ChatGPT时刻"，也是VLA的"范式确立时刻"。


第四层：开源爆发 + 工业验证（2024）
────────────────────────────────────

┌───────────┬──────────────────────────────────────────────────────────────────────┐
│ 领域归属   │ 论文（唯一收录，不跨领域重复）                                        │
├───────────┼──────────────────────────────────────────────────────────────────────┤
│   Action  │ Octo (Team, arXiv 2024) - 27M-93M DDPM轻量通用扩散策略             │
│   Action  │ TinyVLA (北大, IEEE RA-L 2025) - 40M-1.4B紧凑扩散20×加速           │
│   Action  │ CogACT (arXiv 2024) - 7B+扩散动作Transformer                       │
│   Action  │ DexVLA (CoRL 2025) - 1B可插拔扩散动作专家                          │
│   Action  │ Diffusion Policy Optimization (arXiv 2024) - 扩散策略RL理论         │
│   Action  │ EDP (arXiv 2024) - 高效扩散策略加速采样                            │
│   Action  │ Consistency Diffusion Policy (arXiv 2024) - 一致性模型加速          │
│   Action  │ Compositional Diffusion Policy (arXiv 2024) - 组合式扩散策略        │
│   Action  │ Equivariant Diffusion Policy (CoRL 2024) - 等变扩散策略              │
│   Action  │ 3D Diffusion Policy (arXiv 2024) - 3D点云条件扩散策略              │
│   Action  │ Flow Policy (2024) - 条件Flow-Matching视觉运动策略                  │
│   Action  │ CFM Policy (2024) - 条件FM机器人策略                               │
│   Action  │ Rectified Flow for Robotics (2024) - 修正流加速                     │
├───────────┼──────────────────────────────────────────────────────────────────────┤
│ 【共享】  │ OpenVLA (Kim, arXiv 2024) - 7B首次开源VLA                          │
│           │ Action视角：离散Token动作头的开源实现                               │
│           │ VLA视角：打破VLA研究被闭源垄断                                      │
│           │                                                                      │
│ 【共享】  │ π0 (Physical Intelligence, 2024) - 3.3B Flow-Matching动作专家~50Hz  │
│           │ Action视角：验证FM在动作生成的工业级可行性                           │
│           │ VLA视角：扩散作为VLA动作头的最佳实践                                │
│           │                                                                      │
│ 【共享】  │ RDT-1B (清华, ICLR 2025) - 1.2B DiT 381Hz双臂扩散                  │
│           │ Action视角：动作生成速度极限的里程碑                                │
│           │ VLA视角：双臂VLA动作模型的里程碑                                    │
├───────────┼──────────────────────────────────────────────────────────────────────┤
│   VLA     │ DROID (Khazatsky, arXiv 2024) - 76K轨迹Franka场景泛化             │
│   VLA     │ BridgeData V2 (Walke, arXiv 2023) - 60K轨迹WidowX                 │
│   VLA     │ SIMPLER (Li, arXiv 2024) - Google Robot/WidowX Real-to-Sim         │
│   VLA     │ OpenVLA-OFT (2025) - MLP连续动作头→~25Hz                          │
└───────────┴──────────────────────────────────────────────────────────────────────┘

  重要特征：2024年是"工业验证"和"子方向分化"之年。Action模型内部出现DDPM/FM/DiT等
            分化；VLA内部出现7B/93M/1.4B等规模分化。但共享论文表明，两条路线在
            "动作头"这一交叉点上持续深度融合。


第五层：全面深化——7条主线并行（2025）
───────────────────────────────────────

┌───────────┬──────────────────────────────────────────────────────────────────────┐
│ 领域归属   │ 论文（唯一收录，不跨领域重复）                                        │
├───────────┼──────────────────────────────────────────────────────────────────────┤
│ (a) 扩散+自回归统一方向                                                          │
│ 【共享】  │ DiffusionVLA (Wen, ICML 2025) - 2B-72B自回归+扩散统一，82Hz          │
│ 【共享】  │ HybridVLA (PKU-HMI-Lab, 2025) - LLM内扩散+自回归协同                 │
│                                                                                  │
│ (b) 统一理解与控制方向                                                            │
│   VLA     │ ChatVLA (Xu, EMNLP 2025) - MoE分离理解-控制参数，无遗忘              │
│   VLA     │ ChatVLA-2 (Xu, arXiv 2025) - 保持数学/OCR/空间推理能力               │
│   VLA     │ UP-VLA (ICML 2025) - 理解+未来预测联合训练                          │
│   VLA     │ UniVLA (arXiv 2025) - 共享词表统一离散化，LIBERO 95.5%               │
│                                                                                  │
│ (c) RL后训练方向                                                                  │
│   Action  │ SimpleVLA-RL (arXiv 2025) - 高效RL框架，发现pushcut现象              │
│   Action  │ iRe-VLA (arXiv 2025) - SL与RL迭代交替                                │
│   Action  │ RIPT-VLA (arXiv 2025) - 稀疏二进制奖励交互后训练                     │
│   Action  │ Beyond Human Demo (arXiv 2025) - 扩散RL生成训练数据，LIBERO 81.9%    │
│                                                                                  │
│ (d) 潜空间动作方向                                                                │
│   Action  │ UniVLA潜动作 (arXiv 2025) - 任务中心潜动作，1/20计算量               │
│   Action  │ PELA (2025) - 预测嵌入=潜动作，7.5M野外视频                            │
│   Action  │ villa-X (2025) - ViLLA框架零样本潜动作规划                          │
│                                                                                  │
│ (e) 层次化动作方向                                                                │
│   Action  │ LeVERB (arXiv 2025) - 层次化潜指令零样本Sim2Real                     │
│   Action  │ WholeBodyVLA (arXiv 2025) - 统一潜空间层次化+RL                      │
│   Action  │ Humanoid-COA (arXiv 2025) - Chain-of-Action高级指令分解              │
│   Action  │ HANDO (IROS 2025) - 腿式机器人导航-操作双层框架                      │
│   Action  │ SONIC (arXiv 2025) - 42M+100M帧MoCap全身运动跟踪                    │
│   Action  │ TrajBooster (arXiv 2025) - 轮式→双足跨具身动作迁移                   │
│   Action  │ Proprio-MLLM (arXiv 2025) - 双臂本体感知+运动位置编码                │
│                                                                                  │
│ (f) MoE动作方向                                                                   │
│   Action  │ HiMoE-VLA (arXiv 2025) - 双层MoE: AS-MoE+HB-MoE，CALVIN/LIBERO SOTA │
│   Action  │ AdaMoE (arXiv 2025) - 解耦专家选择与加权                             │
│                                                                                  │
│ (g) 效率优化方向                                                                  │
│   Action  │ VLA-Adapter (arXiv 2025) - Qwen2.5-0.5B仅500M参数，LIBERO 97.3%     │
│   Action  │ MoTVLA (arXiv 2025) - TinyVLA+MoE+慢/快推理                         │
│   Action  │ SwiftVLA (arXiv 2025) - 轻量级VLA全优化                              │
│                                                                                  │
│ (h) 世界模型融合方向                                                              │
│   Action  │ FLARE (CoRL 2025) - 隐式世界模型注入VLA，+26%                       │
│   Action  │ IGOR (arXiv 2024) - 原子控制单元+世界模型                           │
│   Action  │ UniVLA-WM (2025) - 视频因果关系后训练                                │
│                                                                                  │
│ (i) 安全可解释方向                                                                │
│   Action  │ Mech. Interp. for VLA (CoRL 2025) - 首个体内解释+引导               │
│   Action  │ VLA-Fool (arXiv 2025) - 多模态对抗攻击框架                          │
│   Action  │ BadVLA (arXiv 2025) - VLA后门攻击~100%成功率                        │
│   VLA     │ Context Impact (EACL 2026) - 自然语言干扰→~50%性能下降             │
│   VLA     │ Exploring Adversarial Vuln. (2025) - 文本攻击动作空间               │
│                                                                                  │
│ (j) 人形全身控制方向                                                              │
│   VLA     │ Humanoid-VLA (arXiv 2025) - 首个人形VLA                             │
│   VLA     │ 3DS-VLA (CoRL 2025) - 2D→3D位置对齐增强3D感知                      │
│   VLA     │ GraphCoT-VLA (arXiv 2025) - 实时3D图谱+结构化CoT                    │
│   VLA     │ ActiveVLA (arXiv 2025) - 主动感知高精度操作                         │
│   VLA     │ VisualMimic (arXiv 2025) - 视觉Sim2Real全身控制                     │
│                                                                                  │
│ (k) 移动操作方向                                                                  │
│   VLA     │ EchoVLA (arXiv 2025) - 场景记忆+情节记忆长期移动操作                 │
│   VLA     │ PosA-VLA (arXiv 2025) - 姿态条件锚点注意力消除冗余动作               │
│                                                                                  │
│ (l) 人类视频学习方向                                                              │
│   VLA     │ π0.5 (arXiv 2025) - 人类→机器人迁移是多样预训练的涌现属性            │
│   VLA     │ MimicDreamer (arXiv 2025) - H2R Aligner视频扩散+14.7%               │
│   VLA     │ VLA Pretraining (ICML 2026) - 人手作为操作模板大规模预训练           │
│                                                                                  │
│ (m) Gemini Robotics系列                                                          │
│   VLA     │ Gemini Robotics-ER 1.5 (DeepMind 2025) - VLM规划器15基准SOTA         │
│   VLA     │ Gemin Robotics 1.5 (DeepMind 2025) - VLA执行器+thinking模式           │
│   VLA     │ ASIMOV Benchmark (DeepMind 2025) - 机器人语义安全评估                │
└───────────┴──────────────────────────────────────────────────────────────────────┘

  总结：2025年Action Model和VLA进入"你中有我、我中有你"的深度融合阶段。
        大量论文同时覆盖两个领域，最前沿的创新（DiffusionVLA、SimpleVLA-RL、
        HiMoE-VLA、FLARE）已无法简单归类为某一方。


第六层：前沿汇聚——潜推理+世界模型+安全体系（2026）
─────────────────────────────────────────────────────

┌───────────┬──────────────────────────────────────────────────────────────────────┐
│ 领域归属   │ 论文（唯一收录，不跨领域重复）                                        │
├───────────┼──────────────────────────────────────────────────────────────────────┤
│ 【共享】  │ LaRA-VLA (ICML 2026) - 统一潜空间CoT推理+预测，推理延迟↓90%          │
│ 【共享】  │ OneVL (小米, arXiv 2026) - 单步潜推理超越显式CoT                      │
│ 【共享】  │ MPCoT (arXiv 2026) - 多路径潜推理测试时计算缩放                      │
│ 【共享】  │ Being-H0.7 (arXiv 2026) - 自中心视频隐式世界-动作模型                │
├───────────┼──────────────────────────────────────────────────────────────────────┤
│   Action  │ Fast-ThinkAct (arXiv 2026) - 紧凑推理→动作策略                       │
│   Action  │ Continuous Reasoning (arXiv 2026) - 高斯潜空间结构化连续思想          │
│   Action  │ LARA (arXiv 2026) - 潜动作表示对齐                                  │
│   Action  │ 3DThinkVLA (arXiv 2026) - 3D思维潜3D先验协同训练                    │
├───────────┼──────────────────────────────────────────────────────────────────────┤
│   VLA     │ VLA Safety Survey (Li, arXiv 2026) - 首个VLA安全系统综述             │
│   VLA     │ Concept Dictionary (arXiv 2026) - 推理时概念字典攻击↓70%             │
│   VLA     │ Feature Control (arXiv 2026) - 特征可观测性+可控制性激活引导          │
│   VLA     │ EdgeWise (KTH/RISE, 2025) - 设备/边缘/云三层部署+形式验证            │
│   VLA     │ ColaVLA (CVPR 2026) - 自动驾驶认知隐式推理+层次化规划                │
│   VLA     │ RobotArena∞ (arXiv 2025) - 大规模Sim2Real基准                       │
│   VLA     │ REALM (arXiv 2025) - Real-to-Sim泛化验证基准                        │
│   VLA     │ VLABench (arXiv 2025) - 4类别VLA评测基准                            │
└───────────┴──────────────────────────────────────────────────────────────────────┘

  关键特征：2026年最前沿的4篇里程碑论文全部是共享的（LaRA-VLA/OneVL/MPCoT/Being-H0.7）。
            这表明Action Model与VLA在最前沿已**无法分割**——"潜空间推理"同时是
            动作表征问题和VLA系统架构问题。


三、汇聚规律的总结与三条核心发现
===================================

发现一：两条路线的"起点差"决定了发展节奏
─────────────────────────────────────────

  Action Model起步早（2013年GPS），前8年（2013-2020）积累动作表征的基础知识。
  VLA从2021年CLIPort/SayCan起步，但依托LLM/VLM的预训练积累，仅用3年（2021-2023）
  就追平了Action Model的积累。2023年RT-2+Diffusion Policy使两者正式交汇。

  关键时间差效应：
  Action Model用了10年完成"回归→生成→推理"的三级跳
  VLA仅用5年就从萌芽走到前沿——因为Action Model提供了"动作"这一维度的现成工具箱


发现二：历史上5个关键汇聚节点
─────────────────────────────

  节点1 (2022)：RT-1的离散Token化
      → Action Token成为VLA与Action Model的第一个共享概念
  节点2 (2023)：RT-2 + Diffusion Policy
      → VLA正式确立，Action扩散范式成为VLA标准动作头
  节点3 (2024)：π0 + OpenVLA + RDT-1B
      → 开源+工业级验证使汇聚从理论走向工程
  节点4 (2025)：DiffusionVLA + SimpleVLA-RL + HiMoE-VLA
      → 七条主线并行，每条都同时属于Action和VLA
  节点5 (2026)：LaRA-VLA + OneVL + MPCoT + Being-H0.7
      → "潜空间推理"使Action和VLA在概念层面不可分割


发现三：从"组件关系"到"一体两面"的演化
─────────────────────────────────────────

  2021-2022年：Action是VLA的"候选组件"
      VLA处于萌芽期，尚未统一；Action提供IBC/DT/RT-1等独立工具

  2023-2024年：Action是VLA的"动作头"
      RT-2/VLA用离散Token，π0/VLA用扩散动作——Action被VLA吸收为标准组件

  2025-2026年：Action = VLA（潜空间推理范式）
      当推理在潜空间完成并直接映射到动作，不再有"独立的动作组件"——
      LaRA-VLA/OneVL既是动作模型又是VLA系统，两者是"一体两面"


四、当前文件架构全览
=====================

┌─────────────────────────────────────────────────────────────────────────────────────┐
│  📂 D:\Claude-test\论文搜索+mujoco+pytorch\                                        │
│                                                                                     │
│  📗 VLA论文全面综述.md                  —— 126篇论文的原始收集清单                 │
│  📗 VLA综述结构.md                      —— VLA综述结构化输出（分期+大纲+分支）    │
│  📗 Action Model的论文全面收集总结.md   —— 141篇论文的Action视角收集清单           │
│  📗 Action Model发展梳理.md             —— Action Model六阶段纵向发展脉络          │
│  📗 Action Model写作整理框架.md         —— Action Model综述写作结构化输出          │
│  📘 Action和VLA综合梳理.doc             —— 本文件：双路线树状图+论文对照           │
│                                                                                     │
│  文件关系：                                                                         │
│    VLA论文全面综述.md ──────────────► VLA综述结构.md  ──┐                          │
│                                                          ├──► 本文件（综合梳理）     │
│    Action Model的论文收集总结.md ──► Action Model发展梳理.md                        │
│                                    ► Action Model写作整理框架.md ──┘               │
└─────────────────────────────────────────────────────────────────────────────────────┘


> **总结**：Action Model 和 VLA 经历了"先独立发展→后组件吸收→终融为一体"的演化。
>   Action Model贡献了Token化/扩散/FM/潜空间等动作表征范式，
>   VLA贡献了VLM预训练/端到端联合/系统架构/安全等系统级方法。
>   2026年两者在"潜空间推理"这一概念上彻底融合——动作不再是VLA的一个组件，
>   而是VLA在推理维度上的自然延伸。
