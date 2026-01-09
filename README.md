# SG-Filter

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![CIKM 2025](https://img.shields.io/badge/CIKM-2025-blue)](#citation)

**SG-Filter** is an efficient retrieval-augmented filtering framework designed for **large-scale similar text retrieval**. It implements the **Hierarchical Summarized-Semantic Index (HSSI)** and **Adaptive Filtering** framework proposed in our **CIKM 2025** paper, achieving high recall with ultra-low latency.

The system is now **serving ByteDance VikingDB** in production scenarios.

---

## ✨ Core Features

* **High-Performance Retrieval**  
  Employs an adaptive multi-path recall mechanism to significantly improve retrieval efficiency while preserving accuracy.

* **Ultra-Low Latency**  
  Achieves **6.13 ms** end-to-end latency in single-path recall settings, meeting industrial-scale online service requirements.

* **Hierarchical Summarized-Semantic Index**  
  Introduces a multi-level semantic summarization structure that enables early-stage filtering and progressive refinement.

* **Extensible Architecture**  
  Supports pluggable filtering strategies and multiple embedding models (e.g., **BGE**, **M3E**), making it easy to adapt to diverse retrieval workloads.

* **Visual Analysis Tools**  
  Built-in utilities for comparing **latency–recall trade-offs**, with visualization support for ablation and strategy analysis.

* **Open Source & Production-Ready**  
  Released under the **MIT License**, suitable for both academic research and commercial deployment.

---

## 🚀 Quick Start

### Prerequisites

* Python **3.8+**
* PyTorch **1.12+**
* Hugging Face `transformers`

### Installation

```bash
# Install the stable version from PyPI
pip install sg-filter

# Or install the latest version from source
git clone https://github.com/Hao-Yu-la/SG-Filter
cd SG-Filter
pip install -e .
```

---

## 🧠 Method Overview

SG-Filter is designed around the observation that **full-vector similarity search is often unnecessary** for most candidates in large-scale retrieval systems.

The framework consists of:

1. **Hierarchical Summarized-Semantic Index (HSSI)**
   Documents are represented at multiple semantic granularities, enabling coarse-to-fine filtering.

2. **Adaptive Filtering Strategy**
   Query-dependent routing dynamically selects filtering paths based on semantic confidence.

3. **Multi-Path Recall (Optional)**
   When higher recall is required, multiple semantic paths are activated with controlled overhead.

This design allows SG-Filter to significantly reduce unnecessary similarity computations while maintaining strong recall guarantees.

---

## 📊 Performance Highlights

* **Single-path latency**: **6.13 ms**
* **Recall**: Comparable to full dense retrieval under the same embedding model
* **Scalability**: Designed for million- to billion-scale candidate pools

(See the built-in visualization scripts for detailed latency–recall curves.)

---

## 📄 Citation

If you find SG-Filter useful in your research or production systems, please consider citing our paper:

> Ye J, Liu J, Zhang H, et al. **SG-Filter: Enhancing Similar Text Retrieval via Hierarchical Summarized-Semantic Index and Adaptive Filtering**.  
> In *Proceedings of the 34th ACM International Conference on Information and Knowledge Management (CIKM)*, 2025, pp. 3866–3876.

### BibTeX

```bibtex
@inproceedings{ye2025sgfilter,
  title     = {SG-Filter: Enhancing Similar Text Retrieval via Hierarchical Summarized-Semantic Index and Adaptive Filtering},
  author    = {Ye, Jiancai and Liu, Jian and Zhang, Hao and others},
  booktitle = {Proceedings of the 34th ACM International Conference on Information and Knowledge Management},
  year      = {2025},
  pages     = {3866--3876}
}
```

---

## 📜 License

This project is licensed under the **MIT License**. See the `LICENSE` file for details.

---

## 🤝 Acknowledgements

This project is developed for large-scale industrial retrieval systems and will been validated in real-world deployments within **ByteDance VikingDB**.

Contributions and discussions are welcome via Issues and Pull Requests.



