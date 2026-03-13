<div align="center">

# 🏛️ G R I P

### **Public Grievance Intelligence & Resolution Platform**

[![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Flask](https://img.shields.io/badge/Flask-3.0-000000?style=for-the-badge&logo=flask&logoColor=white)](https://flask.palletsprojects.com)
[![SQLite](https://img.shields.io/badge/SQLite-3-003B57?style=for-the-badge&logo=sqlite&logoColor=white)](https://sqlite.org)
[![Chart.js](https://img.shields.io/badge/Chart.js-4.4-FF6384?style=for-the-badge&logo=chartdotjs&logoColor=white)](https://www.chartjs.org)
[![Leaflet](https://img.shields.io/badge/Leaflet-1.9-199900?style=for-the-badge&logo=leaflet&logoColor=white)](https://leafletjs.com)
[![License](https://img.shields.io/badge/License-MIT-F4A261?style=for-the-badge)](#license)

---

> **A modern, full-stack civic complaint management system** empowering citizens to report public issues and enabling government officials to track, resolve, and allocate resources — all through a sleek, data-driven web interface.

<br>

[🚀 Quick Start](#-quick-start) · [✨ Features](#-features) · [📸 Screenshots](#-pages--routes) · [🔌 API Reference](#-api-reference) · [🗂 Project Structure](#-project-structure)

</div>

---

## ✨ Features

### 🧑‍💻 For Citizens
| Feature | Description |
|---------|-------------|
| **📝 Smart Complaint Submission** | File civic complaints with title, description, category, area, and priority |
| **🤖 NLP Auto-Categorization** | Automatic category detection (Road, Garbage, Electricity, Water, Transport) and priority assignment using keyword-based NLP |
| **😡 Sentiment Analysis** | Built-in sentiment scorer (1–5 scale) detects citizen frustration level from complaint text |
| **📸 Geotagged Camera Capture** | On-the-spot photo capture using the device camera with automatic GPS geotagging |
| **🗺️ Interactive Map** | Leaflet-powered map for pinpointing exact complaint location with reverse geocoding |
| **⭐ Feedback & Ratings** | Rate resolved complaints and leave feedback for government accountability |
| **📊 My Complaints Dashboard** | Track complaint status, SLA timers, and geotagged coordinates from a personal dashboard |

### 🏢 For Government Officials
| Feature | Description |
|---------|-------------|
| **📊 Intelligence Dashboard** | Real-time KPIs — Total, Pending, Resolved, In Progress — with interactive Chart.js visualizations |
| **🚨 High Alert System** | Automatic flagging of overdue (7+ days), high-priority, or high-sentiment complaints |
| **🗺️ Heatmap View** | Complaint density heatmap across city areas using Leaflet circle markers |
| **📈 Trend Analytics** | Monthly complaint trends, category distribution, and area-wise breakdowns |
| **🔄 Status Management** | Update complaint status (Pending → In Progress → Resolved / Rejected) with full audit trail |
| **📥 CSV Export** | One-click export of all complaints data for offline analysis |

### 🔐 For Administrators
| Feature | Description |
|---------|-------------|
| **👥 Role Management** | Create, assign, and remove officials with area/category-specific permissions |
| **🔒 JWT Authentication** | Secure token-based authentication with session management and password hashing |
| **📋 Audit Logs** | Complete audit trail of all administrative actions across the platform |
| **💰 Fund Transparency** | Budget overview, area-wise government spending analytics, fund allocation tracking, and vendor registry with performance ratings |

### 🌐 Quick Access Resources
| Portal | Link |
|--------|------|
| 🏛️ Central Grievance Portal (CPGRAMS) | [pgportal.gov.in](https://pgportal.gov.in/Home/AboutUs) |
| 🏙️ BBMP Official Portal | [bbmp.gov.in](https://bbmp.gov.in/home) |
| 📜 National Scheme Portal | [myscheme.gov.in](https://www.myscheme.gov.in/) |

---

## 🚀 Quick Start

### Prerequisites

- **Python 3.8+**
- **pip** (Python package manager)

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/your-username/grip-platform.git
cd grip-platform

# 2. Install dependencies
pip install -r requirements.txt

# 3. Start the Flask server
python app.py

# 4. Open your browser
#    → http://localhost:5000
```

### Default Credentials

| Role | Username | Password |
|------|----------|----------|
| **Admin** | `admin` | `admin123` |
| **Citizen** | *Register via the login page* | *Self-created* |

---

## 📄 Pages & Routes

| Route | Page | Access |
|-------|------|--------|
| `/` | 📝 Complaint Submission Form | Public |
| `/login` | 🔑 Login / Register | Public |
| `/dashboard` | 📊 Official Intelligence Dashboard | Officials & Admins |
| `/citizen_dashboard` | 📋 My Complaints | Citizens |
| `/funds` | 💰 Fund & Vendor Transparency | Officials & Admins |

---

## 🔌 API Reference

### Authentication
| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/api/login` | Login with username & password |
| `POST` | `/api/register` | Register a new citizen account |
| `GET` | `/api/me` | Get current authenticated user |
| `GET` | `/logout` | Destroy session & logout |

### Complaints
| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/api/complaints` | Submit a new complaint (multipart/form-data) |
| `GET` | `/api/complaints` | List complaints (filterable by category, area, priority) |
| `PUT` | `/api/complaints/<id>/status` | Update complaint status |
| `GET` | `/api/complaints/<id>/history` | Get complaint status change timeline |
| `GET` | `/api/complaints/stats` | Aggregated statistics for dashboard charts |
| `POST` | `/api/complaints/<id>/rate` | Submit citizen rating & feedback |
| `GET` | `/api/complaints/<id>/rating` | Get rating for a resolved complaint |
| `GET` | `/api/export_complaints` | Export all complaints as CSV |

### NLP & Intelligence
| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/api/categorize` | Auto-categorize and prioritize text using NLP |

### Fund Management
| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/api/funds/summary` | Budget overview (total, used, remaining) |
| `GET` | `/api/funds/allocations` | All fund allocation records |
| `POST` | `/api/funds/allocations` | Create a new fund allocation |
| `GET` | `/api/funds/area_spending` | Area-wise spending breakdown |

### Vendors & Administration
| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/api/vendors` | List registered vendors |
| `GET` | `/api/officials` | List all officials (admin only) |
| `POST` | `/api/officials` | Add a new official (admin only) |
| `DELETE` | `/api/officials/<id>` | Remove an official (admin only) |
| `GET` | `/api/audit_logs` | View system audit logs (admin only) |

---

## 🗂 Project Structure

```
grip-platform/
├── app.py                  # Flask backend — routes, DB, NLP, auth
├── requirements.txt        # Python dependencies
├── grievance.db            # SQLite database (auto-created)
├── static/
│   └── uploads/            # User-uploaded complaint photos
└── templates/
    ├── index.html           # Complaint submission form + map
    ├── login.html           # Authentication page
    ├── dashboard.html       # Official analytics dashboard
    ├── citizen_dashboard.html  # Citizen complaint tracker
    └── funds.html           # Fund & vendor transparency
```

---

## 🗄️ Database Schema

| Table | Purpose |
|-------|---------|
| `complaints` | Citizen-submitted civic complaints with geotag coordinates |
| `complaint_history` | Full status-change audit trail per complaint |
| `users` | Citizen and official accounts with hashed passwords |
| `vendors` | Registered government contractors |
| `fund_allocations` | Complaint-to-vendor fund assignments |
| `budget_config` | Annual budget configuration |
| `feedback` | Citizen ratings and feedback for resolved complaints |
| `audit_logs` | System-wide administrative action logs |

---

## 🛠️ Tech Stack

<div align="center">

| Layer | Technology |
|-------|-----------|
| **Backend** | Python · Flask · SQLite · JWT |
| **Frontend** | HTML5 · CSS3 · Vanilla JavaScript |
| **Charts** | Chart.js 4.4 |
| **Maps** | Leaflet.js 1.9 · OpenStreetMap · Nominatim |
| **Camera** | MediaDevices API (getUserMedia) |
| **Geolocation** | Navigator Geolocation API |
| **Security** | Werkzeug password hashing · JWT tokens · CORS |
| **Fonts** | Google Fonts (Syne · DM Sans) |

</div>

---

## 📜 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

<div align="center">

**Built with ❤️ for smarter civic governance**

*GRIP — Because every grievance deserves a resolution.*

</div>
