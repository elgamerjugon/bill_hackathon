# Bill SaaS 💳📊

Bill SaaS is an AI-powered platform that transforms raw credit card statements (PDFs) into actionable financial insights.

The product is designed primarily for **entrepreneurs and small business owners** who use one or more credit cards for both personal and business expenses and want clarity, control, and better financial decisions.

---

## 🚀 What Problem Does It Solve?

- Credit card statements come in messy PDFs
- Bank categories are generic and often wrong
- Personal and business expenses are mixed
- Financial decisions are made without real visibility

**Financial Insights AI translates spending behavior into clarity and education.**

---

## 🧠 What Does the MVP Do?

1. Upload one or more credit card statement PDFs
2. Automatically extract transactions
3. Classify expenses across multiple dimensions:
   - Personal vs Business
   - Fixed / Variable / Investment
   - Financial quality (necessary, optimizable, risky)
4. Generate:
   - Monthly summaries
   - Visual breakdowns
   - AI-driven financial insights and recommendations

---

## 🏗️ Tech Stack

### Backend
- Python
- FastAPI
- SQLite
- pdfplumber
- OpenAI (LLM-based classification & insights)
- Pydantic

### Frontend
- Streamlit
- Plotly

### Infrastructure (optional)
- Docker
- Render / Railway (deployment)

---

## 🧩 Project Structure

- `backend/` → API, AI logic, PDF parsing, database
- `frontend/` → Streamlit MVP interface
- `data/` → Sample PDFs for demo/testing
- `prompts/` → Versioned LLM prompts

---

## ▶️ How to Run Locally

### 1. Clone the repository
```bash
git clone https://github.com/your-org/financial-insights-ai.git
cd financial-insights-ai

financial-insights-ai/
│
├── README.md
├── .gitignore
├── docker-compose.yml          # optional, for infra later
│
├── backend/
│   ├── app/
│   │   ├── main.py              # FastAPI entrypoint
│   │   │
│   │   ├── api/
│   │   │   ├── __init__.py
│   │   │   └── routes.py        # API endpoints
│   │   │
│   │   ├── core/
│   │   │   ├── config.py        # env vars, settings
│   │   │   └── logging.py
│   │   │
│   │   ├── models/
│   │   │   ├── __init__.py
│   │   │   └── schemas.py       # Pydantic models
│   │   │
│   │   ├── services/
│   │   │   ├── pdf_parser.py    # PDF extraction logic
│   │   │   ├── categorizer.py   # rules + LLM classification
│   │   │   ├── insights.py      # financial insights engine
│   │   │   └── llm_client.py    # OpenAI / LLM wrapper
│   │   │
│   │   ├── prompts/
│   │   │   ├── classify.txt
│   │   │   └── insights.txt
│   │   │
│   │   ├── db/
│   │   │   ├── database.py      # SQLite connection
│   │   │   └── models.py        # ORM models (optional)
│   │   │
│   │   └── utils/
│   │       └── helpers.py
│   │
│   ├── tests/
│   │   └── test_basic.py
│   │
│   ├── requirements.txt
│   └── Dockerfile
│
├── frontend/
│   ├── streamlit_app.py         # MVP frontend
│   └── components.py
│
└── data/
    └── sample_statements/       # sample PDFs for demo
