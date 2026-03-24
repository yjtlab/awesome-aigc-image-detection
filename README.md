# Awesome AI-Generated Image Detection [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A curated and comprehensive list of papers, datasets, and resources for **AI-Generated Image Detection (AIGC Detection)**. This collection covers methods for detecting images synthesized by GANs, diffusion models, autoregressive models, and other generative approaches.

> Continuously updated.

**Last verified**: 2026-03-16 | **Total papers**: 170+ | **Inclusion criteria**: Peer-reviewed papers (CVPR, ICCV, ECCV, NeurIPS, ICML, ICLR, AAAI) and high-impact arXiv preprints on AI-generated **image** detection. Preference for methods providing open-source code.

---

## Table of Contents

- [Survey](#survey)
- [Paper Tree](#paper-tree)
- [SOTA Methods](#sota-methods)
- [Recommended Benchmarks](#recommended-benchmarks)
- [Papers by Venue](#papers-by-venue)
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
  - [1. CLIP / Vision-Language Methods](#1-clip--vision-language-methods)
  - [2. Reconstruction-based Methods](#2-reconstruction-based-methods)
  - [3. Frequency-domain Methods](#3-frequency-domain-methods)
  - [4. Patch / Texture-based Methods](#4-patch--texture-based-methods)
  - [5. Noise / Fingerprint-based Methods](#5-noise--fingerprint-based-methods)
  - [6. Perturbation / Robustness-based Methods](#6-perturbation--robustness-based-methods)
  - [7. LMM / Reasoning-based Methods](#7-lmm--reasoning-based-methods)
  - [8. Zero-shot & Training-free Methods](#8-zero-shot--training-free-methods)
  - [9. Diffusion-specific Detection](#9-diffusion-specific-detection)
  - [10. Autoregressive Model Detection](#10-autoregressive-model-detection)
  - [11. Deepfake / Face Forgery Detection](#11-deepfake--face-forgery-detection)
  - [12. Generalization: Training Strategy & Data Engineering](#12-generalization-training-strategy--data-engineering)
  - [13. Image Attribution / Source Tracing](#13-image-attribution--source-tracing)
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
├── 1. Feature-based Detection
│   ├── 1.1 CLIP / Vision-Language
│   │   ├── CLIP Fine-tuning (CLIPping, Raising the Bar, DeeCLIP)
│   │   ├── Prompt Learning (AntifakePrompt, PLOT, Image-Adaptive)
│   │   ├── Feature Decoupling (NS-Net, CausalCLIP, DGS-Net, MiraGe)
│   │   └── Information Bottleneck (VIB, MCIB)
│   ├── 1.2 Frequency-domain
│   │   ├── Spectral Analysis (Fractal Self-Similarity, Spectral Artifacts)
│   │   ├── Frequency Reconstruction (FIRE)
│   │   └── DCT / Wavelet (LOTA Bit-Planes)
│   ├── 1.3 Patch / Texture
│   │   ├── Patch Learning (SSP, PatchCraft, Panoptic Patch)
│   │   ├── Texture Analysis (TextureCrop, Rich/Poor Texture)
│   │   └── Pixel-level (FerretNet, PiD)
│   └── 1.4 Noise / Fingerprint
│       ├── Noise Imprint (Implicit Noise Imprint)
│       ├── Camera Fingerprint (Wavelet Domain Fingerprint)
│       └── Color Distribution (Secret Lies in Color, Demosaicing)
│
├── 2. Reconstruction-based Detection
│   ├── 2.1 Diffusion Reconstruction (DIRE, FIRE, LATTE)
│   ├── 2.2 Autoencoder Reconstruction (AEROBLADE, GRRE, CINEMAE)
│   ├── 2.3 Latent Space (LaRE², FakeInversion)
│   └── 2.4 Semantic-Aware (SARE)
│
├── 3. Perturbation / Robustness-based
│   ├── RIGID, RA-Det
│   ├── Epistemic Uncertainty
│   └── Noise Benefits (How Noise Benefits)
│
├── 4. LMM / Reasoning-based (Explainable)
│   ├── Grounding & Explanation (LEGION, AIGI-Holmes, FakeReasoning)
│   ├── Multi-modal Detection (ThinkFake, Spot the Fake, SIDA)
│   └── VLM-based (Veritas, FakeShield, FAKEXPLAIN)
│
├── 5. Zero-shot & Training-free
│   ├── Training-free (RIGID, Intermediate Representations, Spectral Artifacts)
│   ├── Zero-shot (Forensic Self-Descriptions)
│   └── Contrastive Inversion
│
├── 6. Generalization: Training Strategy & Data Engineering
│   ├── Data Alignment (Dual Data Alignment, Aligned Datasets)
│   ├── Regularization (SimLBR)
│   ├── Bias-Free Training (B-Free Paradigm)
│   ├── Real-Centric (MIRROR, Real-Centric Envelope)
│   └── Calibration (Calibrated Detector, D³)
│
├── 7. Special Targets
│   ├── 7.1 Deepfake / Face Forgery
│   ├── 7.2 Autoregressive Model (PRADA, D³QE)
│   └── 7.3 Diffusion-specific (DNF, Corvi 2022)
│
├── 8. Image Attribution / Source Tracing
│   ├── Model Attribution (LatentTracer, AEDR)
│   └── Fingerprint-based Attribution
│
└── 9. Recommended Benchmarks
    ├── Datasets (ForenSynths, GenImage, DRCT-2M, Community Forensics, ...)
    └── Evaluation Frameworks (ForensicHub, AIDE)
```

---

## SOTA Methods

Representative methods with open-source code:

|  Title  |   Venue  |   Year   |   Code   |   Category   |
|:--------|:--------:|:--------:|:--------:|:--------:|
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
| **ForenSynths** | 11 CNN-based generators (ProGAN, StyleGAN, etc.) for binary detection | 2020 | ![Star](https://img.shields.io/github/stars/peterwang512/CNNDetection.svg?style=social&label=Star) <br> [GitHub](https://github.com/peterwang512/CNNDetection) |
| **UniversalFakeDetect** | 26 generators spanning GANs and diffusion models | 2023 | ![Star](https://img.shields.io/github/stars/Yuheng-Li/UniversalFakeDetect.svg?style=social&label=Star) <br> [GitHub](https://github.com/Yuheng-Li/UniversalFakeDetect) |
| **GenImage** | Million-scale benchmark covering 8 generators | 2023 | ![Star](https://img.shields.io/github/stars/GenImage-Dataset/GenImage.svg?style=social&label=Star) <br> [GitHub](https://github.com/GenImage-Dataset/GenImage) |
| **Synthbuster** | Diffusion-generated images for detection benchmarking | 2023 | [Paper](https://arxiv.org/abs/2312.02023) |
| **DRCT-2M** | 2M images from 16 diffusion models for universal detection | 2024 | [ModelScope](https://modelscope.cn/datasets/BokingChen/DRCT-2M) |
| **Aligned Forensics** | Semantically-aligned real/fake pairs for unbiased evaluation | 2025 | ![Star](https://img.shields.io/github/stars/AniSundar18/AlignedForensics.svg?style=social&label=Star) <br> [GitHub](https://github.com/AniSundar18/AlignedForensics) |
| **Chameleon** | Human-hard scenarios for sanity-check evaluation | 2025 | ![Star](https://img.shields.io/github/stars/shilinyan99/AIDE.svg?style=social&label=Star) <br> [GitHub](https://github.com/shilinyan99/AIDE) |
| **CO-SPYBench** | 22 generators + 50k wild images | 2025 | ![Star](https://img.shields.io/github/stars/Megum1/Co-Spy.svg?style=social&label=Star) <br> [GitHub](https://github.com/Megum1/Co-Spy) |
| **Community Forensics** | 4803 generators for large-scale generalization | 2025 | ![Star](https://img.shields.io/github/stars/JeongsooP/Community-Forensics.svg?style=social&label=Star) <br> [GitHub](https://github.com/JeongsooP/Community-Forensics) |
| **ForensicHub** | Unified benchmark & codebase for AIGC detection | 2025 | ![Star](https://img.shields.io/github/stars/scu-zjz/ForensicHub.svg?style=social&label=Star) <br> [GitHub](https://github.com/scu-zjz/ForensicHub) |

---

## Papers by Venue

### CVPR 2026

+ [**SimLBR: Learning to Detect Fake Images by Learning to Detect Real Images**](https://arxiv.org/abs/2602.20412) | Dhakal et al. | `Training Strategy`
+ [**Scaling Up AI-Generated Image Detection via Generator-Aware Prototypes**](https://arxiv.org/abs/2512.12982) | Qin et al. | [Code](https://github.com/UltraCapture/GAPL) | `Multi-Generator`
+ [**Towards Generalizable AI-Generated Image Detection via Image-Adaptive Prompt Learning**](https://arxiv.org/abs/2508.01603) | Li et al. | [Code](https://github.com/liyih/IAPL) | `Prompt Learning`
+ [**Layer Consistency Matters: Elegant Latent Transition Discrepancy for Generalizable Synthetic Image Detection**](https://arxiv.org/abs/2603.10598) | `Latent`

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
+ [**Your AI-Generated Image Detector Can Secretly Achieve SOTA Accuracy, If Calibrated**](https://arxiv.org/abs/2602.01973) | Yang et al. | `Calibration`
+ [**Beyond Semantic Features: Pixel-level Mapping for Generalized AI-Generated Image Detection**](https://arxiv.org/abs/2512.17350) | Zhou et al. | `Pixel-level`

### ICCV 2025

+ [**LEGION: Learning to Ground and Explain for Synthetic Image Detection**](https://arxiv.org/abs/2503.15264) | Kang et al. | [Code](https://github.com/opendatalab/LEGION) | `LMM`
+ [**AIGI-Holmes: Towards Explainable and Generalizable AI-Generated Image Detection via Multimodal Large Language Models**](https://arxiv.org/abs/2507.02664) | Zhou et al. | [Code](https://github.com/wyczzy/AIGI-Holmes) | `LMM`
+ [**ForgeLens: Data-Efficient Forgery Focus for Generalizable Forgery Image Detection**](https://arxiv.org/abs/2408.13697) | Chen et al. | [Code](https://github.com/Yingjian-Chen/ForgeLens) | `CLIP`
+ [**LOTA: Bit-Planes Guided AI-Generated Image Detection**](https://arxiv.org/abs/2510.14230) | Wang et al. | [Code](https://github.com/hongsong-wang/LOTA) | `Frequency`
+ [**Forensic-MoE: Exploring Comprehensive Synthetic Image Detection Traces with Mixture of Experts**](https://iccv.thecvf.com/virtual/2025/poster/919) | Fang et al. | [Code](https://github.com/fangmq77/Forensic-MoE) | `Multi-Generator` `MoE`
+ [**Semantic Discrepancy-aware Detector for Image Forgery Identification**](https://arxiv.org/abs/2508.12341) | Wang et al. | `Semantic`
+ [**D³QE: Learning Discrete Distribution Discrepancy-aware Quantization Error for Autoregressive-Generated Image Detection**](https://arxiv.org/abs/2510.05891) | Zhang et al. | `Autoregressive`
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
+ [**FIRE: Robust Detection of Diffusion-Generated Images via Frequency-Guided Reconstruction Error**](https://arxiv.org/abs/2412.07140) | Chu et al. | `Reconstruction`
+ [**Secret Lies in Color: Enhancing AI-Generated Images Detection with Color Distribution Analysis**](https://openaccess.thecvf.com/content/CVPR2025/papers/Jia_Secret_Lies_in_Color_Enhancing_AI-Generated_Images_Detection_with_Color_CVPR_2025_paper.pdf) | Jia et al. | `Color`
+ [**Community Forensics: Using Thousands of Generators to Train Fake Image Detectors**](https://arxiv.org/abs/2411.04125) | Park et al. | [Code](https://github.com/JeongsooP/Community-Forensics) | `Multi-Generator`
+ [**SIDA: Social Media Image Deepfake Detection, Localization and Explanation with LMM**](https://arxiv.org/abs/2412.04292) | Huang et al. | [Code](https://github.com/hzlsaber/SIDA) | `LMM`
+ [**CO-SPY: Combining Semantic and Pixel Features to Detect Synthetic Images by AI**](https://arxiv.org/abs/2503.18286) | Cheng et al. | `Combined`
+ [**D³: Scaling Up Deepfake Detection by Learning from Discrepancy**](https://arxiv.org/abs/2404.04584) | Yang et al. | [Code](https://github.com/BigAandSmallq/D3) | `Training Strategy`
+ [**Forensic Self-Descriptions Are All You Need for Zero-Shot Detection, Open-Set Source Attribution, and Localization**](https://arxiv.org/abs/2503.21003) | Nguyen et al. | `Zero-shot`
+ [**Beyond Generation: A Diffusion-based Low-level Feature Extractor for Detecting AI-generated Images**](https://openaccess.thecvf.com/content/CVPR2025/papers/Zhong_Beyond_Generation_A_Diffusion-based_Low-level_Feature_Extractor_for_Detecting_AI-generated_CVPR_2025_paper.pdf) | Zhong et al. | `Feature`

### ICLR 2025

+ [**Aligned Datasets Improve Detection of Latent Diffusion-Generated Images**](https://arxiv.org/abs/2410.11835) | Rajan et al. | [Code](https://github.com/AniSundar18/AlignedForensics) | `Training Strategy`
+ [**A Sanity Check for AI-generated Image Detection (AIDE)**](https://arxiv.org/abs/2406.19435) | - | [Code](https://github.com/shilinyan99/AIDE) | `Benchmark`
+ [**LOKI: A Comprehensive Synthetic Data Detection Benchmark using Large Multimodal Models**](https://arxiv.org/abs/2410.09732) | - | [Code](https://github.com/opendatalab/LOKI) | `Benchmark`
+ [**FakeShield: Explainable Image Forgery Detection and Localization via Multi-modal Large Language Models**](https://arxiv.org/abs/2410.02761) | Xu et al. | [Code](https://github.com/zhipeixu/FakeShield) | `LMM`

### NeurIPS 2025

+ [**Detecting Generated Images by Fitting Natural Image Distributions**](https://arxiv.org/abs/2411.01674) | Zhang et al. | [Code](https://github.com/tmlr-group/ConV) | `Spotlight` `Distribution`
+ **Denoising Trajectory Biases for Zero-Shot AI-Generated Image Detection** | Liang et al. | `Zero-shot`
+ [**Training-free Detection of AI-generated images via Cropping Robustness (WaRPAD)**](https://arxiv.org/abs/2511.14030) | Choi et al. | [Code](https://github.com/sungikchoi/WaRPAD) | `Training-free`
+ **Towards Generalizable Detector for Generated Image (DEnD)** | Cai et al. | [Code](https://github.com/dav-joy-thon/DEnD-Detection) | `Perturbation`
+ [**Epistemic Uncertainty for Generated Image Detection (WePe)**](https://arxiv.org/abs/2412.05897) | Nie et al. | [Code](https://github.com/tmlr-group/WePe) | `Uncertainty`
+ [**Dual Data Alignment Makes AI-Generated Image Detector Easier Generalizable**](https://arxiv.org/abs/2505.14359) | Chen et al. | `Spotlight` `Training Strategy`
+ [**MLEP: Multi-granularity Local Entropy Patterns for Generalized AI-generated Image Detection**](https://arxiv.org/abs/2504.13726) | Yuan et al. | [Code](https://github.com/fkeufss/MLEP) | `Pattern`
+ [**FerretNet: Efficient Synthetic Image Detection via Local Pixel Dependencies**](https://arxiv.org/abs/2509.20890) | Liang et al. | [Code](https://github.com/xigua7105/FerretNet) | `Pixel`
+ [**Breaking Latent Prior Bias in Detectors for Generalizable AIGC Image Detection**](https://arxiv.org/abs/2506.00874) | Zhou et al. | `Bias-Free`

### ECCV 2024

+ [**Zero-Shot Detection of AI-Generated Images**](https://arxiv.org/abs/2409.15875) | Cozzolino et al. | `Zero-shot`
+ [**Contrasting Deepfakes Diffusion via Contrastive Learning and Global-Local Similarities**](https://arxiv.org/abs/2407.20337) | Baraldi et al. | `Contrastive`
+ **Leveraging Representations from Intermediate Encoder-Blocks for Synthetic Image Detection** | - | `Feature`
+ **Forgery-aware Adaptive Transformer for Generalizable Synthetic Image Detection** | - | `Transformer`

### NeurIPS 2024

+ [**Breaking Semantic Artifacts for Generalized AI-generated Image Detection**](https://github.com/Zig-HS/FakeImageDetection) | Zheng et al. | [Code](https://github.com/Zig-HS/FakeImageDetection) | `Texture`

### CVPR 2024

+ [**FakeInversion: Learning to Detect Images from Unseen Text-to-Image Models by Inverting Stable Diffusion**](https://openaccess.thecvf.com/content/CVPR2024/html/Cazenavette_FakeInversion_Learning_to_Detect_Images_from_Unseen_Text-to-Image_Models_by_CVPR_2024_paper.html) | Cazenavette et al. | [Page](https://fake-inversion.github.io/) | `Reconstruction`
+ [**AEROBLADE: Training-Free Detection of Latent Diffusion Images Using Autoencoder Reconstruction Error**](https://arxiv.org/abs/2401.17879) | Ricker et al. | `Reconstruction`
+ [**LaRE²: Latent Reconstruction Error Based Method for Diffusion-Generated Image Detection**](https://openaccess.thecvf.com/content/CVPR2024/html/Luo_LaRE2_Latent_Reconstruction_Error_Based_Method_for_Diffusion-Generated_Image_Detection_CVPR_2024_paper.html) | Luo et al. | `Reconstruction`
+ [**Rethinking the Up-Sampling Operations in CNN-based Generative Network for Generalizable Deepfake Detection**](https://arxiv.org/abs/2312.10461) | Tan et al. | [Code](https://github.com/chuangchuangtan/NPR-DeepfakeDetection) | `Frequency`
+ [**MaskSim: Detection of Synthetic Images by Masked Spectrum Similarity Analysis**](https://openaccess.thecvf.com/content/CVPR2024W/DFAD/html/Li_MaskSim_Detection_of_Synthetic_Images_by_Masked_Spectrum_Similarity_Analysis_CVPRW_2024_paper.html) | Li et al. | `Frequency`

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
+ **FingerprintNet: Synthesized Fingerprints for Generated Image Detection** | - | `Fingerprint`
+ [**On The Detection of Synthetic Images Generated by Diffusion Models**](https://arxiv.org/abs/2211.00680) | Corvi et al. | [Code](https://github.com/grip-unina/DMimageDetection) | `Diffusion`

</details>

<details>
<summary>CVPR 2020 & NeurIPS 2020</summary>

+ [**CNN-generated images are surprisingly easy to spot...for now**](https://arxiv.org/abs/1912.11035) | Wang et al. | [Code](https://github.com/peterwang512/CNNDetection) | `CNN Forensics`
+ [**Watch your Up-Convolution: CNN Based Generative Deep Neural Networks are Failing to Reproduce Spectral Distributions**](https://arxiv.org/abs/2003.01826) | Durall et al. | `Frequency`
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
+ [**AntifakePrompt: Prompt-Tuned Vision-Language Models are Fake Image Detectors**](https://arxiv.org/abs/2310.17419) | Chang et al. 2023 | `Prompt`
+ [**PatchCraft: Exploring Texture Patch for Efficient AI-generated Image Detection**](https://arxiv.org/abs/2311.12397) | Zhong et al. 2024 | `Patch`
+ [**Bi-LORA: A Vision-Language Approach for Synthetic Image Detection**](https://arxiv.org/abs/2404.01959) | 2024 | `CLIP`
+ [**Fake or JPEG? Revealing Common Biases in Generated Image Detection Datasets**](https://arxiv.org/abs/2403.17608) | Grommelt et al. 2024 | [Page](https://www.unbiased-genimage.org/) | `Bias`

</details>

---

## Papers by Category

### 1. CLIP / Vision-Language Methods

Methods leveraging CLIP or other vision-language models for AIGC detection.

#### 1.1 CLIP Fine-tuning & Adaptation

+ [**Raising the Bar of AI-generated Image Detection with CLIP**](https://arxiv.org/abs/2312.00195) | Cozzolino et al. | 2024 | `CLIP`
+ [**CLIPping the Deception: Adapting Vision-Language Models for Universal Deepfake Detection**](https://dl.acm.org/doi/10.1145/3652583.3658035) | ICMR 2024 | [Code](https://github.com/sohailahmedkhan/CLIPping-the-Deception) | `CLIP`
+ [**DeeCLIP: A Robust and Generalizable Transformer-Based Framework**](https://arxiv.org/abs/2504.19876) | 2025 | `CLIP`
+ [**DGS-Net: Distillation-Guided Gradient Surgery for CLIP Fine-Tuning in AI-Generated Image Detection**](https://arxiv.org/abs/2511.13108) | Yan et al. 2025 | `CLIP`
+ [**NS-Net: Decoupling CLIP Semantic Information through NULL-Space for Generalizable AI-Generated Image Detection**](https://arxiv.org/abs/2508.01248) | Yan et al. 2025 | `CLIP`
+ [**When Semantics Regulate: Rethinking Patch Shuffle for AI-Generated Image Detection**](https://arxiv.org/abs/2511.19126) | 2025 | `CLIP`

#### 1.2 Prompt Learning

+ [**AntifakePrompt: Prompt-Tuned Vision-Language Models are Fake Image Detectors**](https://arxiv.org/abs/2310.17419) | Chang et al. 2024 | `Prompt`
+ **PLOT: Prompt Learning with Optimal Transport** | `Prompt`
+ [**Towards Generalizable AI-Generated Image Detection via Image-Adaptive Prompt Learning**](https://arxiv.org/abs/2508.01603) | Li et al. | CVPR 2026 | [Code](https://github.com/liyih/IAPL) | `Prompt`

#### 1.3 Feature Decoupling & Fusion

+ [**CausalCLIP: Causally-Informed Feature Disentanglement and Filtering for Generalizable Detection**](https://arxiv.org/abs/2512.13285) | Liu et al. 2025 | `CLIP`
+ [**MiraGe: Multimodal Discriminative Representation Learning for Generalizable AI-Generated Image Detection**](https://arxiv.org/abs/2508.01525) | Shi et al. 2025 | `CLIP`
+ [**Mixture of Low-rank Experts for Transferable AI-Generated Image Detection**](https://arxiv.org/abs/2404.04883) | Liu et al. 2024 | [Code](https://github.com/zhliuworks/CLIPMoLE) | `CLIP`
+ [**Orthogonal Subspace Decomposition for Generalizable AI-Generated Image Detection**](https://arxiv.org/abs/2411.15633) | Yan et al. | ICML 2025 | [Code](https://github.com/YZY-stack/Effort-AIGI-Detection) | `CLIP`
+ [**CO-SPY: Combining Semantic and Pixel Features to Detect Synthetic Images by AI**](https://arxiv.org/abs/2503.18286) | Cheng et al. | CVPR 2025 | `Combined`

#### 1.4 Information Bottleneck

+ [**Towards Universal AI-Generated Image Detection by Variational Information Bottleneck Network**](https://openaccess.thecvf.com/content/CVPR2025/papers/Zhang_Towards_Universal_AI-Generated_Image_Detection_by_Variational_Information_Bottleneck_Network_CVPR_2025_paper.pdf) | Zhang et al. | CVPR 2025 | [Code](https://github.com/oceanzhf/VIBAIGCDetect) | `CLIP`
+ [**Multimodal Conditional Information Bottleneck for Generalizable AI-Generated Image Detection**](https://arxiv.org/abs/2505.15217) | Qin et al. 2025 | [Code](https://github.com/Ant0ny44/InfoFD) | `CLIP`

---

### 2. Reconstruction-based Methods

Methods that detect AI-generated images by analyzing reconstruction errors.

#### 2.1 Diffusion Reconstruction

+ [**DIRE for Diffusion-Generated Image Detection**](https://arxiv.org/abs/2303.09295) | Wang et al. | ICCV 2023 | [Code](https://github.com/ZhendongWang6/DIRE) | `Reconstruction`
+ [**FIRE: Robust Detection of Diffusion-Generated Images via Frequency-Guided Reconstruction Error**](https://arxiv.org/abs/2412.07140) | Chu et al. | CVPR 2025 | `Reconstruction`
+ [**DRCT: Diffusion Reconstruction Contrastive Training towards Universal Detection**](https://openreview.net/pdf?id=oRLwyayrh1) | ICML 2024 | `Reconstruction`
+ [**LATTE: Latent Trajectory Embedding for Diffusion-Generated Image Detection**](https://arxiv.org/abs/2507.03054) | Vasilcoiu et al. 2025 | [Code](https://github.com/AnaMVasilcoiu/LATTE-Diffusion-Detector) | `Reconstruction`
+ **STD-FD: Spatio-Temporal Distribution Fitting Deviation for AIGC Forgery Identification** | Lou et al. | `Reconstruction`

#### 2.2 Autoencoder Reconstruction

+ [**AEROBLADE: Training-Free Detection of Latent Diffusion Images Using Autoencoder Reconstruction Error**](https://arxiv.org/abs/2401.17879) | Ricker et al. | CVPR 2024 | `Reconstruction`
+ [**GRRE: Leveraging G-Channel Removed Reconstruction Error for Robust Detection of AI-Generated Images**](https://arxiv.org/abs/2601.02709) | He et al. 2026 | `Reconstruction`
+ [**CINEMAE: Leveraging Frozen Masked Autoencoders for Cross-Generator AI Image Detection**](https://arxiv.org/abs/2511.06325) | Jang et al. 2025 | `Reconstruction`

#### 2.3 Latent Space

+ [**LaRE²: Latent Reconstruction Error Based Method for Diffusion-Generated Image Detection**](https://arxiv.org/abs/2403.17465) | Luo et al. | CVPR 2024 | `Reconstruction`
+ [**FakeInversion: Learning to Detect Images from Unseen Text-to-Image Models by Inverting Stable Diffusion**](https://arxiv.org/abs/2406.08603) | Cazenavette et al. | CVPR 2024 | `Reconstruction`

#### 2.4 Semantic-Aware Reconstruction

+ [**SARE: Semantic-Aware Reconstruction Error for Generalizable Diffusion-Generated Image Detection**](https://arxiv.org/abs/2508.09487) | Kang et al. 2025 | arXiv | `Reconstruction`
+ [**Exposing the Fake: Effective Diffusion-Generated Images Detection**](https://arxiv.org/abs/2307.06272) | Ma et al. | AdvML-Frontiers@ICML 2023 Workshop | `Reconstruction`

#### 2.5 Pixel-level Decomposition

+ [**PiD: Generalized AI-Generated Images Detection with Pixelwise Decomposition Residuals**](https://proceedings.mlr.press/v267/fu25i.html) | Fu et al. | ICML 2025 | `Reconstruction`
+ [**Beyond Semantic Features: Pixel-level Mapping for Generalized AI-Generated Image Detection**](https://arxiv.org/abs/2512.17350) | Zhou et al. | `Pixel-level`
+ [**MLEP: Multi-granularity Local Entropy Patterns for Generalized AI-generated Image Detection**](https://arxiv.org/abs/2504.13726) | Yuan et al. | [Code](https://github.com/fkeufss/MLEP) | `Pattern`

---

### 3. Frequency-domain Methods

+ **Generalizable AI-Generated Image Detection Based on Fractal Self-Similarity in the Spectrum** | Xiao et al. 2025 | `Frequency`
+ [**Any-Resolution AI-Generated Image Detection by Spectral Learning**](https://arxiv.org/abs/2411.19417) | Karageorgiou et al. | CVPR 2025 | [Code](https://github.com/mever-team/spai) | `Frequency`
+ [**LOTA: Bit-Planes Guided AI-Generated Image Detection**](https://arxiv.org/abs/2510.14230) | Wang et al. 2025 | [Code](https://github.com/hongsong-wang/LOTA) | `Frequency`
+ **Improving Synthetic Image Detection Towards Generalization: An Image Transformation Perspective** | Li et al. 2025 | `Frequency`
+ **Training-Free AI-Generated Image Detection via Spectral Artifacts** | `Frequency`
+ [**Secret Lies in Color: Enhancing AI-Generated Images Detection with Color Distribution Analysis**](https://openaccess.thecvf.com/content/CVPR2025/papers/Jia_Secret_Lies_in_Color_Enhancing_AI-Generated_Images_Detection_with_Color_CVPR_2025_paper.pdf) | Jia et al. | CVPR 2025 | `Color`
+ [**Color Matters: Demosaicing-Guided Color Correlation Training for Generalizable AI-Generated Image Detection**](https://arxiv.org/abs/2601.22778) | Zhong et al. 2026 | `Color`
+ [**Fourier Spectrum Discrepancies in Deep Network Generated Images**](https://arxiv.org/abs/1911.06465) | NeurIPS 2020 | [Code](https://github.com/tarikdzanic/FourierSpectrumDiscrepancies) | `Frequency`

---

### 4. Patch / Texture-based Methods

+ [**A Single Simple Patch is All You Need for AI-generated Image Detection**](https://arxiv.org/abs/2402.01123) | Chen et al. 2024 | `Patch`
+ [**PatchCraft: Exploring Texture Patch for Efficient AI-generated Image Detection**](https://arxiv.org/abs/2311.12397) | Zhong et al. 2024 | `Patch`
+ [**All Patches Matter, More Patches Better: Enhance AI-Generated Image Detection via Panoptic Patch Learning**](https://openreview.net/forum?id=ob7PJs8kPU) | Yang et al. | ICLR 2026 | `Patch`
+ [**TextureCrop: Enhancing Synthetic Image Detection through Texture-based Cropping**](https://arxiv.org/abs/2407.15500) | Konstantinidou et al. | `Texture`
+ [**Breaking Semantic Artifacts for Generalized AI-generated Image Detection**](https://github.com/Zig-HS/FakeImageDetection) | Zheng et al. | NeurIPS 2024 | [Code](https://github.com/Zig-HS/FakeImageDetection) | `Texture`
+ [**FerretNet: Efficient Synthetic Image Detection via Local Pixel Dependencies**](https://arxiv.org/abs/2509.20890) | Liang et al. | NeurIPS 2025 | [Code](https://github.com/xigua7105/FerretNet) | `Pixel`
+ [**No Pixel Left Behind: A Detail-Preserving Architecture for Robust High-Resolution AI-Generated Image Detection**](https://openreview.net/forum?id=9QQ3Kc2hj6) | Mu et al. | ICLR 2026 | `Pixel`
+ [**Rethinking the Use of Vision Transformers for AI-Generated Image Detection**](https://arxiv.org/abs/2512.04969) | Park et al. 2025 | `Architecture`

---

### 5. Noise / Fingerprint-based Methods

+ [**Revealing the Implicit Noise-based Imprint of Generative Models**](https://arxiv.org/abs/2503.09314) | Li et al. 2025 | `Noise`
+ [**Perceptual Classifiers: Detecting Generative Images using Perceptual Features**](https://openaccess.thecvf.com/content/ICCV2025W/VQualA/papers/Durbha_Perceptual_Classifiers_Detecting_Generative_Images_using_Perceptual_Features_ICCVW_2025_paper.pdf) | Durbha et al. | ICCV 2025 Workshop | `Perceptual`
+ [**Beyond Generation: A Diffusion-based Low-level Feature Extractor for Detecting AI-generated Images**](https://openaccess.thecvf.com/content/CVPR2025/papers/Zhong_Beyond_Generation_A_Diffusion-based_Low-level_Feature_Extractor_for_Detecting_AI-generated_CVPR_2025_paper.pdf) | Zhong et al. | CVPR 2025 | `Feature`
+ [**HFI: A Unified Framework for Training-free Detection and Implicit Watermarking of Latent Diffusion Models**](https://arxiv.org/abs/2412.20704) | Choi et al. 2024 | `Fingerprint`
+ [**Data-Independent Operator: A Training-Free Artifact Representation Extractor**](https://arxiv.org/abs/2403.06803) | Tan et al. | [Code](https://github.com/chuangchuangtan/Data-Independent-Operator) | `Feature`
+ [**Exploring the Collaborative Advantage of Low-level Information on Generalizable AI-Generated Image Detection**](https://arxiv.org/abs/2504.00463) | Zhou et al. 2025 | `Feature Fusion`

---

### 6. Perturbation / Robustness-based Methods

+ [**RIGID: A Training-free and Model-Agnostic Framework for Robust AI-Generated Image Detection**](https://arxiv.org/abs/2405.20112) | He et al. 2024 | `Perturbation`
+ [**RA-Det: Towards Universal Detection of AI-Generated Images via Robustness Asymmetry**](https://arxiv.org/abs/2603.01544) | Wang et al. 2026 | arXiv | `Perturbation`
+ [**Detecting AI-Generated Images via Distributional Deviations from Real Images**](https://arxiv.org/abs/2601.03586) | Niu et al. 2026 | `Perturbation`
+ [**Epistemic Uncertainty for Generated Image Detection (WePe)**](https://arxiv.org/abs/2412.05897) | Nie et al. | NeurIPS 2025 | [Code](https://github.com/tmlr-group/WePe) | `Uncertainty`
+ [**How Noise Benefits AI-generated Image Detection**](https://arxiv.org/abs/2511.16136) | Yan et al. 2025 | `Noise`
+ **Towards Generalizable Detector for Generated Image (DEnD)** | Cai et al. | NeurIPS 2025 | [Code](https://github.com/dav-joy-thon/DEnD-Detection) | `Perturbation`
+ [**Detecting Generated Images by Fitting Natural Image Distributions**](https://arxiv.org/abs/2411.01674) | Zhang et al. | NeurIPS 2025 Spotlight | [Code](https://github.com/tmlr-group/ConV) | `Distribution`
+ [**ENABLING YOUR FORENSIC DETECTOR KNOW HOW WELL IT PERFORMS ON DISTORTED SAMPLES**](https://openreview.net/forum?id=Jz5SA2KoFt) | Li et al. | ICLR 2026 | `Robustness`

---

### 7. LMM / Reasoning-based Methods

Methods leveraging Large Multimodal Models for explainable and generalizable detection.

+ [**LEGION: Learning to Ground and Explain for Synthetic Image Detection**](https://arxiv.org/abs/2503.15264) | Kang et al. | ICCV 2025 | [Code](https://github.com/opendatalab/LEGION) | `LMM`
+ [**AIGI-Holmes: Towards Explainable and Generalizable AI-Generated Image Detection via Multimodal Large Language Models**](https://arxiv.org/abs/2507.02664) | Zhou et al. | ICCV 2025 | [Code](https://github.com/wyczzy/AIGI-Holmes) | `LMM`
+ [**ThinkFake: Reasoning in Multimodal Large Language Models for AI-Generated Image Detection**](https://arxiv.org/abs/2509.19841) | Huang et al. 2025 | `LMM`
+ [**FakeReasoning: Towards Generalizable Forgery Detection and Reasoning**](https://arxiv.org/abs/2503.21210) | Gao et al. 2025 | `LMM`
+ [**Spot the Fake: Large Multimodal Model-Based Synthetic Image Detection with Artifact Explanation**](https://arxiv.org/abs/2503.14905) | Wen et al. 2025 | `LMM`
+ [**Veritas: Generalizable Deepfake Detection via Pattern-Aware Reasoning**](https://openreview.net/forum?id=5VXJPS1HoM) | Tan et al. | ICLR 2026 Oral | [Code](https://github.com/Rosstein/HydraFake-tanh) | `LMM`
+ [**SIDA: Social Media Image Deepfake Detection, Localization and Explanation with LMM**](https://arxiv.org/abs/2412.04292) | Huang et al. | CVPR 2025 | [Code](https://github.com/hzlsaber/SIDA) | `LMM`
+ [**FakeShield: Explainable Image Forgery Detection and Localization via Multi-modal Large Language Models**](https://arxiv.org/abs/2410.02761) | Xu et al. | ICLR 2025 | [Code](https://github.com/zhipeixu/FakeShield) | `LMM`
+ [**FAKEXPLAIN: AI-Generated Images Detection via Human-Aligned Grounded Reasoning**](https://openreview.net/forum?id=UcpTOa8OnG) | Ji et al. | ICLR 2026 | `LMM`
+ [**Semantic Visual Anomaly Detection and Reasoning in AI-Generated Images**](https://openreview.net/forum?id=0iN4UKZwgn) | Tan et al. | ICLR 2026 | `LMM`
+ [**Explainable Synthetic Image Detection through Diffusion Timestep Ensembling**](https://arxiv.org/abs/2503.06201) | Wu et al. 2025 | `Explainable`
+ [**Unlocking the Capabilities of Large Vision-Language Models for Generalizable and Explainable Deepfake Detection**](https://arxiv.org/abs/2503.14853) | ICML 2025 | `LMM`

---

### 8. Zero-shot & Training-free Methods

+ [**RIGID: A Training-free and Model-Agnostic Framework for Robust AI-Generated Image Detection**](https://arxiv.org/abs/2405.20112) | He et al. 2024 | `Training-free`
+ **Intermediate Representations Are Strong Training-Free AI-Generated Image Detectors** | `Training-free`
+ **Training-Free AI-Generated Image Detection via Spectral Artifacts** | `Training-free`
+ [**Forensic Self-Descriptions Are All You Need for Zero-Shot Detection, Open-Set Source Attribution, and Localization**](https://arxiv.org/abs/2503.21003) | Nguyen et al. | CVPR 2025 | `Zero-shot`
+ [**Zero-Shot Detection of AI-Generated Images**](https://arxiv.org/abs/2409.15875) | Cozzolino et al. | ECCV 2024 | `Zero-shot`
+ [**Detecting Generated Images by Fitting Natural Image Distributions**](https://arxiv.org/abs/2411.01674) | Zhang et al. | NeurIPS 2025 Spotlight | [Code](https://github.com/tmlr-group/ConV) | `Distribution`
+ **Triggering Generative Collapse: A Contrastive Inversion Framework for AI-Generated Image Detection** | arXiv | `Zero-shot`
+ **General and Domain-Specific Zero-shot Detection of Generated Images via Conditional Likelihood** | Betser et al. 2025 | `Zero-shot`
+ [**Training-free Detection of AI-generated images via Cropping Robustness**](https://arxiv.org/abs/2511.14030) | Choi et al. | [Code](https://github.com/sungikchoi/WaRPAD) | `Training-free`
+ **Denoising Trajectory Biases for Zero-Shot AI-Generated Image Detection** | Liang et al. | `Zero-shot`
+ **Revisiting Reconstruction-based AI-generated Image Detection: A Geometric Perspective** | Jiang et al. 2025 | `Zero-shot`
+ **Understanding and Improving Training-Free AI-Generated Image Detections with Vision Foundation Models** | Tsai et al. 2024 | `Training-free`

---

### 9. Diffusion-specific Detection

+ [**On the Detection of Synthetic Images Generated by Diffusion Models**](https://arxiv.org/abs/2211.00680) | Corvi et al. 2022 | [Code](https://github.com/grip-unina/DMimageDetection) | `Diffusion`
+ [**Diffusion Noise Feature: Accurate and Fast Generated Image Detection**](https://arxiv.org/abs/2312.02625) | Zhang et al. | [Code](https://github.com/YichiCS/DNF) | `Diffusion`
+ [**Diffusion Epistemic Uncertainty with Asymmetric Learning for Diffusion-Generated Image Detection**](https://arxiv.org/abs/2601.14625) | Huang et al. | ICCV 2025 | `Diffusion`
+ [**PRADA: Probability-Ratio-Based Attribution and Detection of Autoregressive-Generated Images**](https://arxiv.org/abs/2511.20068) | Damm et al. 2025 | `AR / Diffusion`

---

### 10. Autoregressive Model Detection

+ [**PRADA: Probability-Ratio-Based Attribution and Detection of Autoregressive-Generated Images**](https://arxiv.org/abs/2511.20068) | Damm et al. 2025 | `Autoregressive`
+ [**D³QE: Learning Discrete Distribution Discrepancy-aware Quantization Error for Autoregressive-Generated Image Detection**](https://arxiv.org/abs/2510.05891) | Zhang et al. 2025 | `Autoregressive`
+ [**Data Provenance for Image Auto-Regressive Generation**](https://openreview.net/forum?id=qYu4wj7O3z) | Zhao et al. | ICLR 2026 | `AR / Attribution`

---

### 11. Deepfake Detection (with General AIGC Detection Experiments)

> Only includes papers that also evaluate on general AI-generated image detection benchmarks, not face-only methods.

+ [**D³: Scaling Up Deepfake Detection by Learning from Discrepancy**](https://arxiv.org/abs/2404.04584) | Yang et al. | CVPR 2025 | [Code](https://github.com/BigAandSmallq/D3) | `Deepfake + General`
+ [**Veritas: Generalizable Deepfake Detection via Pattern-Aware Reasoning**](https://openreview.net/forum?id=5VXJPS1HoM) | Tan et al. | ICLR 2026 Oral | [Code](https://github.com/Rosstein/HydraFake-tanh) | `LMM + Deepfake`
+ [**Real-Time Deepfake Detection in the Real-World**](https://arxiv.org/abs/2406.09398) | Cavia et al. 2024 | `Deepfake`

---

### 12. Generalization: Training Strategy & Data Engineering

#### 12.1 Data Alignment & Construction

+ [**Dual Data Alignment Makes AI-Generated Image Detector Easier Generalizable**](https://arxiv.org/abs/2505.14359) | Chen et al. | NeurIPS 2025 Spotlight | `Data Alignment`
+ [**Aligned Datasets Improve Detection of Latent Diffusion-Generated Images**](https://arxiv.org/abs/2410.11835) | Rajan et al. | ICLR 2025 | [Code](https://github.com/AniSundar18/AlignedForensics) | `Data Alignment`
+ [**A Bias-Free Training Paradigm for More General AI-generated Image Detection**](https://arxiv.org/abs/2412.17671) | Guillaro et al. | CVPR 2025 | [Code](https://github.com/grip-unina/B-Free) | `Bias-Free`
+ [**Breaking Latent Prior Bias in Detectors for Generalizable AIGC Image Detection**](https://arxiv.org/abs/2506.00874) | Zhou et al. | NeurIPS 2025 | `Bias-Free`
+ [**Fake or JPEG? Revealing Common Biases in Generated Image Detection Datasets**](https://arxiv.org/abs/2403.17608) | Grommelt et al. 2024 | [Page](https://www.unbiased-genimage.org/) | `Bias`
+ [**Task-Model Alignment: A Simple Path to Generalizable AI-Generated Image Detection**](https://arxiv.org/abs/2512.06746) | Chen et al. 2025 | `Data Alignment`
+ [**SimLBR: Learning to Detect Fake Images by Learning to Detect Real Images**](https://arxiv.org/abs/2602.20412) | Dhakal et al. | CVPR 2026 | `Regularization`

#### 12.2 Real-Centric & Calibration

+ [**MIRROR: Manifold Ideal Reference ReconstructOR for Generalizable AI-Generated Image Detection**](https://arxiv.org/abs/2602.02222) | Liu et al. 2026 | arXiv | [Code](https://github.com/349793927/MIRROR) | `Real-Centric`
+ [**Your AI-Generated Image Detector Can Secretly Achieve SOTA Accuracy, If Calibrated**](https://arxiv.org/abs/2602.01973) | Yang et al. | AAAI 2026 | `Calibration`
+ [**Stay-Positive: A Case for Ignoring Real Image Features in Fake Image Detection**](https://arxiv.org/abs/2502.07778) | ICML 2025 | [Code](https://github.com/AniSundar18/AlignedForensics) | `Real-Centric`
+ [**Towards Generalizable AI-Generated Image Detection via Image-Adaptive Prompt Learning**](https://arxiv.org/abs/2508.01603) | Li et al. | CVPR 2026 | [Code](https://github.com/liyih/IAPL) | `Test-Time Adaptation`

#### 12.3 Multi-Generator

+ [**Community Forensics: Using Thousands of Generators to Train Fake Image Detectors**](https://arxiv.org/abs/2411.04125) | Park et al. | CVPR 2025 | [Code](https://github.com/JeongsooP/Community-Forensics) | `Multi-Generator`
+ [**Scaling Up AI-Generated Image Detection via Generator-Aware Prototypes**](https://arxiv.org/abs/2512.12982) | Qin et al. | CVPR 2026 | [Code](https://github.com/UltraCapture/GAPL) | `Multi-Generator`
+ [**Forensic-MoE: Exploring Comprehensive Synthetic Image Detection Traces with Mixture of Experts**](https://iccv.thecvf.com/virtual/2025/poster/919) | Fang et al. | ICCV 2025 | [Code](https://github.com/fangmq77/Forensic-MoE) | `Multi-Generator`
+ [**HSIC Bottleneck for Cross-Generator and Domain-Incremental Synthetic Image Detection**](https://openreview.net/forum?id=msLnKDvhBx) | Yang et al. | ICLR 2026 | `Multi-Generator`

---

### 13. Image Attribution / Source Tracing

+ [**How to Trace Latent Generative Model Generated Images without Artificial Watermark?**](https://arxiv.org/abs/2405.13360) | Wang et al. | ICML 2024 | [Code](https://github.com/ZhentingWang/LatentTracer) | `Attribution`
+ [**AEDR: Training-Free AI-Generated Image Attribution via Autoencoder Double-Reconstruction**](https://arxiv.org/abs/2501.09245) | Wang et al. | AAAI 2026 Oral | `Attribution`
+ [**Which Model Generated This Image? A Model-Agnostic Approach for Origin Attribution**](https://arxiv.org/abs/2404.02697) | Liu et al. 2024 | [Code](https://github.com/uwFengyuan/OCC-CLIP) | `Attribution`
+ [**PRADA: Probability-Ratio-Based Attribution and Detection of Autoregressive-Generated Images**](https://arxiv.org/abs/2511.20068) | Damm et al. 2025 | `Attribution`
+ [**Data Provenance for Image Auto-Regressive Generation**](https://openreview.net/forum?id=qYu4wj7O3z) | Zhao et al. | ICLR 2026 | `Attribution`

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

**Last Updated**: 2026-03-16 | **Total Papers**: 170+

Contributions and suggestions are welcome! Please open an issue or pull request.
