# Awesome AI-Generated Image Detection [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A curated and comprehensive list of papers, datasets, and resources for **AI-Generated Image Detection (AIGC Detection)**. This collection covers methods for detecting images synthesized by GANs, diffusion models, autoregressive models, and other generative approaches.

> Continuously updated.

**Last verified**: 2026-10-23 | **Total papers**: 170+ | **Inclusion criteria**: Peer-reviewed papers (CVPR, ICCV, ECCV, NeurIPS, ICML, ICLR, AAAI) and high-impact arXiv preprints on AI-generated **image** detection. Preference for methods providing open-source code.

---

## Table of Contents

- [Survey](#survey)
- [Paper Tree](#paper-tree)
- [SOTA Methods](#sota-methods)
- [Recommended Benchmarks](#recommended-benchmarks)
- [Papers by Venue](#papers-by-venue)
  - [NeurIPS 2026](#neurips-2026)
  - [ECCV 2026](#eccv-2026)
  - [ICML 2026](#icml-2026)
  - [CVPR 2026](#cvpr-2026)
  - [ICLR 2026](#iclr-2026)
  - [AAAI 2026](#aaai-2026)
  - [ICCV 2025](#iccv-2025)
  - [ICML 2025](#icml-2025)
  - [CVPR 2025](#cvpr-2025)
  - [ICLR 2025](#iclr-2025)
  - [NeurIPS 2025](#neurips-2025)
  - [ECCV 2024](#eccv-2024)
  - [NeurIPS 2024](#neurips-2024)
  - [CVPR 2024](#cvpr-2024)
  - [ICML 2024](#icml-2024)
  - [Earlier Works (2020-2023)](#earlier-works-2020-2023)
- [Papers by Category](#papers-by-category)
  - [1. Pretrained Foundation Models (CLIP / VLM / DINO)](#1-pretrained-foundation-models-clip--vlm--dino)
  - [2. Reconstruction-based Methods](#2-reconstruction-based-methods)
  - [3. Frequency-domain Methods](#3-frequency-domain-methods)
  - [4. Patch / Texture-based Methods](#4-patch--texture-based-methods)
  - [5. Low-level Artifact Detection](#5-low-level-artifact-detection)
  - [6. Perturbation / Robustness-based Methods](#6-perturbation--robustness-based-methods)
  - [7. LMM / Reasoning-based Methods](#7-lmm--reasoning-based-methods)
  - [8. Zero-shot & Training-free Methods](#8-zero-shot--training-free-methods)
  - [9. Diffusion-specific Detection](#9-diffusion-specific-detection)
  - [10. Autoregressive Model Detection](#10-autoregressive-model-detection)
  - [11. Deepfake / Face Forgery Detection](#11-deepfake--face-forgery-detection)
  - [12. Generalization: Training Strategy & Data Engineering](#12-generalization-training-strategy--data-engineering)
  - [13. Image Attribution / Source Tracing](#13-image-attribution--source-tracing)
  - [14. Real-Centric, Calibration & Test-Time Adaptation](#14-real-centric-calibration--test-time-adaptation)
  - [15. Attacks & Robustness Evaluation](#15-attacks--robustness-evaluation)
- [Related Resources](#related-resources)

---

## Survey

+ [**A Survey on Detecting AI-Generated Images: Key Techniques and Future Directions**](https://arxiv.org/abs/2502.12188) | arXiv 2025
+ [**A Survey on AI-Generated Image Detection: Techniques, Datasets, and Future Directions**](https://arxiv.org/abs/2401.15657) | arXiv 2024
+ [**Deepfake Generation and Detection: A Benchmark and Survey**](https://arxiv.org/abs/2403.17881) | arXiv 2024

---

## Paper Tree

```
Awesome AIGC Image Detection
│
├── 1. Pretrained Foundation Models (CLIP / VLM / DINO)
│   ├── 1.1 CLIP Fine-tuning (CLIPping, Raising the Bar, DeeCLIP, ForgeLens)
│   ├── 1.2 Prompt & Language-Guided (AntifakePrompt, PLOT, FatFormer, IAPL)
│   ├── 1.3 Feature Decoupling & Fusion (NS-Net, CausalCLIP, CLIPMoLE, CO-SPY, OmniAID, LoRC)
│   └── 1.4 Information Bottleneck (VIB, MCIB)
│
├── 2. Reconstruction-based Methods
│   ├── 2.1 Diffusion Reconstruction (DIRE, DRCT, LATTE)
│   ├── 2.2 Autoencoder Reconstruction (AEROBLADE, GRRE, CINEMAE, RDD, EIRES, GLARE)
│   ├── 2.3 Latent Space (LaRE², FakeInversion)
│   └── 2.4 Semantic-Aware (SARE, Exposing the Fake)
│
├── 3. Frequency-domain Methods
│   ├── Spectral Analysis (Fractal Self-Similarity, SPAI, Spectral Artifacts)
│   ├── Color / Demosaicing (Secret Lies in Color, Color Matters)
│   └── Fourier / DCT (Fourier Spectrum Discrepancies)
│
├── 4. Patch / Texture-based Methods
│   ├── Patch Learning (SSP, PatchCraft, Panoptic Patch)
│   └── Texture Analysis (TextureCrop, Breaking Semantic Artifacts)
│
├── 5. Low-level Artifact Detection
│   ├── Up-sampling Artifact (NPR)
│   ├── Pixel-level (FerretNet, PiD, Pixel-level Mapping)
│   ├── Entropy / Bit-plane (MLEP, LOTA)
│   └── Noise / Fingerprint (Implicit Noise Imprint, FingerprintNet)
│
├── 6. Perturbation / Robustness-based Methods
│   ├── Perturbation (RIGID, RA-Det, DEnD)
│   ├── Uncertainty (WePe)
│   └── Distribution Fitting (ConV)
│
├── 7. LMM / Reasoning-based Methods
│   ├── Grounding & Explanation (LEGION, AIGI-Holmes, FakeReasoning)
│   ├── Multi-modal Detection (ThinkFake, Spot the Fake, SIDA)
│   └── VLM-based / Agent (Veritas, FakeShield, FAKEXPLAIN, ForenAgent, UniShield, ReAlign)
│
├── 8. Zero-shot & Training-free Methods
│   ├── Training-free (RIGID, WaRPAD, HFI, AEROBLADE, ConV)
│   └── Zero-shot (Forensic Self-Descriptions, Cozzolino, Beyond Generation)
│
├── 9. Diffusion-specific Detection
│   ├── Reconstruction Error (DIRE, AEROBLADE, LaRE², FIRE, DRCT, FakeInversion)
│   └── Probabilistic / Trajectory (Diffusion Epistemic Uncertainty, Corvi 2022)
│
├── 10. Autoregressive Model Detection (PRADA, D³QE, Data Provenance)
│
├── 11. Deepfake Detection (D³, Veritas, Real-Time Deepfake)
│
├── 12. Generalization: Training Strategy & Data Engineering
│   ├── Data Alignment (Dual Alignment, AlignedForensics, B-Free)
│   ├── (Real-Centric & Calibration → moved to 14)
│   └── Multi-Generator (Community Forensics, GAPL, Forensic-MoE)
│
├── 13. Image Attribution / Source Tracing
│   ├── Model Attribution (LatentTracer, AEDR, OCC-CLIP, LIDA, IncreFA)
│   └── AR Attribution (PRADA, Data Provenance)
│
├── 14. Real-Centric, Calibration & Test-Time Adaptation
│   ├── Real-Centric (MIRROR, REM, SimLBR, Stay-Positive, RAW-RGB, VQ Real-Centric)
│   ├── Calibration & Selective (Calibrated, PGC, Source-Asymmetry, Post-hoc Selective)
│   └── Test-Time Adaptation (IAPL, DEDCA)
│
└── 15. Attacks & Robustness Evaluation (PolyJuice, BIAS-ID, When Understanding Becomes a Risk, AIGIBench)
```

---

## SOTA Methods

Representative methods with open-source code:

|  Title  |   Venue  |   Year   |   Code   |   Category   |
|:--------|:--------:|:--------:|:--------:|:--------:|
| [**MIRROR: Manifold Ideal Reference ReconstructOR for AI-Generated Image Detection**](https://arxiv.org/abs/2602.02222) | NeurIPS | 2026 | ![Star](https://img.shields.io/github/stars/349793927/MIRROR.svg?style=social&label=Star) <br> [GitHub](https://github.com/349793927/MIRROR) | Real-Centric |
| [**OmniAID: Decoupling Semantic and Artifacts for Universal AI-Generated Image Detection in the Wild**](https://arxiv.org/abs/2511.08423) | ICML | 2026 | ![Star](https://img.shields.io/github/stars/yunncheng/OmniAID.svg?style=social&label=Star) <br> [GitHub](https://github.com/yunncheng/OmniAID) | Feature Fusion |
| [**RA-Det: Towards Universal Detection of AI-Generated Images via Robustness Asymmetry**](https://arxiv.org/abs/2603.01544) | ICML | 2026 | ![Star](https://img.shields.io/github/stars/dongdongunique/RA-Det.svg?style=social&label=Star) <br> [GitHub](https://github.com/dongdongunique/RA-Det) | Perturbation |
| [**Scaling Up AI-Generated Image Detection via Generator-Aware Prototypes**](https://arxiv.org/abs/2512.12982) | CVPR | 2026 | ![Star](https://img.shields.io/github/stars/UltraCapture/GAPL.svg?style=social&label=Star) <br> [GitHub](https://github.com/UltraCapture/GAPL) | Multi-Generator |
| [**Towards Generalizable AI-Generated Image Detection via Image-Adaptive Prompt Learning**](https://arxiv.org/abs/2508.01603) | CVPR | 2026 | ![Star](https://img.shields.io/github/stars/liyih/IAPL.svg?style=social&label=Star) <br> [GitHub](https://github.com/liyih/IAPL) | Prompt Learning |
| [**Community Forensics: Using Thousands of Generators to Train Fake Image Detectors**](https://arxiv.org/abs/2411.04125) | CVPR | 2025 | ![Star](https://img.shields.io/github/stars/JeongsooP/Community-Forensics.svg?style=social&label=Star) <br> [GitHub](https://github.com/JeongsooP/Community-Forensics) | Multi-Generator |
| [**A Bias-Free Training Paradigm for More General AI-generated Image Detection**](https://arxiv.org/abs/2412.17671) | CVPR | 2025 | ![Star](https://img.shields.io/github/stars/grip-unina/B-Free.svg?style=social&label=Star) <br> [GitHub](https://github.com/grip-unina/B-Free) | Generalization |
| [**Any-Resolution AI-Generated Image Detection by Spectral Learning**](https://arxiv.org/abs/2411.19417) | CVPR | 2025 | ![Star](https://img.shields.io/github/stars/mever-team/spai.svg?style=social&label=Star) <br> [GitHub](https://github.com/mever-team/spai) | Frequency |
| [**D³: Scaling Up Deepfake Detection by Learning from Discrepancy**](https://arxiv.org/abs/2404.04584) | CVPR | 2025 | ![Star](https://img.shields.io/github/stars/BigAandSmallq/D3.svg?style=social&label=Star) <br> [GitHub](https://github.com/BigAandSmallq/D3) | Generalization |
| [**LEGION: Learning to Ground and Explain for Synthetic Image Detection**](https://arxiv.org/abs/2503.15264) | ICCV | 2025 | ![Star](https://img.shields.io/github/stars/opendatalab/LEGION.svg?style=social&label=Star) <br> [GitHub](https://github.com/opendatalab/LEGION) | LMM |
| [**Orthogonal Subspace Decomposition for Generalizable AI-Generated Image Detection**](https://arxiv.org/abs/2411.15633) | ICML | 2025 | ![Star](https://img.shields.io/github/stars/YZY-stack/Effort-AIGI-Detection.svg?style=social&label=Star) <br> [GitHub](https://github.com/YZY-stack/Effort-AIGI-Detection) | CLIP |
| [**Aligned Datasets Improve Detection of Latent Diffusion-Generated Images**](https://arxiv.org/abs/2410.11835) | ICLR | 2025 | ![Star](https://img.shields.io/github/stars/AniSundar18/AlignedForensics.svg?style=social&label=Star) <br> [GitHub](https://github.com/AniSundar18/AlignedForensics) | Generalization |
| [**Rethinking the Up-Sampling Operations in CNN-based Generative Network for Generalizable Deepfake Detection**](https://arxiv.org/abs/2312.10461) | CVPR | 2024 | ![Star](https://img.shields.io/github/stars/chuangchuangtan/NPR-DeepfakeDetection.svg?style=social&label=Star) <br> [GitHub](https://github.com/chuangchuangtan/NPR-DeepfakeDetection) | Frequency |
| [**AEROBLADE: Training-Free Detection of Latent Diffusion Images Using Autoencoder Reconstruction Error**](https://arxiv.org/abs/2401.17879) | CVPR | 2024 | ![Star](https://img.shields.io/github/stars/jonasricker/aeroblade.svg?style=social&label=Star) <br> [GitHub](https://github.com/jonasricker/aeroblade) | Reconstruction |
| [**DRCT: Diffusion Reconstruction Contrastive Training towards Universal Detection**](https://openreview.net/pdf?id=oRLwyayrh1) | ICML | 2024 | ![Star](https://img.shields.io/github/stars/Alicedyd/DRCT.svg?style=social&label=Star) <br> [GitHub](https://github.com/beibuwandeluori/DRCT) | Reconstruction |
| [**Towards Universal Fake Image Detectors that Generalize Across Generative Models**](https://arxiv.org/abs/2302.10174) | CVPR | 2023 | ![Star](https://img.shields.io/github/stars/Yuheng-Li/UniversalFakeDetect.svg?style=social&label=Star) <br> [GitHub](https://github.com/Yuheng-Li/UniversalFakeDetect) | CLIP |
| [**DIRE for Diffusion-Generated Image Detection**](https://arxiv.org/abs/2303.09295) | ICCV | 2023 | ![Star](https://img.shields.io/github/stars/ZhendongWang6/DIRE.svg?style=social&label=Star) <br> [GitHub](https://github.com/ZhendongWang6/DIRE) | Reconstruction |
| [**Learning on Gradients: Generalized Artifacts Representation for GAN-Generated Images Detection**](https://arxiv.org/abs/2304.04871) | CVPR | 2023 | ![Star](https://img.shields.io/github/stars/chuangchuangtan/LGrad.svg?style=social&label=Star) <br> [GitHub](https://github.com/chuangchuangtan/LGrad) | Gradient |
| [**CNN-generated images are surprisingly easy to spot...for now**](https://arxiv.org/abs/1912.11035) | CVPR | 2020 | ![Star](https://img.shields.io/github/stars/peterwang512/CNNDetection.svg?style=social&label=Star) <br> [GitHub](https://github.com/peterwang512/CNNDetection) | CNN Forensics |

---

## Recommended Benchmarks

Widely-used benchmarks and evaluation frameworks in this field:

| Benchmark | Description | Year | Code |
|:----------|:-----------|:----:|:----:|
| **ForenSynths** | Standard test benchmark with images from 11 GAN-based generators | 2020 | ![Star](https://img.shields.io/github/stars/peterwang512/CNNDetection.svg?style=social&label=Star) <br> [GitHub](https://github.com/peterwang512/CNNDetection) |
| **UniversalFakeDetect** | 19 generators spanning GANs and diffusion models | 2023 | ![Star](https://img.shields.io/github/stars/Yuheng-Li/UniversalFakeDetect.svg?style=social&label=Star) <br> [GitHub](https://github.com/Yuheng-Li/UniversalFakeDetect) |
| **GenImage** | Million-scale benchmark covering 8 generators | 2023 | ![Star](https://img.shields.io/github/stars/GenImage-Dataset/GenImage.svg?style=social&label=Star) <br> [GitHub](https://github.com/GenImage-Dataset/GenImage) |
| **Synthbuster** | Diffusion-generated images for detection benchmarking | 2023 | [Paper](https://arxiv.org/abs/2312.02023) |
| **Chameleon** | Human-hard scenarios for sanity-check evaluation | 2025 | ![Star](https://img.shields.io/github/stars/shilinyan99/AIDE.svg?style=social&label=Star) <br> [GitHub](https://github.com/shilinyan99/AIDE) |
| **DRCT-2M** | 2M images from 16 diffusion models for universal detection | 2024 | [ModelScope](https://modelscope.cn/datasets/BokingChen/DRCT-2M) |
| **Aligned Forensics** | Real images paired with their LDM autoencoder reconstructions, removing spurious correlations for training more generalizable detectors | 2025 | ![Star](https://img.shields.io/github/stars/AniSundar18/AlignedForensics.svg?style=social&label=Star) <br> [GitHub](https://github.com/AniSundar18/AlignedForensics) |
| **FakeInversion** | Images from 14 unseen text-to-image models via inversion, for evaluating generalization to unseen generators | 2024 | [Page](https://fake-inversion.github.io/) |
| **CO-SPYBench** | 22 generators + 50k wild images | 2025 | ![Star](https://img.shields.io/github/stars/Megum1/Co-Spy.svg?style=social&label=Star) <br> [GitHub](https://github.com/Megum1/Co-Spy) |
| **Community Forensics** | 4803 generators for large-scale generalization | 2025 | ![Star](https://img.shields.io/github/stars/JeongsooP/Community-Forensics.svg?style=social&label=Star) <br> [GitHub](https://github.com/JeongsooP/Community-Forensics) |
| **ForensicHub** | Unified benchmark & codebase for AIGC detection | 2025 | ![Star](https://img.shields.io/github/stars/scu-zjz/ForensicHub.svg?style=social&label=Star) <br> [GitHub](https://github.com/scu-zjz/ForensicHub) |

---

## Papers by Venue

### NeurIPS 2026

+ [**MIRROR: Manifold Ideal Reference ReconstructOR for AI-Generated Image Detection**](https://openreview.net/forum?id=rNJxI4kA0N) | Liu et al. | [Code](https://github.com/349793927/MIRROR) | `Real-Centric`
+ [**SAGE: Semantic-Agnostic Image Embedding for Generalized AI-Generated Image Detection**](https://openreview.net/forum?id=sCLdMcBvzN) | - | `CLIP`
+ [**Too Aligned to be Real: Detecting AI-Generated Images via Cross-modal Alignment Shift**](https://openreview.net/forum?id=k72oka2LYR) | - | `Language-Guided`
+ [**Less is More: Fewer Tokens and Blocks Make AIGI Detection Faster and More Generalizable**](https://openreview.net/forum?id=l7AUTUgcKZ) | - | `CLIP` `Efficiency`
+ [**The road reaches every place, the short cut only one: Self-Adversarial Shortcut Mitigation for AI-Generated Image Detection**](https://openreview.net/forum?id=bO6CYKnaZo) | - | `Training Strategy`
+ [**Stability-Weighted Direction Regularization Disentangles Generator Shortcuts from Detection Signal**](https://openreview.net/forum?id=2VpqRkpXM9) | - | `Training Strategy`
+ [**DEDCA: Test-Time Adaptation for Generalized AI-Generated Image Detection**](https://openreview.net/forum?id=WP9ROPHHjk) | - | `Test-Time Adaptation`
+ [**Post-hoc Selective Classification for Reliable Synthetic Image Detection**](https://openreview.net/forum?id=WYncw2up3x) | - | `Calibration`
+ [**Unified Forensic Preference Learning for Generalizable Synthetic Image Detection**](https://openreview.net/forum?id=fGUaeL5g1k) | - | `LMM`
+ [**FARE: Forensic Acceptance Region Estimation for Catching Bait-and-Switch Image Generators**](https://openreview.net/forum?id=biz1Z9lOtc) | - | [Code](https://github.com/kaikaiyao/FARE) | `Attribution`
+ [**BIAS-ID: A Framework for Analyzing Transformation Biases in AI-Generated Image Detectors**](https://openreview.net/forum?id=GIewosR83I) | - | `Analysis`
+ [**Beyond Real or Fake: A Dual-Channel Authenticity and Reasoning Protocol for Photographic Assessment**](https://neurips.cc/virtual/2026/poster/154533) | Li et al. | `Camera Fingerprint` `Authenticity`
+ [**SALART-VQA: Diagnosing Whether VLMs Understand Salient Artifacts in Generated Images**](https://openreview.net/forum?id=iVvXeIwD1f) | - | `Benchmark`

### ECCV 2026

+ [**GLARE: Towards Generalizable Detection of Latent Diffusion Images with Global-Local Reconstruction Error**](https://media.eventhosts.cc/Conferences/ECCV2026/pdfs/6737.pdf) | Yan et al. | `Reconstruction` `Training-free`
+ [**LoRC: Detecting AI-Generated Images via Low-Rank Collapse in the Semantic-Residual Space**](https://arxiv.org/abs/2608.20882) | Yan et al. | `Feature Decoupling`
+ [**Beyond Artifacts: Real-Centric Envelope Modeling for Reliable AI-Generated Image Detection**](https://arxiv.org/abs/2512.20937) | - | `Real-Centric`
+ [**Prior-Conditioned Gaussian Discriminants for Generalizable AI-generated Image Detection**](https://eccv.ecva.net/virtual/2026/poster/5771) | - | `Adaptation`
+ [**FAIR: Feature-Augmented Implicit Regularization for AI-generated Fake Image Detection**](https://eccv.ecva.net/virtual/2026/poster/5812) | - | `Training Strategy`
+ [**REVEAL: Reasoning-Enhanced Forensic Evidence Analysis for Explainable AI-Generated Image Detection**](https://eccv.ecva.net/virtual/2026/poster/5044) | - | `LMM`
+ [**UC-VLM: Consistency-Driven Learning for AI-Generated Image Detection with Vision-Language Large Models**](https://eccv.ecva.net/virtual/2026/poster/5204) | - | `LMM`
+ [**Few-Shot Synthetic Image Attribution: Identifying Unseen Generators with Limited Samples**](https://eccv.ecva.net/virtual/2026/poster/5926) | - | [Code](https://github.com/teheperinko541/OmniDFA) | `Attribution`
+ [**Code-in-the-Loop Forensics: Agentic Tool Use for Image Forgery Detection**](https://eccv.ecva.net/virtual/2026/poster/5823) | Zhang et al. | [Code](https://github.com/zfr00/ForenAgent) | `LMM` `Agent`
+ [**Trustworthy Image Authentication using Forensic Knowledge Graphs**](https://eccv.ecva.net/virtual/2026/poster/3521) | Nguyen et al. | `LMM` `Explainable`
+ [**Asymmetric Anchoring: Opening the Black Box of MLLMs for Forgery Detection**](https://eccv.ecva.net/virtual/2026/poster/5294) | - | [Code](https://github.com/rstao-bjtu/AAP) | `LMM` `Real Anchor`
+ [**Data Circuit Breaker: Identifying Training, Test, and Generated Data in Image Generative Models**](https://eccv.ecva.net/virtual/2026/poster/3593) | - | `Attribution` `Membership`

### ICML 2026

+ [**RA-Det: Towards Universal Detection of AI-Generated Images via Robustness Asymmetry**](https://arxiv.org/abs/2603.01544) | Wang et al. | [Code](https://github.com/dongdongunique/RA-Det) | `Perturbation`
+ [**OmniAID: Decoupling Semantic and Artifacts for Universal AI-Generated Image Detection in the Wild**](https://openreview.net/forum?id=d5rrjYG5pi) | - | [Code](https://github.com/yunncheng/OmniAID) | `Feature Fusion` `MoE`
+ [**DGS-Net: Distillation-Guided Gradient Surgery for CLIP Fine-Tuning in AI-Generated Image Detection**](https://arxiv.org/abs/2511.13108) | Yan et al. | `CLIP`
+ [**Can We Build a Monolithic Model for Fake Image Detection? SICA: Semantic-Induced Constrained Adaptation for Unified-Yet-Discriminative Artifact Feature Space Reconstruction**](https://openreview.net/forum?id=0B54C7rFJa) | - | [Code](https://github.com/venus-guangjian/SICA_OpenMMSec) | `CLIP`
+ [**ForensicConcept: Transferable Forensic Concepts for AIGI Detection**](https://openreview.net/forum?id=SzPII70Uta) | - | `Feature Fusion`
+ [**Dissect and Prune: Enhancing Robustness in AI-Generated Image Detection**](https://openreview.net/forum?id=JcjRShiRQz) | - | [Code](https://github.com/anti-fake/dear) | `Robustness`
+ [**PGC: Peak-Guided Calibration for Generalizable AI-Generated Image Detection**](https://openreview.net/forum?id=yEjix8H6Dw) | - | [Code](https://github.com/xiaoyu6868/PGC) | `Calibration`
+ [**Where Detectors Fail: Probing Generative Space for Generalizable AI-Generated Image Detection**](https://openreview.net/forum?id=gAXiBfnvbD) | - | [Code](https://github.com/Amamiya-C/PROBE-AIGI-Detection) | `Data Construction`
+ [**Fleet: Few Shots Lead Effective AI-generated Image Detection**](https://openreview.net/forum?id=3QstqZrwjO) | - | [Code](https://github.com/ICTMCG/Fleet) | `Few-shot`
+ [**Breaking Manifold Continuity: Vector Quantized Modeling for Real-Centric Deepfake Detection**](https://openreview.net/forum?id=WrlqkXYYCx) | - | `Deepfake` `Real-Centric` (main eval on face datasets; GenImage only in appendix)
+ [**TranX-Adapter: Bridging Artifacts and Semantics within MLLMs for Robust AI-generated Image Detection**](https://openreview.net/forum?id=Iy6isx8QOp) | - | `LMM`
+ [**Deep Residual Injection for Full-Spectrum Forensic Signal Perception in Multimodal Large Language Models**](https://openreview.net/forum?id=S2ilvpV9du) | - | [Code](https://github.com/KQL11/Deep-VRM) | `LMM`
+ [**GenShield: Unified Detection and Artifact Correction for AI-Generated Images**](https://openreview.net/forum?id=Fhtwta4397) | - | [Code](https://github.com/zhipeixu/GenShield) | `LMM`

### CVPR 2026

+ [**SimLBR: Learning to Detect Fake Images by Learning to Detect Real Images**](https://arxiv.org/abs/2602.20412) | Dhakal et al. | `Training Strategy`
+ [**Scaling Up AI-Generated Image Detection via Generator-Aware Prototypes**](https://arxiv.org/abs/2512.12982) | Qin et al. | [Code](https://github.com/UltraCapture/GAPL) | `Multi-Generator`
+ [**Towards Generalizable AI-Generated Image Detection via Image-Adaptive Prompt Learning**](https://arxiv.org/abs/2508.01603) | Li et al. | [Code](https://github.com/liyih/IAPL) | `Prompt Learning`
+ [**Layer Consistency Matters: Elegant Latent Transition Discrepancy for Generalizable Synthetic Image Detection**](https://arxiv.org/abs/2603.10598) | Yang et al. | [Code](https://github.com/yywencs/LTD) | `Latent`
+ [**A Debiased Reconstruction-based Framework for Training-Free Detection of AI-Generated Images**](https://openaccess.thecvf.com/content/CVPR2026/html/Choi_A_Debiased_Reconstruction-based_Framework_for_Training-Free_Detection_of_AI-Generated_Images_CVPR_2026_paper.html) | Choi et al. | `Reconstruction` `Training-free`
+ [**A Difference-in-Difference Approach to Detecting AI-Generated Images**](https://openaccess.thecvf.com/content/CVPR2026/html/Qi_A_Difference-in-Difference_Approach_to_Detecting_AI-Generated_Images_CVPR_2026_paper.html) | Qi et al. | [Code](https://github.com/Qixinyi1122lucky/DID) | `Reconstruction`
+ [**Enabling Supervised Learning of Generative Signatures for Generalized AI-Generated Images Detection**](https://openaccess.thecvf.com/content/CVPR2026/html/Fei_Enabling_Supervised_Learning_of_Generative_Signatures_for_Generalized_AI-Generated_Images_CVPR_2026_paper.html) | Fei et al. | [Code](https://github.com/jumpycat/GenSign) | `Data Construction`
+ [**Zero-shot Detection of AI-Generated Image via RAW-RGB Alignment**](https://openaccess.thecvf.com/content/CVPR2026/html/Wu_Zero-shot_Detection_of_AI-Generated_Image_via_RAW-RGB_Alignment_CVPR_2026_paper.html) | Wu et al. | `Zero-shot`
+ [**PPM-CLIP: Probabilistic Prompt Modeling for Generalizable AI-Generated Image Detection**](https://openaccess.thecvf.com/content/CVPR2026/html/Wang_PPM-CLIP_Probabilistic_Prompt_Modeling_for_Generalizable_AI-Generated_Image_Detection_CVPR_2026_paper.html) | Wang et al. | `Prompt Learning`
+ [**Diversity over Uniformity: Rethinking Representation in Generated Image Detection**](https://openaccess.thecvf.com/content/CVPR2026/html/He_Diversity_over_Uniformity_Rethinking_Representation_in_Generated_Image_Detection_CVPR_2026_paper.html) | He et al. | `Feature Fusion`
+ [**SAIDO: Generalizable Detection of AI-Generated Images via Scene-Aware and Importance-Guided Dynamic Optimization in Continual Learning**](https://openaccess.thecvf.com/content/CVPR2026/html/Hu_SAIDO_Generalizable_Detection_of_AI-Generated_Images_via_Scene-Aware_and_Importance-Guided_CVPR_2026_paper.html) | Hu et al. | `Multi-Generator` `Continual`
+ [**Detecting Compressed AI-Generated Images via Phase Spectrum Robustness**](https://openaccess.thecvf.com/content/CVPR2026/html/Li_Detecting_Compressed_AI-Generated_Images_via_Phase_Spectrum_Robustness_CVPR_2026_paper.html) | Li et al. | `Frequency`
+ [**Cross-modal Representation Learning for Diffusion-generated Image Detection**](https://openaccess.thecvf.com/content/CVPR2026/html/Gong_Cross-modal_Representation_Learning_for_Diffusion-generated_Image_Detection_CVPR_2026_paper.html) | Gong et al. | `Up-sampling Artifact`
+ [**Locate-Then-Examine: Grounded Region Reasoning Improves Detection of AI-Generated Images**](https://openaccess.thecvf.com/content/CVPR2026/html/Ji_Locate-Then-Examine_Grounded_Region_Reasoning_Improves_Detection_of_AI-Generated_Images_CVPR_2026_paper.html) | Ji et al. | `LMM`
+ [**UniGenDet: A Unified Generative-Discriminative Framework for Co-Evolutionary Image Generation and Generated Image Detection**](https://openaccess.thecvf.com/content/CVPR2026/html/Zhang_UniGenDet_A_Unified_Generative-Discriminative_Framework_for_Co-Evolutionary_Image_Generation_and_CVPR_2026_paper.html) | Zhang et al. | [Code](https://github.com/Zhangyr2022/UniGenDet) | `LMM`
+ [**Attribution as Retrieval: Model-Agnostic AI-Generated Image Attribution**](https://openaccess.thecvf.com/content/CVPR2026/html/Wang_Attribution_as_Retrieval_Model-Agnostic_AI-Generated_Image_Attribution_CVPR_2026_paper.html) | Wang et al. | [Code](https://github.com/hongsong-wang/LIDA) | `Attribution`
+ [**IncreFA: Breaking the Static Wall of Generative Model Attribution**](https://openaccess.thecvf.com/content/CVPR2026/html/Qin_IncreFA_Breaking_the_Static_Wall_of_Generative_Model_Attribution_CVPR_2026_paper.html) | Qin et al. | [Code](https://github.com/Ant0ny44/IncreFA) | `Attribution`
+ [**When Understanding Becomes a Risk: Authenticity and Safety Risks in the Emerging Image Generation Paradigm**](https://openaccess.thecvf.com/content/CVPR2026/html/Leng_When_Understanding_Becomes_a_Risk_Authenticity_and_Safety_Risks_in_CVPR_2026_paper.html) | Leng et al. | `Analysis`
+ [**EIRES: Training-free AI-Generated Image Detection via Edit-Induced Reconstruction Error Shift**](https://openaccess.thecvf.com/content/CVPR2026F/html/Jiang_EIRESTraining-free_AI-Generated_Image_Detection_via_Edit-Induced_Reconstruction_Error_Shift_CVPRF_2026_paper.html) | Jiang et al. | **Findings** | `Reconstruction` `Training-free`
+ [**PRADA: Probability-Ratio-Based Attribution and Detection of Autoregressive-Generated Images**](https://openaccess.thecvf.com/content/CVPR2026F/html/Damm_PRADA_Probability-Ratio-Based_Attribution_and_Detection_of_Autoregressive-Generated_Images_CVPRF_2026_paper.html) | Damm et al. | [Code](https://github.com/jonasricker/prada) | **Findings** | `Autoregressive` `Attribution`
+ [**Exploiting the Source-Asymmetry Confidence Gap for Generalizable AI-Generated Image Detection**](https://openaccess.thecvf.com/content/CVPR2026F/html/Zheng_Exploiting_the_Source-Asymmetry_Confidence_Gap_for_Generalizable_AI-Generated_Image_Detection_CVPRF_2026_paper.html) | Zheng et al. | **Findings** | `Calibration`
+ [**Leveraging Arbitrary Data Sources for AI-Generated Image Detection Without Sacrificing Generalization**](https://openaccess.thecvf.com/content/CVPR2026F/html/He_Leveraging_Arbitrary_Data_Sources_for_AI-Generated_Image_Detection_Without_Sacrificing_CVPRF_2026_paper.html) | He et al. | **Findings** | `One-class`
+ [**In2CLR: Joint Intra-Inter Curriculum Learning with Review for Degraded Fake Image Detection**](https://openaccess.thecvf.com/content/CVPR2026F/html/Li_In2CLR_Joint_Intra-Inter_Curriculum_Learning_with_Review_for_Degraded_Fake_CVPRF_2026_paper.html) | Li et al. | **Findings** | `Robustness`
+ [**ForenDeX: Unlocking Forensic Insights for Explainable AI-Generated Image Detection**](https://openaccess.thecvf.com/content/CVPR2026F/html/Tan_ForenDeX_Unlocking_Forensic_Insights_for_Explainable_AI-Generated_Image_Detection_CVPRF_2026_paper.html) | Tan et al. | **Findings** | `LMM`
+ [**Improving Synthesized Image Detection by Disentangling Generator-Shared and Generator-Specific Image Artifacts**](https://openaccess.thecvf.com/content/CVPR2026F/html/Yang_Improving_Synthesized_Image_Detection_by_Disentangling_Generator-Shared_and_Generator-Specific_Image_CVPRF_2026_paper.html) | Yang et al. | **Findings** | `Multi-Generator`
+ [**ReAlign: Generalizable Image Forgery Detection via Reasoning-Aligned Representation**](https://openaccess.thecvf.com/content/CVPR2026/html/Huang_ReAlign_Generalizable_Image_Forgery_Detection_via_Reasoning-Aligned_Representation_CVPR_2026_paper.html) | Huang et al. | `LMM` `Distillation`
+ [**Rethinking VLMs for Image Forgery Detection and Localization**](https://openaccess.thecvf.com/content/CVPR2026F/html/Guo_Rethinking_VLMs_for_Image_Forgery_Detection_and_Localization_CVPRF_2026_paper.html) | Guo et al. | [Code](https://github.com/sha0fengGuo/IFDL-VLM) | **Findings** | `LMM` `Localization`
+ [**UniShield: An Adaptive Multi-Agent Framework for Unified Forgery Image Detection and Localization**](https://openaccess.thecvf.com/content/CVPR2026F/html/Huang_UniShield_An_Adaptive_Multi-Agent_Framework_for_Unified_Forgery_Image_Detection_CVPRF_2026_paper.html) | Huang et al. | **Findings** | `LMM` `Agent`

### ICLR 2026

+ [**Unveiling Perceptual Artifacts: A Fine-Grained Benchmark for Interpretable AI-Generated Image Detection (X-AIGD)**](https://openreview.net/forum?id=Tk8ujiOgHM) | Xiao et al. | [Code](https://github.com/Coxy7/X-AIGD) | `Benchmark`
+ [**FakeXplain: AI-Generated Image Detection via Human-Aligned Grounded Reasoning**](https://openreview.net/forum?id=UcpTOa8OnG) | Ji et al. | `LMM`
+ [**Semantic Visual Anomaly Detection and Reasoning in AI-Generated Images**](https://openreview.net/forum?id=0iN4UKZwgn) | Tan et al. | `LMM`
+ [**No Pixel Left Behind: A Detail-Preserving Architecture for Robust High-Resolution AI-Generated Image Detection**](https://openreview.net/forum?id=9QQ3Kc2hj6) | Mu et al. | `Patch`
+ [**All Patches Matter, More Patches Better: Enhance AI-Generated Image Detection via Panoptic Patch Learning**](https://openreview.net/forum?id=ob7PJs8kPU) | Yang et al. | `Patch`
+ [**HSIC Bottleneck for Cross-Generator and Domain-Incremental Synthetic Image Detection**](https://openreview.net/forum?id=msLnKDvhBx) | Yang et al. | `Multi-Generator`
+ [**Enabling Your Forensic Detector Know How Well It Performs on Distorted Samples**](https://openreview.net/forum?id=Jz5SA2KoFt) | Li et al. | `Robustness`
+ [**Data Provenance for Image Auto-Regressive Generation**](https://openreview.net/forum?id=qYu4wj7O3z) | Zhao et al. | `AR / Attribution`
+ [**A Rich Knowledge Space for Scalable Deepfake Detection**](https://openreview.net/forum?id=hNd5L7WnjC) | Jung et al. | `Deepfake`
+ [**Veritas: Generalizable Deepfake Detection via Pattern-Aware Reasoning**](https://openreview.net/forum?id=5VXJPS1HoM) | Tan et al. | **Oral** | [Code](https://github.com/Rosstein/HydraFake-tanh) | `LMM`

### AAAI 2026

+ [**AEDR: Training-Free AI-Generated Image Attribution via Autoencoder Double-Reconstruction**](https://arxiv.org/abs/2501.09245) | Wang et al. | **Oral** | `Attribution`
+ [**Your AI-Generated Image Detector Can Secretly Achieve SOTA Accuracy, If Calibrated**](https://arxiv.org/abs/2602.01973) | Yang et al. | [Code](https://github.com/muliyangm/AIGI-Det-Calib) | `Calibration`
+ [**Beyond Semantic Features: Pixel-level Mapping for Generalized AI-Generated Image Detection**](https://arxiv.org/abs/2512.17350) | Zhou et al. | `Pixel-level`
+ [**Aggregating Diverse Cue Experts for AI-Generated Image Detection**](https://arxiv.org/abs/2601.08790) | Tan et al. | `Feature Fusion`
+ [**Explainable Synthetic Image Detection through Diffusion Timestep Ensembling**](https://arxiv.org/abs/2503.06201) | Wu et al. | [Code](https://github.com/Shadowlized/ESIDE) | `LMM`

### NeurIPS 2025

+ [**Detecting Generated Images by Fitting Natural Image Distributions**](https://arxiv.org/abs/2411.01674) | Zhang et al. | [Code](https://github.com/tmlr-group/ConV) | `Spotlight` `Training-free`
+ [**Denoising Trajectory Biases for Zero-Shot AI-Generated Image Detection**](https://openreview.net/forum?id=2h8vXbEufN) | Liang et al. | `Training-free`
+ [**Training-free Detection of AI-generated images via Cropping Robustness**](https://arxiv.org/abs/2511.14030) | Choi et al. | [Code](https://github.com/sungikchoi/WaRPAD) | `Training-free`
+ [**Towards Generalizable Detector for Generated Image**](https://openreview.net/forum?id=MeawZGFIcT) | Cai et al. | [Code](https://github.com/dav-joy-thon/DEnD-Detection) | `Perturbation`
+ [**Epistemic Uncertainty for Generated Image Detection**](https://arxiv.org/abs/2412.05897) | Nie et al. | [Code](https://github.com/tmlr-group/WePe) | `Uncertainty`
+ [**Dual Data Alignment Makes AI-Generated Image Detector Easier Generalizable**](https://arxiv.org/abs/2505.14359) | Chen et al. | [Code](https://github.com/roy-ch/Dual-Data-Alignment) | `Spotlight` `Training Strategy`
+ [**MLEP: Multi-granularity Local Entropy Patterns for Generalized AI-generated Image Detection**](https://arxiv.org/abs/2504.13726) | Yuan et al. | [Code](https://github.com/fkeufss/MLEP) | `Entropy`
+ [**FerretNet: Efficient Synthetic Image Detection via Local Pixel Dependencies**](https://arxiv.org/abs/2509.20890) | Liang et al. | [Code](https://github.com/xigua7105/FerretNet) | `Pixel`
+ [**Breaking Latent Prior Bias in Detectors for Generalizable AIGC Image Detection**](https://arxiv.org/abs/2506.00874) | Zhou et al. | `Bias-Free`
+ [**Spot the Fake: Large Multimodal Model-Based Synthetic Image Detection with Artifact Explanation**](https://arxiv.org/abs/2503.14905) | Wen et al. | [Code](https://github.com/opendatalab/FakeVLM) | `LMM`
+ [**Tracing the Roots: Leveraging Temporal Dynamics in Diffusion Trajectories for Origin Attribution**](https://neurips.cc/virtual/2025/poster/116226) | - | `Attribution`
+ [**Is Artificial Intelligence Generated Image Detection a Solved Problem?**](https://arxiv.org/abs/2505.12335) | - | [Code](https://github.com/HorizonTEL/AIGIBench) | `Benchmark`
+ [**ForensicHub: A Unified Benchmark & Codebase for All-Domain Fake Image Detection and Localization**](https://neurips.cc/virtual/2025/poster/121732) | - | [Code](https://github.com/scu-zjz/ForensicHub) | `Benchmark`
+ [**PolyJuice Makes It Real: Black-Box, Universal Red Teaming for Synthetic Image Detectors**](https://neurips.cc/virtual/2025/poster/115746) | - | `Attack`
+ [**NeuroRenderedFake: A Challenging Benchmark to Detect Fake Images Generated by Advanced Neural Rendering Methods**](https://neurips.cc/virtual/2025/poster/121516) | - | `Benchmark`

### ICCV 2025

+ [**LEGION: Learning to Ground and Explain for Synthetic Image Detection**](https://arxiv.org/abs/2503.15264) | Kang et al. | [Code](https://github.com/opendatalab/LEGION) | `LMM`
+ [**AIGI-Holmes: Towards Explainable and Generalizable AI-Generated Image Detection via Multimodal Large Language Models**](https://arxiv.org/abs/2507.02664) | Zhou et al. | [Code](https://github.com/wyczzy/AIGI-Holmes) | `LMM`
+ [**ForgeLens: Data-Efficient Forgery Focus for Generalizable Forgery Image Detection**](https://arxiv.org/abs/2408.13697) | Chen et al. | [Code](https://github.com/Yingjian-Chen/ForgeLens) | `CLIP`
+ [**LOTA: Bit-Planes Guided AI-Generated Image Detection**](https://arxiv.org/abs/2510.14230) | Wang et al. | [Code](https://github.com/hongsong-wang/LOTA) | `Bit-plane`
+ [**Forensic-MoE: Exploring Comprehensive Synthetic Image Detection Traces with Mixture of Experts**](https://iccv.thecvf.com/virtual/2025/poster/919) | Fang et al. | [Code](https://github.com/fangmq77/Forensic-MoE) | `Multi-Generator` `MoE`
+ [**Semantic Discrepancy-aware Detector for Image Forgery Identification**](https://arxiv.org/abs/2508.12341) | Wang et al. | [Code](https://github.com/wzy1111111/SSD) | `Reconstruction`
+ [**D³QE: Learning Discrete Distribution Discrepancy-aware Quantization Error for Autoregressive-Generated Image Detection**](https://arxiv.org/abs/2510.05891) | Zhang et al. | [Code](https://github.com/Zhangyr2022/D3QE) | `Autoregressive`
+ [**Bridging the Gap Between Ideal and Real-world Evaluation: Benchmarking AI-Generated Image Detection**](https://arxiv.org/abs/2509.09172) | Li et al. | `Benchmark`
+ [**Diffusion Epistemic Uncertainty with Asymmetric Learning for Diffusion-Generated Image Detection**](https://arxiv.org/abs/2601.14625) | Huang et al. | `Diffusion`

### ICML 2025

+ [**Are High-Quality AI-Generated Images More Difficult for Models to Detect?**](https://openreview.net/pdf?id=sKYdVKE1tS) | Xiao et al. | [Code](https://github.com/Coxy7/AIGI-Detection-Quality-Paradox) | `Analysis`
+ [**Few-Shot Learner Generalizes Across AI-Generated Image Detection**](https://arxiv.org/abs/2501.08763) | - | [Code](https://github.com/teheperinko541/Few-Shot-AIGI-Detector) | `Few-shot`
+ [**Orthogonal Subspace Decomposition for Generalizable AI-Generated Image Detection**](https://arxiv.org/abs/2411.15633) | Yan et al. | [Code](https://github.com/YZY-stack/Effort-AIGI-Detection) | `CLIP`
+ [**Stay-Positive: A Case for Ignoring Real Image Features in Fake Image Detection**](https://arxiv.org/abs/2502.07778) | - | [Code](https://github.com/AniSundar18/AlignedForensics) | `Training Strategy`
+ [**Unlocking the Capabilities of Large Vision-Language Models for Generalizable and Explainable Deepfake Detection**](https://arxiv.org/abs/2503.14853) | - | `LMM`
+ [**PiD: Generalized AI-Generated Images Detection with Pixelwise Decomposition Residuals**](https://proceedings.mlr.press/v267/fu25i.html) | Fu et al. | `Reconstruction`

### CVPR 2025

+ [**Any-Resolution AI-Generated Image Detection by Spectral Learning**](https://arxiv.org/abs/2411.19417) | Karageorgiou et al. | [Code](https://github.com/mever-team/spai) | `Frequency`
+ [**A Bias-Free Training Paradigm for More General AI-generated Image Detection**](https://arxiv.org/abs/2412.17671) | Guillaro et al. | [Code](https://github.com/grip-unina/B-Free) | `Training Strategy`
+ [**Towards Universal AI-Generated Image Detection by Variational Information Bottleneck Network**](https://openaccess.thecvf.com/content/CVPR2025/papers/Zhang_Towards_Universal_AI-Generated_Image_Detection_by_Variational_Information_Bottleneck_Network_CVPR_2025_paper.pdf) | Zhang et al. | [Code](https://github.com/oceanzhf/VIBAIGCDetect) | `CLIP`
+ [**FIRE: Robust Detection of Diffusion-Generated Images via Frequency-Guided Reconstruction Error**](https://arxiv.org/abs/2412.07140) | Chu et al. | [Code](https://github.com/Chuchad/FIRE) | `Reconstruction`
+ [**Secret Lies in Color: Enhancing AI-Generated Images Detection with Color Distribution Analysis**](https://openaccess.thecvf.com/content/CVPR2025/papers/Jia_Secret_Lies_in_Color_Enhancing_AI-Generated_Images_Detection_with_Color_CVPR_2025_paper.pdf) | Jia et al. | `Color`
+ [**Community Forensics: Using Thousands of Generators to Train Fake Image Detectors**](https://arxiv.org/abs/2411.04125) | Park et al. | [Code](https://github.com/JeongsooP/Community-Forensics) | `Multi-Generator`
+ [**SIDA: Social Media Image Deepfake Detection, Localization and Explanation with LMM**](https://arxiv.org/abs/2412.04292) | Huang et al. | [Code](https://github.com/hzlsaber/SIDA) | `LMM`
+ [**CO-SPY: Combining Semantic and Pixel Features to Detect Synthetic Images by AI**](https://arxiv.org/abs/2503.18286) | Cheng et al. | [Code](https://github.com/Megum1/CO-SPY) | `Feature Fusion`
+ [**D³: Scaling Up Deepfake Detection by Learning from Discrepancy**](https://arxiv.org/abs/2404.04584) | Yang et al. | [Code](https://github.com/BigAandSmallq/D3) | `Training Strategy`
+ [**Forensic Self-Descriptions Are All You Need for Zero-Shot Detection, Open-Set Source Attribution, and Localization**](https://arxiv.org/abs/2503.21003) | Nguyen et al. | `Zero-shot`
+ [**Beyond Generation: A Diffusion-based Low-level Feature Extractor for Detecting AI-generated Images**](https://openaccess.thecvf.com/content/CVPR2025/papers/Zhong_Beyond_Generation_A_Diffusion-based_Low-level_Feature_Extractor_for_Detecting_AI-generated_CVPR_2025_paper.pdf) | Zhong et al. | `Zero-shot`

### ICLR 2025

+ [**Aligned Datasets Improve Detection of Latent Diffusion-Generated Images**](https://arxiv.org/abs/2410.11835) | Rajan et al. | [Code](https://github.com/AniSundar18/AlignedForensics) | `Training Strategy`
+ [**A Sanity Check for AI-generated Image Detection**](https://arxiv.org/abs/2406.19435) | - | [Code](https://github.com/shilinyan99/AIDE) | `Benchmark` `Feature Fusion`
+ [**LOKI: A Comprehensive Synthetic Data Detection Benchmark using Large Multimodal Models**](https://arxiv.org/abs/2410.09732) | - | [Code](https://github.com/opendatalab/LOKI) | `Benchmark`
+ [**FakeShield: Explainable Image Forgery Detection and Localization via Multi-modal Large Language Models**](https://arxiv.org/abs/2410.02761) | Xu et al. | [Code](https://github.com/zhipeixu/FakeShield) | `LMM`


### ECCV 2024

+ [**Zero-Shot Detection of AI-Generated Images**](https://arxiv.org/abs/2409.15875) | Cozzolino et al. | [Code](https://github.com/grip-unina/ZED) | `Zero-shot`
+ [**Contrasting Deepfakes Diffusion via Contrastive Learning and Global-Local Similarities**](https://arxiv.org/abs/2407.20337) | Baraldi et al. | [Code](https://github.com/aimagelab/CoDE) | `Contrastive`
+ [**Leveraging Representations from Intermediate Encoder-Blocks for Synthetic Image Detection**](https://arxiv.org/abs/2402.19091) | Koutlis et al. | [Code](https://github.com/mever-team/rine) | `CLIP`

### NeurIPS 2024

+ [**Breaking Semantic Artifacts for Generalized AI-generated Image Detection**](https://github.com/Zig-HS/FakeImageDetection) | Zheng et al. | [Code](https://github.com/Zig-HS/FakeImageDetection) | `Texture`

### CVPR 2024

+ [**FakeInversion: Learning to Detect Images from Unseen Text-to-Image Models by Inverting Stable Diffusion**](https://openaccess.thecvf.com/content/CVPR2024/html/Cazenavette_FakeInversion_Learning_to_Detect_Images_from_Unseen_Text-to-Image_Models_by_CVPR_2024_paper.html) | Cazenavette et al. | [Page](https://fake-inversion.github.io/) | `Reconstruction`
+ [**AEROBLADE: Training-Free Detection of Latent Diffusion Images Using Autoencoder Reconstruction Error**](https://arxiv.org/abs/2401.17879) | Ricker et al. | [Code](https://github.com/jonasricker/aeroblade) | `Reconstruction`
+ [**LaRE²: Latent Reconstruction Error Based Method for Diffusion-Generated Image Detection**](https://openaccess.thecvf.com/content/CVPR2024/html/Luo_LaRE2_Latent_Reconstruction_Error_Based_Method_for_Diffusion-Generated_Image_Detection_CVPR_2024_paper.html) | Luo et al. | [Code](https://github.com/luo3300612/LaRE) | `Reconstruction`
+ [**MaskSim: Detection of Synthetic Images by Masked Spectrum Similarity Analysis**](https://openaccess.thecvf.com/content/CVPR2024W/DFAD/html/Li_MaskSim_Detection_of_Synthetic_Images_by_Masked_Spectrum_Similarity_Analysis_CVPRW_2024_paper.html) | Li et al. | `Frequency`
+ [**Forgery-aware Adaptive Transformer for Generalizable Synthetic Image Detection**](https://arxiv.org/abs/2312.16649) | Liu et al. | [Code](https://github.com/Michel-liu/FatFormer) | `Adaptation`

### ICML 2024

+ [**How to Trace Latent Generative Model Generated Images without Artificial Watermark?**](https://arxiv.org/abs/2405.13360) | Wang et al. | [Code](https://github.com/ZhentingWang/LatentTracer) | `Attribution`
+ [**DRCT: Diffusion Reconstruction Contrastive Training towards Universal Detection**](https://openreview.net/pdf?id=oRLwyayrh1) | Chen et al. | [Code](https://github.com/beibuwandeluori/DRCT) | `Reconstruction`

### Earlier Works (2020-2023)

<details>
<summary>ICCV 2023</summary>

+ [**DIRE for Diffusion-Generated Image Detection**](https://openaccess.thecvf.com/content/ICCV2023/html/Wang_DIRE_for_Diffusion-Generated_Image_Detection_ICCV_2023_paper.html) | Wang et al. | [Code](https://github.com/ZhendongWang6/DIRE) | `Reconstruction`

</details>

<details>
<summary>CVPR 2023</summary>

+ [**Towards Universal Fake Image Detectors that Generalize Across Generative Models**](https://arxiv.org/abs/2302.10174) | Ojha et al. | [Code](https://github.com/Yuheng-Li/UniversalFakeDetect) | `CLIP`
+ [**Learning on Gradients: Generalized Artifacts Representation for GAN-Generated Images Detection**](https://openaccess.thecvf.com/content/CVPR2023/papers/Tan_Learning_on_Gradients_Generalized_Artifacts_Representation_for_GAN-Generated_Images_Detection_CVPR_2023_paper.pdf) | Tan et al. | [Code](https://github.com/chuangchuangtan/LGrad) | `Gradient`

</details>

<details>
<summary>ECCV 2022</summary>

+ [**Detecting Generated Images by Real Images**](https://link.springer.com/content/pdf/10.1007/978-3-031-19781-9.pdf) | Tang et al. | [Code](https://github.com/Tangsenghenshou/Detecting-Generated-Images-by-Real-Images) | `Real-Only`
+ [**FingerprintNet: Synthesized Fingerprints for Generated Image Detection**](https://www.ecva.net/papers/eccv_2022/papers_ECCV/papers/136740071.pdf) | - | `Fingerprint`
+ [**On The Detection of Synthetic Images Generated by Diffusion Models**](https://arxiv.org/abs/2211.00680) | Corvi et al. | [Code](https://github.com/grip-unina/DMimageDetection) | `Diffusion`

</details>

<details>
<summary>CVPR 2020 & NeurIPS 2020</summary>

+ [**CNN-generated images are surprisingly easy to spot...for now**](https://arxiv.org/abs/1912.11035) | Wang et al. | [Code](https://github.com/peterwang512/CNNDetection) | `CNN Forensics`
+ [**Watch your Up-Convolution: CNN Based Generative Deep Neural Networks are Failing to Reproduce Spectral Distributions**](https://arxiv.org/abs/2003.01826) | Durall et al. | [Code](https://github.com/cc-hpc-itwm/UpConv) | `Frequency`
+ [**Fourier Spectrum Discrepancies in Deep Network Generated Images**](https://arxiv.org/abs/1911.06465) | - | [Code](https://github.com/tarikdzanic/FourierSpectrumDiscrepancies) | `Frequency`
+ [**Leveraging Frequency Analysis for Deep Fake Image Recognition**](http://proceedings.mlr.press/v119/frank20a/frank20a.pdf) | Frank et al. | [Code](https://github.com/RUB-SysSec/GANDCTAnalysis) | `Frequency`

</details>

<details>
<summary>Other Notable Works (arXiv)</summary>

+ [**Detecting Generated Images by Real Images Only**](https://arxiv.org/abs/2311.00962) | 2023 | `Real-Only`
+ [**Transfer Learning of Real Image Features with Soft Contrastive Loss for Fake Image Detection**](https://arxiv.org/abs/2403.16513) | 2024 | `Training Strategy`
+ [**RIGID: A Training-free and Model-Agnostic Framework for Robust AI-Generated Image Detection**](https://arxiv.org/abs/2405.20112) | He et al. 2024 | `Perturbation`
+ [**GenDet: Towards Good Generalizations for AI-Generated Image Detection**](https://arxiv.org/abs/2312.08880) | 2023 | `Training Strategy`
+ [**Generalizable Synthetic Image Detection via Language-guided Contrastive Learning (LASTED)**](https://arxiv.org/abs/2305.13800) | [Code](https://github.com/HighwayWu/LASTED) | 2023 | `CLIP`
+ [**AntifakePrompt: Prompt-Tuned Vision-Language Models are Fake Image Detectors**](https://arxiv.org/abs/2310.17419) | Chang et al. 2023 | [Code](https://github.com/nctu-eva-lab/AntifakePrompt) | `Prompt`
+ [**PatchCraft: Exploring Texture Patch for Efficient AI-generated Image Detection**](https://arxiv.org/abs/2311.12397) | Zhong et al. 2024 | `Patch`
+ [**Bi-LORA: A Vision-Language Approach for Synthetic Image Detection**](https://arxiv.org/abs/2404.01959) | 2024 | [Code](https://github.com/Mamadou-Keita/VLM-DETECT) | `CLIP`
+ [**Fake or JPEG? Revealing Common Biases in Generated Image Detection Datasets**](https://arxiv.org/abs/2403.17608) | Grommelt et al. 2024 | [Page](https://www.unbiased-genimage.org/) | `Bias`

</details>

---

## Papers by Category

<a id="1-clip--vision-language-methods"></a>

### 1. Pretrained Foundation Models (CLIP / VLM / DINO)

> Leverage pretrained foundation models (CLIP, other vision-language models, or self-supervised backbones such as DINOv2/v3) whose pre-trained features already encode subtle generative artifacts, enabling strong cross-generator generalization with minimal fine-tuning.

#### 1.1 CLIP Fine-tuning & Adaptation

> Adapt CLIP's visual encoder via linear probes, LoRA, or lightweight adapters to extract forgery-discriminative features with minimal parameter updates.

+ [**Raising the Bar of AI-generated Image Detection with CLIP**](https://arxiv.org/abs/2312.00195) | Cozzolino et al. | 2024 | [Code](https://github.com/grip-unina/ClipBased-SyntheticImageDetection) | `CLIP`
+ [**CLIPping the Deception: Adapting Vision-Language Models for Universal Deepfake Detection**](https://dl.acm.org/doi/10.1145/3652583.3658035) | ICMR 2024 | [Code](https://github.com/sohailahmedkhan/CLIPping-the-Deception) | `CLIP`
+ [**DeeCLIP: A Robust and Generalizable Transformer-Based Framework**](https://arxiv.org/abs/2504.19876) | 2025 | [Code](https://github.com/Mamadou-Keita/DeeCLIP) | `CLIP`
+ [**DGS-Net: Distillation-Guided Gradient Surgery for CLIP Fine-Tuning in AI-Generated Image Detection**](https://arxiv.org/abs/2511.13108) | Yan et al. | ICML 2026 | `CLIP`
+ [**NS-Net: Decoupling CLIP Semantic Information through NULL-Space for Generalizable AI-Generated Image Detection**](https://arxiv.org/abs/2508.01248) | Yan et al. 2025 | `CLIP`
+ [**When Semantics Regulate: Rethinking Patch Shuffle for AI-Generated Image Detection**](https://arxiv.org/abs/2511.19126) | 2025 | `CLIP`
+ [**ForgeLens: Data-Efficient Forgery Focus for Generalizable Forgery Image Detection**](https://arxiv.org/abs/2408.13697) | Chen et al. | ICCV 2025 | [Code](https://github.com/Yingjian-Chen/ForgeLens) | `CLIP`
+ [**Can We Build a Monolithic Model for Fake Image Detection? SICA: Semantic-Induced Constrained Adaptation for Unified-Yet-Discriminative Artifact Feature Space Reconstruction**](https://openreview.net/forum?id=0B54C7rFJa) | - | ICML 2026 | [Code](https://github.com/venus-guangjian/SICA_OpenMMSec) | `CLIP`
+ [**SAGE: Semantic-Agnostic Image Embedding for Generalized AI-Generated Image Detection**](https://openreview.net/forum?id=sCLdMcBvzN) | - | NeurIPS 2026 | `CLIP`
+ [**Less is More: Fewer Tokens and Blocks Make AIGI Detection Faster and More Generalizable**](https://openreview.net/forum?id=l7AUTUgcKZ) | - | NeurIPS 2026 | `CLIP`
+ [**Prior-Conditioned Gaussian Discriminants for Generalizable AI-generated Image Detection**](https://eccv.ecva.net/virtual/2026/poster/5771) | - | ECCV 2026 | `Adaptation`

#### 1.2 Prompt Learning & Language-Guided

> Steer CLIP's representation via learnable prompts or language-guided objectives rather than weight adaptation, enabling few-shot domain transfer.

+ [**AntifakePrompt: Prompt-Tuned Vision-Language Models are Fake Image Detectors**](https://arxiv.org/abs/2310.17419) | Chang et al. 2024 | [Code](https://github.com/nctu-eva-lab/AntifakePrompt) | `Prompt`
+ [**Forgery-aware Adaptive Transformer for Generalizable Synthetic Image Detection**](https://arxiv.org/abs/2312.16649) | Liu et al. | CVPR 2024 | [Code](https://github.com/Michel-liu/FatFormer) | `Language-Guided`
+ [**MiraGe: Multimodal Discriminative Representation Learning for Generalizable AI-Generated Image Detection**](https://arxiv.org/abs/2508.01525) | Shi et al. 2025 | `Prompt`
+ [**Towards Generalizable AI-Generated Image Detection via Image-Adaptive Prompt Learning**](https://arxiv.org/abs/2508.01603) | Li et al. | CVPR 2026 | [Code](https://github.com/liyih/IAPL) | `Prompt`
+ [**PPM-CLIP: Probabilistic Prompt Modeling for Generalizable AI-Generated Image Detection**](https://openaccess.thecvf.com/content/CVPR2026/html/Wang_PPM-CLIP_Probabilistic_Prompt_Modeling_for_Generalizable_AI-Generated_Image_Detection_CVPR_2026_paper.html) | Wang et al. | CVPR 2026 | `Prompt`
+ [**Too Aligned to be Real: Detecting AI-Generated Images via Cross-modal Alignment Shift**](https://openreview.net/forum?id=k72oka2LYR) | - | NeurIPS 2026 | `Language-Guided`

#### 1.3 Feature Fusion

> Decompose or fuse heterogeneous features—semantic, frequency, pixel-level—to separate forgery clues from content and improve cross-domain robustness.

+ [**CausalCLIP: Causally-Informed Feature Disentanglement and Filtering for Generalizable Detection**](https://arxiv.org/abs/2512.13285) | Liu et al. 2025 | `CLIP`
+ [**Mixture of Low-rank Experts for Transferable AI-Generated Image Detection**](https://arxiv.org/abs/2404.04883) | Liu et al. 2024 | [Code](https://github.com/zhliuworks/CLIPMoLE) | `CLIP`
+ [**Orthogonal Subspace Decomposition for Generalizable AI-Generated Image Detection**](https://arxiv.org/abs/2411.15633) | Yan et al. | ICML 2025 | [Code](https://github.com/YZY-stack/Effort-AIGI-Detection) | `CLIP`
+ [**CO-SPY: Combining Semantic and Pixel Features to Detect Synthetic Images by AI**](https://arxiv.org/abs/2503.18286) | Cheng et al. | CVPR 2025 | [Code](https://github.com/Megum1/CO-SPY) | `Feature Fusion`
+ [**Aggregating Diverse Cue Experts for AI-Generated Image Detection**](https://arxiv.org/abs/2601.08790) | Tan et al. | AAAI 2026 | `Feature Fusion`
+ [**AIDE: A Sanity Check for AI-generated Image Detection**](https://arxiv.org/abs/2406.19435) | Yan et al. | ICLR 2025 | [Code](https://github.com/shilinyan99/AIDE) | `Feature Fusion`
+ [**OmniAID: Decoupling Semantic and Artifacts for Universal AI-Generated Image Detection in the Wild**](https://openreview.net/forum?id=d5rrjYG5pi) | - | ICML 2026 | [Code](https://github.com/yunncheng/OmniAID) | `Feature Fusion`
+ [**Diversity over Uniformity: Rethinking Representation in Generated Image Detection**](https://openaccess.thecvf.com/content/CVPR2026/html/He_Diversity_over_Uniformity_Rethinking_Representation_in_Generated_Image_Detection_CVPR_2026_paper.html) | He et al. | CVPR 2026 | `Feature Fusion`
+ [**ForensicConcept: Transferable Forensic Concepts for AIGI Detection**](https://openreview.net/forum?id=SzPII70Uta) | - | ICML 2026 | `Feature Fusion`
+ [**LoRC: Detecting AI-Generated Images via Low-Rank Collapse in the Semantic-Residual Space**](https://arxiv.org/abs/2608.20882) | Yan et al. | ECCV 2026 | `Feature Decoupling`

#### 1.4 Information Bottleneck

> Apply information bottleneck principles to compress away content and retain only detection-relevant signals, improving robustness to distribution shift.

+ [**Towards Universal AI-Generated Image Detection by Variational Information Bottleneck Network**](https://openaccess.thecvf.com/content/CVPR2025/papers/Zhang_Towards_Universal_AI-Generated_Image_Detection_by_Variational_Information_Bottleneck_Network_CVPR_2025_paper.pdf) | Zhang et al. | CVPR 2025 | [Code](https://github.com/oceanzhf/VIBAIGCDetect) | `CLIP`
+ [**Multimodal Conditional Information Bottleneck for Generalizable AI-Generated Image Detection**](https://arxiv.org/abs/2505.15217) | Qin et al. 2025 | [Code](https://github.com/Ant0ny44/InfoFD) | `CLIP`

---

### 2. Reconstruction-based Methods

> Detect AI-generated images by measuring how well a pre-trained generative model can reconstruct them—synthetic images yield lower error than real ones.

#### 2.1 Diffusion Reconstruction

> Compute reconstruction errors via DDIM inversion or latent trajectory encoding under a fixed diffusion model.

+ [**DIRE for Diffusion-Generated Image Detection**](https://arxiv.org/abs/2303.09295) | Wang et al. | ICCV 2023 | [Code](https://github.com/ZhendongWang6/DIRE) | `Reconstruction`
+ [**DRCT: Diffusion Reconstruction Contrastive Training towards Universal Detection**](https://openreview.net/pdf?id=oRLwyayrh1) | ICML 2024 | [Code](https://github.com/beibuwandeluori/DRCT) | `Reconstruction`
+ [**LATTE: Latent Trajectory Embedding for Diffusion-Generated Image Detection**](https://arxiv.org/abs/2507.03054) | Vasilcoiu et al. 2025 | [Code](https://github.com/AnaMVasilcoiu/LATTE-Diffusion-Detector) | `Reconstruction`
+ [**STD-FD: Spatio-Temporal Distribution Fitting Deviation for AIGC Forgery Identification**](https://proceedings.mlr.press/v267/lou25a.html) | Lou et al. | [Code](https://github.com/HengruiLou/STDFD) | `Reconstruction`
+ [**A Difference-in-Difference Approach to Detecting AI-Generated Images**](https://openaccess.thecvf.com/content/CVPR2026/html/Qi_A_Difference-in-Difference_Approach_to_Detecting_AI-Generated_Images_CVPR_2026_paper.html) | Qi et al. | CVPR 2026 | [Code](https://github.com/Qixinyi1122lucky/DID) | `Reconstruction`

#### 2.2 Autoencoder Reconstruction

> Exploit VAE or MAE encoder–decoder reconstruction error, which is near-zero for in-distribution generated images but elevated for real ones.

+ [**AEROBLADE: Training-Free Detection of Latent Diffusion Images Using Autoencoder Reconstruction Error**](https://arxiv.org/abs/2401.17879) | Ricker et al. | CVPR 2024 | [Code](https://github.com/jonasricker/aeroblade) | `Reconstruction`
+ [**GRRE: Leveraging G-Channel Removed Reconstruction Error for Robust Detection of AI-Generated Images**](https://arxiv.org/abs/2601.02709) | He et al. 2026 | `Reconstruction`
+ [**CINEMAE: Leveraging Frozen Masked Autoencoders for Cross-Generator AI Image Detection**](https://arxiv.org/abs/2511.06325) | Jang et al. 2025 | `Reconstruction`
+ [**FIRE: Robust Detection of Diffusion-Generated Images via Frequency-Guided Reconstruction Error**](https://arxiv.org/abs/2412.07140) | Chu et al. | CVPR 2025 | [Code](https://github.com/Chuchad/FIRE) | `Reconstruction`
+ [**A Debiased Reconstruction-based Framework for Training-Free Detection of AI-Generated Images**](https://openaccess.thecvf.com/content/CVPR2026/html/Choi_A_Debiased_Reconstruction-based_Framework_for_Training-Free_Detection_of_AI-Generated_Images_CVPR_2026_paper.html) | Choi et al. | CVPR 2026 | `Reconstruction`
+ [**EIRES: Training-free AI-Generated Image Detection via Edit-Induced Reconstruction Error Shift**](https://openaccess.thecvf.com/content/CVPR2026F/html/Jiang_EIRESTraining-free_AI-Generated_Image_Detection_via_Edit-Induced_Reconstruction_Error_Shift_CVPRF_2026_paper.html) | Jiang et al. | CVPR 2026 Findings | `Reconstruction`
+ [**GLARE: Towards Generalizable Detection of Latent Diffusion Images with Global-Local Reconstruction Error**](https://media.eventhosts.cc/Conferences/ECCV2026/pdfs/6737.pdf) | Yan et al. | ECCV 2026 | `Reconstruction`

#### 2.3 Latent Space

> Work in the compressed latent space of a diffusion VAE, using inversion residuals as detection signals.

+ [**LaRE²: Latent Reconstruction Error Based Method for Diffusion-Generated Image Detection**](https://arxiv.org/abs/2403.17465) | Luo et al. | CVPR 2024 | [Code](https://github.com/luo3300612/LaRE) | `Reconstruction`
+ [**FakeInversion: Learning to Detect Images from Unseen Text-to-Image Models by Inverting Stable Diffusion**](https://arxiv.org/abs/2406.08603) | Cazenavette et al. | CVPR 2024 | `Reconstruction`

#### 2.4 Semantic-Aware Reconstruction

> Condition reconstruction errors on semantic content to better disentangle generation artifacts from content-related variation.

+ [**SARE: Semantic-Aware Reconstruction Error for Generalizable Diffusion-Generated Image Detection**](https://arxiv.org/abs/2508.09487) | Kang et al. 2025 | arXiv | `Reconstruction`
+ [**Exposing the Fake: Effective Diffusion-Generated Images Detection**](https://arxiv.org/abs/2307.06272) | Ma et al. | AdvML-Frontiers@ICML 2023 Workshop | `Reconstruction`

---

### 3. Frequency-domain Methods

> Exploit spectral artifacts—fractal self-similarity, missing high-frequency fall-off, color demosaicing inconsistencies—left by generative pipelines in the frequency domain.

+ [**Generalizable AI-Generated Image Detection Based on Fractal Self-Similarity in the Spectrum**](https://arxiv.org/abs/2503.08484) | Xiao et al. 2025 | `Frequency`
+ [**Any-Resolution AI-Generated Image Detection by Spectral Learning**](https://arxiv.org/abs/2411.19417) | Karageorgiou et al. | CVPR 2025 | [Code](https://github.com/mever-team/spai) | `Frequency`
+ [**Improving Synthetic Image Detection Towards Generalization: An Image Transformation Perspective**](https://arxiv.org/abs/2408.06741) | Li et al. 2025 | [Code](https://github.com/Ouxiang-Li/SAFE) | `Frequency`
+ [**Training-Free AI-Generated Image Detection via Spectral Artifacts**](https://openreview.net/forum?id=G9Oj0dMQIJ) | `Frequency`
+ [**Secret Lies in Color: Enhancing AI-Generated Images Detection with Color Distribution Analysis**](https://openaccess.thecvf.com/content/CVPR2025/papers/Jia_Secret_Lies_in_Color_Enhancing_AI-Generated_Images_Detection_with_Color_CVPR_2025_paper.pdf) | Jia et al. | CVPR 2025 | `Color`
+ [**Color Matters: Demosaicing-Guided Color Correlation Training for Generalizable AI-Generated Image Detection**](https://arxiv.org/abs/2601.22778) | Zhong et al. 2026 | `Color`
+ [**Fourier Spectrum Discrepancies in Deep Network Generated Images**](https://arxiv.org/abs/1911.06465) | NeurIPS 2020 | [Code](https://github.com/tarikdzanic/FourierSpectrumDiscrepancies) | `Frequency`
+ [**Detecting Compressed AI-Generated Images via Phase Spectrum Robustness**](https://openaccess.thecvf.com/content/CVPR2026/html/Li_Detecting_Compressed_AI-Generated_Images_via_Phase_Spectrum_Robustness_CVPR_2026_paper.html) | Li et al. | CVPR 2026 | `Frequency`

---

### 4. Patch / Texture-based Methods

> Extract and compare local patch-level texture features—noise residuals, texture contrast, patch-contrastive signals—to expose synthetic origin independent of semantic content.

+ [**A Single Simple Patch is All You Need for AI-generated Image Detection**](https://arxiv.org/abs/2402.01123) | Chen et al. 2024 | [Code](https://github.com/bcmi/SSP-AI-Generated-Image-Detection) | `Patch`
+ [**PatchCraft: Exploring Texture Patch for Efficient AI-generated Image Detection**](https://arxiv.org/abs/2311.12397) | Zhong et al. 2024 | `Patch`
+ [**All Patches Matter, More Patches Better: Enhance AI-Generated Image Detection via Panoptic Patch Learning**](https://openreview.net/forum?id=ob7PJs8kPU) | Yang et al. | ICLR 2026 | `Patch`
+ [**TextureCrop: Enhancing Synthetic Image Detection through Texture-based Cropping**](https://arxiv.org/abs/2407.15500) | Konstantinidou et al. | `Texture`
+ [**Breaking Semantic Artifacts for Generalized AI-generated Image Detection**](https://github.com/Zig-HS/FakeImageDetection) | Zheng et al. | NeurIPS 2024 | [Code](https://github.com/Zig-HS/FakeImageDetection) | `Texture`
+ [**No Pixel Left Behind: A Detail-Preserving Architecture for Robust High-Resolution AI-Generated Image Detection**](https://openreview.net/forum?id=9QQ3Kc2hj6) | Mu et al. | ICLR 2026 | `Pixel`
+ [**Rethinking the Use of Vision Transformers for AI-Generated Image Detection**](https://arxiv.org/abs/2512.04969) | Park et al. 2025 | [Code](https://github.com/nahyeonkaty/mold) | `Architecture`

---

### 5. Low-level Artifact Detection

> Detect fine-grained pixel-level artifacts—upsampling patterns, local pixel dependencies, bit-plane anomalies, entropy deviations—that are architecture-agnostic byproducts of the generation pipeline.

+ [**Rethinking the Up-Sampling Operations in CNN-based Generative Network for Generalizable Deepfake Detection**](https://arxiv.org/abs/2312.10461) | Tan et al. | CVPR 2024 | [Code](https://github.com/chuangchuangtan/NPR-DeepfakeDetection) | `Up-sampling Artifact`
+ [**FerretNet: Efficient Synthetic Image Detection via Local Pixel Dependencies**](https://arxiv.org/abs/2509.20890) | Liang et al. | NeurIPS 2025 | [Code](https://github.com/xigua7105/FerretNet) | `Pixel`
+ [**Beyond Semantic Features: Pixel-level Mapping for Generalized AI-Generated Image Detection**](https://arxiv.org/abs/2512.17350) | Zhou et al. | AAAI 2026 | `Pixel`
+ [**PiD: Generalized AI-Generated Images Detection with Pixelwise Decomposition Residuals**](https://proceedings.mlr.press/v267/fu25i.html) | Fu et al. | ICML 2025 | `Pixel`
+ [**MLEP: Multi-granularity Local Entropy Patterns for Generalized AI-generated Image Detection**](https://arxiv.org/abs/2504.13726) | Yuan et al. | NeurIPS 2025 | [Code](https://github.com/fkeufss/MLEP) | `Entropy`
+ [**LOTA: Bit-Planes Guided AI-Generated Image Detection**](https://arxiv.org/abs/2510.14230) | Wang et al. | ICCV 2025 | [Code](https://github.com/hongsong-wang/LOTA) | `Bit-plane`
+ [**Revealing the Implicit Noise-based Imprint of Generative Models**](https://arxiv.org/abs/2503.09314) | Li et al. 2025 | `Fingerprint`
+ [**Perceptual Classifiers: Detecting Generative Images using Perceptual Features**](https://openaccess.thecvf.com/content/ICCV2025W/VQualA/papers/Durbha_Perceptual_Classifiers_Detecting_Generative_Images_using_Perceptual_Features_ICCVW_2025_paper.pdf) | Durbha et al. | ICCV 2025 Workshop | `Perceptual`
+ [**Beyond Generation: A Diffusion-based Low-level Feature Extractor for Detecting AI-generated Images**](https://openaccess.thecvf.com/content/CVPR2025/papers/Zhong_Beyond_Generation_A_Diffusion-based_Low-level_Feature_Extractor_for_Detecting_AI-generated_CVPR_2025_paper.pdf) | Zhong et al. | CVPR 2025 | `Zero-shot`
+ [**Exploring the Collaborative Advantage of Low-level Information on Generalizable AI-Generated Image Detection**](https://arxiv.org/abs/2504.00463) | Zhou et al. 2025 | `Feature Fusion`
+ [**Cross-modal Representation Learning for Diffusion-generated Image Detection**](https://openaccess.thecvf.com/content/CVPR2026/html/Gong_Cross-modal_Representation_Learning_for_Diffusion-generated_Image_Detection_CVPR_2026_paper.html) | Gong et al. | CVPR 2026 | `Up-sampling Artifact`
+ [**Beyond Real or Fake: A Dual-Channel Authenticity and Reasoning Protocol for Photographic Assessment**](https://neurips.cc/virtual/2026/poster/154533) | Li et al. | NeurIPS 2026 | `Camera Fingerprint`

---

### 6. Perturbation / Robustness-based Methods

> Exploit the asymmetric response of real vs. synthetic images to controlled perturbations—real images are more stable on the natural manifold, while generated images deviate more.

+ [**RIGID: A Training-free and Model-Agnostic Framework for Robust AI-Generated Image Detection**](https://arxiv.org/abs/2405.20112) | He et al. 2024 | `Perturbation`
+ [**RA-Det: Towards Universal Detection of AI-Generated Images via Robustness Asymmetry**](https://arxiv.org/abs/2603.01544) | Wang et al. | ICML 2026 | [Code](https://github.com/dongdongunique/RA-Det) | `Perturbation`
+ [**Detecting AI-Generated Images via Distributional Deviations from Real Images**](https://arxiv.org/abs/2601.03586) | Niu et al. 2026 | `Perturbation`
+ [**Epistemic Uncertainty for Generated Image Detection (WePe)**](https://arxiv.org/abs/2412.05897) | Nie et al. | NeurIPS 2025 | [Code](https://github.com/tmlr-group/WePe) | `Uncertainty`
+ [**How Noise Benefits AI-generated Image Detection**](https://arxiv.org/abs/2511.16136) | Yan et al. 2025 | `Perturbation`
+ [**Towards Generalizable Detector for Generated Image**](https://openreview.net/forum?id=MeawZGFIcT) | Cai et al. | NeurIPS 2025 | [Code](https://github.com/dav-joy-thon/DEnD-Detection) | `Perturbation`
+ [**Detecting Generated Images by Fitting Natural Image Distributions**](https://arxiv.org/abs/2411.01674) | Zhang et al. | NeurIPS 2025 Spotlight | [Code](https://github.com/tmlr-group/ConV) | `Training-free`
+ [**ENABLING YOUR FORENSIC DETECTOR KNOW HOW WELL IT PERFORMS ON DISTORTED SAMPLES**](https://openreview.net/forum?id=Jz5SA2KoFt) | Li et al. | ICLR 2026 | `Robustness`
+ [**Dissect and Prune: Enhancing Robustness in AI-Generated Image Detection**](https://openreview.net/forum?id=JcjRShiRQz) | - | ICML 2026 | [Code](https://github.com/anti-fake/dear) | `Robustness`
+ [**In2CLR: Joint Intra-Inter Curriculum Learning with Review for Degraded Fake Image Detection**](https://openaccess.thecvf.com/content/CVPR2026F/html/Li_In2CLR_Joint_Intra-Inter_Curriculum_Learning_with_Review_for_Degraded_Fake_CVPRF_2026_paper.html) | Li et al. | CVPR 2026 Findings | `Robustness`

---

### 7. LMM / Reasoning-based Methods

> Leverage large multimodal models to provide not just binary detection but also artifact localization, reasoning, and natural-language explanations of *why* an image is fake.

+ [**LEGION: Learning to Ground and Explain for Synthetic Image Detection**](https://arxiv.org/abs/2503.15264) | Kang et al. | ICCV 2025 | [Code](https://github.com/opendatalab/LEGION) | `LMM`
+ [**AIGI-Holmes: Towards Explainable and Generalizable AI-Generated Image Detection via Multimodal Large Language Models**](https://arxiv.org/abs/2507.02664) | Zhou et al. | ICCV 2025 | [Code](https://github.com/wyczzy/AIGI-Holmes) | `LMM`
+ [**ThinkFake: Reasoning in Multimodal Large Language Models for AI-Generated Image Detection**](https://arxiv.org/abs/2509.19841) | Huang et al. 2025 | `LMM`
+ [**FakeReasoning: Towards Generalizable Forgery Detection and Reasoning**](https://arxiv.org/abs/2503.21210) | Gao et al. 2025 | [Code](https://github.com/PRIS-CV/FakeReasoning) | `LMM`
+ [**Spot the Fake: Large Multimodal Model-Based Synthetic Image Detection with Artifact Explanation**](https://arxiv.org/abs/2503.14905) | Wen et al. | NeurIPS 2025 | [Code](https://github.com/opendatalab/FakeVLM) | `LMM`
+ [**Veritas: Generalizable Deepfake Detection via Pattern-Aware Reasoning**](https://openreview.net/forum?id=5VXJPS1HoM) | Tan et al. | ICLR 2026 Oral | [Code](https://github.com/Rosstein/HydraFake-tanh) | `LMM`
+ [**SIDA: Social Media Image Deepfake Detection, Localization and Explanation with LMM**](https://arxiv.org/abs/2412.04292) | Huang et al. | CVPR 2025 | [Code](https://github.com/hzlsaber/SIDA) | `LMM`
+ [**FakeShield: Explainable Image Forgery Detection and Localization via Multi-modal Large Language Models**](https://arxiv.org/abs/2410.02761) | Xu et al. | ICLR 2025 | [Code](https://github.com/zhipeixu/FakeShield) | `LMM`
+ [**FAKEXPLAIN: AI-Generated Images Detection via Human-Aligned Grounded Reasoning**](https://openreview.net/forum?id=UcpTOa8OnG) | Ji et al. | ICLR 2026 | `LMM`
+ [**Semantic Visual Anomaly Detection and Reasoning in AI-Generated Images**](https://openreview.net/forum?id=0iN4UKZwgn) | Tan et al. | ICLR 2026 | `LMM`
+ [**Explainable Synthetic Image Detection through Diffusion Timestep Ensembling**](https://arxiv.org/abs/2503.06201) | Wu et al. | AAAI 2026 | [Code](https://github.com/Shadowlized/ESIDE) | `LMM`
+ [**Unlocking the Capabilities of Large Vision-Language Models for Generalizable and Explainable Deepfake Detection**](https://arxiv.org/abs/2503.14853) | ICML 2025 | `LMM`
+ [**Locate-Then-Examine: Grounded Region Reasoning Improves Detection of AI-Generated Images**](https://openaccess.thecvf.com/content/CVPR2026/html/Ji_Locate-Then-Examine_Grounded_Region_Reasoning_Improves_Detection_of_AI-Generated_Images_CVPR_2026_paper.html) | Ji et al. | CVPR 2026 | `LMM`
+ [**UniGenDet: A Unified Generative-Discriminative Framework for Co-Evolutionary Image Generation and Generated Image Detection**](https://openaccess.thecvf.com/content/CVPR2026/html/Zhang_UniGenDet_A_Unified_Generative-Discriminative_Framework_for_Co-Evolutionary_Image_Generation_and_CVPR_2026_paper.html) | Zhang et al. | CVPR 2026 | [Code](https://github.com/Zhangyr2022/UniGenDet) | `LMM`
+ [**ForenDeX: Unlocking Forensic Insights for Explainable AI-Generated Image Detection**](https://openaccess.thecvf.com/content/CVPR2026F/html/Tan_ForenDeX_Unlocking_Forensic_Insights_for_Explainable_AI-Generated_Image_Detection_CVPRF_2026_paper.html) | Tan et al. | CVPR 2026 Findings | `LMM`
+ [**REVEAL: Reasoning-Enhanced Forensic Evidence Analysis for Explainable AI-Generated Image Detection**](https://eccv.ecva.net/virtual/2026/poster/5044) | - | ECCV 2026 | `LMM`
+ [**UC-VLM: Consistency-Driven Learning for AI-Generated Image Detection with Vision-Language Large Models**](https://eccv.ecva.net/virtual/2026/poster/5204) | - | ECCV 2026 | `LMM`
+ [**TranX-Adapter: Bridging Artifacts and Semantics within MLLMs for Robust AI-generated Image Detection**](https://openreview.net/forum?id=Iy6isx8QOp) | - | ICML 2026 | `LMM`
+ [**Deep Residual Injection for Full-Spectrum Forensic Signal Perception in Multimodal Large Language Models**](https://openreview.net/forum?id=S2ilvpV9du) | - | ICML 2026 | [Code](https://github.com/KQL11/Deep-VRM) | `LMM`
+ [**GenShield: Unified Detection and Artifact Correction for AI-Generated Images**](https://openreview.net/forum?id=Fhtwta4397) | - | ICML 2026 | [Code](https://github.com/zhipeixu/GenShield) | `LMM`
+ [**Unified Forensic Preference Learning for Generalizable Synthetic Image Detection**](https://openreview.net/forum?id=fGUaeL5g1k) | - | NeurIPS 2026 | `LMM`
+ [**ReAlign: Generalizable Image Forgery Detection via Reasoning-Aligned Representation**](https://openaccess.thecvf.com/content/CVPR2026/html/Huang_ReAlign_Generalizable_Image_Forgery_Detection_via_Reasoning-Aligned_Representation_CVPR_2026_paper.html) | Huang et al. | CVPR 2026 | `LMM` `Distillation`
+ [**Rethinking VLMs for Image Forgery Detection and Localization**](https://openaccess.thecvf.com/content/CVPR2026F/html/Guo_Rethinking_VLMs_for_Image_Forgery_Detection_and_Localization_CVPRF_2026_paper.html) | Guo et al. | CVPR 2026 Findings | [Code](https://github.com/sha0fengGuo/IFDL-VLM) | `LMM` `Localization`
+ [**UniShield: An Adaptive Multi-Agent Framework for Unified Forgery Image Detection and Localization**](https://openaccess.thecvf.com/content/CVPR2026F/html/Huang_UniShield_An_Adaptive_Multi-Agent_Framework_for_Unified_Forgery_Image_Detection_CVPRF_2026_paper.html) | Huang et al. | CVPR 2026 Findings | `LMM` `Agent`
+ [**Code-in-the-Loop Forensics: Agentic Tool Use for Image Forgery Detection**](https://eccv.ecva.net/virtual/2026/poster/5823) | Zhang et al. | ECCV 2026 | [Code](https://github.com/zfr00/ForenAgent) | `LMM` `Agent`
+ [**Trustworthy Image Authentication using Forensic Knowledge Graphs**](https://eccv.ecva.net/virtual/2026/poster/3521) | Nguyen et al. | ECCV 2026 | `LMM` `Explainable`
+ [**Asymmetric Anchoring: Opening the Black Box of MLLMs for Forgery Detection**](https://eccv.ecva.net/virtual/2026/poster/5294) | - | ECCV 2026 | [Code](https://github.com/rstao-bjtu/AAP) | `LMM` `Real Anchor`

---

### 8. Training-free & Zero-shot Methods

> Require no training on fake data—exploit intrinsic properties of pre-trained models (reconstruction error, feature distributions, perturbation response) to detect without any task-specific optimization, naturally generalizing to unseen generators.

+ [**RIGID: A Training-free and Model-Agnostic Framework for Robust AI-Generated Image Detection**](https://arxiv.org/abs/2405.20112) | He et al. 2024 | `Training-free`
+ [**Intermediate Representations Are Strong Training-Free AI-Generated Image Detectors**](https://openreview.net/forum?id=NfM92qRuew) | `Training-free`
+ [**Training-Free AI-Generated Image Detection via Spectral Artifacts**](https://openreview.net/forum?id=G9Oj0dMQIJ) | `Training-free`
+ [**Forensic Self-Descriptions Are All You Need for Zero-Shot Detection, Open-Set Source Attribution, and Localization**](https://arxiv.org/abs/2503.21003) | Nguyen et al. | CVPR 2025 | `Zero-shot`
+ [**Zero-Shot Detection of AI-Generated Images**](https://arxiv.org/abs/2409.15875) | Cozzolino et al. | ECCV 2024 | [Code](https://github.com/grip-unina/ZED) | `Zero-shot`
+ [**Detecting Generated Images by Fitting Natural Image Distributions**](https://arxiv.org/abs/2411.01674) | Zhang et al. | NeurIPS 2025 Spotlight | [Code](https://github.com/tmlr-group/ConV) | `Training-free`
+ [**General and Domain-Specific Zero-shot Detection of Generated Images via Conditional Likelihood**](https://arxiv.org/abs/2512.05590) | Betser et al. 2025 | `Zero-shot`
+ [**Training-free Detection of AI-generated images via Cropping Robustness**](https://arxiv.org/abs/2511.14030) | Choi et al. | NeurIPS 2025 | [Code](https://github.com/sungikchoi/WaRPAD) | `Training-free`
+ [**Denoising Trajectory Biases for Zero-Shot AI-Generated Image Detection**](https://openreview.net/forum?id=2h8vXbEufN) | Liang et al. | NeurIPS 2025 | `Training-free`
+ [**Revisiting Reconstruction-based AI-generated Image Detection: A Geometric Perspective**](https://arxiv.org/abs/2510.25141) | Jiang et al. 2025 | `Training-free`

+ [**HFI: A Unified Framework for Training-free Detection and Implicit Watermarking of Latent Diffusion Models**](https://arxiv.org/abs/2412.20704) | Choi et al. 2024 | `Training-free`
+ [**Understanding and Improving Training-Free AI-Generated Image Detections with Vision Foundation Models**](https://arxiv.org/abs/2411.19117) | Tsai et al. 2024 | `Training-free`
+ [**A Debiased Reconstruction-based Framework for Training-Free Detection of AI-Generated Images**](https://openaccess.thecvf.com/content/CVPR2026/html/Choi_A_Debiased_Reconstruction-based_Framework_for_Training-Free_Detection_of_AI-Generated_Images_CVPR_2026_paper.html) | Choi et al. | CVPR 2026 | `Training-free`
+ [**EIRES: Training-free AI-Generated Image Detection via Edit-Induced Reconstruction Error Shift**](https://openaccess.thecvf.com/content/CVPR2026F/html/Jiang_EIRESTraining-free_AI-Generated_Image_Detection_via_Edit-Induced_Reconstruction_Error_Shift_CVPRF_2026_paper.html) | Jiang et al. | CVPR 2026 Findings | `Training-free`
+ [**GLARE: Towards Generalizable Detection of Latent Diffusion Images with Global-Local Reconstruction Error**](https://media.eventhosts.cc/Conferences/ECCV2026/pdfs/6737.pdf) | Yan et al. | ECCV 2026 | `Training-free`

---

### 9. Diffusion-specific Detection

> Core mechanism exploits DDIM inversion, VAE reconstruction, or denoising trajectories specific to diffusion models—would not transfer to GANs or AR generators.

+ [**DIRE for Diffusion-Generated Image Detection**](https://arxiv.org/abs/2303.09295) | Wang et al. | ICCV 2023 | [Code](https://github.com/ZhendongWang6/DIRE) | `Diffusion`
+ [**AEROBLADE: Training-Free Detection of Latent Diffusion Images Using Autoencoder Reconstruction Error**](https://arxiv.org/abs/2401.17879) | Ricker et al. | CVPR 2024 | [Code](https://github.com/jonasricker/aeroblade) | `Diffusion` `Training-free`
+ [**LaRE²: Latent Reconstruction Error Based Method for Diffusion-Generated Image Detection**](https://arxiv.org/abs/2403.17465) | Luo et al. | CVPR 2024 | [Code](https://github.com/luo3300612/LaRE) | `Diffusion`
+ [**FakeInversion: Learning to Detect Images from Unseen Text-to-Image Models by Inverting Stable Diffusion**](https://arxiv.org/abs/2406.08603) | Cazenavette et al. | CVPR 2024 | [Page](https://fake-inversion.github.io/) | `Diffusion`
+ [**DRCT: Diffusion Reconstruction Contrastive Training towards Universal Detection**](https://openreview.net/pdf?id=oRLwyayrh1) | Chen et al. | ICML 2024 | [Code](https://github.com/beibuwandeluori/DRCT) | `Diffusion`
+ [**On the Detection of Synthetic Images Generated by Diffusion Models**](https://arxiv.org/abs/2211.00680) | Corvi et al. | ECCV 2022 | [Code](https://github.com/grip-unina/DMimageDetection) | `Diffusion`
+ [**FIRE: Robust Detection of Diffusion-Generated Images via Frequency-Guided Reconstruction Error**](https://arxiv.org/abs/2412.07140) | Chu et al. | CVPR 2025 | [Code](https://github.com/Chuchad/FIRE) | `Diffusion`
+ [**Diffusion Epistemic Uncertainty with Asymmetric Learning for Diffusion-Generated Image Detection**](https://arxiv.org/abs/2601.14625) | Huang et al. | ICCV 2025 | `Diffusion`
+ [**Exposing the Fake: Effective Diffusion-Generated Images Detection**](https://arxiv.org/abs/2307.06272) | Ma et al. | AdvML-Frontiers@ICML 2023 Workshop | `Diffusion`
+ [**A Difference-in-Difference Approach to Detecting AI-Generated Images**](https://openaccess.thecvf.com/content/CVPR2026/html/Qi_A_Difference-in-Difference_Approach_to_Detecting_AI-Generated_Images_CVPR_2026_paper.html) | Qi et al. | CVPR 2026 | [Code](https://github.com/Qixinyi1122lucky/DID) | `Diffusion`

---

### 10. Autoregressive Model Detection

> Target the unique artifacts of token-by-token autoregressive generation—discrete quantization errors and conditional token probability patterns.

+ [**PRADA: Probability-Ratio-Based Attribution and Detection of Autoregressive-Generated Images**](https://arxiv.org/abs/2511.20068) | Damm et al. | CVPR 2026 Findings | [Code](https://github.com/jonasricker/prada) | `Autoregressive`
+ [**D³QE: Learning Discrete Distribution Discrepancy-aware Quantization Error for Autoregressive-Generated Image Detection**](https://arxiv.org/abs/2510.05891) | Zhang et al. 2025 | [Code](https://github.com/Zhangyr2022/D3QE) | `Autoregressive`
+ [**Data Provenance for Image Auto-Regressive Generation**](https://openreview.net/forum?id=qYu4wj7O3z) | Zhao et al. | ICLR 2026 | `AR / Attribution`

---

### 11. Deepfake Detection

> Face deepfake methods that also generalize to general AI-generated image detection benchmarks.

+ [**D³: Scaling Up Deepfake Detection by Learning from Discrepancy**](https://arxiv.org/abs/2404.04584) | Yang et al. | CVPR 2025 | [Code](https://github.com/BigAandSmallq/D3) | `Deepfake + General`
+ [**Veritas: Generalizable Deepfake Detection via Pattern-Aware Reasoning**](https://openreview.net/forum?id=5VXJPS1HoM) | Tan et al. | ICLR 2026 Oral | [Code](https://github.com/Rosstein/HydraFake-tanh) | `LMM + Deepfake`
+ [**Real-Time Deepfake Detection in the Real-World**](https://arxiv.org/abs/2406.09398) | Cavia et al. 2024 | `Deepfake`

---

### 12. Generalization: Training Strategy & Data Engineering

> Address the generalization gap through training data engineering—bias elimination, semantic alignment, multi-generator scaling, and calibration.

#### 12.1 Data Alignment & Construction

> Eliminate spurious dataset biases (JPEG quality, resolution, content mismatch) by constructing semantically aligned real–fake training pairs.

+ [**Dual Data Alignment Makes AI-Generated Image Detector Easier Generalizable**](https://arxiv.org/abs/2505.14359) | Chen et al. | NeurIPS 2025 Spotlight | [Code](https://github.com/roy-ch/Dual-Data-Alignment) | `Data Alignment`
+ [**Aligned Datasets Improve Detection of Latent Diffusion-Generated Images**](https://arxiv.org/abs/2410.11835) | Rajan et al. | ICLR 2025 | [Code](https://github.com/AniSundar18/AlignedForensics) | `Data Alignment`
+ [**A Bias-Free Training Paradigm for More General AI-generated Image Detection**](https://arxiv.org/abs/2412.17671) | Guillaro et al. | CVPR 2025 | [Code](https://github.com/grip-unina/B-Free) | `Bias-Free`
+ [**Breaking Latent Prior Bias in Detectors for Generalizable AIGC Image Detection**](https://arxiv.org/abs/2506.00874) | Zhou et al. | NeurIPS 2025 | `Bias-Free`
+ [**Fake or JPEG? Revealing Common Biases in Generated Image Detection Datasets**](https://arxiv.org/abs/2403.17608) | Grommelt et al. 2024 | [Page](https://www.unbiased-genimage.org/) | `Data Alignment`
+ [**Task-Model Alignment: A Simple Path to Generalizable AI-Generated Image Detection**](https://arxiv.org/abs/2512.06746) | Chen et al. 2025 | [Code](https://github.com/GzZning/Align-Dont-Blend) | `Data Alignment`
+ [**Enabling Supervised Learning of Generative Signatures for Generalized AI-Generated Images Detection**](https://openaccess.thecvf.com/content/CVPR2026/html/Fei_Enabling_Supervised_Learning_of_Generative_Signatures_for_Generalized_AI-Generated_Images_CVPR_2026_paper.html) | Fei et al. | CVPR 2026 | [Code](https://github.com/jumpycat/GenSign) | `Data Construction`
+ [**Where Detectors Fail: Probing Generative Space for Generalizable AI-Generated Image Detection**](https://openreview.net/forum?id=gAXiBfnvbD) | - | ICML 2026 | [Code](https://github.com/Amamiya-C/PROBE-AIGI-Detection) | `Data Construction`
+ [**FAIR: Feature-Augmented Implicit Regularization for AI-generated Fake Image Detection**](https://eccv.ecva.net/virtual/2026/poster/5812) | - | ECCV 2026 | `Regularization`
+ [**The road reaches every place, the short cut only one: Self-Adversarial Shortcut Mitigation for AI-Generated Image Detection**](https://openreview.net/forum?id=bO6CYKnaZo) | - | NeurIPS 2026 | `Shortcut Mitigation`
+ [**Stability-Weighted Direction Regularization Disentangles Generator Shortcuts from Detection Signal**](https://openreview.net/forum?id=2VpqRkpXM9) | - | NeurIPS 2026 | `Shortcut Mitigation`

<a id="122-real-centric--calibration"></a>
#### 12.2 Real-Centric & Calibration → moved

> Moved to [14. Real-Centric, Calibration & Test-Time Adaptation](#14-real-centric-calibration--test-time-adaptation).

#### 12.3 Multi-Generator

> Scale training to thousands of generative models, empirically showing monotonic generalization improvement with generator diversity.

+ [**Community Forensics: Using Thousands of Generators to Train Fake Image Detectors**](https://arxiv.org/abs/2411.04125) | Park et al. | CVPR 2025 | [Code](https://github.com/JeongsooP/Community-Forensics) | `Multi-Generator`
+ [**Scaling Up AI-Generated Image Detection via Generator-Aware Prototypes**](https://arxiv.org/abs/2512.12982) | Qin et al. | CVPR 2026 | [Code](https://github.com/UltraCapture/GAPL) | `Multi-Generator`
+ [**Forensic-MoE: Exploring Comprehensive Synthetic Image Detection Traces with Mixture of Experts**](https://iccv.thecvf.com/virtual/2025/poster/919) | Fang et al. | ICCV 2025 | [Code](https://github.com/fangmq77/Forensic-MoE) | `Multi-Generator`
+ [**HSIC Bottleneck for Cross-Generator and Domain-Incremental Synthetic Image Detection**](https://openreview.net/forum?id=msLnKDvhBx) | Yang et al. | ICLR 2026 | `Multi-Generator`
+ [**SAIDO: Generalizable Detection of AI-Generated Images via Scene-Aware and Importance-Guided Dynamic Optimization in Continual Learning**](https://openaccess.thecvf.com/content/CVPR2026/html/Hu_SAIDO_Generalizable_Detection_of_AI-Generated_Images_via_Scene-Aware_and_Importance-Guided_CVPR_2026_paper.html) | Hu et al. | CVPR 2026 | `Multi-Generator`
+ [**Improving Synthesized Image Detection by Disentangling Generator-Shared and Generator-Specific Image Artifacts**](https://openaccess.thecvf.com/content/CVPR2026F/html/Yang_Improving_Synthesized_Image_Detection_by_Disentangling_Generator-Shared_and_Generator-Specific_Image_CVPRF_2026_paper.html) | Yang et al. | CVPR 2026 Findings | `Multi-Generator`
+ [**Fleet: Few Shots Lead Effective AI-generated Image Detection**](https://openreview.net/forum?id=3QstqZrwjO) | - | ICML 2026 | [Code](https://github.com/ICTMCG/Fleet) | `Few-shot`

---

### 13. Image Attribution / Source Tracing

> Go beyond binary detection to identify *which* generative model produced an image, exploiting model-specific reconstruction fingerprints and latent signatures.

+ [**How to Trace Latent Generative Model Generated Images without Artificial Watermark?**](https://arxiv.org/abs/2405.13360) | Wang et al. | ICML 2024 | [Code](https://github.com/ZhentingWang/LatentTracer) | `Attribution`
+ [**AEDR: Training-Free AI-Generated Image Attribution via Autoencoder Double-Reconstruction**](https://arxiv.org/abs/2501.09245) | Wang et al. | AAAI 2026 Oral | `Attribution`
+ [**Which Model Generated This Image? A Model-Agnostic Approach for Origin Attribution**](https://arxiv.org/abs/2404.02697) | Liu et al. 2024 | [Code](https://github.com/uwFengyuan/OCC-CLIP) | `Attribution`
+ [**PRADA: Probability-Ratio-Based Attribution and Detection of Autoregressive-Generated Images**](https://arxiv.org/abs/2511.20068) | Damm et al. | CVPR 2026 Findings | [Code](https://github.com/jonasricker/prada) | `Attribution`
+ [**Data Provenance for Image Auto-Regressive Generation**](https://openreview.net/forum?id=qYu4wj7O3z) | Zhao et al. | ICLR 2026 | `Attribution`
+ [**Attribution as Retrieval: Model-Agnostic AI-Generated Image Attribution**](https://openaccess.thecvf.com/content/CVPR2026/html/Wang_Attribution_as_Retrieval_Model-Agnostic_AI-Generated_Image_Attribution_CVPR_2026_paper.html) | Wang et al. | CVPR 2026 | [Code](https://github.com/hongsong-wang/LIDA) | `Attribution`
+ [**IncreFA: Breaking the Static Wall of Generative Model Attribution**](https://openaccess.thecvf.com/content/CVPR2026/html/Qin_IncreFA_Breaking_the_Static_Wall_of_Generative_Model_Attribution_CVPR_2026_paper.html) | Qin et al. | CVPR 2026 | [Code](https://github.com/Ant0ny44/IncreFA) | `Attribution`
+ [**Few-Shot Synthetic Image Attribution: Identifying Unseen Generators with Limited Samples**](https://eccv.ecva.net/virtual/2026/poster/5926) | - | ECCV 2026 | [Code](https://github.com/teheperinko541/OmniDFA) | `Attribution`
+ [**Tracing the Roots: Leveraging Temporal Dynamics in Diffusion Trajectories for Origin Attribution**](https://neurips.cc/virtual/2025/poster/116226) | - | NeurIPS 2025 | `Attribution`
+ [**FARE: Forensic Acceptance Region Estimation for Catching Bait-and-Switch Image Generators**](https://openreview.net/forum?id=biz1Z9lOtc) | - | NeurIPS 2026 | [Code](https://github.com/kaikaiyao/FARE) | `Attribution`
+ [**Data Circuit Breaker: Identifying Training, Test, and Generated Data in Image Generative Models**](https://eccv.ecva.net/virtual/2026/poster/3593) | - | ECCV 2026 | `Attribution` `Membership`

---

### 14. Real-Centric, Calibration & Test-Time Adaptation

> Model the real-image distribution (or only trust real-side evidence) and treat anything that deviates as synthetic, instead of chasing fake-specific artifacts. This category also collects **calibration / selective prediction** and **test-time adaptation (TTA)** methods, which likewise act on the decision boundary around real data rather than on fake-data engineering. (Formerly 12.2.)

+ [**MIRROR: Manifold Ideal Reference ReconstructOR for Generalizable AI-Generated Image Detection**](https://arxiv.org/abs/2602.02222) | Liu et al. | NeurIPS 2026 | [Code](https://github.com/349793927/MIRROR) | `Real-Centric`
+ [**Your AI-Generated Image Detector Can Secretly Achieve SOTA Accuracy, If Calibrated**](https://arxiv.org/abs/2602.01973) | Yang et al. | AAAI 2026 | [Code](https://github.com/muliyangm/AIGI-Det-Calib) | `Calibration`
+ [**Stay-Positive: A Case for Ignoring Real Image Features in Fake Image Detection**](https://arxiv.org/abs/2502.07778) | ICML 2025 | [Code](https://github.com/AniSundar18/AlignedForensics) | `Real-Centric`
+ [**Towards Generalizable AI-Generated Image Detection via Image-Adaptive Prompt Learning**](https://arxiv.org/abs/2508.01603) | Li et al. | CVPR 2026 | [Code](https://github.com/liyih/IAPL) | `Test-Time Adaptation`
+ [**Beyond Artifacts: Real-Centric Envelope Modeling for Reliable AI-Generated Image Detection**](https://arxiv.org/abs/2512.20937) | - | ECCV 2026 | `Real-Centric`
+ [**Breaking Manifold Continuity: Vector Quantized Modeling for Real-Centric Deepfake Detection**](https://openreview.net/forum?id=WrlqkXYYCx) | - | ICML 2026 | `Real-Centric` `Deepfake` (main eval on face datasets FF++/CDF/DFDC etc.; GenImage only in appendix)
+ [**Leveraging Arbitrary Data Sources for AI-Generated Image Detection Without Sacrificing Generalization**](https://openaccess.thecvf.com/content/CVPR2026F/html/He_Leveraging_Arbitrary_Data_Sources_for_AI-Generated_Image_Detection_Without_Sacrificing_CVPRF_2026_paper.html) | He et al. | CVPR 2026 Findings | `One-class`
+ [**Exploiting the Source-Asymmetry Confidence Gap for Generalizable AI-Generated Image Detection**](https://openaccess.thecvf.com/content/CVPR2026F/html/Zheng_Exploiting_the_Source-Asymmetry_Confidence_Gap_for_Generalizable_AI-Generated_Image_Detection_CVPRF_2026_paper.html) | Zheng et al. | CVPR 2026 Findings | `Calibration`
+ [**PGC: Peak-Guided Calibration for Generalizable AI-Generated Image Detection**](https://openreview.net/forum?id=yEjix8H6Dw) | - | ICML 2026 | [Code](https://github.com/xiaoyu6868/PGC) | `Calibration`
+ [**Post-hoc Selective Classification for Reliable Synthetic Image Detection**](https://openreview.net/forum?id=WYncw2up3x) | - | NeurIPS 2026 | `Calibration`
+ [**DEDCA: Test-Time Adaptation for Generalized AI-Generated Image Detection**](https://openreview.net/forum?id=WP9ROPHHjk) | - | NeurIPS 2026 | `Test-Time Adaptation`
+ [**Zero-shot Detection of AI-Generated Image via RAW-RGB Alignment**](https://openaccess.thecvf.com/content/CVPR2026/html/Wu_Zero-shot_Detection_of_AI-Generated_Image_via_RAW-RGB_Alignment_CVPR_2026_paper.html) | Wu et al. | CVPR 2026 | `Real-Centric` `Zero-shot`
+ [**SimLBR: Learning to Detect Fake Images by Learning to Detect Real Images**](https://arxiv.org/abs/2602.20412) | Dhakal et al. | CVPR 2026 | `Real-Centric`

---

### 15. Attacks & Robustness Evaluation

> Adversarial / black-box attacks on AIGI detectors and systematic evaluations of detector robustness (post-processing, transformation bias, evasion). Robust *detection methods* stay in their method category (e.g., Phase Spectrum Robustness in 3, In2CLR in 6).

+ [**PolyJuice Makes It Real: Black-Box, Universal Red Teaming for Synthetic Image Detectors**](https://neurips.cc/virtual/2025/poster/115746) | - | NeurIPS 2025 | `Attack`
+ [**BIAS-ID: A Framework for Analyzing Transformation Biases in AI-Generated Image Detectors**](https://openreview.net/forum?id=GIewosR83I) | - | NeurIPS 2026 | `Robustness Evaluation`
+ [**When Understanding Becomes a Risk: Authenticity and Safety Risks in the Emerging Image Generation Paradigm**](https://openaccess.thecvf.com/content/CVPR2026/html/Leng_When_Understanding_Becomes_a_Risk_Authenticity_and_Safety_Risks_in_CVPR_2026_paper.html) | Leng et al. | CVPR 2026 | `Evasion` `Analysis`
+ [**Is Artificial Intelligence Generated Image Detection a Solved Problem?**](https://arxiv.org/abs/2505.12335) | - | NeurIPS 2025 | [Code](https://github.com/HorizonTEL/AIGIBench) | `Robustness Evaluation` `Benchmark`

---

## Citation

If you find this repository useful, please consider citing:

```bibtex
@misc{awesome-aigc-image-detection,
  title={Awesome AI-Generated Image Detection},
  author={yjtlab},
  year={2026},
  publisher={GitHub},
  howpublished={\url{https://github.com/yjtlab/awesome-aigc-image-detection}}
}
```

---

**Last Updated**: 2026-10-23 | **Total Papers**: 170+

Contributions and suggestions are welcome! Please open an issue or pull request.
