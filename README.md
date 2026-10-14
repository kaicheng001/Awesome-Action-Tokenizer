# Awesome Action Tokenizer

A curated collection of discrete action representations for autoregressive vision-language-action (VLA) models, robot manipulation, and imitation learning.

## Contents

- [1. Compact Action Representation](#1-compact-action-representation)
- [2. Autoregressive-Friendly Action Tokens](#2-autoregressive-friendly-action-tokens)
- [3. Control-Faithful Action Representation](#3-control-faithful-action-representation)
- [4. Generalizable Action Interfaces](#4-generalizable-action-interfaces)
- [Related Works](#related-works)
- [Contributing](#contributing)

## Papers by Research Problem

Each work appears under its primary contribution; the focus is discrete robot-control tokens and their interfaces with continuous execution.
Years denote first public release unless a conference is named; MiniVLA links to its original author report.
Coverage includes work released through October 14, 2026.
**Code** links to official implementations, **Project** to author pages, and **—** indicates no verified public implementation or project link.

### 1. Compact Action Representation

Represent continuous action chunks with fewer discrete symbols while retaining control precision.

#### 1.1 Quantization and Analytical Tokenization

| Paper | Key Idea | Code |
|---|---|---|
| [BEAST (2025)](https://arxiv.org/abs/2506.06072) | Fixed-length B-spline control-point coding for smooth action sequences. | [Code](https://github.com/intuitive-robots/beast_calvin) |
| [FAST (2025)](https://arxiv.org/abs/2501.09747) | Discrete cosine transform followed by quantization and byte-pair encoding. | [Code](https://github.com/Physical-Intelligence/openpi) |
| [OpenVLA (2024)](https://arxiv.org/abs/2406.09246) | Per-dimension uniform bins within percentile-normalized action ranges. | [Code](https://github.com/openvla/openvla) |
| [RT-2 (2023)](https://arxiv.org/abs/2307.15818) | Uniform action discretization into language-model output tokens. | [Project](https://robotics-transformer2.github.io/) |

#### 1.2 Learned Action Compression

| Paper | Key Idea | Code |
|---|---|---|
| [M²Tok (2026)](https://arxiv.org/abs/2609.18259) | Multi-head latent decomposition with independent quantization codebooks. | [Code](https://github.com/cpaaax/M2Tok) |
| [FASTer (2025)](https://arxiv.org/abs/2512.04952) | Image-shaped action chunks compressed through transformer-based residual vector quantization. | — |
| [OmniSAT (2025)](https://arxiv.org/abs/2510.09667) | B-spline normalization with residual quantization of separate action subspaces. | — |
| [VQ-VLA (2025)](https://arxiv.org/abs/2507.01016) | Residual VQ action compression pretrained on large-scale synthetic and real trajectories. | [Code](https://github.com/xiaoxiao0406/VQ-VLA) |
| [MiniVLA (2024, report)](https://sail.stanford.edu/blog/minivla/) | Residual vector quantization compresses action chunks for compact VLAs. | [Code](https://github.com/Stanford-ILIAD/openvla-mini) |
| [QueST (2024)](https://arxiv.org/abs/2407.15840) | Causally structured quantized skill sequences for transferable temporal abstractions. | [Code](https://github.com/pairlab/QueST) |
| [VQ-BeT (2024)](https://arxiv.org/abs/2403.03181) | Hierarchical residual vector quantization of multimodal action chunks. | [Code](https://github.com/jayLEE0301/vq_bet_official) |

### 2. Autoregressive-Friendly Action Tokens

Structure action representations to make token prediction reliable and efficient.

#### 2.1 Ordered and Progressive Tokenization

| Paper | Key Idea | Code |
|---|---|---|
| [ReAT (2026)](https://arxiv.org/abs/2610.13093) | Decoded-prefix feedback guides tokenization of remaining action reconstruction errors. | — |
| [CATok (2026)](https://arxiv.org/abs/2609.35469) | Conditional flow annealing organizes discrete tokens into causal refinement stages. | [Code](https://github.com/ChenyuZhangX/CausalActionTokenizer) |
| [OAT (2026)](https://arxiv.org/abs/2607.21670) | Ordered finite-scalar-quantized tokens support progressively refined prefix decoding. | [Code](https://github.com/Chaoqi-LIU/praxis-vla) |
| [CARP (2024)](https://arxiv.org/abs/2412.06782) | Multi-scale action autoencoding with coarse-to-fine next-scale autoregressive prediction. | [Code](https://github.com/ZhefeiGong/carp) |

#### 2.2 Predictability and Policy-Aware Tokenization

| Paper | Key Idea | Code |
|---|---|---|
| [CAP (2026)](https://arxiv.org/abs/2610.09178) | Reuses tokenizer code vectors as policy classification prototypes. | — |
| [ProAct (2026)](https://arxiv.org/abs/2610.09170) | Augments reconstruction training to improve token predictability and decoder robustness. | — |
| [Beyond Reconstruction Error (2026)](https://arxiv.org/abs/2609.25820) | Compares analytical and learned representations through predictability, stability, and control. | — |
| [ActionCodec (2026)](https://arxiv.org/abs/2602.15397) | Temporal and language alignment, compact vocabularies, and residual-quantization post-training. | [Code](https://github.com/ZibinDong/actioncodec) |

### 3. Control-Faithful Action Representation

Preserve physical relationships, temporal structure, and intent that matter for execution.

#### 3.1 Physical and Temporal Consistency

| Paper | Key Idea | Code |
|---|---|---|
| [BAAT (2026)](https://arxiv.org/abs/2609.27513) | Soft-DTW motion alignment with quantized-coordinate supervision and history-conditioned diffusion decoding. | — |
| [ActionPiece (2026)](https://arxiv.org/abs/2609.18487) | Physical distance-rank supervision shapes representations and codeword assignment distributions. | [Code](https://github.com/DeepCybo-PhysAI/ActionPiece) |
| [LipVQ-VAE (2025)](https://arxiv.org/abs/2503.01206) | Weight-normalized Lipschitz constraints preserve smoothness in quantized action representations. | [Code](https://github.com/andvg3/LipVQ-VAE) |

#### 3.2 Semantic and Intent Alignment

| Paper | Key Idea | Code |
|---|---|---|
| [SALT (2026)](https://arxiv.org/abs/2608.10484) | Frozen-VLM instruction recovery aligns quantized action latents with language semantics. | — |
| [X-Tokenizer (2026)](https://arxiv.org/abs/2606.14752) | Semantic residual quantization separates masked-modeling intent codes from reconstruction residuals. | [Project](https://x-square-robot.github.io/X-Tokenizer_projectPage/) |
| [MINT (2026)](https://arxiv.org/abs/2602.08602) | Multi-scale frequency tokenization separates low-frequency intent from fine execution details. | [Code](https://github.com/RenMing-Huang/MINT) |

### 4. Generalizable Action Interfaces

Adapt action-token interfaces across robot states, embodiments, and continuous decoding mechanisms.

#### 4.1 State- and Embodiment-Aware Tokenization

| Paper | Key Idea | Code |
|---|---|---|
| [G0.5 (2026)](https://arxiv.org/abs/2608.11739) | Shared cross-embodiment action vocabulary within a unified reasoning–action autoregressive stream. | [Code](https://github.com/OpenGalaxea/GalaxeaVLA) |
| [SA-VLA (2026)](https://arxiv.org/abs/2606.30113) | Robot-state attention or adapters condition reconstruction from quantized action codes. | — |
| [UniT (2026)](https://arxiv.org/abs/2604.19734) | Visual–action cross-reconstruction anchors shared discrete codes across human and humanoid embodiments. | [Code](https://github.com/xpeng-robotics/UniT) |

#### 4.2 Hybrid Discrete-Continuous Action Modeling

| Paper | Key Idea | Code |
|---|---|---|
| [RDT2 (2026)](https://arxiv.org/abs/2602.03310) | Residual-VQ pretraining followed by flow-matching control and one-step distillation. | [Code](https://github.com/thu-ml/RDT2) |
| [FACT / GenieReasoner (2025)](https://arxiv.org/abs/2512.24125) | Lookup-free bitwise action quantization with a token-conditioned flow-matching decoder. | [Project](https://geniereasoner.github.io/GenieReasoner/) |
| [Behavior Transformer (BeT, 2022)](https://arxiv.org/abs/2206.11251) | Predicts k-means action clusters together with continuous residual corrections. | [Code](https://github.com/notmahi/bet) |

## Related Works

Video-derived latent actions, continuous effect representations, and motion generation offer complementary insights but differ from discrete robot-control token prediction.

| Paper | Key Idea | Code |
|---|---|---|
| [AFCE (2026)](https://arxiv.org/abs/2610.13212) | Flow predicts continuous effects grounded in actions, robot responses, and visual transitions. | [Project](https://afceproject.github.io/AFCE-Web/) |
| [LaPla (2026)](https://arxiv.org/abs/2609.04070) | Driving policy predicts continuous latents through a pretrained residual-VQ decoder. | — |
| [LingBot-VA 2.0 (2026)](https://arxiv.org/abs/2607.08639) | Semantic visual–action latents learned from video transitions support causal flow-based control. | — |
| [MotionVLA (2026)](https://arxiv.org/abs/2606.15142) | Separate pose and dynamics streams use DCT and BPE for humanoid motion generation. | [Code](https://github.com/AIGeeksGroup/MotionVLA) |
| [LARA (2026)](https://arxiv.org/abs/2606.07100) | Jointly aligns video-derived latent actions with diffusion-policy representations. | [Code](https://github.com/lmy1001/LARA) |
| [CycleMimic (CVPR 2026)](https://openaccess.thecvf.com/content/CVPR2026/html/Chen_Learning_a_Unified_Latent_Action_Space_from_Videos_with_Action-centric_CVPR_2026_paper.html) | Action-centric cycle consistency unifies latent actions inferred from videos. | — |
| [LAPA (2024)](https://arxiv.org/abs/2410.11758) | Quantizes image transitions for action-free pretraining before robot-action fine-tuning. | [Code](https://github.com/LatentActionPretraining/LAPA) |

## Contributing

Submit a pull request with the official paper link, a short distinguishing method description, and verified author code or project links.
Place each work once under its primary research problem, keep entries newest first within each method category, and distinguish discrete control tokens from adjacent latent-action methods.
