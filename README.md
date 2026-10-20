# CoMerge

**Conflict-Driven Preference Optimization for Multi-Task Model Merging**

Accepted to the **EMNLP 2026 Main Conference**.

Mingjie Zheng, Zihao Chen, Wenqing Chen, Weile Yuan, Zhixuan Chu,
Jianxing Yu, and Zibin Zheng

**[Paper (PDF)](assets/CoMerge_paper.pdf)** |
**[Citation](#citation)**

## Overview

CoMerge learns to merge task-specific experts through **self-supervised
preference optimization**. It pairs expert outputs (**chosen**) with naive
Task Arithmetic outputs (**rejected**) and optimizes only **tensor-wise merging
coefficients**, keeping the base model and preprocessed task vectors frozen.

## Main results

**Llama-3.1-8B-Instruct**, five task domains and 12 datasets under the adapted
MergeBench protocol. Scores are normalized to expert performance and
macro-averaged across the five domains.

| Method | Average normalized performance |
| --- | ---: |
| Task Arithmetic | 0.9538 |
| AdaMerging (Gen.) | 0.9788 |
| **CoMerge** | **0.9968** |
| Full-DPO (reference) | 0.9983 |

CoMerge optimizes **1,445 scalar coefficients** and uses **60.1% fewer total
GPU-minutes to peak** than Full-DPO (38.3 vs. 95.9, summed across GPUs).
This comparison uses the same preconstructed preference dataset and excludes
preference generation and offline evaluation. See the paper for full details.

## Release status

**Code is not yet released.** Code, evaluation scripts, configurations, and
environment specifications will be released upon publication.

## Citation

Provisional citation:

```bibtex
@inproceedings{zheng2026comerge,
  title     = {CoMerge: Conflict-Driven Preference Optimization for Multi-Task Model Merging},
  author    = {Zheng, Mingjie and Chen, Zihao and Chen, Wenqing and Yuan, Weile and
               Chu, Zhixuan and Yu, Jianxing and Zheng, Zibin},
  booktitle = {Proceedings of the 2026 Conference on Empirical Methods in Natural Language Processing},
  year      = {2026},
  note      = {Accepted to the Main Conference}
}
```

## Contact

Mingjie Zheng: <zhengmingjie@myhexin.com>
