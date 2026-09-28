# multi-llm-api-integration
A Python project demonstrating OpenAI and Google Gemini API integration with error handling, retry mechanisms, and LLM response generation.
# Multi-LLM API Integration with OpenAI and Gemini

A Python-based project demonstrating how to integrate and interact with multiple Large Language Model (LLM) APIs using **OpenAI** and **Google Gemini**.

The project sends the same prompt to different AI models and demonstrates API authentication, response generation, error handling, and retry mechanisms.

## 🚀 Project Overview

This project explores how different LLM providers can be integrated into a Python application.

Currently, the project supports:

* OpenAI API
* Google Gemini API

The same question is sent to both models:

> "What is the meaning of life?"

The generated responses are then displayed in the notebook.

## 🤖 AI Models

### OpenAI

The project uses the OpenAI API with:

```text
gpt-4o-mini
```

### Google Gemini

The project uses the Gemini API with:

```text
gemini-3.8-flash
```

## 🛠️ Technologies Used

* Python
* Jupyter Notebook
* Google Colab
* OpenAI API
* Google Gemini API
* Large Language Models (LLMs)

## ✨ Features

* OpenAI API integration
* Google Gemini API integration
* API key authentication
* LLM response generation
* Error handling
* API connection error handling
* Rate-limit handling
* Automatic retry mechanism
* Server error retry mechanism
* Multiple AI provider support

## 🔄 How It Works

```text
              User Prompt
                   │
                   ▼
        ┌─────────────────────┐
        │   Python Notebook   │
        └──────────┬──────────┘
                   │
          ┌────────┴────────┐
          ▼                 ▼
      OpenAI API        Gemini API
          │                 │
          ▼                 ▼
     GPT Model         Gemini Model
          │                 │
          └────────┬────────┘
                   ▼
            Generated Output
```

## 📁 Project Structure

```text
multi-llm-api-integration/
│
├── multi_llm_api.ipynb
├── README.md
├── requirements.txt
├── .gitignore
└── LICENSE
```

## ⚙️ Installation

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/multi-llm-api-integration.git
```

Open the project:

```bash
cd multi-llm-api-integration
```

Install the required libraries:

```bash
pip install -U openai google-genai
```

## 🔑 API Key Configuration

API keys should **never be hard-coded or uploaded to GitHub**.

For Google Colab, store your keys in **Secrets**.

Create:

```text
OPENAI_API_KEY
GEMINI_API_KEY
```

Then load them using:

```python
from google.colab import userdata

OPENAI_API_KEY = userdata.get("OPENAI_API_KEY")
GEMINI_API_KEY = userdata.get("GEMINI_API_KEY")
```

### OpenAI

```python
from openai import OpenAI

client = OpenAI(api_key=OPENAI_API_KEY)
```

### Gemini

```python
from google import genai

client = genai.Client(api_key=GEMINI_API_KEY)
```

## ▶️ Running the Project

Open the notebook:

```text
multi_llm_api.ipynb
```

The notebook can be executed using:

* Google Colab
* Jupyter Notebook
* JupyterLab

Configure the API keys before running the API cells.

## 🧪 Example Prompt

The current project uses:

```text
What is the meaning of life?
```

You can replace this with any other prompt, for example:

```text
Explain machine learning in simple words.
```

or:

```text
What are the applications of artificial intelligence?
```

## 🛡️ Error Handling

The project includes error handling for common API problems.

### Rate Limit

The OpenAI implementation detects rate-limit errors and retries requests when appropriate.

### Insufficient Credits

If the OpenAI API account has no remaining credits, the program displays a message instead of repeatedly retrying the request.

### Connection Errors

Temporary connection problems are handled using a retry mechanism.

### Server Errors

Temporary server-side errors are retried with increasing delays.

The retry process uses:

```text
Attempt 1 → wait
Attempt 2 → wait longer
Attempt 3 → wait longer
...
```

This helps make the application more reliable when temporary API problems occur.

## 📊 Example Output

```text
OpenAI:
[Generated response from OpenAI]

Gemini:
[Generated response from Gemini]
```

The exact output depends on the model and the prompt.

## 🎯 Project Objectives

* Understand LLM API integration
* Learn how to authenticate API requests
* Work with multiple AI providers
* Generate responses using different LLMs
* Handle API errors
* Implement retry mechanisms
* Understand practical usage of generative AI APIs

## 🔮 Future Improvements

Possible improvements include:

* Add more LLM providers
* Add interactive user input
* Compare responses automatically
* Measure response time
* Compare token usage
* Add cost tracking
* Build a web interface
* Add model selection
* Save responses to CSV or JSON
* Create an automated response evaluation system

## 🔐 Security

**Never upload API keys to GitHub.**

Use environment variables, Google Colab Secrets, or another secure secret-management system.

If an API key has already been exposed publicly, revoke it and generate a new key before publishing the repository.

## 📌 Disclaimer

This project is created for educational, experimental, and development purposes.

API availability, model names, pricing, limits, and provider APIs may change over time.

## 👨‍💻 Author

**Rahul Mondal**

B.Tech in Computer Science and Engineering
Specialization: Data Science
