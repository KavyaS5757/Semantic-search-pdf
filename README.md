## 🔍 Semantic PDF Search Engine

This project implements a **semantic search engine** that intelligently retrieves the most relevant pieces of text from a collection of PDF documents using language model embeddings and FAISS indexing.

### 📌 Features

* ✅ Extracts text from one or more PDF files
* ✅ Splits text into manageable chunks
* ✅ Generates semantic embeddings using a transformer model (`sentence-transformers`)
* ✅ Stores embeddings in an in-memory FAISS index for fast retrieval
* ✅ Accepts a user query and retrieves the top-k most semantically similar chunks
* ✅ Displays:

  * Text chunk
  * Source PDF filename
  * Cosine similarity score

---

### 🧠 Tech Stack

| Component        | Library                 |
| ---------------- | ----------------------- |
| PDF Text Parsing | `PyMuPDF`, `PyPDF2`     |
| Embeddings       | `sentence-transformers` |
| Search Index     | `FAISS` (CPU version)   |
| Language Model   | `all-MiniLM-L6-v2`      |
| Platform         | Notebook (Kaggle/Colab) |

### 🚀 How It Works

1. **Load PDFs** from a specified folder.
2. **Extract text** using `fitz` or fallback to `PyPDF2`.
3. **Split text into chunks** for better embedding and context resolution.
4. **Generate embeddings** using a Sentence-BERT model.
5. **Build an FAISS index** in memory using the embeddings.
6. **Accept a query**, embed it, and perform similarity search.
7. **Return the top-k matching text chunks** with scores and source filenames.

---

### 🧪 Example Usage

```bash
# Set the PDF folder path and query
pdf_folder = "/kaggle/input/pdf-files/2024"
query = "machine learning optimization techniques"

# Run the search
run_semantic_search(pdf_folder, query, top_k=5)

### 📦 Requirements

Install dependencies with:

```bash
pip install faiss-cpu sentence-transformers PyMuPDF PyPDF2
```

### 🎥 Demo Plan (For Presentation)

* Show PDF files in your input folder
* Run search queries like:

  * `"optimization techniques in machine learning"`
  * `"applications of AI in healthcare"`
* Explain output:

  * Cosine similarity score
  * Source PDF name
  * Matching text snippet
* Wrap up with advantages: fast, memory-efficient, easy to adapt


### ✨ Future Improvements

* Add PDF page numbers in the output
* Streamline for large-scale datasets using chunk storage
* Add UI (e.g., with Gradio or Streamlit)
* Store FAISS index persistently (optional)
