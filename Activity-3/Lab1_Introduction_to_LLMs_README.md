# Lab 1 - Introduction to Large Language Models (LLMs)

**Student:** Jatin Kolhapure  
**Roll Number:** SCFP125014  
**Course:** MCA  
**Repository:** `GenAi_LLM_Engineering_SCFP125014`

## Overview

This lab explores the practical foundations of Large Language Models (LLMs), including model discovery, tokenization, GPU-based inference, hardware and memory requirements, local model execution, API-based inference, temperature settings, conversation history, and chatbot customization.

The activities were completed using a combination of a local Windows environment, Google Colab, Ollama, Hugging Face, and the Groq API.

## Activities Covered

| Activity | Topic | Key Work |
|---|---|---|
| 1 | Explore LLMs on Hugging Face | Compared small, medium, and larger language models. |
| 2 | Tokenization | Examined tokens, token IDs, punctuation, and subword splitting. |
| 3 | Run an LLM using Google Colab GPU | Tested text generation on an NVIDIA Tesla T4 GPU and measured generation time and GPU memory. |
| 4 | Can My Computer Run an LLM? | Inspected local hardware and estimated model memory requirements at different precisions. |
| 5 | Run an LLM Locally Using Ollama | Installed Ollama and tested local model inference. |
| 6 | Use an LLM Through an API | Called a hosted model through the Groq API using Python. |
| 7 | Compare Local, Colab, and API Inference | Compared hardware, memory, privacy, connectivity, cost, and scalability. |
| 8 | Temperature Experiment | Compared generated text at temperatures 0.1, 0.7, and 1.0. |
| 9 | Build a Mini Chatbot | Implemented a chatbot loop that retains conversation history using Ollama. |
| 10 | Customize the Chatbot | Used a system message to turn the chatbot into a Java programming tutor. |

## Experimental Results

### 1. Model Exploration and Tokenization

- Explored DistilGPT-2, GPT-2 Medium, and Llama 3.2 1B using Hugging Face model information.
- Tokenized a sample sentence and observed that words can be represented by multiple tokens.
- Examined token IDs and the role of tokenization in language-model processing.

### 2. Google Colab GPU Inference

The Colab experiment used DistilGPT-2 with an NVIDIA Tesla T4 GPU.

| Measurement | Observed Result |
|---|---:|
| GPU reported | NVIDIA Tesla T4 |
| Reported GPU memory | 14.56 GB |
| Peak GPU memory with 20 new tokens | 324.52 MB |
| Peak GPU memory with 50 new tokens | 325.57 MB |
| Peak GPU memory with 100 new tokens | 327.33 MB |
| Generation time for 20 new tokens | 0.158 seconds |
| Generation time for 50 new tokens | 0.395 seconds |
| Generation time for 100 new tokens | 0.804 seconds |

These measurements are from the recorded Colab experiment. Results may vary with runtime conditions and hardware allocation.

### 3. Local Hardware and Memory Estimation

The local Windows environment reported approximately 15.68 GB of system RAM, and PyTorch did not detect a CUDA-capable GPU.

Theoretical weight-memory estimates were calculated for 4B FP16, 4B INT4, and 7B INT4 models. These estimates cover model weights only; runtime overhead, activations, and other memory requirements also matter.

### 4. Local and API Inference

- **Local inference:** Used Ollama with `qwen2.5:0.5b` to test a locally hosted model.
- **API inference:** Successfully generated text using the Groq API and the model `openai/gpt-oss-20b`.
- **Comparison:** Examined the differences between local execution, cloud GPU execution, and remote API inference.

API access depends on the provider's current model availability, account limits, and pricing.

### 5. Temperature Experiment

The same prompt was tested at temperatures 0.1, 0.7, and 1.0.

- Temperature 0.1 produced relatively consistent responses about C++.
- Temperature 0.7 produced varied responses, including very short outputs.
- Temperature 1.0 produced more diverse references, including Haskell, Ruby, and Python, although some responses were less coherent.

The experiment illustrated how temperature affects sampled output diversity and predictability.

### 6. Chatbot and Role Customization

The Ollama chatbot retained a system message, user prompts, and assistant responses in a conversation-history list. It answered follow-up questions about information introduced earlier in the conversation.

The chatbot was then customized as a Java programming tutor. It explained Java classes using a `Student` class example and discussed inheritance, demonstrating how system instructions can guide the same model toward a specialized role.

## Technologies and Tools

- Python
- Jupyter Notebook and VS Code
- PyTorch
- Hugging Face Transformers and Hub
- Google Colab
- Ollama
- Groq API
- Git and GitHub

## Prerequisites

- Python and Jupyter Notebook
- Required Python packages installed in the selected environment
- Internet connectivity for downloading models and using hosted APIs
- Ollama installed and running for the local chatbot activities
- A valid Groq API key for the API activity

GPU availability is optional for the local setup; performance depends on available hardware.

## How to Run

1. Open `Lab1_Introduction_to_LLMs.ipynb` in Jupyter Notebook or VS Code.
2. Select the appropriate Python environment and install the required dependencies.
3. Run the notebook cells in order, following any activity-specific instructions.
4. Use Google Colab with a GPU runtime for Activity 3 if reproducing the GPU measurements.
5. Ensure Ollama is running and the required model is installed before running Activities 5, 9, and 10.
6. Configure the Groq API key securely in a local `.env` file before running Activity 6. Never commit API keys or secret files to GitHub.

Some measurements and outputs depend on the execution environment and may differ when the notebook is rerun.

## Learning Outcomes

By completing this lab, I explored:

- How LLMs tokenize and generate text.
- How hardware and numerical precision affect model memory requirements.
- The differences between local, cloud GPU, and API-based inference.
- How temperature influences sampled text generation.
- How conversation history supports contextual chatbot responses.
- How system instructions customize chatbot behavior.

## Conclusion

This lab provided practical experience with language-model discovery, inference, resource estimation, API integration, and chatbot development. It demonstrated the trade-offs among local hardware, cloud computing, and hosted APIs, along with the importance of context and system instructions in conversational applications.
