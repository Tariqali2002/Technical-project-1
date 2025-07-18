# Devloper-Tariq/Project-GenAI
Multi-Functional Python Application:

A comprehensive AI-integrated desktop utility leveraging OpenCV, MediaPipe, LangChain (Gemini Pro), Geopy, SMTP, and Tkinter — built for real-world automation, productivity, and computer vision tasks.

🧩 Overview

This project is a Tkinter-based multi-functional Python GUI application that seamlessly integrates:

📷 Real-time camera sketch filter

📍 Location coordinate extraction

📧 Email automation (SMTP)

🌐 Browser & system-level shortcuts

🔍 Web search utilities

🤖 LangChain + Gemini Pro AI agent

✋ Hand gesture recognition using MediaPipe Holistic

📊 System Architecture

                +-------------------------------+
                |          Tkinter GUI          |
                +-------------------------------+
                  |       |       |      |     |
        +---------+       |       |      |     +-------------------+
        |                 |       |      |                         |
+---------------+ +--------------------+ +-----------------+ +----------------+
| OpenCV Sketch | |    Email Sender     | |  AI Chat Agent  | | App Shortcuts  |
|   (Webcam)    | | (SMTP + Gmail Auth) | | (LangChain +    | |  (Browser /    |
|               | |                    | | Gemini Pro)     | | Subprocess)    |
+---------------+ +--------------------+ +-----------------+ +----------------+
                                   |
                      +-------------------------+
                      | Geolocation via Geopy   |
                      +-------------------------+
                                   |
                     +----------------------------+
                     | MediaPipe Gesture Detection |
                     +----------------------------+

🧱 Tech Stack

Layer

Libraries / Tools

GUI

tkinter

AI Agent

langchain, langchain-google-genai, serpapi

Geolocation

geopy

Vision

opencv, mediapipe

Automation

smtplib, pywhatkit, subprocess, webbrowser

Sketch Filter

OpenCV Grayscale + Gaussian Blur + Divide blend

✨ Feature Breakdown

🗾️ 1. Real-Time Sketch Camera

def apply_sketch(frame):
    ...

Captures live feed from webcam.

Converts to grayscale.

Applies inverse Gaussian blur.

Creates pencil sketch using cv2.divide().

📧 2. Email Sending (Gmail SMTP)

def send_email():
    ...

Flow:

[Input Password] --> [SMTP Login] --> [Send Email] --> [Success/Failure Dialog]

Uses port 587 (TLS). Enable Gmail App Password or allow less secure apps.

📍 3. Location to Coordinates (Geopy)

def get_location_coordinates():
    ...

Uses Nominatim (OpenStreetMap) to geocode locations.

Input: New York City
Output:
  Address: New York, NY, USA
  Latitude: 40.7128
  Longitude: -74.0060

🌐 4. App Shortcuts Panel

Shortcut

Action

Gmail

Opens Gmail in browser

Camera

Launches built-in camera

Settings

Opens Windows settings

WhatsApp Web

Opens WhatsApp Web UI

def open_camera():
    subprocess.Popen('start microsoft.windows.camera:', shell=True)

🔍 5. Word Search (Google)

def search_word():
    pwk.search(word)

Opens the default browser with a search for any typed term.

🤖 6. LangChain + Gemini AI Agent

mygoogleai = initialize_agent(...)
mygoogleai.run("today date")

Flow:

[Prompt] --> [LangChain Agent] --> [Gemini Pro via Google API] --> [Response]

Uses ZERO_SHOT_REACT_DESCRIPTION agent type.

✋ 7. Gesture Detection (MediaPipe Holistic)

with mp_holistic.Holistic(...) as holistic:
    ...

Gesture

Condition (Landmarks)

Message

"Done"

Thumb tip above index tip

✅ done

"Hey"

Pinky tip above wrist

👋 hey

Uses webcam feed and real-time drawing via MediaPipe Holistic.

💾 GUI Preview

+------------------------------------------+
|     Multi-function Application (Tk)      |
|------------------------------------------|
| [ Sketch Camera ]  [ Send Email ]        |
| [ Get Coordinates ] [ Open Apps Panel ]  |
| [ Search Word ]                          |
| [ Run AI Agent ]                         |
| [ Detect Hand Gestures ]                |
+------------------------------------------+

🔐 Security Notes

Do not hardcode credentials.

Use .env files or secret managers (python-dotenv, keyring, etc.).

Keep Gemini and SerpAPI keys secured via environment variables.

🔮 How to Run

pip install -r requirements.txt
python app.py

Click UI buttons to trigger respective functionality.

📁 Suggested Folder Structure

github-multitool/
├── app.py
├── README.md
├── requirements.txt
├── assets/
│   └── gesture_sample.gif
├── .env
└── docs/
    └── architecture.png

🧠 Future Enhancements

✅ Add password masking (Tkinter Entry show="*")

🌍 Add language translation via Gemini

📦 Dockerize the project

🔐 Switch to OAuth2 for Gmail

🧼 Refactor to use MVC pattern

📄 License

MIT License

📃 About the Author

Tariq A.🧠 AI + CV Developer🌐 Passionate about Human-Computer Interaction📧 Email: ta5877286@gmail.com

