# Medical Domain Adaptation of Gemma-2B via QLoRA

## Project Overview
This research project demonstrates the fine-tuning of Google's **Gemma-2B-IT** large language model for specialized medical question-answering. By utilizing **Quantized Low-Rank Adaptation (QLoRA)**, the model was adapted from a general-purpose conversational agent into a domain-specific assistant capable of providing more clinical and concise responses.

## Technical Specifications
* **Base Model:** [Gemma-2B-IT](https://huggingface.co/google/gemma-2b-it)
* **Dataset:** [MedQuad-MedicalQnADataset](https://huggingface.co/datasets/keivalya/MedQuad-MedicalQnADataset) (1,000 instruction-response pairs)
* **Quantization:** 4-bit NormalFloat (NF4) via `bitsandbytes`
* **Fine-Tuning Method:** LoRA (Rank=8, Alpha=32, Dropout=0.05)
* **Precision:** BFloat16/Float16 Mixed Precision
* **Hardware Compatibility:** Optimized for Tesla T4 (16GB VRAM) and Ampere architectures.

## Training Performance
The model underwent supervised fine-tuning (SFT) for **500 steps**. The training process showed consistent convergence, with the loss decreasing from an initial **2.93** to a final **2.35**.

> **Note:** Raw training logs are available in `training_loss_log.csv`.

## Qualitative Results: Baseline vs. Fine-Tuned
A comparative analysis shows a distinct shift in linguistic style. While the baseline model provides generalized, consumer-friendly lists, the fine-tuned model adopts a more technical, clinical summary format.

| Feature | Baseline (Pre-trained) | Fine-Tuned (LoRA Adapted) |
| :--- | :--- | :--- |
| **Response Tone** | Conversational & Broad | Clinical & Concise |
| **Structuring** | Bulleted lists for general readability | Narrative summaries with medical terminology |
| **Accuracy** | High general health literacy | Improved focus on clinical risk factors |

### Comparative Inference Example
**Prompt:** *What are the primary risk factors for heart disease?*

**Baseline Output:**
> "Sure, here are the primary risk factors for heart disease: 1. Age... 2. Family history... 3. High blood pressure..."

**Fine-Tuned Output:**
> "Heart disease is a major cause of death worldwide. The principal risk factors include high blood pressure, obesity (especially in men), unhealthy diet and lack of physical activity... cardia arrhythmias such as atrial fibrillation..."

## Repository Structure
* `adapters/`: LoRA weight deltas and configuration files.
* `lora.py`: The full pipeline for quantization, training, and inference.
* `training_loss_log.csv`: Step-by-step loss metrics.
* `model_comparison_results.md`: Expanded qualitative comparison data.

## How to Use
1. Clone the repository.
2. Ensure `transformers`, `peft`, and `bitsandbytes` are installed.
3. Use `PeftModel.from_pretrained(base_model, "adapters/")` to load the medical weights.
