# Devy – AI-Powered Tech Career Recommendation Chatbot

**Devy** is an AI-driven career advisory chatbot built using a fine-tuned Meta-LLaMA 3.1 model with LoRA adapters. It guides users through a structured conversation to recommend suitable tech career paths based on their responses, inferred traits, and preferences.

---

## Features

- **Custom LLaMA 3.1 Model with LoRA Adapters**  
  Loads and serves a fine-tuned LLaMA 3.1 model for efficient, adaptive question generation and scoring.

- **Multi-Phase Conversational Flow**  
  Structured 5-phase assessment covering onboarding, preference checks, trait inference, adaptive questioning, and final career recommendations.

- **Trait Inference & Scoring System**  
  Tracks over 40 traits, including problem-solving, creativity, adaptability, and team collaboration, to personalize career recommendations.

- **Dynamic Question Generation**  
  Generates scenario-based, open-ended questions tailored to user responses using model inference.

- **Top 3 Tech Career Recommendations**  
  Recommends careers from 20+ tech paths with score-based rankings and professional explanations.

- **Interactive Gradio UI**  
  Simple web interface for user interaction, powered by Gradio.

---

## System Requirements

- Python 3.8+
- CUDA-enabled GPU (recommended)
- Packages:
  - `transformers`
  - `accelerate`
  - `bitsandbytes`
  - `gradio`
  - `peft`
  - `huggingface_hub`

---

## Setup

1. Install dependencies:

   ```bash
   pip install transformers accelerate bitsandbytes gradio peft
   ```

2. Authenticate with Hugging Face:

   ```python
   from huggingface_hub import notebook_login
   notebook_login()
   ```

3. Ensure LoRA adapters and base model paths are correctly configured:
   - **Base Model**: `unsloth/Meta-Llama-3.1-8B`
   - **LoRA Adapter**: `Poll027/my-lora-llama`

---

## How It Works

- Load the fine-tuned LLaMA model with LoRA adapters using Accelerate and BitsAndBytes for optimized inference.
- Conduct step-by-step conversation:
  1. Onboard user and gather basic profile.
  2. Suggest careers based on initial profiling.
  3. Dynamically assess traits via generated questions.
  4. Score multiple domains (Software Dev, Data Science, Cybersecurity, etc.).
  5. Recommend top 3 careers based on inferred traits and scores.

---

## Usage

Run the chatbot directly:

```bash
python 14_06.py
```

The Gradio web interface will launch automatically for interactive chat.

---

## Example Interaction

```
Hi! I'm Devy, your career advisor from Devspace. I'm here to help you find the best tech career paths by understanding your personality and preferences.

Assistant: What's something you enjoy creating or building in your free time?

User: I love working on small coding projects and designing websites.

Assistant: How do you typically approach solving challenging problems?

...

🎉 CAREER ASSESSMENT COMPLETE 🎉

Here are your top 3 tech career recommendations:

#1. Software Development (Score: 9.0/10)
   You have strong programming skills, creativity, and problem-solving abilities.

#2. UX/UI Design (Score: 8.5/10)
   Your creative mindset and focus on user experience make this an ideal path.

#3. Data Science (Score: 7.8/10)
   Your analytical thinking and curiosity align well with data analysis.
```

---

## File Structure

- `14_06.py`: Full chatbot logic, model loading, and Gradio UI.

---

## Notes

- Requires valid Hugging Face authentication.
- Uses Gradio for serving the interactive chat interface.
- Optimized for GPU inference via BitsAndBytes and Accelerate.

---

## License

This project is for research and educational use.
