# Safe-signal-against-violence
Panic Buttom or Panic safety.
Is an MVP (Minimum Viable Product) safety system designed to explore how emergency assistance tools could be integrated into mobile applications through a lightweight SDK and API.

The project demonstrates a proof-of-concept for a **panic button system**, allowing users to discreetly trigger emergency alerts, share location, notify trusted contacts, and simulate real-time tracking.

⚠️ Disclaimer: This project is an educational and portfolio MVP only. It is **not production-ready emergency software** and should not be relied upon for real-world emergency response.

# Vision

SafeSignal aims to explore a simple but impactful question:
*How could digital platforms improve personal safety using lightweight emergency workflows?*

The MVP focuses on:

* Emergency SOS trigger
* Silent emergency mode
* GPS location sharing
* Trusted emergency contacts
* Real-time tracking simulation
* Lightweight SDK integration
* Low-cost/free-tier infrastructure
* Mobile-first UX

The system is intentionally scoped for **rapid experimentation and technical demonstration**, not mission-critical use.

# Product Concept

SafeSignal is composed of **three layers**:

### 1. Mobile App (Flutter)

A simple mobile interface where users can:

* Trigger SOS alerts
* Activate silent mode
* Share GPS location
* Add trusted contacts
* View emergency status

### 2. Backend API (FastAPI + Python)

Handles:

* Authentication
* Emergency event processing
* Contact management
* GPS updates
* SDK requests
* Notification simulation

### 3. SDK Layer

A lightweight SDK designed to simulate how external apps could integrate SafeSignal functionality.

Example:

```python
from safesignal import SafeSignal

client = SafeSignal(API_KEY)

client.trigger_alert(
    user_id="123",
    lat=-23.5,
    lng=-46.8
)

 Included

✅ SOS panic button

✅ Silent emergency trigger

✅ GPS location sharing

✅ Emergency contacts

✅ Authentication (JWT)

✅ Real-time location simulation

System Architecture

```text
                ┌──────────────────┐
                │ Flutter Mobile   │
                │ App              │
                └────────┬─────────┘
                         │ REST API
                         ▼
                ┌──────────────────┐
                │ FastAPI Backend  │
                │ Python           │
                └───────┬──────────┘
                        │
      ┌─────────────────┼─────────────────┐
      ▼                 ▼                 ▼
 ┌──────────┐    ┌──────────┐      ┌──────────┐
 │ SQLite   │    │ Firebase │      │ SDK API  │
 │ Database │    │ Realtime │      │ Layer    │
 └──────────┘    └──────────┘      └──────────┘
```

---

# Tech Stack

## Backend

* Python 3.11+
* FastAPI
* SQLAlchemy
* SQLite (MVP)
* JWT Authentication
* Uvicorn

## Mobile

* Flutter

## Realtime

* Firebase (Free Tier)

## Infrastructure

* Docker
* GitHub

# Repository Structure

```text
safe-signal-mvp/

├── backend/
│   ├── app/
│   │   ├── routes/
│   │   ├── services/
│   │   ├── models/
│   │   ├── schemas/
│   │   ├── database.py
│   │   ├── config.py
│   │   └── main.py
│   │
│   ├── requirements.txt
│   └── Dockerfile
│
├── mobile/
│   └── flutter_app/
│
├── sdk/
│   └── python_sdk/
│
├── docs/
│   ├── architecture.md
│   ├── roadmap.md
│   ├── backlog.md
│   └── tutor-python-fastapi.md
│
└── README.md


# MVP User Flow

```text
User opens app
      ↓
Presses SOS button
      ↓
Location captured
      ↓
Emergency event created
      ↓
Trusted contacts notified
      ↓
Live location shared
      ↓
Emergency session active


# Example API Routes

Authentication

```http
POST /auth/register
POST /auth/login
POST /auth/refresh
```

Emergency

```http
POST /sos/trigger
POST /sos/silent
POST /sos/cancel
```

Contacts

```http
POST /contacts/add
GET /contacts
DELETE /contacts/{id}
```

Location

```http
POST /location/update
GET /location/live/{user_id}
```

SDK

```http
POST /sdk/trigger-alert
```

---

# Development Setup

## Clone repository

```bash
git clone https://github.com/YOUR_USERNAME/safe-signal-mvp.git

## Create virtual environment

```bash
python -m venv .venv
```

Mac/Linux

```bash
source .venv/bin/activate
```

Windows

```bash
.venv\Scripts\activate
```

---

## Install dependencies

```bash
pip install -r requirements.txt
```

---

## Run backend

```bash
uvicorn app.main:app --reload
```

API:

```text
http://127.0.0.1:8000
```

Swagger Docs:

```text
http://127.0.0.1:8000/docs

# 90-Day Roadmap (Summary)

## Phase 1 — Planning & Architecture

* Define scope
* Create GitHub structure
* Define API endpoints
* Create wireframes
* Write documentation

## Phase 2 — Backend MVP

* FastAPI setup
* Authentication
* Database
* Emergency endpoints
* Contacts system

## Phase 3 — Flutter MVP

* Login screen
* Home screen
* SOS button
* Silent mode
* GPS permissions

## Phase 4 — Realtime Tracking

* Firebase integration
* Live location simulation
* Session tracking

## Phase 5 — SDK Layer

* Python SDK
* API integration examples
* Documentation

## Phase 6 — Optional AI

* Emergency phrase detection
* Keyword-based trigger

Example:

> "Cancel blue order"

Triggers simulated SOS workflow.


## Phase 7 — GitHub Polish

* Screenshots
* GIF demos
* Documentation cleanup
* Architecture diagrams

# Design Principles

SafeSignal prioritizes:

* Simplicity
* Low cost
* Fast iteration
* Developer learning
* MVP-first execution

The project intentionally avoids unnecessary engineering complexity.


# Future Improvements

Potential future versions may include:

* Voice activation
* Better encryption
* Production authentication
* Admin dashboards
* SMS integration
* Risk scoring
* Native SDK packages
* Real partner integrations

# License

MIT License
