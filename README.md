# NetSense 

> **AI-powered Wi-Fi reliability and network diagnostics platform for remote workers, students, and everyday users**

---

## Problem Statement

Reliable internet connectivity is essential for remote work, online meetings, gaming, streaming, and everyday browsing.

However, a simple speed test does not always tell the complete story. A connection may have high download speed but still perform poorly because of:

- High latency
- Network jitter
- Packet loss
- Weak signal strength
- Network congestion
- Too many connected devices
- Unstable connectivity

Users often know that their internet is slow or unstable, but do not know **why** it is happening or what they should do about it.

NetSense aims to provide an intelligent and understandable way to evaluate network reliability and identify potential causes of poor connectivity.

---

## Solution

**NetSense** is a network reliability and diagnostics platform that analyzes multiple network conditions to provide a comprehensive assessment of connectivity.

The platform combines:

- Network performance analysis
- Machine learning-based quality classification
- Network quality scoring
- Intelligent recommendations
- Historical network analysis
- AI-powered diagnostics
- Retrieval-augmented troubleshooting

The goal is to answer not only:

> "How fast is my internet?"

but also:

> **"How reliable is my connection, what is affecting it, and what can I do about it?"**

---

## Key Features

### Network Quality Analysis

NetSense analyzes multiple network parameters instead of relying only on download speed.

The system considers:

- Download speed
- Upload speed
- Ping / latency
- Jitter
- Packet loss
- Signal strength
- Number of connected users
- Time of day
- Location type

---

### Machine Learning-Based Quality Classification

The current implementation uses a Machine Learning model to classify network conditions into different quality levels:

- Excellent
- Good
- Moderate
- Poor

The model evaluates multiple network parameters together to provide a more comprehensive assessment of connectivity.

---

### Network Quality Score

NetSense generates a numerical quality score based on the observed network conditions.

Example:

```text
Network Score: 78/100

Status: Good

Recommendation:
Suitable for normal browsing and remote work.
## 🏗️ Project Architecture

```
Frontend (UI)
        ↓
Speed Test UI
        ↓
FastAPI Backend
        ↓
AI Model (Decision Tree)
        ↓
Trust Score + Recommendation
        ↓
(Optional) Database
```

---

## 📁 Project Structure

```text
netsense/
│
├── frontend/
│   ├── index.html              # Main page
│   ├── test.html               # Run Wi-Fi test
│   ├── result.html             # Show results
│   ├── map.html                # Nearby places (future enhancement)
│   │
│   ├── css/
│   │   └── styles.css
│   │
│   └── js/
│       ├── app.js              # General application logic
│       ├── api.js              # API calls
│       ├── wifi.js             # Wi-Fi testing and scoring
│       └── map.js              # Map functionality (future enhancement)
│
├── backend/                    # FastAPI server
│   ├── app/
│   │   ├── main.py             # Application entry point
│   │   │
│   │   ├── routes/             # API routes
│   │   │   ├── wifi.py
│   │   │   └── recommendation.py
│   │   │
│   │   ├── models/             # Data models
│   │   │   └── wifi_model.py
│   │   │
│   │   ├── services/           # Business logic
│   │   │   ├── wifi_service.py
│   │   │   └── ai_service.py
│   │   │
│   │   ├── db/                 # Database connection
│   │   │   └── database.py
│   │   │
│   │   └── utils/
│   │       └── score_calculator.py
│   │
│   ├── ai-model/               # Machine learning model
│   │   ├── train.py
│   │   ├── model.pkl
│   │   ├── columns.pkl
│   │   └── dataset.csv
│   │
│   ├── requirements.txt
│   └── run.py
│
├── docs/                       # Documentation
│   ├── architecture.md
│   └── api-docs.md
│
├── .env                        # Environment variables
├── .gitignore
└── README.md

## ⚙️ Tech Stack

### Frontend

* HTML, CSS
* JavaScript

### Backend

* FastAPI
* Python

### AI / ML

* Scikit-learn
* Decision Tree Classifier

### Database (Optional)

* SQLite

---

## 🚀 How It Works

1. User clicks **Start Test**
2. UI simulates speed testing
3. Network parameters are collected
4. Data sent to backend API
5. AI model predicts:

   * Trust Score
   * Status
   * Recommendation
6. Results displayed to user

---

## 📡 API Endpoint

### POST `/recommend`

#### Request:

```json
{
  "download": 65,
  "upload": 12,
  "ping": 20,
  "jitter": 5,
  "users_connected": 20,
  "signal_strength": -60,
  "packet_loss": 1,
  "time_of_day": "afternoon",
  "location_type": "hotel"
}
```

---

#### Response:

```json
{
  "trust_score": 78,
  "status": "Good 👍",
  "recommendation": "Good for normal work"
}
```

---

## 🛠️ Installation & Setup

### 1️⃣ Clone Repository

```
git clone https://github.com/your-username/netverity-ai.git
cd netverity-ai
```

---

### 2️⃣ Backend Setup

```
cd backend
pip install -r requirements.txt
uvicorn app.main:app --reload
```

---

### 3️⃣ Frontend Setup

```
cd frontend
npm install
npm run dev
```

---

### 4️⃣ Train AI Model

```
cd ai-model
python train.py
```

---

