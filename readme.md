# Lightweight LLM Benchmark

## Overview
This project benchmarks and compares multiple lightweight, open-source
large language models (LLMs) under identical conditions to evaluate their
instruction-following ability, output quality, and suitability for
practical GenAI applications.

The goal is to understand real-world trade-offs between conversational
models and instruction-tuned models when operating under limited
compute constraints.

---

## Models Evaluated
The following publicly available models were evaluated:

| Model | Type | Notes |
|-----|-----|------|
| facebook/blenderbot-400M-distill | Dialogue model | Optimized for conversational flow |
| google/flan-t5-small | Instruction-tuned | Extremely lightweight, limited capacity |
| google/flan-t5-base | Instruction-tuned | Improved instruction awareness |

---

## Experimental Setup
- Identical prompt set for all models
- Greedy decoding (no sampling)
- Fixed maximum output length
- CPU-based inference
- No fine-tuning or prompt optimization applied

This setup ensures a fair baseline comparison across models.

---

## Evaluation Prompts
The models were tested on a small, fixed set of prompts designed to assess:
- Concept explanation
- Instruction following
- Structured response generation

Examples:
- *Explain overfitting in simple terms.*
- *Write a polite email declining a meeting.*
- *What are the pros and cons of electric cars?*

---

## Key Findings
- Dialogue-optimized models generate fluent responses but frequently ignore task instructions.
- Instruction-tuned models attempt task completion but struggle with factual accuracy at small scales.
- Extremely lightweight models trade reliability for efficiency and are not suitable for complex reasoning tasks.

---

## Limitations
- No automatic metrics (BLEU/ROUGE) applied in this version
- Small prompt set
- No decoding strategy comparison
- No fine-tuning or retrieval augmentation

These limitations are intentional to highlight baseline model behavior.

---

## Project Structure
```
lightweight-llm-benchmark/
├── lightweight_llm_benchmark.ipynb
├── README.md
```

---

## How to Run
1. Install dependencies:
   ```bash
   pip install transformers torch
   ```
2. Open the notebook:
   ```bash
   jupyter notebook lightweight_llm_benchmark.ipynb
   ```
3. Run all cells sequentially.

---



     

## Why This Project Matters
Model selection is a critical step in GenAI system design.
This project demonstrates a structured, reproducible approach
to evaluating LLMs rather than relying on anecdotal results.
