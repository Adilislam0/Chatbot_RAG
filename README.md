🔍 Adil’s RAG Chatbot (FAISS + Sentence Transformers + OpenAI)

Live Demo: https://huggingface.co/spaces/Adilislam00/Adil-RAG-Chatbot

A fully functional Retrieval-Augmented Generation (RAG) system that combines:

FAISS vector search

Sentence Transformers embeddings

OpenAI GPT-4o-mini

Gradio UI

Deployment on HuggingFace Spaces

This project demonstrates a production-style RAG pipeline that you can extend for research, internships, or real-world applications.

🚀 Features
✅ 1. Retrieval-Augmented Generation (RAG)

Converts your custom text corpus into embeddings

Uses FAISS to retrieve top-K similar documents

Sends retrieved docs + query to OpenAI

Ensures answers are grounded in actual context

✅ 2. Efficient Embedding Pipeline

Lazy loading (initializes only on first request — fast startup)

Precomputed embedding/index support (embeddings.npy, saved_index.faiss)

✅ 3. Clean, User-Friendly UI

Built using Gradio Blocks

Displays:

Answer

Sources used

Retrieved context

✅ 4. Cloud Deployment

Runs completely on HuggingFace Spaces, publicly accessible.

🧠 Architecture Overview
User Query
     │
     ▼
Sentence Transformers (query embedding)
     │
     ▼
FAISS Vector Search (top-K docs)
     │
     ▼
OpenAI GPT-4o-mini (answer using context)
     │
     ▼
Gradio UI (answer + sources)

📁 Project Structure
Adil-RAG-Chatbot/
│
├── app.py                 # Gradio UI
├── requirements.txt       # Dependencies
│
└── core/
    ├── rag_chatbot_openai.py     # RAG engine
    ├── rag_basic.py              # (optional test script)
    ├── corpus.txt                # Your knowledge base
    ├── embeddings.npy            # (optional) precomputed embeddings
    └── saved_index.faiss         # (optional) FAISS index

🛠️ Technologies Used

Python 3.10+

FAISS (CPU)

Sentence Transformers (all-MiniLM-L6-v2)

OpenAI Chat Completions API

NumPy

Gradio

HuggingFace Spaces

🧩 How Retrieval Works

Convert corpus sentences into 384-dimensional embeddings

Build FAISS index

Convert user query into embedding

FAISS retrieves top-k most similar documents

Construct prompt using retrieved docs

OpenAI model generates grounded, citation-supported answer

🖥️ Running Locally
1. Clone repo
git clone https://github.com/Adilislam0/ML-
cd ML-/RAG

2. Create virtual environment
python -m venv rag_env

3. Activate venv

Windows

rag_env\Scripts\activate

4. Install dependencies
pip install -r requirements.txt

5. Add your OpenAI key
setx OPENAI_API_KEY "sk-xxxxx"

6. Run app
python app.py

🌐 Deployment (HuggingFace Spaces)
Step-1: Create a new Space

Choose Gradio template.

Step-2: Upload these files:

app.py

requirements.txt

Entire core/ folder

Step-3: Add your secret key

Settings → Variables and Secrets

OPENAI_API_KEY = sk-xxxxxx

Step-4: Space will auto-build

Your live RAG app becomes available instantly.

🧪 Example Query

Q: What is gradient descent?
A: “Gradient descent is an optimization algorithm used to minimize loss functions…”
Sources: Doc 1, Doc 2, …


📈 Future Improvements

Chunking long documents

Metadata-enhanced retrieval

Reranking using cross encoder

Chat history memory

Streaming answers

Vector DB migration (Chroma / Pinecone / Qdrant)

👨‍💻 Author

Aadil Islam
MTech Artificial Intelligence
