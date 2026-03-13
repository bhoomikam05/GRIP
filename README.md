# GRIP — Public Grievance Intelligence & Resolution Platform

## Setup & Run

### Prerequisites
- Python 3.8+
- MySQL Server running locally
- pip

### Installation

```bash
# 1. Install dependencies
pip install -r requirements.txt

# 2. Configure MySQL credentials in app.py (line ~12)
DB_CONFIG = {
    'host': 'localhost',
    'user': 'root',       # ← your MySQL username
    'password': '',       # ← your MySQL password
    'database': 'grievance_db',
    'autocommit': True
}

# 3. Start the Flask server
python app.py

# 4. Open browser: http://localhost:5000
# 5. Click "Setup Database" on the homepage to initialize MySQL tables + demo data
```

## Pages
| URL | Description |
|-----|-------------|
| `/` | Citizen complaint submission form |
| `/dashboard` | Admin analytics dashboard with Chart.js |
| `/funds` | Government fund & vendor transparency |

## API Endpoints
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/setup` | Initialize DB + seed demo data |
| POST | `/api/complaints` | Submit a complaint (multipart/form-data) |
| GET | `/api/complaints` | List complaints (filterable) |
| PUT | `/api/complaints/<id>/status` | Update status |
| GET | `/api/complaints/stats` | Stats for charts |
| POST | `/api/categorize` | NLP auto-categorize text |
| GET | `/api/funds/summary` | Budget summary |
| GET | `/api/funds/allocations` | Fund allocation records |
| POST | `/api/funds/allocations` | Add new allocation |
| GET | `/api/funds/area_spending` | Area-wise spending |
| GET | `/api/vendors` | Vendor list |

## Database Tables
- `complaints` — Citizen-submitted civic complaints
- `vendors` — Registered contractors/vendors
- `fund_allocations` — Complaint-to-vendor fund assignments
- `budget_config` — Annual budget configuration
