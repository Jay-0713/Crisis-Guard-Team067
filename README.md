...README placeholder...# WhatsApp Fake News & Threat Detection Bot

This project is a full WhatsApp bot that detects:
- ✔ Fake news & misinformation (Google Fact Check API)
- ✔ Malicious / phishing URLs (Google Safe Browsing + heuristics)
- ✔ Fake / edited images (EXIF, pHash, Google Vision Web Detection)
- ✔ Suspicious content & scam indicators
- ✔ Auto-logging of all activity into CSV & Excel
- ✔ Auto-saving of images + analysis text

It runs on:
- Python (Flask)
- Twilio WhatsApp Sandbox / WhatsApp Business API
- Google Vision API (REST, API Key only — no JSON needed)
- Google Fact Check Tools API
- Ngrok (for local development)
- Docker (optional, production-ready)

---

## 📁 Project Structure


.
├── app.py # Main Flask webhook logic
├── data_store.py # CSV/Excel logging + image saving
├── requirements.txt
├── README.md
├── saved_data/
│ ├── data.csv
│ └── data.xlsx
└── saved_media/
├── images/
└── texts/


---

## ⚡ Features

### 📰 **Fake News Detection**
- Uses Google Fact Check Tools API
- Generates a clean summary with publisher, rating, link
- Assigns a confidence score (0–100) with reasoning

### 🔗 **Malicious URL Scanner**
- Google Safe Browsing Lookup API
- Domain heuristics for phishing patterns
- Detects malware sites, scams, “verify-login”, etc.
- Logs all URLs with verdicts

### 🖼 **Fake / Edited Image Detection**
- Downloads image from WhatsApp
- EXIF metadata inspection
- pHash similarity matching
- Google Vision Web Detection
- Matches known hoax images
- Saves:
  - original image (`saved_media/images/…`)
  - analysis text (`saved_media/texts/…`)

### 🗂 **Logging (CSV + Excel)**
Everything is saved automatically:
- `saved_data/data.csv`
- `saved_data/data.xlsx`
- Images & text analysis files

This makes your bot ready for:
- audits
- analytics dashboards
- admin review tools

---

## 🛠 Installation & Setup

### 1. Create virtual environment

**macOS / Linux**
```bash
python3 -m venv venv
source venv/bin/activate

YouTube Link: https://youtu.be/BgvICjPIYZw
