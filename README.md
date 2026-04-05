# 🚀 CodeX: Syntax-Aware Logic Engine

CodeX is a specialized Large Language Model (LLM) fine-tuned for high-fidelity code generation and pseudocode-to-code translation. Built on the **Llama-3.2-1B** architecture, this model utilizes advanced quantization and Low-Rank Adaptation (LoRA) to provide a lightweight yet powerful engine capable of maintaining strict syntax validity.

---

## 📖 Introduction

In the transition from logic to implementation, developers often face syntax hurdles. **CodeX** acts as a bridge, transforming high-level logic and pseudocode into executable snippets. By leveraging the latest advancements in Parameter-Efficient Fine-Tuning (PEFT), CodeX achieves high performance in specialized coding tasks while remaining small enough to run on consumer-grade hardware.

The model is specifically patched to handle long-range dependencies and uses a structured instruction-response format to ensure the output remains focused on technical accuracy.

---

## 🛠️ Technology Stack

### **Core Model & Fine-Tuning**
* **Base Model:** Llama-3.2-1B (via Unsloth)
* **Architecture:** Transformer-based Decoupled Architecture with RoPE (Rotary Positional Embedding) Scaling.
* **Fine-Tuning:** PEFT using **LoRA (Low-Rank Adaptation)** to update specific weight matrices, reducing trainable parameters significantly.
* **Quantization:** 4-bit NormalFloat (NF4) via `bitsandbytes` to enable training on 16GB VRAM GPUs (like NVIDIA Tesla T4).

### **Frameworks & Libraries**
* **Unsloth:** Utilized for 2x faster training and 70% less memory consumption.
* **PyTorch:** The primary deep learning framework for tensor computations.
* **Hugging Face (Transformers & TRL):** Used for the `SFTTrainer` (Supervised Fine-Tuning) and seamless model versioning.
* **Xformers:** Integrated for optimized memory-efficient attention mechanisms.

---

## ⚙️ Model Specifications

| Feature | Configuration |
| :--- | :--- |
| **Max Sequence Length** | 2048 Tokens |
| **Quantization** | 4-bit (NF4) |
| **LoRA Rank (r)** | 16 |
| **LoRA Alpha** | 16 |
| **Optimizer** | 8-bit AdamW |
| **Learning Rate** | 2e-4 |
| **Weight Decay** | 0.01 |

---

## 📊 Evaluation Metrics

The model is evaluated against two primary benchmarks to ensure it is "Developer-Ready":

1.  **BLEU-4 Score:** Measures the linguistic overlap between the generated code and reference human-written solutions.
2.  **Syntax Validity Rate:** A custom validation step that checks if the generated code snippets are syntactically correct and can be parsed by an interpreter.

---

## 📦 Deployment & Export

CodeX is designed for versatility. The project includes a pipeline to export the fine-tuned weights into:
* **Hugging Face Safetensors:** For cloud-based inference.
* **GGUF Format (Q4_K_M):** Optimized for high-speed local execution on **llama.cpp**, allowing you to use CodeX on standard CPUs or mobile devices.

---

## 👨‍💻 Developed By
**Lashan Chanaka**
*Undergraduate at Rajarata University of Sri Lanka*
