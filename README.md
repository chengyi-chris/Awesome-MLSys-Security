# Awesome MLSys Security

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

A curated list of research papers, defenses, and real-world vulnerabilities on **security and privacy in machine learning systems**, with a particular focus on **LLM inference and serving**. Topics include KV cache management, speculative decoding, multi-tenant isolation, resource scheduling, distributed ML, and the ML systems supply chain.

> **Scope:** This repository focuses on security issues arising from the **design, implementation, optimization, and deployment of ML systems**. General-purpose LLM jailbreaks, prompt injection, and alignment research are included only when they expose a concrete systems-level attack surface or defense.

## Contents

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

## 1. LLM Inference Security

Security and privacy risks in the mechanisms used to execute and optimize model inference.

### KV Cache Security

- **[NDSS 2026]** *Shadow in the Cache: Unveiling and Mitigating Privacy Risks of KV-cache in LLM Inference* [[Paper](https://www.ndss-symposium.org/wp-content/uploads/2026-f258-paper.pdf)]

### Speculative Decoding Security

- **[IEEE S&P 2027]** *Secure Speculative Decoding for Large Language Models* [[Paper](https://arxiv.org/abs/2610.08678v2)]

### Attention & Inference Optimization

*Papers to be added.*

### Model Compression & Quantization

*Papers to be added.*

---

## 2. LLM Serving Security

Security risks introduced by serving frameworks, caching policies, resource sharing, and request scheduling.

### Multi-Tenant Isolation

- **[USENIX 2026]** *HijackKV: New Threat in Position-Independent KV Cache Reuse* [[Paper](https://arxiv.org/abs/2607.19957)]

### Cache Poisoning

*Papers to be added.*

### Scheduling & Resource Exhaustion

- **[NeurIPS 2026]** *Rethinking Latency Denial-of-Service: Attacking the LLM Serving Framework, Not the Model* [[Paper](https://arxiv.org/abs/2602.07878)]
  - `Target: PagedAttention & Scheduler` | `Attack: Preemption & Latency DoS` | `System: vLLM`

### Side-Channel Attacks

- **[NDSS 2025]** *I Know What You Asked: Prompt Leakage via KV-Cache Sharing in Multi-Tenant LLM Serving* [[Paper](https://www.ndss-symposium.org/wp-content/uploads/2025-1772-paper.pdf)]
  - `Target: Prefix Caching` | `Attack: Timing & Scheduling Side-Channel` | `System: vLLM / SGLang`
- **[ICML 2025]** *Auditing Prompt Caching in Language Model APIs* [[Paper](https://arxiv.org/abs/2502.07776)]

---

## 3. Distributed ML Security

Security of distributed training and inference, including cross-node communication and trust boundaries.

### Distributed Training

*Papers to be added.*

### Distributed Inference

*Papers to be added.*

### Communication Security

*Papers to be added.*

---

## 4. ML Systems Supply Chain

Security of the artifacts, dependencies, and runtime components used to load, execute, and deploy ML models.

### Model Serialization

*Papers to be added.*

### Model Loading & Deployment

*Papers to be added.*

### Runtime & Framework Security

*Papers to be added.*

---

## Contributing

Contributions are welcome! Please open a **Pull Request** to suggest a relevant research paper, defense, or real-world vulnerability, or open an **Issue** for discussion.

To help keep the list consistent:

- Submit work with a clear **ML systems component** and **security or privacy implication**.
- Add each paper to its **primary category**; avoid duplicate entries across sections.
- Use the format `**[Venue Year]** *Paper Title* [[Paper](URL)]` and optionally include a code link.
- When useful, add a short metadata line with `Target`, `Attack` or `Defense`, and `System`.
- Prefer publisher or official proceedings links; use arXiv links when appropriate.

