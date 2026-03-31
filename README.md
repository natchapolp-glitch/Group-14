# Animal-AI Network

AI Semantic Interpreter สำหรับแปลสัญญาณชีวภาพของสัตว์

## โครงสร้างโปรเจค

```
network/
├── backend/                 # FastAPI Backend
│   ├── main.py             # Main API server
│   ├── requirements.txt    # Python dependencies
│   └── interpreter/        # Signal analysis modules
│       ├── sound_analyzer.py
│       ├── movement_analyzer.py
│       ├── biosignal_analyzer.py
│       └── semantic_mapper.py
└── frontend/               # React Frontend
    ├── src/
    │   ├── components/
    │   ├── pages/
    │   └── App.tsx
    ├── package.json
    └── vite.config.ts
```

## คุณสมบัติหลัก

- **Backend**: FastAPI สำหรับประมวลผลสัญญาณชีวภาพ
- **Frontend**: React + TypeScript + TailwindCSS
- **การวิเคราะห์**: เสียง, การเคลื่อนไหว, สัญญาณชีวภาพ
- **Use Cases**: Wildlife, Livestock, Companion animals

## วิธีการติดตั้งและรัน

### Backend
```bash
cd backend
pip install -r requirements.txt
uvicorn main:app --reload
```

### Frontend
```bash
cd frontend
npm install
npm run dev
```

## API Endpoints

- `GET /api/health` - Health check
- `POST /api/analyze` - Analyze biological signals

## เทคโนโลยีที่ใช้

- **Backend**: FastAPI, Python, Uvicorn
- **Frontend**: React 19, TypeScript, Vite, TailwindCSS
- **Data Visualization**: Chart.js, react-chartjs-2

---

*โปรเจคนี้จัดทำขึ้นเพื่อการเรียนการสอนและส่งเป็น portfolio*
