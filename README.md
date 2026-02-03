
---

# Multi-LLM Chatbot Project 🤖

## 📝 Description

This project is a versatile Python-based chatbot that integrates and compares multiple Large Language Models (LLMs) from both cloud and local sources.

### Supported Models:

1. **OpenAI GPT-5 Nano** (Cloud-based API)
2. **Ollama Llama 3.2** (Local execution)
3. **DeepSeek Qwen 1.5b** (Distilled local model via Ollama)

---

## ✨ Features

* **Hybrid Integration:** Seamlessly switch between Cloud APIs and Local Endpoints.
* **Privacy-Focused:** Run local models without sending data to external servers.
* **Cost-Effective:** Zero API costs when using local models via Ollama.

---

## 🚀 Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/multi-llm-chatbot.git
cd multi-llm-chatbot

```

### 2. Install Dependencies

```bash
pip install openai python-dotenv

```

### 3. Environment Configuration

Create a `.env` file in the root directory:

```env
OPENAI_API_KEY=your_sk_key_here

```

### 4. Local Models Setup (Ollama)

```bash
ollama pull llama3.2
ollama pull deepseek-r1:1.5b

```

---

## 💻 Usage Examples

### 🌐 Using OpenAI GPT-5 Nano

```python
from openai import OpenAI
client = OpenAI()
response = client.chat.completions.create(
    model="gpt-5-nano",
    messages=[{"role": "user", "content": "Hi!"}]
)
print(response.choices[0].message.content)

```

### 🏠 Using Local Models (Ollama)

```python
from openai import OpenAI
local_client = OpenAI(base_url="http://localhost:11434/v1", api_key="ollama")
response = local_client.chat.completions.create(
    model="llama3.2",
    messages=[{"role": "user", "content": "Hi!"}]
)
print(response.choices[0].message.content)

```

---

## 📄 License

MIT License

---
