# AI-Workflow
# 🧠 No-Code/Low-Code Workflow Builder

## 🚀 Objective

Build a **No-Code/Low-Code web application** that allows users to visually create and interact with intelligent workflows using components such as document extractors, vector stores, language models, and a chat interface.

Users can:
- Design workflows via drag-and-drop UI.
- Connect components like `User Query`, `KnowledgeBase`, `LLM Engine`, and `Output`.
- Ask questions and receive answers processed by the defined workflow.

---

## 🛠️ Tech Stack

| Layer        | Technology              |
|-------------|--------------------------|
| Frontend    | React.js, React Flow     |
| Backend     | FastAPI                  |
| Database    | PostgreSQL               |
| Vector Store| ChromaDB (or similar)    |
| Embeddings  | OpenAI / Gemini          |
| LLM         | OpenAI GPT, Gemini       |
| Web Search  | SerpAPI / Brave          |
| File Parsing| PyMuPDF or equivalent    |
| Deployment  | Docker (+ optional K8s)  |

---

## 📦 Core Components

### 1. 🔍 User Query Component
- Entry point to accept user input.
- Sends query to connected components.

### 2. 📄 KnowledgeBase Component
- Upload and parse documents (PDF, etc.).
- Extract text using PyMuPDF or similar.
- Generate & store embeddings (OpenAI/Gemini).
- Retrieve context based on queries.

### 3. 🧠 LLM Engine Component
- Receives query + optional context + prompt.
- Queries OpenAI GPT or Gemini.
- Optionally performs web search via SerpAPI.
- Returns a generated response.

### 4. 💬 Output Component
- Displays the final response to the user.
- Interactive chat interface.
- Supports follow-up questions.

---

## 🧩 Application Features

### 🔧 Workflow Builder
- Drag-and-drop components using React Flow.
- Connect components with arrows.
- Configure each component from the sidebar.
- Snap-to-grid & zoom/pan for canvas alignment.

### 🧪 Execution Controls
- **Build Stack**: Validates and saves the workflow.
- **Chat with Stack**: Opens the chat interface for interaction.
- (Optional) Real-time logs or execution steps.

---

## 📁 Project Structure

AI-Workflow/
├── backend/
│   ├── app/                     # FastAPI application code (main.py, routers, services)
│   ├── dockerfile               # Dockerfile for backend
│   └── requirements.txt         # Python dependencies
│
├── workflow/                   # Frontend (React)
│   ├── node_modules/
│   ├── public/
│   ├── src/
│   │   ├── assets/             # Static files like icons, images
│   │   ├── components/         # React components (Sidebar, Canvas, etc.)
│   │   ├── App.jsx             # Main App logic
│   │   ├── main.jsx            # Entry point
│   │   ├── App.css             # Component-level styles
│   │   └── index.css           # Global styles
│   ├── index.html              # Root HTML file
│   ├── vite.config.js          # Vite bundler config
│   ├── package.json            # Frontend dependencies
│   └── eslint.config.js        # Linting rules
│
├── docker-compose.yaml         # Orchestrates frontend + backend services
└── README.md                   # Project documentation


---

## ⚙️ Setup Instructions

### 🐳 Dockerized Setup (Recommended)

> Make sure Docker and Docker Compose are installed.

```bash
# From root directory
docker-compose up --build

Then open: http://localhost:5173 for frontend and http://localhost:8000/docs for backend API.

Manual Local Setup

🔹 Frontend
cd frontend
npm install
npm run dev

🔹 Backend
cd backend
python -m venv venv
venv\Scripts\activate       # For PowerShell
pip install -r requirements.txt
uvicorn main:app --reload

📬 Contact
Developed by Bhumika Maheshwari
GitHub: BhumikaMaheshwari05
