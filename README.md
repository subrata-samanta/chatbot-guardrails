# Azure OpenAI Banking Assistant with Advanced Guardrails 🏦

A comprehensive, secure banking assistant powered by Azure OpenAI services with multiple layers of guardrails and security features.

![Banking Assistant Architecture](https://mermaid.ink/img/pako:eNqNk81OwzAQhF9l5XOJ1GsfgQsHBEIqEhKIA-KQ2pvWUmIH22mhqt-ddZK0DQUEvsSy_c3s7HrXA0-UQAbZJpQGX9YE69h6FVW0iWUuGsNeWWsiw69ksU6llnxHZep84ZwxlSmVMQtZG7avUviUlprSV55aheVFU_GshPFzF_1Axo6DW4LSGleHpeG5YmF4IxPkUvM6TCtYGh0GXkY-xkHFqpBCUQVjFMZqhVbFOQ8K6DD8M7Sb5SU_RviORvQ5nXsLpR7wl1WJvlJJYbkMiFYLixr9ocfH8y0mp3X2NTKft0NA3e3iCVjv9VsMkzNjLDrw7B5OgRSBUJSPwNmKi9rmHjNVfF3xL5Zh-9v5HxesweuI4HV_kKBbfQhZEzgoQ_sdgM2BBaVhksi6gCxSHLKO9CU6HtFNyOq4hKyN2RrWiAVkD_0YUuL1BgjKW8jGFCB7hmxaC1xVPN2E2eCYGtiuFX_AAfm-0T8TQDY7Uk7V-n4NsXzOhr7EJtgm4G8ZlsKr)

## 📝 Table of Contents

- [Overview](#overview)
- [Key Features](#key-features)
- [Architecture](#architecture)
- [Security Features](#security-features)
- [Components](#components)
- [Installation](#installation)
- [Usage](#usage)
- [Configuration](#configuration)

## 🎯 Overview

This system implements a secure banking assistant with multiple layers of protection:

- Content filtering
- Vector-based guardrails
- Keyword-based security
- Advanced NeMo guardrails
- Document reranking

## 🔑 Key Features

- **Multi-layer Security** 
    - Content validation
    - Query filtering
    - Access control
    - Information protection

- **Smart Document Retrieval**
    - Vector search
    - Query expansion
    - Document reranking

- **Advanced Guardrails**
    - Banking content validation
    - Sensitive info protection
    - Unauthorized access prevention

## 🏗️ Architecture

```mermaid
graph TD
        A[User Query] --> B[Content Filter]
        B --> C{Is Banking Related?}
        C -->|Yes| D[Vector Search]
        C -->|No| E[Rejection Response]
        D --> F[Query Expansion]
        F --> G[Document Reranking]
        G --> H[Response Generation]
        H --> I[Security Check]
        I --> J[Final Response]
```

## 🔒 Security Features

1. **Content Filtering**
     - Banking relevance check
     - Sensitive information detection
     - Access control validation

2. **Information Protection**
     - PII data protection
     - Account info security
     - Credential protection

## 🧩 Components

| Component | Purpose |
|-----------|---------|
| AzureConfig | Configuration management |
| Content Filter | Query validation |
| Vector Store | Document retrieval |
| Guardrails | Security enforcement |
| Reranking | Result optimization |

## 💻 Installation

```bash
# Clone repository
git clone https://github.com/subrata-samanta/chatbot-guardrails

# Install dependencies
pip install -r requirements.txt

# Configure environment
cp .env.example .env
```

## 🚀 Usage

```python

print(final_guardrails_chain.invoke({
    "question": "How can I apply for a loan?",
    "chat_history": [
        {"role": "user", "content": "How to check my bank balance?"}, 
        {"role": "assistant", "content": "To check your account balance, you can log in to the online banking portal or use the mobile banking app."}
    ]
}))

```

## ⚙️ Configuration

1. Set up Azure OpenAI credentials in `.env`:
```
AZURE_ENDPOINT=<your-endpoint>
AZURE_API_KEY=<your-api-key>
```

2. Configure model deployments:
```python
config = AzureConfig(
        chat_model="gpt-4",
        embedding_model="text-embedding-3-large"
)
```

