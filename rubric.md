# Project Rubric

Use this project rubric to understand and assess the project criteria.

---

## 1. Model Setup

| Criteria | Submission Requirements |
|----------|------------------------|
| **Configure the LoRA model with valid parameters.** | The submission includes code that applies LoRA (e.g., via PEFT) to the chosen base LLM. |

### LoRA Hyperparameters Requirements

LoRA hyperparameters must be explicitly set and valid:

- **`lora_rank`**: one of `8`, `16`, `32`, `64`, `128`
- **`target_modules`** includes:
  - `q_proj`, `k_proj`, `v_proj`, `o_proj` **and/or**
  - `gate_proj`, `up_proj`, `down_proj`

> ✅ The configuration must be used to successfully instantiate a trainable model **without runtime errors** prior to training.

---

## 2. Baseline Prompting

| Criteria | Submission Requirements |
|----------|------------------------|
| **Establish a baseline solution using prompting only (CoT with one example).** | The submission demonstrates a single-example Chain-of-Thought (CoT) prompt attempting the letter-counting task without additional fine-tuning. |

### Requirements

- At least **one concrete input–output example** (one-shot) is shown
- The model's **reasoning (step-by-step)** is visible in the output

---

## 3. Reward Design & Validation

| Criteria | Submission Requirements |
|----------|------------------------|
| **Implement and validate reward functions for the task.** | The submission defines rewards that are positive for correct/desired behavior and negative for incorrect/undesired behavior. |

### Required Reward Aspects

Rewards must cover, at minimum, the following aspects:

- ✅ Numbering
- ✅ Spelling
- ✅ Counting
- ✅ Formatting
- ✅ Correctness

> 📋 The validation at the end of the cells must demonstrate that the reward(s) have a **higher value for a correct sample** and a **lower value for an incorrect sample**.

---

## 4. Training & Monitoring

| Criteria | Submission Requirements |
|----------|------------------------|
| **Execute a longer training session and monitor progress.** | A longer training run is executed (more steps/epochs than the quick pass). |

### Requirements

- The submission reports **mean correctness reward over time** (table, log, or plot)
- The mean correctness reward shows an **increasing trend** over training

> ⚠️ If the trend is not increasing, the learner must explain anomalies with evidence (e.g., unstable runs, GPU limits) and attempt a remedial configuration.

---

## 5. Final Comparison

| Criteria | Submission Requirements |
|----------|------------------------|
| **Demonstrate the baseline model and the fine-tuned model on the letter-counting task.** | The submission shows both the fine-tuned and the original (pretrained) model on at least one example from the project dataset. |

---

## Summary Checklist

- [ ] LoRA configuration with valid hyperparameters
- [ ] Baseline CoT prompting with one-shot example
- [ ] Reward functions covering all required aspects
- [ ] Reward validation showing correct vs. incorrect sample scores
- [ ] Extended training run with progress monitoring
- [ ] Comparison of baseline vs. fine-tuned model outputs
