# JobSync 🔄

<div align="center">

**A powerful job aggregation platform with automated LinkedIn scraping and smart filtering**

![Python](https://img.shields.io/badge/Python-3.9+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-2.3-000000?style=for-the-badge&logo=flask&logoColor=white)
![React](https://img.shields.io/badge/React-18-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![Selenium](https://img.shields.io/badge/Selenium-4.15-43B02A?style=for-the-badge&logo=selenium&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white)

</div>

---

## 📖 Overview

JobSync is a full-stack job listing aggregator that combines **automated web scraping** with a **modern React interface**. It scrapes job listings from LinkedIn using Selenium with anti-detection measures, stores them in a SQLite database, and presents them through a beautiful, filterable dashboard.

Whether you're actively job hunting or just keeping an eye on the market, JobSync brings all the relevant opportunities to one centralized location.

---

## ✨ Features

### 🤖 Intelligent Web Scraping
- **LinkedIn Integration** — Automated scraping of job listings from LinkedIn
- **Anti-Detection Measures** — Randomized user agents, human-like delays, and stealth browser settings
- **Smart Filtering** — Prioritizes full-time, mid-to-senior level positions with Easy Apply enabled
- **Experience Level Detection** — Automatically extracts experience levels from job titles

### 📊 Dashboard & Analytics
- **Real-time Statistics** — View total jobs, scraped vs manual entries, top companies, and locations
- **Global Search** — Search across job titles, companies, and locations
- **Advanced Filtering** — Filter by location, company, job type, and experience level
- **Multi-Column Sorting** — Sort by date, title, company, or location

### 💼 Job Management
- **Manual Job Entry** — Add job listings manually with a comprehensive form
- **CRUD Operations** — Create, read, update, and delete job listings
- **Duplicate Prevention** — Automatically skips duplicate entries during scraping

### 🎨 Modern UI/UX
- **Responsive Design** — Works seamlessly on desktop and mobile
- **Hero Section** — Eye-catching search interface with job count display
- **Job Cards** — Clean, scannable job cards with key information at a glance
- **Modal Dialogs** — Smooth modal interactions for adding jobs

---

## 🏗️ Architecture

```
JobSync/
├── Backend/                    # Flask API Server
│   ├── app.py                 # Application factory & entry point
│   ├── routes.py              # RESTful API endpoints
│   ├── models.py              # SQLAlchemy Job model
│   ├── database.py            # Database configuration
│   ├── selenium_scraper.py    # LinkedIn scraper with anti-detection
│   └── requirements.txt       # Python dependencies
│
└── Frontend/                   # React Application
    ├── src/
    │   ├── App.js             # Main application component
    │   ├── App.css            # Global styles
    │   ├── components/
    │   │   ├── Header.js      # Navigation header
    │   │   ├── HeroSection.js # Search hero section
    │   │   ├── JobCard.js     # Individual job card
    │   │   ├── FilterSidebar.js # Filtering controls
    │   │   └── AddJobModal.js # Job submission modal
    │   ├── screens/
    │   │   └── JobListScreen.js
    │   └── services/
    │       └── BackendService.js
    └── package.json
```

---

## 🚀 Getting Started

### Prerequisites

- **Python 3.9+**
- **Node.js 16+** & npm
- **Google Chrome** (for Selenium scraping)
- **ChromeDriver** (auto-managed via webdriver-manager)

### Backend Setup

1. **Navigate to the backend directory:**
   ```bash
   cd Backend
   ```

2. **Create and activate a virtual environment:**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the Flask server:**
   ```bash
   python app.py
   ```
   The API will be available at `http://localhost:5000`

### Frontend Setup

1. **Navigate to the frontend directory:**
   ```bash
   cd Frontend
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Start the development server:**
   ```bash
   npm start
   ```
   The app will open at `http://localhost:3000`

---

## 🔌 API Reference

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/api/jobs` | Fetch all jobs with optional filters |
| `POST` | `/api/jobs` | Add a new job listing |
| `PUT` | `/api/jobs/:id` | Update an existing job |
| `DELETE` | `/api/jobs/:id` | Delete a job listing |
| `GET` | `/api/stats` | Get dashboard statistics |
| `GET/POST` | `/api/scrape` | Trigger LinkedIn scraping |
| `GET` | `/api/health` | Health check endpoint |

### Query Parameters for `/api/jobs`

| Parameter | Type | Description |
|-----------|------|-------------|
| `location` | string | Filter by location |
| `company` | string | Filter by company name |
| `job_type` | string | Filter by job type (Full-time, Part-time, etc.) |
| `experience` | string | Filter by experience level |
| `sort_by` | string | Sort field (posted_date, title, company, location) |
| `sort_order` | string | Sort direction (asc, desc) |

---

## 🛠️ Tech Stack

### Backend
- **Flask** — Lightweight Python web framework
- **Flask-SQLAlchemy** — ORM for database operations
- **Flask-CORS** — Cross-origin resource sharing
- **Selenium** — Browser automation for web scraping
- **Fake-UserAgent** — Random user agent generation

### Frontend
- **React 18** — Component-based UI library
- **Create React App** — Zero-config React tooling
- **CSS3** — Modern styling with custom properties

### Database
- **SQLite** — Lightweight, file-based database

---

## ⚠️ Disclaimer

This project is intended for **educational and personal use only**. Web scraping may violate the terms of service of certain websites. Please:

- Review and comply with LinkedIn's Terms of Service
- Use scraping responsibly and ethically
- Implement appropriate rate limiting
- Consider using official APIs where available

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).

---
