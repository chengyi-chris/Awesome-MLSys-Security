# Awesome LLM Serving & Inference Systems Security

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

A curated list of research papers, defenses, and real-world CVEs focusing on **LLM Serving & Inference Systems Security** — examining system-level vulnerabilities introduced by performance optimizations such as KV cache sharing, memory paging, continuous batching, speculative decoding, quantization, and disaggregated inference (e.g., vLLM, SGLang, TensorRT-LLM).

> **Scope Note:** Unlike general LLM safety repositories focused on prompt injection, jailbreaks, or alignment, this repository specifically tracks **systems-level attack surfaces and defenses** in inference engines and serving infrastructure.

---

## Contents

- [1. KV Cache & Memory Management Security](#1-kv-cache--memory-management-security)
  - [Prefix Caching Side-Channels](#prefix-caching-side-channels)
  - [Memory Exhaustion & Preemption DoS](#memory-exhaustion--preemption-dos)
  - [Cache Isolation & Defenses](#cache-isolation--defenses)
- [2. Scheduling & Decoding Dynamics](#2-scheduling--decoding-dynamics)
- [3. Quantization & Kernel-Level Security](#3-quantization--kernel-level-security)
- [4. Disaggregated & Distributed Serving Security](#4-disaggregated--distributed-serving-security)
- [5. Multimodal Serving Pipeline Security](#5-multimodal-serving-pipeline-security)
- [6. Hardware-Assisted Confidential Inference](#6-hardware-assisted-confidential-inference)
- [7. Notable CVEs & Real-World Advisories](#7-notable-cves--real-world-advisories)
- [Contributing](#contributing)

---

## 1. KV Cache & Memory Management Security

### Prefix Caching Side-Channels
- **[USENIX 2026]** *HijackKV: New Threat in Position-Independent KV Cache Reuse* [[Paper](https://arxiv.org/abs/2607.19957)]
- **[NDSS 2026]** *Shadow in the Cache: Unveiling and Mitigating Privacy Risks of KV-cache in LLM Inference* [[Paper](https://www.ndss-symposium.org/wp-content/uploads/2026-f258-paper.pdf)]
- **[NDSS 2025]** *I Know What You Asked: Prompt Leakage via KV-Cache Sharing in Multi-Tenant LLM Serving* [[Paper](https://www.ndss-symposium.org/wp-content/uploads/2025-1772-paper.pdf)]
  - `Target: Prefix Caching` | `Attack: Timing & Scheduling Side-Channel` | `System: vLLM / SGLang`
  
### Memory Exhaustion & Preemption DoS
- **[NeurIPS 2026]** *Rethinking Latency Denial-of-Service: Attacking the LLM Serving Framework, Not the Model* [[Paper](https://arxiv.org/abs/2602.07878)]
  - `Target: PagedAttention & Scheduler` | `Attack: Preemption & Latency DoS` | `System: vLLM`
- **[ICML 2025]** *Auditing Prompt Caching in Language Model APIs* [[Paper](https://arxiv.org/abs/2502.07776)]
  
---

## 2. Speculative Decoding
- **[IEEE S&P 2027]** *Secure Speculative Decoding for Large Language Models* [[Paper](https://arxiv.org/abs/2610.08678v2)]

---

## Contributing
Contributions are welcome! If you have a relevant paper, defense mechanism, or CVE in LLM serving systems, please feel free to open a **Pull Request** or **Issue** following the tag format above.
