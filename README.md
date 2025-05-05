# 🧠 Retrieval-Augmented Generation (RAG) Based QA System

This project implements a local **Retrieval-Augmented Generation (RAG)** system that can answer user questions about **Machine Learning**. It combines **web scraping**, **semantic search** using FAISS, and **language generation** using a large language model (Zephyr 7B).

---

## 🚀 Features

- ✅ Scrapes machine learning-related articles from the web.
- ✅ Cleans and preprocesses text into manageable chunks.
- ✅ Creates vector embeddings for chunks using SentenceTransformers.
- ✅ Uses FAISS for efficient similarity-based retrieval.
- ✅ Generates context-aware answers using a Zephyr-7B model.
- ✅ Interactive Gradio UI to ask questions.

---

## 📦 Components

### 1. Web Scraper (`WebScraper`)

Scrapes and cleans content from given URLs.

- Removes unwanted tags (headers, scripts, etc.).
- Extracts main content from `<main>`, `<article>`, or divs.
- Collects up to 30,000 words.

### 2. Text Processor (`TextProcessor`)

Processes raw scraped content into smaller chunks.

- Uses `nltk` sentence tokenizer.
- Splits content into ~200-word chunks for better embedding.

### 3. Local RAG (`LocalRAG`)

The heart of the system, combining retrieval and generation.

#### Retrieval:
- Embeds chunks using `all-MiniLM-L6-v2`.
- Creates a FAISS index for semantic similarity search.
- Retrieves top-k relevant chunks for a user query.

#### Generation:
- Constructs a prompt from the retrieved context and user question.
- Uses `zephyr-7b-beta` model to generate an answer.

---

## 🧪 How It Works

1. **Scraping**: Articles from Wikipedia, IBM, and TechTarget are scraped.
2. **Chunking**: Texts are broken into ~200-word chunks.
3. **Embedding**: Chunks are embedded and indexed using FAISS.
4. **Querying**: User question is embedded and top relevant chunks are retrieved.
5. **Answering**: Zephyr model generates a response using the context.

---

## 💻 Gradio Interface

The system provides a simple web UI:

- Input: Any question related to machine learning.
- Output: 
  - 📘 Retrieved context
  - 🤖 Answer from the language model

---

## 🛠️ Technologies Used

- Python
- FAISS
- SentenceTransformers
- HuggingFace Transformers
- Zephyr-7B
- BeautifulSoup
- Gradio

---

## 📌 Example

**Question**: *What is supervised learning?*

**Context (retrieved)**:
> Supervised learning is a type of machine learning where the model is trained on labeled data...

**Answer (generated)**:
> Supervised learning involves training a model on input-output pairs, allowing it to learn the mapping...

---

## 📝 Future Improvements

- Add PDF/Doc scraping capability.
- Use long-context models (e.g., Claude or Gemini) for deeper context analysis.
- Add caching and persistent indexing.
- UI enhancements.

---

## 📄 License

This project is for educational and research purposes.

