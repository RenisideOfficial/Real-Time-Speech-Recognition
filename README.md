---
# 🎙️ Real-Time Voice Recognition with WebSockets

A lightweight system for **live speech-to-text transcription** using WebSockets. The project streams microphone audio to the backend, transcribes it in real-time, and displays the results instantly in the browser.
---

## ✨ Features

- 🎤 **Microphone recording** directly in the browser
- 🔗 **WebSocket streaming** for low-latency communication
- 📝 **Real-time transcription** (word-by-word / sentence-by-sentence)
- 📜 **Final transcripts panel** with auto-scrolling
- ⚡ Powered by **Django Channels** and a modular `voice` engine

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/RenisideOfficial/Real-Time-Speech-Recognition.git
cd Real-Time-Speech-Recognition
```

### 2. Backend setup (Django + Channels)

```bash
python -m venv .venv
source '.venv'/bin/activate   # On Windows: . '.venv'\Scripts\activate
pip install -r requirements.txt
```

Run the Django server (with Daphne or Uvicorn) on the terminal:

```bash
daphne main.asgi:application
```

### 3. Frontend setup

Simply open the `index.html` in your browser

---

## 📂 Project Structure

```
alpha/
│
│── backend/                        # Django backend
│   ├── asgi.py                     # ASGI entrypoint for Django Channels
│   ├── settings.py                 # Django project configuration
│   │
│   ├── commands/                   # WebSocket app for handling voice commands
│   │   ├── consumers.py            # WebSocket consumer (streams audio, returns transcripts)
│   │   ├── routing.py              # WebSocket URL routing
│   │   └── __init__.py
│   │
│   ├── voice/                      # Voice engine logic
│   │   ├── speech.py               # Handles voice chunking & speech recognition
│   │   └── __init__.py             # Makes `voice` a Python package
│   │
│   ├── main/                       # Core Django app
│   │   ├── wsgi.py                 # WSGI entrypoint (if needed for non-async servers)
│   │   └── urls.py                 # URL routing for HTTP views
│   │
│   └── requirements.txt            # Python dependencies (Django, Channels, SpeechRecognition, etc.)
│
│── frontend/
│   ├── index.html                  # Main UI page (records voice + displays transcripts)
│   ├── js/
│   │   └── script.js               # Handles WebSocket connection & real-time transcription
│   ├── styles/
│   │   └── styles.css              # Basic styling for panels, transcripts, buttons
│   └── img/                        # Any icons, assets, or images used in the UI
│
│── .gitignore                      # Ignored files (venv, DBs, node_modules, etc.)
│── README.md                       # Project documentation

```

---

## 🖼️ Demo Flow

1. Click **Start Recording**
2. Speak into your microphone
3. Watch the **transcripts appear in real-time**
4. Final results are stored in the transcripts panel

---

## 🔧 Tech Stack

- **Backend:** Django, Django Channels, WebSockets
- **Speech:** SpeechRecognition / Whisper (configurable)
- **Frontend:** Vanilla JS + WebSocket API

---

## 📌 Roadmap

- [ ] Add **speaker diarization** (who’s talking)
- [ ] Support **multiple languages**
- [ ] Add **real-time translation**
- [ ] Store transcripts in a database

---

## 🤝 Contributing

Pull requests are welcome! For major changes, please open an issue first to discuss what you’d like to change.

---

## 📜 License

MIT License © 2025 Ezika Chinweike

---
