# Medical QA — LoRA Fine-Tune.

Fine-tuning Qwen2.5-1.5B-Instruct on MedMCQA (medical exam Q&A) using QLoRA on a free Colab T4 GPU.

## Status.
🚧 In progress

## Method.
- Base model: Qwen2.5-1.5B-Instruct
- Dataset: MedMCQA (openlifescienceai/medmcqa), 3000-example training subset
- Fine-tuning: QLoRA (4-bit, LoRA rank=16) via PEFT + TRL
- Trained 1 epoch, final training loss ~1.72

## Results (100 held-out questions)
- Fine-tuned model accuracy: **48%**
- Base model accuracy: 9% raw, but 86/100 of its answers didn't even follow the required answer format — so this isn't a fair comparison of medical knowledge, it mainly shows fine-tuning taught the model to answer in the expected structured format reliably, in addition to improving correctness.

## Next steps
- [ ] Retrain and immediately save adapter to Hugging Face Hub (avoid losing it to a runtime disconnect)
- [ ] Deploy a demo via Hugging Face Spaces (Gradio)
- [ ] Expand evaluation set
