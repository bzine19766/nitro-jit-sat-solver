# nitro-jit-sat-solver
Hardware-Aligned Bit-Parallel Conflict Evaluation for High-Throughput Stochastic Local Search

<!--
======================================================================
NITRO-JIT: Hardware-Aligned Bit-Parallel SAT Solver
======================================================================
-->

<div align="center">

# 🚀 Nitro-JIT

## Hardware-Aligned Bit-Parallel Conflict Evaluation for High-Throughput Stochastic Local Search

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![Numba](https://img.shields.io/badge/Numba-0.57.0+-green.svg)](https://numba.pydata.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![Colab](https://img.shields.io/badge/Colab-Open-F9AB00.svg)](https://colab.research.google.com/)
[![Paper](https://img.shields.io/badge/Paper-IJAISC-red)](https://www.inderscience.com/ijait)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.XXXXXX.svg)](https://doi.org/10.5281/zenodo.XXXXXX)

**Nitro-JIT** is a high-performance stochastic local search (SLS) SAT solver that leverages hardware-aligned bit-parallel conflict evaluation. By reformulating 3-SAT as a geometric placement problem on a K×3 grid, the solver achieves up to **11.47× median speedup** over scalar implementations through word-level bit-parallel encoding and POPCNT acceleration.

[**📄 Read the Paper**](#) • [**🚀 Quick Start**](#quick-start) • [**📊 Results**](#key-results) • [**📖 Documentation**](#documentation) • [**🤝 Contribute**](#contributing)

</div>

---

## 📋 Table of Contents

- [Features](#-features)
- [Key Results](#-key-results)
- [Quick Start](#-quick-start)
- [Installation](#-installation)
- [Usage](#-usage)
- [Benchmarks](#-benchmarks)
- [Memory Scaling](#-memory-scaling)
- [Repository Structure](#-repository-structure)
- [Citation](#-citation)
- [License](#-license)
- [Acknowledgments](#-acknowledgments)

---

## 🚀 Features

| Feature | Description |
|---------|-------------|
| **Geometric Reformulation** | Transforms 3-SAT clauses into a K×3 grid placement problem |
| **Bit-Parallel Evaluation** | Uses 64-bit word operations for O(k/64) conflict detection |
| **Hardware Acceleration** | Leverages POPCNT instructions for population counting |
| **JIT Compilation** | Uses Numba for native machine code generation |
| **Identical Trajectories** | Controlled ablation confirms speedup is from evaluation kernel only |
| **Memory Scaling Analysis** | Cache-resident regimes identified for different instance sizes |
| **Ready for Colab** | Runs seamlessly on Google Colab with no setup |

---

## 📊 Key Results

### Performance Comparison

| Metric | Scalar | Bit-Parallel | Speedup |
|--------|--------|--------------|---------|
| **Mean Time (s)** | 6.701990 | 0.602390 | **11.04×** |
| **Median Time (s)** | 2.114264 | 0.187284 | **11.22×** |
| **Mean Total Flips** | 3,436.41 | 3,436.41 | 1.00× |
| **Mean Attempts** | 67.85 | 67.85 | 1.00× |
| **Success Rate** | 99.7% | 99.7% | — |

### Pure Evaluation Microbenchmark

| Metric | Scalar | Bit-Parallel | Speedup |
|--------|--------|--------------|---------|
| **Time per Evaluation (ns)** | 107.95 | 4.09 | **26.39×** |

### Statistical Significance

| Metric | Value |
|--------|-------|
| **Paired Cohen's dz** | 0.5046 |
| **Wilcoxon p-value** | 1.03×10⁻¹⁶⁴ |
| **Bootstrap 95% CI (mean diff)** | [5.38, 6.88] s |

---

## ⚡ Quick Start

### Option 1: Run on Google Colab (Recommended)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/your-username/nitro-jit-sat-solver/blob/main/notebooks/sourcecode.ipynb)

**Click the badge above** to open the notebook in Google Colab. All dependencies are pre-installed, and you can run the entire solver with one click.

### Option 2: Run Locally

```bash
# Clone the repository
git clone https://github.com/bouneb-zine-abidine/nitro-jit-sat-solver.git
cd nitro-jit-sat-solver

# Install dependencies
pip install -r requirements.txt

# Run the complete notebook
jupyter notebook notebooks/sourcecode.ipynb



@article{bouneb2026hardware,
  title={Hardware-Aligned Bit-Parallel Conflict Evaluation for High-Throughput Stochastic Local Search},
  author={Bouneb, Zine El Abidine},
  journal={International Journal of Artificial Intelligence and Soft Computing},
  year={2026},
  publisher={Inderscience Publishers}
}
