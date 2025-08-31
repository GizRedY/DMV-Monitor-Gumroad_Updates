# DMV Monitor — NC DMV Appointment Tracker (Windows)

A desktop app that monitors North Carolina DMV appointment availability and notifies you when new slots appear. Built with **Python**, **Flask + Socket.IO**, and **Playwright**, packaged for Windows.

> **Note**  
> This repository hosts **release builds** and the **update manifest (JSON)**. Source code is **not** published here.

---

## 📥 Download

Get the latest installer from **[Releases](https://github.com/GizRedY/DMV-Monitor-Gumroad_Updates/releases)**.

---

## 🗂 What’s in this repo

- **Update manifest (JSON)** used by the app’s auto-update mechanism  
- **Releases** with packaged Windows builds  
- This README and (optionally) screenshots/GIFs

---

## ✨ Highlights

- Real-time monitoring UI with live logs and status indicators  
- Push notifications via **Pushbullet** (Android supported)  
- Windows packaging (single executable), **single-instance** guard  
- Background **auto-update** driven by this repo’s JSON manifest  
- Clean startup/shutdown routines and user-friendly error handling

---

## 🧭 How it works (high-level)

```mermaid
flowchart LR
  U[User] --> APP[DMV Monitor (Windows EXE)]
  APP <---> UI[Embedded HTML UI / Socket.IO]
  APP --> PW[Playwright Chromium]
  APP --> DMV[NC DMV website]
  APP --> PB[Pushbullet API]
  APP --> GH[GitHub JSON Manifest]
The app periodically checks DMV availability using a headless browser (Playwright).

Results stream to the UI over Socket.IO.

When a new slot is detected, a Pushbullet notification is sent.

On startup, the app compares its version with the update manifest hosted in this repo and offers an in-app update if a newer build is available.

🚀 Quick Start (End-Users)

Download the latest installer from Releases

Install and run DMV Monitor on Windows 10/11

(Optional) Open Settings → Notifications and paste your Pushbullet Access Token

Click “Send Test Notification” to confirm delivery, then start monitoring

iOS: Pushbullet is Android-focused; iPhone push flow not supported currently.

🔄 Auto-Update

The app reads an update manifest (JSON) in this repository

If a newer version is available, you’ll be prompted to update in-app

You can also manually download the latest build from Releases

If you rename or relocate the manifest file, update the app’s config accordingly (the manifest URL is configurable in app settings/build config).

🔐 Privacy & Security

Your Pushbullet token is stored locally on your device

The app sends notifications only to the configured Pushbullet account

No personal data is uploaded to this repository

⚖️ Ethical Use

Please respect DMV terms and avoid aggressive polling. This tool is for personal convenience only and does not guarantee appointment availability.

🧩 For Hiring Managers (what this demonstrates)

Desktop packaging of a Python app and auto-update pipeline via GitHub

Browser automation with Playwright and a real-time Socket.IO UI

External notification integration (Pushbullet)

Operational guardrails: single-instance lock, safe startup/shutdown

Product thinking: onboarding flow, status/health indicators, and update UX

🗺 Roadmap

Alternative notification channels (including iOS-friendly options)

Adjustable polling profiles and back-off strategies

Cross-platform dev convenience

🖼 Screenshots / Demo

Add screenshots or a short GIF here (loading screen, settings, “slot found” log, test notification confirmation).

📬 Contact

Mikhail Drogalev — Durham, NC
LinkedIn: https://www.linkedin.com/in/mikhail-drogalev-a4bbab341/

(This repository is part of my portfolio; source code available for discussion during interviews.)
