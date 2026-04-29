**📚 AI PDF Chatbot (RAG-based Conversational QA System)**

An end-to-end Retrieval-Augmented Generation (RAG) system that allows users to upload multiple PDFs and interact with them using natural language queries.

Built to simulate real-world AI systems used in knowledge assistants, document search, and enterprise chatbots.

**🚀 Features**
📄 Upload and process multiple PDF documents
✂️ Intelligent text chunking for better retrieval
🧠 Semantic search using vector embeddings (FAISS)
🤖 Context-aware answers using LLMs (OpenAI)
💬 Conversational memory for multi-turn chat
⚡ Interactive UI using Streamlit
🔄 Switch between OpenAI (paid) and HuggingFace (free) embeddings

**🧠 How It Works (RAG Pipeline)**
PDF Ingestion → Extract text using PyPDF2
Chunking → Split text into overlapping chunks
Embedding → Convert chunks into vectors
Vector Store → Store embeddings in FAISS
Retrieval → Fetch relevant chunks for query
LLM Generation → Generate answer using retrieved context
Memory → Maintain chat history for conversation continuity

**🛠️ Tech Stack**
Language: Python
Frameworks/Libraries: LangChain, Streamlit
LLM: OpenAI (ChatOpenAI)
Vector DB: FAISS
Embeddings: OpenAI / HuggingFace
PDF Processing: PyPDF2
Environment Management: python-dotenv

**📂 Project Structure**
AI-PDF-Chatbot/
│── app.py
│── htmlTemplates.py
│── requirements.txt
│── .env
│── README.md

**⚙️ Setup & Installation**
git clone https://github.com/your-username/ai-pdf-chatbot.git
cd ai-pdf-chatbot

python -m venv venv
venv\Scripts\activate  # Windows

pip install -r requirements.txt

Create a .env file:

OPENAI_API_KEY=your_api_key

Run the app:

streamlit run app.py

**📸 Demo**

Upload PDFs → Ask questions → Get contextual answers 💬
(Add screenshots/gif here for more impact)

**📌 Reference**

This project was inspired by:
👉 https://github.com/alejandro-ao/ask-multiple-pdfs

However, I rebuilt and extended the system from scratch, focusing on understanding core concepts instead of just replicating functionality.

**⚠️ Challenges Faced & Solutions**
1. Dependency Conflicts (LangChain + Pydantic + NumPy)
Faced multiple errors like:
ModuleNotFoundError: pydantic_core
NumPy build failures
Solution:
Switched to Python 3.10
Used strict version pinning for LangChain ecosystem
Rebuilt virtual environment from scratch
2. Circular Import Errors (tiktoken, regex)
Errors due to partially installed compiled packages
Solution:
Clean reinstall of environment
Ensured compatible binary versions
3. PDF Text Extraction Issues
extract_text() returning None for some pages
Solution:
Added null checks to prevent crashes
4. Performance Bottleneck (Embedding Model)
Initial use of instructor-xl caused:
High memory usage (~4GB)
Slow processing
Solution:
Switched to lightweight all-MiniLM-L6-v2 for local usage
Kept OpenAI embeddings as optional faster alternative
5. Incorrect LLM Usage
Used OpenAI() (completion model) instead of chat model
Solution:
Migrated to ChatOpenAI for better conversational responses
6. UX Issues
App crashed if user queried before processing PDFs
Solution:
Added session state checks and warnings

**📈 What I Learned**
Deep understanding of RAG architecture
How vector databases enable semantic search
Importance of chunking strategies in LLM pipelines
Handling real-world dependency issues in AI projects
Trade-offs between local vs API-based embeddings
Designing stateful conversational systems


**🔮 Future Improvements**
📄 Show source citations (which chunk/page answer came from)
⚡ Streaming responses (real-time typing effect)
💾 Persistent vector storage (save/load FAISS)
🌐 Deployment (Streamlit Cloud / AWS)
🧠 Hybrid search (keyword + semantic)

**🙌 Final Note**

This project was not just about building a chatbot, but about understanding how modern AI systems are architected and deployed.

It reflects hands-on experience with LLMs, RAG pipelines, debugging, and system design, rather than just following a tutorial.
