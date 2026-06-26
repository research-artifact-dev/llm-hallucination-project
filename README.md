# HECTOR: A Framework for Detecting and Mitigating Context-Conflicting Hallucinations in LLM-Based Java-C++ Code Translation

## Overview

This repository contains the research artifact accompanying the paper **"HECTOR: A Framework for Detecting and Mitigating Context-Conflicting Hallucinations in LLM-Based Java-C++ Code Translation."**

The artifact includes the experimental dataset, intermediate pipeline outputs, final evaluation results, and analysis notebook required to reproduce the experiments presented in the paper.

---

## Repository Structure

```text
.
├── README.md
├── hallucination_analysis.ipynb      # Main notebook for analysis and evaluation
├── final_dataset.csv                 # Experimental dataset
├── pipeline_results_java.csv         # Java generation results
├── pipeline_results_cpp.csv          # C++ translation results
├── pipeline_results_complete.csv     # Complete pipeline outputs and evaluation
```

---

## System Requirements

* Python 3.10+
* Jupyter Notebook
* CUDA-enabled GPU (recommended for fine-tuning and inference)

---

## Installation

Clone the repository:

```bash
git clone https://github.com/research-artifact-dev/llm-hallucination-project.git

cd llm-hallucination-project
```

### Install Core Dependencies

```bash
pip install pandas numpy scipy scikit-learn matplotlib notebook jupyter tqdm
```

---

## LLM Fine-Tuning Dependencies (QLoRA)

The fine-tuning pipeline is implemented using the Hugging Face ecosystem together with QLoRA.

Install the required packages:

```bash
pip install torch transformers datasets accelerate peft bitsandbytes trl sentencepiece huggingface_hub
```

These libraries are used for:

| Library         | Purpose                           |
| --------------- | --------------------------------- |
| Transformers    | Loading and fine-tuning LLMs      |
| Datasets        | Dataset loading and preprocessing |
| PEFT            | LoRA fine-tuning                  |
| BitsAndBytes    | 4-bit QLoRA quantization          |
| Accelerate      | Optimized training                |
| TRL             | Supervised fine-tuning            |
| HuggingFace Hub | Model management                  |

---

## Code Analysis and Evaluation Dependencies

The hallucination detection framework relies on syntax-aware program analysis and code similarity evaluation.

Install:

```bash
pip install tree-sitter tree-sitter-languages codebleu
```

These libraries provide:

* **Tree-sitter** for parsing Java and C++ Abstract Syntax Trees (ASTs)
* **tree-sitter-languages** for language grammars
* **CodeBLEU** for syntax-aware code similarity evaluation

---

## Additional Dependencies

If required, install:

```bash
pip install ipykernel regex nltk
```


## Repository Files

| File                            | Description                                                    |
| ------------------------------- | -------------------------------------------------------------- |
| `final_dataset.csv`             | Experimental dataset used throughout the evaluation            |
| `pipeline_results_java.csv`     | Generated Java code and intermediate outputs                   |
| `pipeline_results_cpp.csv`      | Generated C++ code and translation outputs                     |
| `pipeline_results_complete.csv` | Final outputs of the complete hallucination detection pipeline |
| `hallucination_analysis.ipynb`  | Notebook containing the complete experimental analysis         |

---

## Reproducing the Experiments

### Step 1

Clone the repository.

### Step 2

Install all required dependencies.

### Step 3

Launch Jupyter Notebook.

```bash
jupyter notebook
```

### Step 4

Open

```text
hallucination_analysis.ipynb
```

### Step 5

Execute all notebook cells sequentially.

The notebook reproduces:

* Dataset preprocessing
* Java code analysis
* C++ translation analysis
* AST extraction
* Feature extraction
* Hallucination analysis
* Evaluation
* Final pipeline results

---

## Hardware Requirements

The experiments were conducted using:

* NVIDIA GPU (CUDA supported)
* Python 3.10+
* QLoRA-based fine-tuning

Although fine-tuning is GPU-intensive, the provided notebook and datasets can be analyzed independently once the generated outputs are available.

