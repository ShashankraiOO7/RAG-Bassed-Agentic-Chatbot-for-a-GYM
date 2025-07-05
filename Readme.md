
# 🔍 RAG Bassed ChatBot For a GYM

### Author: **Shashank Rai**

---

## 📌 Overview

This project implements a **Retrieval-Augmented Generation (RAG)** pipeline using **Google's Gemini-1.5 Pro** with the **LangChain** framework. It enables intelligent document querying and context-aware responses powered by **Google Generative AI**, **ChromaDB** for vector storage, and **LangGraph** for flow management.

---

## 🚀 Features

- 🔹 Embedding generation with `GoogleGenerativeAIEmbeddings`
- 🔹 Vector storage and retrieval using **ChromaDB**
- 🔹 Intelligent response generation using **ChatGoogleGenerativeAI**
- 🔹 Prompt templates with chat history context
- 🔹 Modular and composable RAG chain
- 🔹 Easy retrieval with `MMR` search strategy
- 🔹 Built-in prompt formatting and history injection

---

## 🧠 Tech Stack

| Component     | Tool / Library                        |
|---------------|----------------------------------------|
| Embeddings    | `GoogleGenerativeAIEmbeddings`         |
| Vector Store  | `ChromaDB`                             |
| Language Model| `ChatGoogleGenerativeAI (Gemini 1.5)`  |
| Orchestration | `LangChain`, `LangGraph`               |
| Prompting     | `ChatPromptTemplate`, `StrOutputParser`|

---

## 📦 Installation

```bash
pip install langchain-google-genai
pip install langchain-community
pip install chromadb
pip install langgraph
```

---

## 🛠️ How It Works

1. **Embedding Documents**:  
   Input documents are embedded using `GoogleGenerativeAIEmbeddings` and stored in ChromaDB.

2. **Retrieval with MMR**:  
   The retriever fetches relevant documents based on the user’s query using Max Marginal Relevance (`search_type="mmr"`).

3. **Prompt Creation**:  
   A dynamic prompt template incorporates both **chat history** and **retrieved context**.

4. **LLM Inference**:  
   The `ChatGoogleGenerativeAI` model (Gemini-1.5 Pro) answers queries using the prompt.

5. **RAG Chain Execution**:  
   The whole chain is composed and executed using a pipe: `prompt | llm | output_parser`.

---

## 📄 Example Query

```python
retriever = db.as_retriever(search_type="mmr", search_kwargs={"k": 5})
response = retriever.invoke("Who is the owner and what are the timings?")
```

---

## 🧪 Output Parsing

```python
output_parser = StrOutputParser()
rag_chain = prompt | llm | output_parser
```

---

## 📚 Use Case

This setup is ideal for:

- RAG chatbots
- Contextual document Q&A
- Smart assistants over custom knowledge bases
- Enterprise search engines with LLM reasoning

---
---

## 🤝 Contact

**Shashank Rai**  
📧 shashankjirai4@gmail.com  
🔗 IIIT Lucknow
