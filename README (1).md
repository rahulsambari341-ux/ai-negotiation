# 🤝 AI Negotiation Simulator (Flask + Ollama)

![Python](https://img.shields.io/badge/python-3.10%2B-blue?logo=python)
![Flask](https://img.shields.io/badge/Flask-2.3-green?logo=flask)
![Ollama](https://img.shields.io/badge/Ollama-LLaMA--3.1-orange?logo=openai)
![License](https://img.shields.io/badge/license-MIT-lightgrey)
![Status](https://img.shields.io/badge/status-active-success)

An **AI-powered negotiation simulator** where a **Buyer** and a **Seller** negotiate over a product price.  
Agents follow different **personas** (Aggressive Trader, Smooth Diplomat, Data-Driven Analyst)  
and interact through natural language powered by **Ollama (LLaMA 3.1)**.

---

## 📂 Project Structure

negotiation-app/
│── app.py # Flask backend with negotiation logic
│── templates/
│ └── index.html # Simple frontend form
│── venv/ # Virtual environment (optional)


---

## 🚀 Features
- 🤖 Two AI negotiation agents (**Buyer & Seller**)  
- 🎭 Supports **multiple personas** with distinct strategies  
- ⏱️ Time-limited negotiation rounds  
- 💬 Conversation history with ₹ price offers  
- 🌐 REST API built with **Flask**  
- 🖥️ Simple HTML UI for testing  

---

## ⚡ Setup Instructions

### 1️⃣ Clone Repository
```bash
git clone https://github.com/<your-username>/negotiation-app.git
cd negotiation-app

2️⃣ Create Virtual Environment
python -m venv venv


Activate it:

Windows (PowerShell)

.\venv\Scripts\Activate.ps1


Linux / Mac

source venv/bin/activate

3️⃣ Install Dependencies
pip install flask ollama

4️⃣ Run Flask Server
python app.py


Server will start at:
👉 http://127.0.0.1:5000

🌐 Usage
🔹 Web UI

Open http://127.0.0.1:5000 → fill form → start negotiation.

🔹 API Endpoint

POST /negotiate

Example Request
{
  "product_name": "Laptop",
  "market_price": 50000,
  "seller_price": 45000,
  "buyer_price": 48000,
  "seller_persona": "Aggressive Trader",
  "buyer_persona": "Smooth Diplomat",
  "turns": 6,
  "time_limit_sec": 120
}

Example Request
{
  "conversation": [
    "Seller: Let's begin. I have a great deal on Laptop.",
    "Seller: Clock’s ticking! Final price: ₹45000. Take it or leave it.",
    "Buyer: Time is almost up! Let's settle for ₹48000 — deal?"
  ],
  "deal": true,
  "final_price": 48000
}

git clone https://github.com/<your-username>/negotiation-app.git
cd negotiation-app


Example Response
{
  "conversation": [
    "Seller: Let's begin. I have a great deal on Laptop.",
    "Seller: Clock’s ticking! Final price: ₹45000. Take it or leave it.",
    "Buyer: Time is almost up! Let's settle for ₹48000 — deal?"
  ],
  "deal": true,
  "final_price": 48000
}

🎭 Personas

Aggressive Trader → pushy, final-offer style

Smooth Diplomat → collaborative, partnership tone

Data-Driven Analyst → logical, stats & market-driven

⚠️ Notes

Requires Ollama installed locally. Ensure model llama3.1:8b is available.

Flask’s dev server is for development only. For production, use Gunicorn / Uvicorn + Nginx.

📜 License

This project is licensed under the MIT License.

✨ Ready to negotiate like a pro with AI ✨


---

✅ This will look **professional on GitHub** with badges on top.  

Do you also want me to add a **demo screenshot section** (where you can later add UI or conversation screenshots)?
Negotiation Simulator

Negotiation Simulator — a simple web app that simulates an AI buyer and seller negotiating a price for an item. Built as a lightweight Flask front-end that calls local AI agents (LLaMA / Ollama in my setup) for generating persona-based negotiation dialogues.

Demo screenshots

(Saved screenshots are referenced from screenshots/)
### Screenshot 1 — Pen negotiation
![Pen negotiation screenshot](screenshots/IMG-20250818-WA0012.jpg)

### Screenshot 2 — Bag negotiation (deal reached / not reached)
![Bag negotiation screenshot](screenshots/IMG-20250818-WA0011.jpg)

### Screenshot 3 — Alternate bag negotiation view
![Bag negotiation screenshot 2](screenshots/IMG-20250818-WA0010.jpg)
Features

Choose seller & buyer persona (e.g. Smooth Diplomat, Aggressive Trader, Data-Driven Analyst).

Configure item name, market price, seller asking price, buyer max budget.

Simulated negotiation dialogue with final outcome (deal reached or no deal).

Simple, copyable UI for demonstration and education.

Tech stack

Python 3.10+

Flask (web UI)

Ollama / LLaMA model (local model endpoint used for agent responses) — replace with your local model or API call if unavailable.

HTML + Bootstrap (basic styling)

Quick start (local)

Clone the repo:

git clone https://github.com/<your-github-username>/<repo-name>.git
cd <repo-name>


Create and activate a venv:

python -m venv venv
# Windows
venv\Scripts\activate
# macOS / Linux
source venv/bin/activate


Install requirements:

pip install -r requirements.txt


(If you don't have requirements.txt, typical packages are flask, ollama or whichever client you use.)

Set environment variables if needed (example):

# export OLLAMA_HOST=localhost
# export OLLAMA_API_KEY=your_key_if_required


Run the app:

python app.py
# or
flask run


Open http://127.0.0.1:5000 in your browser.

How to include screenshots in the repo

Create a folder screenshots at repo root:

mkdir screenshots


Copy the three images into screenshots/:

IMG-20250818-WA0010.jpg

IMG-20250818-WA0011.jpg

IMG-20250818-WA0012.jpg

Use the markdown snippet above inside your README.md to show them.

Commit & push to GitHub
git add README.md screenshots/IMG-20250818-WA0010.jpg screenshots/IMG-20250818-WA0011.jpg screenshots/IMG-20250818-WA0012.jpg
git commit -m "Add README and demo screenshots"
git push origin main


(Adjust branch name if you use master or another branch.)

Personas & usage notes

The personas are text prompts used to shape the model responses. Keep them short and consistent to avoid persona drift.

For deterministic behavior consider using a temperature close to 0.2 (if using an API that supports temperature).

If your model returns very long outputs, you can post-process to extract just the negotiation messages.

License

Choose a license (e.g. MIT). Example:

MIT License
Copyright (c) 2025 <your name>

Contact / GitHub

If you’d like to link your GitHub profile in the README, replace the placeholder below with your username:

**Author:** [Your Name](https://github.com/<your-github-username>)
