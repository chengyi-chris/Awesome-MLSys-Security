# Awesome MLSys Security

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

A curated list of **peer-reviewed conference and journal papers** on security and privacy in machine learning systems, with a particular focus on **LLM inference and serving**. Topics include KV cache management, speculative decoding, multi-tenant isolation, resource scheduling, distributed ML, and the ML systems supply chain.

> **Scope:** This repository focuses on security issues arising from the **design, implementation, optimization, and deployment of ML systems**. General-purpose LLM jailbreaks, prompt injection, and alignment research are included only when they expose a concrete systems-level attack surface or defense.
>
> **Publication policy:** Only papers **accepted to or published in peer-reviewed conferences or journals** are included. **arXiv-only preprints, submissions under review, and unverified venue claims are excluded.** Accepted papers awaiting publication may be listed with their confirmed venue and year. A paper hosted on arXiv is eligible if its peer-reviewed acceptance is independently verifiable.

## Contents

- [Paper Selection Criteria](#paper-selection-criteria)
- [1. LLM Inference Security](#1-llm-inference-security)
  - [KV Cache Security](#kv-cache-security)
  - [Speculative Decoding Security](#speculative-decoding-security)
  - [Attention & Inference Optimization](#attention--inference-optimization)
  - [Model Compression & Quantization](#model-compression--quantization)
- [2. LLM Serving Security](#2-llm-serving-security)
  - [Multi-Tenant Isolation](#multi-tenant-isolation)
  - [Cache Poisoning](#cache-poisoning)
  - [Scheduling & Resource Exhaustion](#scheduling--resource-exhaustion)
  - [Side-Channel Attacks](#side-channel-attacks)
- [3. Distributed ML Security](#3-distributed-ml-security)
  - [Distributed Training](#distributed-training)
  - [Distributed Inference](#distributed-inference)
  - [Communication Security](#communication-security)
- [4. ML Systems Supply Chain](#4-ml-systems-supply-chain)
  - [Model Serialization](#model-serialization)
  - [Model Loading & Deployment](#model-loading--deployment)
  - [Runtime & Framework Security](#runtime--framework-security)
- [Contributing](#contributing)

---

## Paper Selection Criteria

We prioritize **ML systems security** research published in CORE/ICORE A*/A conferences or other maintainer-approved high-quality peer-reviewed conferences and journals.

Papers must study a **concrete security or privacy issue arising from ML system design, optimization, or deployment**. Only accepted or published papers are eligible; arXiv-only and workshop-only works are excluded.

See [Contribution Guidelines](CONTRIBUTING.md) for priority venues, detailed eligibility criteria, and the manual update workflow.

---

## 1. LLM Inference Security

Security and privacy risks in the mechanisms used to execute and optimize model inference.

### KV Cache Security

- **[NDSS 2026]** *Shadow in the Cache: Unveiling and Mitigating Privacy Risks of KV-cache in LLM Inference* [[Paper](https://www.ndss-symposium.org/wp-content/uploads/2026-f258-paper.pdf)]

### Speculative Decoding Security

- **[IEEE S&P 2027, to appear]** *Secure Speculative Decoding for Large Language Models* [[Paper](https://arxiv.org/abs/2610.08678)] [[Code](https://github.com/YichiCS/Secure-Speculative-Decoding)]

### Attention & Inference Optimization

- **[USENIX Security 2025]** *Activation Approximations Can Incur Safety Vulnerabilities in Aligned LLMs: Comprehensive Analysis and Defense* [[Paper](https://www.usenix.org/conference/usenixsecurity25/presentation/zhang-jiawen)]
  - `Target: LLM activation approximation for efficient inference` | `Attack/Impact: Safety degradation after polynomialization, sparsification, or quantization` | `Defense: QuadA`

### Model Compression & Quantization

- **[USENIX Security 2026]** *CompLeak: Deep Learning Model Compression Exacerbates Privacy Leakage* [[Paper](https://www.usenix.org/conference/usenixsecurity26/presentation/li-na)]
  - `Target: Pruning, quantization, and weight clustering in deployed ML models` | `Attack: Membership inference / privacy leakage across compressed model versions`

---

## 2. LLM Serving Security

Security risks introduced by serving frameworks, caching policies, resource sharing, and request scheduling.

### Multi-Tenant Isolation

- **[USENIX Security 2026]** *Behind Bars: A Side-Channel Attack on NVIDIA MIG Cache Partitioning Using Memory Barriers* [[Paper](https://www.usenix.org/conference/usenixsecurity26/presentation/gu-cheng)]
  - `Target: NVIDIA MIG GPU cache isolation` | `Attack: Cross-instance side channel`
- **[USENIX Security 2026]** *TIMESLICE-SANDWICH: A GPU Side-Channel Attack Exploiting Time-Sliced Scheduling* [[Paper](https://www.usenix.org/conference/usenixsecurity26/presentation/kim-hodong)]
  - `Target: Shared GPU scheduling` | `Attack: Time-slicing side channel`
- **[USENIX 2026]** *HijackKV: New Threat in Position-Independent KV Cache Reuse* [[Paper](https://www.usenix.org/conference/usenixsecurity26/presentation/zhang-yichi)]

### Cache Poisoning

- **[NDSS 2026]** *Cache Me, Catch You: Cache Related Security Threats in LLM Serving Frameworks* [[Paper](https://www.ndss-symposium.org/ndss-paper/cache-me-catch-you-cache-related-security-threats-in-llm-serving-frameworks/)]
  - `Target: LLM serving caches` | `Attack: Cache-related integrity and security threats`
- **[NDSS 2026]** *When Cache Poisoning Meets LLM Systems: Semantic Cache Poisoning and Its Countermeasures* [[Paper](https://www.ndss-symposium.org/ndss-paper/when-cache-poisoning-meets-llm-systems-semantic-cache-poisoning-and-its-countermeasures/)]
  - `Target: Semantic caching` | `Attack: Cache poisoning` | `Defense: Countermeasures`

### Scheduling & Resource Exhaustion

- **[NeurIPS 2026]** *Rethinking Latency Denial-of-Service: Attack the LLM Serving Framework, Not the Model* [[Paper](https://arxiv.org/abs/2602.07878)]
  - `Target: PagedAttention & Scheduler` | `Attack: Preemption & Latency DoS` | `System: vLLM`

### Side-Channel Attacks

- **[NDSS 2026]** *Peering Inside the Black-Box: Long-Range and Scalable Model Architecture Snooping via GPU Electromagnetic Side-Channel* [[Paper](https://www.ndss-symposium.org/ndss-paper/peering-inside-the-black-box-long-range-and-scalable-model-architecture-snooping-via-gpu-electromagnetic-side-channel/)]
  - `Target: DNN inference on GPUs` | `Attack: Electromagnetic side-channel model architecture extraction`
- **[USENIX Security 2026]** *From Length to Content: Token-Length Side-Channel Attacks on LLM API Merged Outputs* [[Paper](https://www.usenix.org/conference/usenixsecurity26/presentation/li-sijia)]
  - `Target: LLM API response streaming` | `Attack: Encrypted-traffic side channel`
- **[USENIX Security 2025]** *I Know What You Said: Unveiling Hardware Cache Side-Channels in Local Large Language Model Inference* [[Paper](https://www.usenix.org/conference/usenixsecurity25/presentation/gao-zibo)]
  - `Target: Local LLM inference / hardware cache` | `Attack: Cache side channel`
- **[NDSS 2025]** *I Know What You Asked: Prompt Leakage via KV-Cache Sharing in Multi-Tenant LLM Serving* [[Paper](https://www.ndss-symposium.org/wp-content/uploads/2025-1772-paper.pdf)]
  - `Target: Prefix Caching` | `Attack: Timing & Scheduling Side-Channel` | `System: vLLM / SGLang`
- **[ICML 2025]** *Auditing Prompt Caching in Language Model APIs* [[Paper](https://proceedings.mlr.press/v267/gu25b.html)]

---

## 3. Distributed ML Security

Security of distributed training and inference, including cross-node communication and trust boundaries.

### Distributed Training

- **[OSDI 2026]** *Safeguarding LLM Training at Scale: Online SDC Detection and Insights from 35 Million GPU Hours* [[Paper](https://www.usenix.org/conference/osdi26/presentation/lei)]
  - `Target: Large-scale GPU training` | `Focus: Silent data corruption detection / reliability`

### Distributed Inference

- **[USENIX Security 2026]** *SMASH: Scalable Maliciously Secure Hybrid Multi-party Computation Framework for Privacy-Preserving Large Language Models* [[Paper](https://www.usenix.org/conference/usenixsecurity26/presentation/lv)]
  - `Target: Distributed privacy-preserving LLM inference` | `Defense: Maliciously secure hybrid multi-party computation`
- **[USENIX Security 2025]** *Depth Gives a False Sense of Privacy: LLM Internal States Inversion* [[Paper](https://www.usenix.org/conference/usenixsecurity25/presentation/dong-tian)]
  - `Target: Intermediate states in collaborative LLM inference` | `Attack: Input reconstruction / privacy leakage`
- **[ISPASS 2026]** *An Empirical Study of LLM Serving in Confidential GPUs* [[Paper](https://ieeexplore.ieee.org/abstract/document/11527301)]
  - `Target: Confidential GPU-based LLM serving` | `Focus: Security-performance overhead`
- **[IISWC 2025]** *Confidential LLM Inference: Performance and Cost Across CPU and GPU TEEs* [[Paper](https://spcl.ethz.ch/Publications/index.php?pub=561)]
  - `Target: CPU and GPU trusted execution environments` | `Focus: Confidential inference / performance`

### Communication Security

*Papers to be added.*

---

## 4. ML Systems Supply Chain

Security of the artifacts, dependencies, and runtime components used to load, execute, and deploy ML models.

### Model Serialization

- **[ACM CCS 2025]** *PickleBall: Secure Deserialization of Pickle-based Machine Learning Models* [[Paper](https://www.cs.columbia.edu/~junfeng/papers/pickleball-ccs25.pdf)] [[Code](https://github.com/columbia/pickleball)]
  - `Target: Pickle-based ML model loading` | `Defense: Secure deserialization`
- **[USENIX Security 2026]** *The Art of Hide and Seek: Making Pickle-Based Model Supply Chain Poisoning Stealthy Again* [[Paper](https://www.usenix.org/conference/usenixsecurity26/cycle1-accepted-papers)]
  - `Target: Pickle model artifacts and scanners` | `Attack: Stealthy supply-chain poisoning`

### Model Loading & Deployment

- **[USENIX Security 2025]** *From Purity to Peril: Backdooring Merged Models From "Harmless" Benign Components* [[Paper](https://www.usenix.org/conference/usenixsecurity25/presentation/wang-lijin)]
  - `Target: Model merging pipeline` | `Attack: Backdoored model components`
- **[ICML 2025, position paper]** *Position: Machine Learning Models Have a Supply Chain Problem* [[Paper](https://proceedings.mlr.press/v267/meiklejohn25a.html)]
  - `Target: ML model distribution and provenance` | `Focus: Supply-chain risks`

### Runtime & Framework Security

*Papers to be added.*

---

## Contributing

Contributions are welcome! Please read the [Contribution Guidelines](CONTRIBUTING.md) before suggesting papers via Pull Request or Issue.
