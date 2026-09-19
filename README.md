# InterviewIQ — AI Interview Practice Prototype

InterviewIQ is a small full-stack prototype for generating role-specific interview questions and evaluating written answers with an OpenAI model. The repository currently stores the prototype source in `interviewiq_project.zip`.

## Included prototype

```text
interviewiq/
├── backend/
│   ├── main.py          # FastAPI endpoints and CORS setup
│   ├── ai_engine.py     # OpenAI question and feedback prompts
│   ├── requirements.txt
│   └── .env             # Example environment configuration
└── frontend/src/
    ├── App.jsx
    ├── api.js
    ├── components/Navbar.jsx
    └── pages/
        ├── Home.jsx
        └── MockInterview.jsx
```

## Features

- Generate one interview question for a chosen role
- Submit a written answer for coaching feedback and a score
- FastAPI backend with `/question` and `/feedback` endpoints
- React components for role input, question display and answer feedback

## Run the backend

1. Download and extract `interviewiq_project.zip`.
2. Open a terminal in `interviewiq/backend`.
3. Create and activate a virtual environment.
4. Install dependencies and configure an API key:

```bash
python -m venv .venv
# Windows: .venv\Scripts\activate
# macOS/Linux: source .venv/bin/activate
pip install -r requirements.txt
```

Create or update `.env`:

```env
OPENAI_API_KEY=your_api_key_here
```

Start the API:

```bash
uvicorn main:app --reload
```

The API is available at `http://127.0.0.1:8000`; interactive documentation is at `/docs`.

## Frontend note

The archive contains the React source components but does not include `package.json` or a complete Vite/React scaffold. To run the UI, place `frontend/src` into an existing React project, install `axios`, and configure `api.js` to target the FastAPI URL.

## Security

Never commit a real API key. Use the placeholder `.env` value as a template and keep local credentials out of version control. The permissive CORS configuration is suitable only for local prototyping and should be restricted before deployment.
