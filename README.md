# Teaching an LLM to Reason: Letter Counting with GRPO

This project teaches a Large Language Model (LLM) to use step-by-step reasoning to answer the question: **"How many X's are there in the word Y?"**

## Overview

Counting letters in a word is surprisingly complex for LLMs. This project uses **GRPO (Group Relative Policy Optimization)** reinforcement learning to fine-tune a model to break down words into individual letters and count them systematically.

### Example

**Question:** How many of the letter "o" are there in the word "room"?

**Response:**
```
<reasoning>
1. r - 0 o's so far
2. o - 1 o's so far
3. o - 2 o's so far
4. m - 2 o's so far
</reasoning>
<answer>
2
</answer>
```

## Project Structure

```
├── README.md
├── rubric.md                                              # Project evaluation criteria
└── submission/
    └── tnmayer_gen_ai_fundamentals_project_submission.ipynb  # Main notebook
```

## Key Components

1. **Model Setup** - Configure LoRA (Low-Rank Adaptation) for parameter-efficient fine-tuning using `unsloth` and `vllm`
2. **Baseline Prompting** - Establish baseline with Chain-of-Thought (CoT) one-shot prompting
3. **Reward Design** - Create reward functions that guide the model toward correct reasoning and answers
4. **Training** - Fine-tune using GRPO with monitored progress
5. **Evaluation** - Compare baseline vs. fine-tuned model outputs

## Technical Details

- **Base Model:** Qwen 2.5 3B Instruct (4-bit quantized)
- **Fine-tuning Method:** LoRA with GRPO
- **Key Hyperparameters:**
  - Learning rate: 5e-6
  - Beta: 0.04
  - LoRA rank: 8, 16, 32, 64, or 128

## Requirements

- Python 3.x
- `unsloth`
- `vllm`
- ~15GB VRAM

## Usage

Run the Jupyter notebook [`tnmayer_gen_ai_fundamentals_project_submission.ipynb`](submission/tnmayer_gen_ai_fundamentals_project_submission.ipynb) to:

1. Set up the environment and load the model
2. Create the letter-counting dataset
3. Define and validate reward functions
4. Train the model with GRPO
5. Compare results before and after fine-tuning

## Acknowledgments

This project is part of the Udacity GenAI Fundamentals course.
