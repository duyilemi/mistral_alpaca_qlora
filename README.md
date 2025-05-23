# Mistral-7B-Alpaca QLoRA Fine-Tuning (Colab Version)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1ERT9SK0SdqKHQF7fD7lWR894SDZMMiu5?usp=sharing)
[![Hugging Face Model](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Model%20Hub-blue)](https://huggingface.co/duyilemi/mistral-alpaca-qlora)

## Overview
Fine-tuned Mistral-7B on Alpaca dataset using QLoRA **on free Colab T4 GPU** in ~1 hour. Achieved evaluation loss of 0.9073 (perplexity 2.48) on 5% dataset subset.

**Key Highlights**:
- 🆓 Runs on free-tier Colab (T4 GPU)
- ⏱️ ~1 hour training time
- 📚 Full implementation in single notebook
- 📊 Built-in sample outputs
- 💾 Google Drive integration for model saving

## Results
**Metrics**:
- Evaluation Loss: 0.9073
- Perplexity: 2.48

**Sample Outputs from Code**:
```python
# From notebook's inference section
Prompt: "Explain quantum entanglement in simple terms."
Generated: "Quantum entanglement is a phenomenon in which two or more particles are linked in such a way that the quantum state of each particle cannot be described independently of the others, even when the particles are separated by a large distance." 

Prompt: "How to make a perfect omelette?"
Generated: "To make a perfect omelette, follow these steps: 1. Crack the eggs into a bowl and whisk them until they are well combined. 2. Heat a non-stick pan over medium heat" 
```

## How to Use

### Colab Setup
1. Click the [Open in Colab](https://colab.research.google.com/github/yourusername/mistral-alpaca-qlora/blob/main/mistral_finetuning.ipynb) button
2. **Runtime → Change runtime type → T4 GPU**
3. Run all cells sequentially

### Critical Steps
1. **Install Dependencies** - First cell installs required packages
2. **HF Login** - Cell 2 for Hugging Face authentication
3. **Drive Mount** - Cell 3 connects Google Drive for model storage
4. **Training** - Runs in ~60 mins on T4 GPU

## Repository Contents
```
├── mistral_finetuning.ipynb    
│   ├── Dataset processing
│   ├── QLoRA config
│   ├── Training loop
│   ├── Evaluation metrics
│   └── Sample outputs
└── README.md                   
```


## Hardware Requirements
- **GPU**: Google Colab T4 (free tier)
- **RAM**: ~15GB
- **Storage**: 2GB notebook + ~8GB cached models

## Optimization Tips
The current configuration achieves:
- 2x batch size with gradient accumulation
- 4-bit quantization for memory efficiency
- LoRA adapters (8M trainable params)
- FP16 mixed precision training

