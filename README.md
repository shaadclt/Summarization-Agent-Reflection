# 🧠 Summarizer Agent with Reflection using LlamaIndex
This project uses LlamaIndex's Introspective Agent to summarize product specification documents with a focus on performance specs and safety features. The pipeline loads PDF documents, extracts text, and generates a summary in less than 50 words using a reflective agent loop.

# 🚀 Demo Notebook
You can run the full pipeline on Google Colab using the notebook:
summarization_agent_reflection.ipynb

# 🔧 Features
- ✅ Uses Groq LLaMA 3.3-70B via llama-index-llms-groq

- ✅ Embedding with HuggingFace (BAAI/bge-small-en-v1.5)

- ✅ Document reading using PyMuPDF

- ✅ Intelligent summarization using Self-Reflection + Introspective Agents

- ✅ Focused output: performance specs + safety features (under 50 words)

# 🛠️ Installation
Install required packages:

```bash
pip install llama-index
pip install llama-index-llms-groq
pip install llama-index-embeddings-huggingface
pip install llama-index-agent-introspective
pip install pymupdf
```

# 🧪 How It Works
1. Load PDF using PyMuPDFReader

2. Extract Text from the first page (or any relevant section)

3. Set up Groq LLaMA-3.3-70B model

4. Create Introspective Agent with a system prompt

5. Generate Summarized Output

# 🧠 Prompt Engineering
System Prompt:

```text
You are a Product specification summarizer who can summarize a product specification.
For the input provided, create a summary with less than 50 words.
Ensure that the summary focuses on performance specifications and safety features.
```

# 📂 Sample File Structure
```text
├── summarization_agent_reflection.ipynb
├── EcoSprint_Specification_Document.pdf
├── README.md
├── LICENSE.txt
```

# 🔐 API Key Setup
The Groq API key is securely loaded from the Colab environment:

```python
from google.colab import userdata
llm = Groq(model="llama-3.3-70b-versatile", api_key=userdata.get('GROQ_API_KEY'))
Make sure to upload your API key via the Colab interface (userdata.set('GROQ_API_KEY', 'your_key') or manually inject via secrets).
```

# 📌 Notes
- The current version processes only the first page of the input document.

- For multi-page documents, extend the logic with summarization chaining or chunking.

- Customize the system_prompt as per your domain (e.g., automotive, electronics, medical devices, etc.)

# 📜 License
MIT License. See [LICENSE](LICENSE.txt) file for details.
