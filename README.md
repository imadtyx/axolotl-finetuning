# Alpaca Zero-Shot Finetuning with Axolotl

This repository contains the setup for finetuning Llama 3.1-8B on the Alpaca dataset using axolotl.


Where `{output}` is the target label ("True" or "False").

## Setup Instructions

### 1. Clone Axolotl Repository
```bash
git clone git@github.com:axolotl-ai-cloud/axolotl.git
cd axolotl
```

### 2. Create Virtual Environment
```bash
uv venv
source .venv/bin/activate
```

### 3. Install Dependencies
```bash
uv pip install setuptools
uv pip install torch==2.4.1+cu124 --index-url https://download.pytorch.org/whl/cu124
uv pip install --no-build-isolation -e '.[flash-attn,deepspeed]'
uv pip install huggingface-cli hf_transfer
```

### 4. Set GPU Configuration
```bash
export CUDA_VISIBLE_DEVICES="0,1,2,3"
```

### 5. Run Training
```bash
cd /path/to/your/finetuning/directory
axolotl train config/yml
```

## Project Structure

```
finetuning/
├── data/
│   ├── train_alpaca.json      # Training dataset
│   └── test_alpaca.json       # Test dataset
├── config/                    # Configuration files
├── outputs/                   # Training outputs (gitignored)
└── README.md                  # This file
```

