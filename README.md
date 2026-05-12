Audra Labs — Forensic Image Authenticity Analyzer

Detect. Verify. Protect.
AI-powered forensic image analysis to uncover deepfakes, manipulation, steganography, and cyber threats in under 5 seconds.

WEBSITE LiNK:- https://audralabs-eight.vercel.app/
<img width="1912" height="977" alt="Screenshot 2026-05-12 152057" src="https://github.com/user-attachments/assets/0161a011-6d37-4810-8281-ebd30958c716" />
<img width="1906" height="727" alt="image" src="https://github.com/user-attachments/assets/993d2dd5-42bc-4f6e-b5ca-2fb6eb705490" />
<img width="1896" height="960" alt="image" src="https://github.com/user-attachments/assets/e5cf5fce-22bd-4218-b8d4-8153f8e622ae" />
<img width="1902" height="952" alt="image" src="https://github.com/user-attachments/assets/17cf993d-3806-4167-9922-a9f8d5403877" />
<img width="1901" height="947" alt="image" src="https://github.com/user-attachments/assets/989e9dd2-ac8f-416e-b3df-301e469cf64f" />
<img width="1902" height="962" alt="image" src="https://github.com/user-attachments/assets/ed3fd52a-1bb2-4472-a779-732f42aec16b" />


🛡️ Audra Labs — Forensic Image Authenticity Analyzer

Detect. Verify. Protect.
AI-powered forensic image analysis to uncover deepfakes, manipulation, steganography, and cyber threats in under 5 seconds.

Show Image
Show Image
Show Image
Show Image

📌 What is Audra Labs?
Audra Labs is a forensic image authenticity platform built for the HackOrbit 2026 hackathon. It combines client-side canvas forensics with Claude Vision AI to deliver a full 7-module analysis of any uploaded image — detecting AI generation, deepfakes, hidden steganographic payloads, physics inconsistencies, and social engineering intent.

90% of people cannot spot AI-generated images. Audra Labs can.


✨ Features
FeatureDescription🌡 Thermal HeatmapJet-colormap simulation exposing AI flatness in skin regions📊 Noise Map6× amplified high-pass filter revealing AI grid artifacts🔬 LSB Steganography ScanLeast Significant Bit analysis for hidden payload detection⚡ ELA (Error Level Analysis)JPEG recompression delta exposing edited regions🧬 Biological Anomaly DetectionEye glint, skin pores, micro-vessel analysis⚙️ Physics Consistency AuditShadow, reflection, and lighting cross-checks🎯 Social Engineering IntentDetects panic generation, impersonation, credential theft🏛 C2PA Provenance CheckDigital content authenticity manifest validation📁 Batch Redline ReportingAudit up to 20 images with a downloadable report

🖥️ Demo
Upload any image → get a full forensic verdict with:

Confidence score (0–100%)
6 animated risk metrics
7 expandable module cards
Threat indicator chips
Downloadable .txt report


🏗️ Tech Stack
Frontend

HTML5, CSS3, Vanilla JavaScript (ES6+)
Canvas API (Thermal, Noise, LSB, ELA renderers)

Backend

Python 3.11, Flask, Gunicorn
Celery + Redis (async batch processing)
OpenCV, NumPy, scikit-image, Pillow, FFT Analysis

AI

Anthropic Claude Vision AI (claude-sonnet-4-20250514)

Infrastructure

PostgreSQL, Redis, MinIO (S3-compatible storage)
Docker + Docker Compose
GitHub Actions (CI/CD)
Vercel (frontend), Nginx (reverse proxy)
Grafana + Prometheus (monitoring)


🚀 Getting Started
Prerequisites

Python 3.11+
Docker & Docker Compose
An Anthropic API key

1. Clone the repo
bashgit clone https://github.com/heygaurav1/Audra-Labs.git
cd Audra-Labs
2. Set up environment variables
bashcp .env.example .env
Edit .env and fill in your values:
envANTHROPIC_API_KEY=sk-ant-...
DATABASE_URL=postgresql://user:pass@localhost:5432/audralabs
REDIS_URL=redis://localhost:6379/0
MINIO_ENDPOINT=localhost:9000
MINIO_ACCESS_KEY=minioadmin
MINIO_SECRET_KEY=minioadmin
3. Run with Docker (recommended)
bashdocker-compose up --build
This starts:

Flask API on http://localhost:5000
Frontend on http://localhost:3000
PostgreSQL on port 5432
Redis on port 6379
MinIO console on http://localhost:9001

4. Run without Docker (dev mode)
bash# Backend
cd backend
pip install -r requirements.txt
python app.py

# In a separate terminal — start Celery worker
celery -A tasks.celery_tasks worker --loglevel=info
Open frontend/index.html in your browser.

📁 Project Structure
Audra-Labs/
├── frontend/           # HTML/CSS/JS client
├── backend/
│   ├── api/            # Flask routes & validators
│   ├── forensics/      # ELA, LSB, noise, C2PA, thermal engines
│   ├── ai/             # Claude Vision API wrapper & prompt templates
│   ├── models/         # Pydantic schemas
│   └── tasks/          # Celery async tasks
├── database/           # Migrations & ORM models
├── monitoring/         # Grafana + Prometheus configs
├── docker/             # Dockerfiles & Nginx config
├── tests/              # Pytest test suite
└── docker-compose.yml

🔌 API Endpoints
MethodEndpointDescriptionPOST/api/analyzeAnalyze a single imagePOST/api/batchSubmit a batch of up to 20 imagesGET/api/batch/:job_idPoll batch job statusGET/api/healthHealth check
Example Request
bashcurl -X POST http://localhost:5000/api/analyze \
  -H "Content-Type: application/json" \
  -d '{"image": "<base64-encoded-image>", "mime_type": "image/jpeg"}'
Example Response
json{
  "verdict": "TAMPERED",
  "confidence": 91,
  "ai_generation_score": 87,
  "metadata_integrity": 32,
  "noise_pattern_anomaly": 74,
  "steganography_risk": 15,
  "biological_anomaly": 83,
  "physics_consistency_issues": 61,
  "threat_indicators": ["Irregular skin texture", "Missing C2PA manifest"],
  "why_fake_proof": "Noise pattern reveals AI grid artifacts...",
  "social_engineering_intent": "Impersonation",
  "c2pa_status": "Missing",
  "modules": { ... }
}

🧪 Running Tests
bashcd backend
pytest tests/ -v

🌱 Sustainability
Audra Labs is designed with green computing principles:

Serverless-ready — scales to zero when idle
Zero data retention — images processed ephemerally, never stored
Batched inference — minimises GPU cycles per analysis
Open source — shared tooling reduces duplicated effort globally


👥 Team
NameRoleGaurav PaulTeam Lead · Full-Stack · DevOpsNishant Kumar SharmaAI · Backend EngineeringShadman PerwezUI/UX · ResearchDebarati SarkarContent · Pitching

📄 License
This project is licensed under the MIT License — see LICENSE for details.
🔗 Links

🐙 GitHub: github.com/nishant24by7/Audra-Labs-NSUT
🤖 Powered by: Anthropic Claude
🏆 Built for: NSUT
