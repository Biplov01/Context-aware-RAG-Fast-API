
---

## ⚙️ Requirements

- Python 3.10+
- Ollama installed and running
- OS: Windows / Linux / macOS

---

## 📦 Installation

### 1️⃣ Clone the repository
```bash
git clone <your-repo-url>
cd app
2️⃣ Create and activate virtual environment (optional but recommended)
bash
Copy code
python -m venv venv
venv\Scripts\activate   # Windows
3️⃣ Install dependencies
bash
Copy code
pip install -r requirements.txt
🤖 Setup Ollama
Install Ollama
👉 https://ollama.com/

Pull the model
bash
Copy code
ollama pull llama3.2:1b
Start Ollama server
bash
Copy code
ollama serve
📄 Add PDFs for RAG
Place your PDF files inside:

kotlin
Copy code
D:\app\data\pdfs\
Example:

Copy code
s41598-024-71118-7.pdf
These documents will be chunked, embedded, and indexed automatically.

▶️ Run the Application
Start FastAPI server (from project root)
powershell
Copy code
D:
cd D:\app
python -m uvicorn app.main:app --reload
You should see:

nginx
Copy code
Uvicorn running on http://127.0.0.1:8000
🌐 Access the Application
API Documentation
arduino
Copy code
http://127.0.0.1:8000/docs
Web UI
Open directly:

makefile
Copy code
D:\app\ui\index.html
OR (if served via FastAPI):

cpp
Copy code
http://127.0.0.1:8000/
🧪 Example API Request
json
Copy code
POST /chat
{
  "session_id": "user1",
  "query": "What is CTNet?"
}
Example Response
json
Copy code
{
  "answer": "CTNet is a convolutional neural network architecture designed for..."
}
🧠 Context Awareness
Each session_id maintains its own conversation history

LangGraph manages state transitions

Past messages influence future responses

Retrieved PDF context is injected dynamically

🛡️ Notes & Limitations
In-memory session storage (resets on server restart)

Designed for local development and demos

Can be extended with:

Redis / DB for persistence

Authentication

