# TalentGenie - AI-Powered HR Management Platform

**Project:** HR LLM-Enabled Assistant
**Version:** 1.0.0

## Problem Statement

Human Resources departments often struggle with time-consuming manual processes ranging from recruitment screening to employee engagement analysis. **TalentGenie** is a comprehensive web application designed to modernize HR operations using Generative AI. It streamlines the hiring pipeline through automated resume parsing and candidate ranking, enhances employee development via personalized learning paths, and provides real-time insights into workforce sentiment and wellness.

## Project Structure

```
├── backend/                        # Flask backend application
│   ├── app_modular.py              # Main application entry point
│   ├── models.py                   # SQLAlchemy database models
│   ├── swagger.yaml                # API Documentation
│   ├── requirements.txt            # Python dependencies
│   ├── routes/                     # API Route Controllers
│   │   ├── analytics_routes.py
│   │   ├── auth_routes.py
│   │   ├── employee_routes.py
│   │   ├── recruitment_routes.py
│   │   └── ...
│   ├── utils/                      # AI & Helper Utilities
│   │   ├── ai_chatbot.py           # RAG-based Chatbot logic
│   │   ├── ai_jd_generator.py      # Job Description Generator
│   │   ├── ai_ranking.py           # Candidate Scoring
│   │   ├── ai_resume_parser.py     # PDF Resume Parsing
│   │   └── ...
│   └── uploads/                    # Storage for uploaded resumes
├── frontend/                       # Vue.js frontend application
│   ├── index.html
│   ├── package.json                # Node.js dependencies
│   ├── vite.config.js
│   ├── tailwind.config.js
│   └── src/
│       ├── App.vue
│       ├── main.js
│       ├── config/
│       │   └── axios.js            # HTTP Client configuration
│       ├── components/             # Reusable UI components
│       ├── stores/                 # Pinia State Management
│       │   ├── auth.js
│   │   │   ├── chatbot.js
│   │   │   └── ...
│       └── views/                  # Application Pages
│           ├── AdminDashboard.vue
│           ├── EmployeeDashboard.vue
│           ├── RecruitmentView.vue
│           └── ...
├── LICENSE
└── README.md                       # Project documentation
```

## Getting Started

### Prerequisites

- Node.js (v16+)
- Python (v3.10+)
- Google Gemini API Key

### Backend Setup

1.  Navigate to the backend directory:

    ```bash
    cd backend
    ```

2.  Create and activate a virtual environment:

    ```bash
    python -m venv venv
    # Windows
    venv\Scripts\activate
    # Mac/Linux
    source venv/bin/activate
    ```

3.  Install dependencies:

    ```bash
    pip install -r requirements.txt
    ```

4.  Configure Environment Variables:
    Create a `.env` file in the `backend/` directory:

    ```env
    GEMINI_API_KEY=your_google_gemini_api_key_here
    JWT_SECRET_KEY=super-secret-key
    ```

5.  Initialize the Database and Run the Server:
    ```bash
    # This will create talentgenie.db and start the server on port 5001
    python app_modular.py
    ```

### Frontend Setup

1.  Navigate to the frontend directory:

    ```bash
    cd frontend
    ```

2.  Install Node dependencies:

    ```bash
    npm install
    ```

3.  Run the development server:
    ```bash
    npm run dev
    ```
    Access the app at `http://localhost:5173`.

### Demo Credentials

The system is pre-seeded with the following accounts (see `backend/create_users.py`):

- **HR Manager**:
  - Email: `hr@company.com`
  - Password: `password123`
- **Employee**:
  - Email: `employee@company.com`
  - Password: `password123`

## Features

### 🤖 AI-Powered Recruitment

- **Resume Parsing:** Automatically extracts skills, experience, and contact info from PDF/DOCX resumes.
- **Candidate Ranking:** Uses LLMs to score candidates (0-100%) against specific job descriptions.
- **Smart Job Descriptions:** Generates professional JDs based on minimal input (title, seniority).
- **Interview Guide:** Generates tailored interview questions based on the candidate resume and the job role.

### 📊 Workforce Analytics

- **Dashboard:** Real-time metrics on absenteeism, retention risk, and training completion.
- **Sentiment Analysis:** Analyzes employee feedback to identify key themes (e.g., Work-Life Balance, Compensation) and sentiment trends.

### 🎓 Learning & Development

- **Adaptive Learning Paths:** Generates personalized career roadmaps and training modules based on current roles and career goals.
- **Skill Gap Analysis:** Recommends specific skills to bridge the gap between current competencies and target roles.

### 💬 Employee Services

- **AI HR Chatbot:** A RAG-enabled chatbot that answers employee questions about company policies, leave balances, and benefits.
- **Leave Management:** Streamlined request and approval workflow with calendar integration.
- **Wellness Hub:** Resources for mental and physical health, including tip generation and event tracking.

## 📑 API Documentation

The backend provides a comprehensive Swagger/OpenAPI documentation.
Once the backend is running, the API capabilities map can be found in `backend/swagger.yaml`.

**Core Endpoints:**

- `POST /api/auth/login` - User authentication
- `POST /api/recruitment/upload` - Resume processing
- `POST /api/askhr/chat` - AI Chatbot interaction
- `GET /api/analytics/summary` - HR Metrics
- `POST /api/learning/path/generate` - Learning path creation

## 🧪 Testing

The project includes several utility scripts for testing backend functionality located in the `backend/` directory.

### Backend Testing

To test specific modules, run the standalone scripts:

```bash
cd backend

# Test performance logging logic
python test_performance.py

# Verify database content
python debug_db_content.py

# Update/Verify database schema
python update_db_schema_combined.py
```

### Frontend Linting

To ensure code quality in the Vue application:

```bash
cd frontend
npm run lint
```

## Tech Stack

- **Frontend:** Vue 3, Vite, Tailwind CSS, Pinia (State Management), Axios, ApexCharts.
- **Backend:** Flask, SQLAlchemy (SQLite), Flask-JWT-Extended.
- **AI/LLM:** Google Generative AI (Gemini 2.5 Flash).
- **Tools:** PyPDF2 (PDF Parsing), Swagger (API Docs).

## License

See the `LICENSE` file for details.

---

## Local Backend Setup (MacOS)

- Created isolated virtual environment
- Resolved dependency conflicts
- Fixed invalid package versions
- Added missing libraries
- Successfully validated secured API endpoints

Backend tested locally on MacOS.

## Backend Setup (MacOS)

- Created isolated Python virtual environment
- Resolved dependency conflicts during installation
- Fixed invalid package versions
- Added missing libraries (PyYAML)
- Successfully started the modular Flask server
- Validated authenticated API routes locally

Backend tested and stabilized on MacOS.
