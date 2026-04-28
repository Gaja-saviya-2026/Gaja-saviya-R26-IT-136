# 🐘 Project Gaja-Saviya
### An Intelligent Multi-Modal Framework for Human–Elephant Conflict Mitigation

![Python](https://img.shields.io/badge/Python-3.10+-blue?style=flat-square&logo=python)
![Flask](https://img.shields.io/badge/Flask-REST_API-green?style=flat-square&logo=flask)
![TensorFlow](https://img.shields.io/badge/TensorFlow-ML_Models-orange?style=flat-square&logo=tensorflow)
![React Native](https://img.shields.io/badge/React_Native-Mobile_App-61DAFB?style=flat-square&logo=react)
![Tests](https://img.shields.io/badge/Tests-20_Passed-brightgreen?style=flat-square)
![Status](https://img.shields.io/badge/Status-Active-success?style=flat-square)
![SLIIT](https://img.shields.io/badge/SLIIT-IT4010_RP-red?style=flat-square)

> **IT4010 — Research Project | SLIIT 2026**
> Group ID: **R26-IT-136** | Specialization: **Information Technology**

---

## 📌 Table of Contents

- [Project Overview](#-project-overview)
- [Problem Statement](#-problem-statement)
- [Proposed Solution](#-proposed-solution)
- [System Architecture](#-system-architecture)
- [Team Members](#-team-members)
- [Repository Structure](#-repository-structure)
- [Components](#-components)
  - [Member 01 — Sensor Fusion](#member-01--cross-modal-sensor-fusion)
  - [Member 02 — Bio-Acoustic Analyst](#member-02--bio-acoustic-behavior-analyst)
  - [Member 03 — Fence Signal Interpreter](#member-03--intelligent-fence-signal-interpreter)
  - [Member 04 — Safe-Routing Platform](#member-04--dynamic-safe-routing--trust-platform)
- [API Contract](#-api-contract)
- [Database Design](#-database-design)
- [Getting Started](#-getting-started)
- [Tech Stack](#-tech-stack)
- [Expected Results](#-expected-results)
- [Commercialization](#-commercialization)

---

## 🌍 Project Overview

**Project Gaja-Saviya** (meaning "Elephant Protection" in Sinhala) is an intelligent, AI-driven IoT framework designed to transform Human–Elephant Conflict (HEC) management in Sri Lanka from a reactive approach into a **proactive, reliable, and user-centered system**.

The system integrates **electrical sensing** and **acoustic sensing** through a single IoT Sentinel Node, applies **machine learning models** with **cross-modal validation**, and delivers **real-time decision support** to farmers through a mobile platform.

---

## 🚨 Problem Statement

Human–Elephant Conflict (HEC) remains a critical issue in Sri Lanka, resulting in:

- 🌾 Significant **crop destruction** and economic losses for rural farmers
- 🏠 **Property damage** affecting farming communities
- ⚠️ Frequent **threats to human life** in agricultural border zones

### Why Existing Solutions Fail

Current mitigation strategies suffer from **"infrastructure blindness"**:

| Problem | Impact |
|---------|--------|
| Electric fences use simple voltage drop detection | Cannot distinguish elephant contact from environmental noise |
| Acoustic systems detect presence but not behavior | Cannot tell if elephant is calm or aggressive |
| No real-time information sharing | Farmers have no guidance during critical situations |
| High false alarm rates | Farmers lose trust in existing alert systems |

---

## 💡 Proposed Solution

Project Gaja-Saviya introduces a **multi-layered intelligent system** combining:

- 🔌 **IoT Sensing** — ESP32-based Sentinel Node with electrical & acoustic sensors
- 🧠 **Machine Learning** — LSTM for signals, CNN for audio, Bayesian fusion
- 📱 **Mobile Platform** — Real-time alerts and safe navigation for farmers
- 🔗 **Cross-Modal Validation** — Alerts only when multiple sensors confirm a threat

---

## 🏗️ System Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                        IoT LAYER                                │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │           ESP32 Sentinel Node                           │   │
│   │   ┌──────────────────┐  ┌──────────────────────────┐   │   │
│   │   │  Fence Sensors   │  │   Acoustic Microphone    │   │   │
│   │   │ (Voltage/Current)│  │  (High-sensitivity mic)  │   │   │
│   │   └────────┬─────────┘  └─────────────┬────────────┘   │   │
│   └────────────┼────────────────────────── ┼────────────────┘   │
└────────────────┼─────────────────────────── ┼──────────────────┘
                 │                             │
                 ▼                             ▼
┌─────────────────────────────────────────────────────────────────┐
│                      BACKEND LAYER                              │
│  ┌─────────────────┐          ┌────────────────────────────┐   │
│  │  Member 03       │          │       Member 02            │   │
│  │  Fence Signal    │          │    Bio-Acoustic            │   │
│  │  Interpreter     │          │    Behavior Analyst        │   │
│  │  (LSTM Model)    │          │    (CNN + Mel-Spectrogram) │   │
│  └────────┬─────────┘          └──────────────┬─────────────┘  │
│           │  disturbance_type  │               │  behavior_label │
│           │  confidence_score  │               │  confidence     │
│           └────────────────────┘               │                │
│                        │                       │                │
│                        ▼                       ▼                │
│              ┌──────────────────────────────────────┐          │
│              │           Member 01                  │          │
│              │   Cross-Modal Sensor Fusion Engine   │          │
│              │   (Bayesian/Rule-based Fusion)        │          │
│              │   → threat_status                    │          │
│              │   → severity_level                   │          │
│              │   → joint_confidence                 │          │
│              └──────────────────┬───────────────────┘          │
│                                 │                               │
│                                 ▼                               │
│                        ┌─────────────────┐                     │
│                        │    Database     │                     │
│                        │   (SQLite/DB)   │                     │
│                        └────────┬────────┘                     │
└─────────────────────────────────┼───────────────────────────────┘
                                  │
                                  ▼
┌─────────────────────────────────────────────────────────────────┐
│                    APPLICATION LAYER                            │
│              ┌──────────────────────────────────┐              │
│              │          Member 04               │              │
│              │  Dynamic Safe-Routing &          │              │
│              │  Trust Platform                  │              │
│              │  (React Native Mobile App)       │              │
│              │  → Real-time alerts              │              │
│              │  → Safe route navigation         │              │
│              │  → Community sighting reports    │              │
│              └──────────────────────────────────┘              │
└─────────────────────────────────────────────────────────────────┘
```

---

## 👥 Team Members

| Member | Name | Component | Technology | Branch |
|--------|------|-----------|------------|--------|
| **Member 01 (Leader)** | Saisuhani Leslinihal | Cross-Modal Sensor Fusion | Python, Flask, SQLite | `member-01-fusion` |
| **Member 02** | Wijesooriya W.M.R.A.B | Bio-Acoustic Behavior Analyst | Python, Librosa, CNN, TensorFlow | `member-02-acoustic` |
| **Member 03** | Dhananjaya A.G.G | Intelligent Fence Signal Interpreter | Python, LSTM, TensorFlow | `member-03-fence` |
| **Member 04** | Gunathilake D.R.G.L | Dynamic Safe-Routing & Trust Platform | React Native, OpenStreetMap | `member-04-mobile` |

---

## 📁 Repository Structure

```
Gaja-saviya-R26-IT-136/
│
├── member-01-fusion/              # Cross-Modal Sensor Fusion
│   ├── fusion/
│   │   ├── fusion_engine.py       # Core fusion logic
│   │   ├── confidence_scorer.py   # Joint confidence calculation
│   │   └── alert_manager.py       # Duplicate alert prevention
│   ├── api/
│   │   └── routes.py              # Flask API endpoints
│   ├── models/
│   │   └── schemas.py             # Data structures
│   ├── database/
│   │   └── db_handler.py          # SQLite operations
│   ├── tests/
│   │   └── test_fusion.py         # 20 unit tests
│   ├── simulate/
│   │   └── mock_inputs.py         # Simulation scripts
│   ├── conftest.py
│   ├── app.py
│   ├── requirements.txt
│   └── README.md
│
├── member-02-acoustic/            # Bio-Acoustic Behavior Analyst
│   ├── audio/                     # Raw audio files
│   ├── spectrograms/              # Mel-spectrograms
│   ├── model/                     # Trained CNN model
│   ├── api/
│   │   └── routes.py              # Flask API
│   ├── acoustic_analyzer.py       # Main analysis logic
│   ├── train_model.py             # CNN training script
│   ├── app.py
│   ├── requirements.txt
│   └── README.md
│
├── member-03-fence/               # Fence Signal Interpreter
│   ├── data/                      # Signal datasets
│   ├── model/                     # Trained LSTM model
│   ├── api/
│   │   └── routes.py              # Flask API
│   ├── signal_processor.py        # Preprocessing logic
│   ├── train_model.py             # LSTM training script
│   ├── app.py
│   ├── requirements.txt
│   └── README.md
│
├── member-04-mobile/              # Safe-Routing Mobile App
│   ├── screens/
│   │   ├── HomeScreen.js          # Main map screen
│   │   └── AlertScreen.js         # Alert details
│   ├── components/
│   │   └── ThreatMarker.js        # Map threat marker
│   ├── services/
│   │   ├── api.js                 # Fusion API connector
│   │   └── routing.js             # Route calculation
│   ├── App.js
│   ├── package.json
│   └── README.md
│
├── .gitignore
└── README.md                      # This file
```

---

## 🔧 Components

### Member 01 — Cross-Modal Sensor Fusion

**Role:** Central decision-making unit of the system.

Receives outputs from both the fence signal interpreter and bio-acoustic analyzer, synchronizes them using timestamps, and determines whether a threat is real or a false alarm.

#### Key Features
- Receives and synchronizes inputs from 2 sensors within a 10-second time window
- Calculates joint confidence score using weighted averaging
- Classifies threats as `REAL_THREAT`, `FALSE_ALARM`, or `UNCERTAIN`
- Determines severity: `HIGH`, `MEDIUM`, `LOW`, or `NONE`
- Prevents duplicate alerts using a 5-minute buffer
- Saves all results to SQLite database
- Exposes RESTful API for inter-component communication

#### Fusion Logic

| Fence Label | Acoustic Label | Confidence | Result |
|-------------|----------------|------------|--------|
| `elephant_contact` | `aggressive` | ≥ 0.60 | `REAL_THREAT` |
| `elephant_contact` | `calm` | any | `UNCERTAIN` |
| `environmental_noise` | `calm` | any | `FALSE_ALARM` |

#### API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/health` | Check API status |
| POST | `/api/fuse` | Submit sensor inputs |
| GET | `/api/results` | Get all results |
| GET | `/api/threats` | Get real threats only |

#### Test Results
```
✅ TestConfidenceScorer   — 7 tests passed
✅ TestFusionEngine       — 6 tests passed
✅ TestTimeWindow         — 3 tests passed
✅ TestAlertManager       — 4 tests passed
════════════════════════════════════
20 passed in 0.12s
```

---

### Member 02 — Bio-Acoustic Behavior Analyst

**Role:** Analyze environmental audio to detect elephant presence and classify behavior.

Converts audio signals into Mel-spectrogram representations and applies a CNN model to classify whether an elephant is calm or aggressive, improving the relevance of alerts.

#### Key Features
- Captures environmental audio using high-sensitivity microphone
- Converts audio into Mel-spectrogram representations using Librosa
- CNN model trained on Elephant Listening Project & Elephant Voices datasets
- Classifies elephant behavior: `aggressive` or `calm`
- Applies temporal smoothing to improve prediction stability
- Outputs behavior label with confidence score via Flask API

#### Output Format
```json
{
  "component": "acoustic",
  "timestamp": "2026-04-26T10:30:00",
  "confidence_score": 0.87,
  "label": "aggressive",
  "sensor_id": "node_001"
}
```

---

### Member 03 — Intelligent Fence Signal Interpreter

**Role:** Analyze electrical disturbances in the fence to identify the source of interference.

Instead of simple voltage drop detection, captures detailed waveform patterns and uses an LSTM model to differentiate between disturbance types.

#### Key Features
- Continuously samples voltage and current pulses via Sentinel Node
- Detects waveform distortions: amplitude variation, pulse width changes, spikes
- Preprocessing: denoising, segmentation, normalization
- LSTM model trained on time-series signal sequences
- Multi-class classification: `elephant_contact`, `environmental_noise`, `structural_issue`
- Outputs disturbance type with confidence score via Flask API

#### Output Format
```json
{
  "component": "fence",
  "timestamp": "2026-04-26T10:30:00",
  "confidence_score": 0.91,
  "label": "elephant_contact",
  "sensor_id": "node_001"
}
```

---

### Member 04 — Dynamic Safe-Routing & Trust Platform

**Role:** Mobile application delivering real-time alerts and safe navigation to farmers.

Translates validated sensor data into meaningful guidance by identifying dangerous zones and suggesting safer routes.

#### Key Features
- Built with React Native for cross-platform support (iOS & Android)
- Visualizes real-time threat zones on OpenStreetMap
- Applies Dijkstra/A* algorithm for safe route calculation
- Dynamically adjusts routes based on threat proximity and severity
- User-reported sightings with trust scoring mechanism
- Filters unreliable reports using sensor validation

---

## 🔗 API Contract

All components must follow this agreed JSON format when communicating:

### Input to Fusion Engine (POST /api/fuse)
```json
{
  "fence": {
    "component": "fence",
    "timestamp": "2026-04-26T10:30:00",
    "confidence_score": 0.89,
    "label": "elephant_contact",
    "sensor_id": "node_001"
  },
  "acoustic": {
    "component": "acoustic",
    "timestamp": "2026-04-26T10:30:02",
    "confidence_score": 0.92,
    "label": "aggressive",
    "sensor_id": "node_001"
  }
}
```

### Output from Fusion Engine
```json
{
  "threat_status": "REAL_THREAT",
  "severity_level": "HIGH",
  "joint_confidence": 0.905,
  "fence_label": "elephant_contact",
  "acoustic_label": "aggressive",
  "sensor_id": "node_001",
  "message": "Alert validated: REAL_THREAT at sensor node_001",
  "timestamp": "2026-04-26T10:30:02.123456"
}
```

---

## 🗄️ Database Design

The database stores all data generated by the system:

| Table | Description |
|-------|-------------|
| `fusion_results` | All fusion engine outputs with threat status and severity |
| `sensor_readings` | Raw sensor inputs from fence and acoustic components |
| `alert_history` | History of all alerts sent to users |
| `user_reports` | Community-reported elephant sightings with trust scores |

---

## 🚀 Getting Started

### Prerequisites
- Python 3.10+
- Node.js 18+
- Git
- Expo CLI (for mobile)

### Clone the Repository
```bash
git clone https://github.com/YOUR_USERNAME/Gaja-saviya-R26-IT-136.git
cd Gaja-saviya-R26-IT-136
```

### Run Member 01 — Sensor Fusion
```bash
cd member-01-fusion
python -m venv venv
venv\Scripts\activate        # Windows
pip install -r requirements.txt
python app.py
```
API runs at: `http://localhost:5000`

### Run Member 02 — Acoustic Analyzer
```bash
cd member-02-acoustic
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
python app.py
```

### Run Member 03 — Fence Signal
```bash
cd member-03-fence
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
python app.py
```

### Run Member 04 — Mobile App
```bash
cd member-04-mobile
npm install
npx expo start
```

### Run Tests (Member 01)
```bash
cd member-01-fusion
pytest tests/test_fusion.py -v
```

---

## 🛠️ Tech Stack

| Layer | Technology | Purpose |
|-------|------------|---------|
| IoT Hardware | ESP32 | Sentinel Node microcontroller |
| Signal ML | Python, TensorFlow, LSTM | Fence signal classification |
| Audio ML | Python, Librosa, CNN | Elephant behavior classification |
| Fusion Engine | Python, Flask, SQLite | Cross-modal decision making |
| Mobile App | React Native, Expo | Farmer alert & navigation |
| Mapping | OpenStreetMap | Map data and routing |
| Routing Algorithm | Dijkstra / A* | Safe path calculation |
| Testing | Pytest | Unit testing (20 tests) |
| Version Control | Git, GitHub | Collaboration |

---

## 📊 Expected Results

| Metric | Target |
|--------|--------|
| False alarm reduction | > 60% compared to existing systems |
| Threat detection accuracy | > 85% |
| Alert response time | < 5 seconds |
| Mobile app availability | iOS & Android |
| System scalability | Multiple sentinel nodes |

---

## 💼 Commercialization

Project Gaja-Saviya has strong commercial potential:

- 🌏 **Scalable** to other HEC-affected countries: India, Kenya, Thailand, Indonesia
- 🤝 **Partnership opportunities** with wildlife departments and environmental NGOs
- 💰 **Subscription model** for farming communities and government wildlife agencies
- 📡 **Low-cost deployment** using affordable ESP32 IoT nodes
- 🏆 **Social impact** — protecting both human livelihoods and elephant populations

---

## 📄 License

This project is developed for academic purposes as part of **IT4010 Research Project** at **SLIIT**.

---

<div align="center">
  <strong>🐘 Project Gaja-Saviya | R26-IT-136 | SLIIT 2026</strong><br>
  <em>Protecting People. Protecting Elephants.</em>
</div>
