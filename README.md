# AI API Assignment – OpenAI/Groq and Google Gemini

## Student Assignment

This project demonstrates how to use API keys to access Large Language Models (LLMs) through Python/Google Colab.

### Assignment Topics

1. Accessing LLM models using an API key
2. Accessing Google Gemini LLM models using the Gemini API key

---

## Technologies Used

- Python
- Google Colab
- Groq API
- Google Gemini API
- Python SDKs
- Jupyter Notebook

---

# 1. Groq API – LLM Model Access

The OpenAI-related notebooks in this repository use the **Groq API** to access LLM models.

### Python Package

```bash
pip install groq
```

### API Key

The API key is stored securely using Google Colab Secrets.

The code retrieves the key using:

```python
from google.colab import userdata

os.environ["GROQ_API_KEY"] = userdata.get("GROQ_API_KEY")
```

The API key itself is not included in the source code.

### Example

```python
from groq import Groq

client = Groq()

completion = client.chat.completions.create(
    model="openai/gpt-oss-120b",
    messages=[
        {
            "role": "user",
            "content": "Give me a list of animals that may become extinct in the future."
        }
    ]
)

print(completion.choices[0].message.content)
```

---

# 2. Google Gemini API

The Gemini notebook demonstrates how to use the Google Gemini API with Python.

### Python Package

```bash
pip install google-genai
```

### API Key

The Gemini API key is stored securely using Google Colab Secrets.

The code retrieves the key using:

```python
from google.colab import userdata

os.environ["GEMINI_API_KEY"] = userdata.get("GEMINI_API_KEY")
```

The API key itself is not included in the source code.

### Example

```python
from google import genai

client = genai.Client()

response = client.models.generate_content(
    model="gemini-3.8-flash",
    contents="What is the closest habitable planet in our galaxy according to scientists? Answer in one line."
)

print(response.text)
```

---

# Project Files

| File | Description |
|---|---|
| `OpenAI.ipynb` | LLM API example using Groq and Qwen model |
| `OpenAI_2.ipynb` | LLM API example using Groq and OpenAI GPT-OSS model |
| `Gemini.ipynb` | Google Gemini API example |

---

# How to Run the Notebooks

## Step 1: Open Google Colab

Open:

https://colab.research.google.com/

## Step 2: Upload the notebook

Upload the required `.ipynb` file.

## Step 3: Add the API key to Colab Secrets

In Google Colab, open the **Secrets** section and add the required API key.

For Groq:

```text
GROQ_API_KEY
```

For Gemini:

```text
GEMINI_API_KEY
```

The secret value should contain the actual API key.

## Step 4: Run the notebook

Run the cells from top to bottom.

The program sends a prompt to the selected LLM and prints the generated response.

---

# Security

API keys are sensitive credentials.

They should never be written directly in the Python source code or uploaded to GitHub.

This project uses Google Colab Secrets so that the API keys are not exposed in the notebook.

---

# Conclusion

This assignment demonstrates how Python applications can communicate with Large Language Models using APIs.

The project contains examples using:

- Groq API
- Qwen LLM
- OpenAI GPT-OSS model through Groq
- Google Gemini API
- Gemini LLM

The API key is securely retrieved from Google Colab Secrets instead of being stored directly in the source code.


# 👨‍💻 Author

**Subhadip Samanta**

🎓 B.Tech in Data Science

GitHub: https://github.com/subhadip136


---

# ⭐ Support

If you found this project useful, please consider giving it a ⭐ on GitHub.

It helps others discover the project and motivates future improvements.

---
