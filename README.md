# 🦁 Animal-AI Network

<div align="center">

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![FastAPI](https://img.shields.io/badge/FastAPI-0.104+-green.svg)
![React](https://img.shields.io/badge/React-19-blue.svg)
![TypeScript](https://img.shields.io/badge/TypeScript-5.7+-blue.svg)
![License](https://img.shields.io/badge/License-Educational-orange.svg)

**AI Semantic Interpreter สำหรับแปลสัญญาณชีวภาพของสัตว์**

*CP352005 Networks - กลุ่ม 14 - 4-Week Sprint Project*

</div>

---

## 📋 Overview

Animal-AI Network เป็นระบบเครือข่ายที่ออกแบบมาเพื่อเปิดใช้งานการสื่อสารระหว่างสัตว์ ระบบ AI และมนุษย์ โดยการบูรณาการสัญญาณชีวภาพ ข้อมูลพฤติกรรม และความเข้าใจเชิงความหมายเข้าสู่โครงสร้างเครือข่ายโดยตรง

### 🎯 Project Vision

- 🔍 **Bio-Signal Processing**: ประมวลผลสัญญาณชีวภาพจากสัตว์
- 🧠 **AI-Native Architecture**: ฝัง AI ไว้ในทุกชั้นของเครือข่าย
- 🌐 **Cross-Species Communication**: สนับสนุนการสื่อสารข้ามสายพันธุ์
- 📊 **Real-time Analysis**: วิเคราะห์ข้อมูลแบบ real-time ด้วย priority-based routing

---

## 🏗️ Project Structure

```
network/
├── 📁 backend/                    # FastAPI Backend Server
│   ├── 📄 main.py                 # Main API application
│   ├── 📄 requirements.txt        # Python dependencies
│   └── 📁 interpreter/            # Signal Analysis Modules
│       ├── 🎵 sound_analyzer.py   # Audio signal processing
│       ├── 🏃 movement_analyzer.py # Movement pattern analysis
│       ├── 💓 biosignal_analyzer.py # Biometric signal processing
│       └── 🧠 semantic_mapper.py  # AI semantic interpretation
│
├── 📁 frontend/                   # React TypeScript Frontend
│   ├── 📄 package.json           # Node.js dependencies
│   ├── 📄 vite.config.ts         # Vite configuration
│   └── 📁 src/                   # Source code
│       ├── 📁 components/        # React components
│       ├── 📁 pages/             # Application pages
│       └── 📄 App.tsx            # Main application
│
├── 📁 Doc/                       # Project Documentation
│   ├── 📄 TS-Com Project Documentation Suite (1).docx.md
│   ├── 📄 Animal–AI Network.docx
│   └── 📄 Sprint Alpha + 1 (1).docx
│
├── 📄 .gitignore                 # Git ignore rules
└── 📄 README.md                  # This file
```

---

## 🚀 Quick Start

### Prerequisites

- **Python 3.8+**
- **Node.js 18+**
- **npm** or **yarn**

### Installation & Setup

```bash
# Clone the repository
git clone <repository-url>
cd network

# Backend Setup
cd backend
pip install -r requirements.txt
uvicorn main:app --reload --host 0.0.0.0 --port 8000

# Frontend Setup (in new terminal)
cd frontend
npm install
npm run dev
```

## 🏛️ Architecture Overview

### 5-Layer Network Architecture

```
┌─────────────────────────────────────────────────────────────┐
│ Layer 5: Semantic Application Layer                         │
│ (Wildlife Monitor, Livestock Manager, Pet Translator)      │
├─────────────────────────────────────────────────────────────┤
│ Layer 4: Context-Aware Transport Layer                      │
│ (Priority Management, Adaptive Reliability)                 │
├─────────────────────────────────────────────────────────────┤
│ Layer 3: AI-Native Network Layer                           │
│ (Bio-Addressing, Semantic Routing Protocol)                │
├─────────────────────────────────────────────────────────────┤
│ Layer 2: Bio-Signal Link Layer                             │
│ (Bio-Frame Format, Signal Synchronization)                  │
├─────────────────────────────────────────────────────────────┤
│ Layer 1: Biological Physical Layer                          │
│ (Sensors, Wearables, Bio-signal Acquisition)               │
└─────────────────────────────────────────────────────────────┘
                              ↑
                        AI Integration
                    (Embedded at Every Layer)
```

### 🧬 Bio-Addressing Scheme

- **16-byte hierarchical address** based on biological taxonomy
- **Species-aware routing** with semantic understanding
- **Priority-based packet handling** (CRITICAL → BACKGROUND)

### 🔄 Semantic Routing Protocol

```
Cost = α*priority_weight + β*species_similarity + γ*network_distance
```

- **Priority Levels**: CRITICAL, HIGH, MEDIUM, LOW, BACKGROUND
- **Species Similarity**: Taxonomic distance calculation
- **Network Distance**: Physical/network hops

---

## 📡 API Documentation

### Core Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/api/health` | System health check |
| `POST` | `/api/analyze` | Analyze biological signals |
| `GET` | `/api/species` | List supported species |
| `POST` | `/api/sensor/register` | Register new sensor |

### Request/Response Example

```python
# Analyze Request
{
    "use_case": "wildlife",
    "data_type": "wav", 
    "file_name": "elephant_call.wav",
    "data": {
        "signal_data": "...",
        "metadata": {...}
    }
}

# Response
{
    "meaning": " distress call detected",
    "label": "emergency",
    "confidence": 0.92,
    "action": "alert_rangers",
    "priority": "CRITICAL",
    "rawFeatures": {...},
    "details": "High-frequency distress pattern detected"
}
```

---

## 🎯 Use Cases

### 🦁 Wildlife Conservation
- **Real-time monitoring** ของสัตว์ป่า
- **Distress detection** และ alert system
- **Migration tracking** ด้วย bio-signals

### 🐄 Smart Livestock Management
- **Health monitoring** แบบ continuous
- **Behavior analysis** สำหรับ optimization
- **Early disease detection**

### 🐕 Companion Animal Care
- **Pet translator** สำหรับความต้องการพื้นฐาน
- **Health alerts** ส่งไปยัง owners
- **Activity tracking** และ wellness

---

## 🛠️ Technology Stack

### Backend Technologies
- **FastAPI** - Modern Python web framework
- **Python 3.8+** - Core programming language
- **Uvicorn** - ASGI server
- **Pydantic** - Data validation
- **NetworkX** - Graph simulation (planned)

### Frontend Technologies
- **React 19** - UI framework
- **TypeScript 5.7** - Type safety
- **Vite 6.2** - Build tool
- **TailwindCSS** - Styling
- **Chart.js** - Data visualization
- **React Router** - Navigation

### AI & Signal Processing
- **Librosa** - Audio analysis
- **NumPy** - Numerical computing
- **SciPy** - Signal processing
- **Scikit-learn** - Machine learning

---

## 🧪 Testing & Development

### Running Tests

```bash
# Backend tests
cd backend
pytest tests/ -v

# Frontend tests
cd frontend
npm test
```

### Development Workflow

```bash
# Development servers
npm run dev          # Frontend dev server
uvicorn main:app --reload  # Backend dev server

# Code formatting
black backend/       # Python formatting
npm run lint         # TypeScript linting
```

---

## 📊 Project Metrics

### Performance Targets
- **Routing Decision**: < 1 second
- **Signal Processing**: < 500ms
- **API Response**: < 200ms
- **Packet Delivery**: 95% reliability

### Current Status
| Component | Status | Coverage |
|-----------|--------|----------|
| API Layer | ✅ Complete | 85% |
| Signal Processing | 🔄 In Progress | 70% |
| Frontend UI | ✅ Complete | 80% |
| Documentation | ✅ Complete | 95% |

---

## 👥 Team

| Role | Name | Student ID | Responsibilities |
|------|------|------------|------------------|
| 🏛️ **Architect** | ณภัทร อรัญพูล | 673380036-3 | System design, Layer interfaces |
| ⚙️ **Engineer** | ธนินธร อันทรบุตร | 673380043-6 | Protocol implementation |
| 🧠 **Specialist** | ศุภกร กรมรินทร์ | 673380061-4 | AI algorithms, Semantic routing |
| 🔧 **DevOps** | ณัชพล เพ็งพล | 673380267-4 | Infrastructure, CI/CD |
| 🧪 **Tester/QA** | ณัฐกรณ์ อินธิสาร | 673380268-2 | Testing, Quality assurance |

---

## 📚 Documentation

- **[Architecture Specification](https://github.com/natchapolp-glitch/Group-14/blob/main/Doc/Sprint%20Alpha%20%2B%201.md#architecture_specmd)** - Complete technical design

- **[Implementation Plan](https://github.com/natchapolp-glitch/Group-14/blob/main/Doc/Sprint%20Alpha%20%2B%201.md#implementation_planmd)** - 4-week sprint planning

- **[TS-Com Project Documentation Suite](https://github.com/natchapolp-glitch/Group-14/blob/main/Doc/TS-Com%20Project%20Documentation%20Suite%20(1).docx.md#ts-com-project-documentation-suite)**
---

## 🗺️ Roadmap

### Phase 1: Foundation ✅
- [x] Basic API structure
- [x] Frontend framework
- [x] Documentation setup

### Phase 2: Core Features 🔄
- [ ] Signal processing modules
- [ ] Semantic routing implementation
- [ ] AI integration

### Phase 3: Advanced Features 📋
- [ ] Real-time visualization
- [ ] Multi-species support
- [ ] Performance optimization

---

## 🤝 Contributing

1. Fork the repository
2. Create feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open Pull Request

---

## 📄 License

This project is developed for educational purposes as part of CP352005 Networks course.

---

## 🙏 Acknowledgments

- **CP352005 Networks Course** - Project guidance and requirements
- **Team Members** - Collaborative development and testing
- **Open Source Community** - Tools and libraries used

---

<div align="center">

**🦁 Made with ❤️ for Animal Communication Research**

[![GitHub stars](https://img.shields.io/github/stars/username/network.svg?style=social&label=Star)](https://github.com/username/network)
[![GitHub forks](https://img.shields.io/github/forks/username/network.svg?style=social&label=Fork)](https://github.com/username/network)

</div>

---


