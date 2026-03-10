# Offline First-Aid Advice Assistant
_Small Language Model Build Day (AWS × AGI House, NYC), 🥈 2nd Place_

An **on-device first-aid AI assistant** designed to provide immediate emergency guidance without internet connectivity.

_*The overall explanation of the project can be found_ [here](https://docs.google.com/presentation/d/1zS5iHfKa873uBwA6A-LgpXBN-2WAJiXxrHC5Ox_uIa4/edit?slide=id.p#slide=id.p)! 
<img width="750" height="480" alt="Image" src="https://github.com/user-attachments/assets/6fcdb71f-7265-4042-bb72-3b183171db95" />

---
## Motivation
Most AI assistants rely on cloud-based LLMs, which require stable internet access.
However, emergency situations (e.g., mountains, disasters, remote areas) often occur in environments where connectivity cannot be guaranteed.

To address this limitation, we asked a key question:

> **"When does a Small Language Model (SLM) make more sense than a large cloud LLM?"**

We identified **offline first-aid guidance** as a practical scenario where:
* low latency
* edge deployment
* offline inference

are more important than large model capacity.

---
## Approach

We built an on-device first-aid assistant optimized for fast and reliable emergency guidance.

**Model**: `Qwen3-1.7B`

**Dataset**: [FirstAidInstructions](https://huggingface.co/datasets/lextale/FirstAidInstructionsDataset) Dataset (HuggingFace)

**Training Strategy**

* LoRA-based parameter-efficient fine-tuning
* structured prompts for **concise, actionable first-aid instructions**

Training was performed on **AWS Trainium** infrastructure.

___
## Results
| Metric  | Base   | Fine-tuned              |
| ------- | ------ | ----------------------- |
| ROUGE-L | 0.1345 | **0.1742 (+29%)**       |
| Latency | 29.6s  | **1.72s (~25× faster)** |

The optimized SLM achieved higher response quality while dramatically reducing latency, enabling real-time offline assistance. 

___
## Key Insight
For edge AI scenarios where latency, cost, and connectivity matter,
a well-optimized Small Language Model can outperform cloud-based LLM systems in practical usability.
