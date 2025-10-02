# LangChain AI Chatbots

Interactive AI chatbot applications built with LangChain and Streamlit supporting both cloud OpenAI models and local Ollama (Llama 3.2) with LangSmith observability.

---

## Overview

This repository demonstrates how to build conversational AI interfaces using LangChain Expression Language (LCEL) and Streamlit. It includes dual implementations: one utilizing OpenAI's cloud models and another running fully offline using open-weights models through local Ollama, both tracked with LangSmith for prompt and response tracing.

---

## Applications

### 1. OpenAI Chatbot (`chatbot/app.py`)
- Powered by `ChatOpenAI` (`gpt-3.5-turbo`).
- Employs `ChatPromptTemplate` and `StrOutputParser`.
- Captures token usage and execution traces via LangSmith.

### 2. Local Ollama Chatbot (`chatbot/lacallama.py`)
- Runs fully locally using `Ollama` (`llama3.2` or `deepseek-r1:8b`).
- Zero API fees and complete data privacy.
- Integrated with LangSmith tracing for performance analysis.

---

## Tech Stack

- **Framework**: LangChain (`langchain`, `langchain-core`, `langchain-community`, `langchain-openai`)
- **Frontend UI**: Streamlit
- **Local LLM Engine**: Ollama (`llama3.2`)
- **Cloud Models**: OpenAI (`gpt-3.5-turbo`)
- **Observability**: LangSmith (`LANGCHAIN_TRACING_V2`)

---

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/iamjunaidjutt/LangChain.git
cd LangChain
```

### 2. Set up virtual environment & install dependencies

```bash
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate

pip install -r requirements.txt
```

### 3. Configure environment variables

Copy the example environment file and configure your API keys:

```bash
cp .env.example .env
```

Set your credentials in `.env`:

```env
OPENAI_API_KEY="your_openai_api_key_here"
LANGCHAIN_TRACING_V2="true"
LANGCHAIN_API_KEY="your_langsmith_api_key_here"
```

---

## Running the Applications

### Run the OpenAI Streamlit Chatbot

```bash
streamlit run chatbot/app.py
```

### Run the Local Ollama Chatbot

Ensure Ollama is running locally with the target model:

```bash
ollama run llama3.2
```

Then in your application terminal:

```bash
streamlit run chatbot/lacallama.py
```

The Streamlit UI will open in your browser at `http://localhost:8501`.

---

## Project Structure

```
LangChain/
├── chatbot/
│   ├── app.py             # Streamlit chatbot using OpenAI GPT-3.5
│   └── lacallama.py       # Streamlit chatbot using local Ollama (Llama 3.2)
├── .env.example           # Environment variable template
├── requirements.txt       # Python dependencies
├── LICENSE                # Open-source license
└── README.md              # Project documentation
```

---

## License

This project is open-source and available under the [MIT License](LICENSE).
