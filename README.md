# Abdelrahman Ibrahim

**AI Engineer — LLM agents and RAG**

Based in Graz, Austria.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Profile-0A66C2)](https://www.linkedin.com/in/abdelrahman-mohsen-4438991a8/)
[![Email](https://img.shields.io/badge/Email-ibrahimabdelrahman335%40gmail.com-555555)](mailto:ibrahimabdelrahman335@gmail.com)

## About me

I build AI systems that run in production: LLM agents and text-to-SQL for banking, Arabic speech for insurance, fraud models for health claims, and segmentation and classification models for medical images. I also teach data science and AI.
I've been reading about regulated medical AI (ISO 13485, IEC 62304, EU MDR and the EU AI Act), and it's where I'd like to grow.

## Featured projects

### Banking

| Project | What it is | Impact |
|---|---|---|
| [Voice of the Customer Reclassification](projects/voc-reclassification.md) | Routes app complaints out of an "Other" bucket to the team that can fix them | Accuracy 60% → 92%; ~EGP 12M a year of revenue at risk quantified |
| [Agentic Portfolio Analytics](projects/agentic-portfolio-analytics.md) | Three AI assistants that answer staff questions from portfolio data, corporate documents and onboarding forms | 6,000+ users; over 90% of answers rated correct |
| [Customer-Service Chatbot Proposal](projects/customer-service-chatbot-bid.md) | Solution design and proof of concept for a bank's customer-service chatbot tender | Won the bid |
| [Voice Assistant for ATM Services](projects/atm-voice-assistant.md) | Led a voice assistant for ATM services | – |

### Health insurance

| Project | What it is | Impact |
|---|---|---|
| [Claims Fraud Detection](projects/claims-fraud-detection.md) | Scores every claim before payout: reject, investigate, or pay | ~US$35K in fraudulent payouts prevented in 6 months |
| [Risk-Based Pricing](projects/claims-cost-pricing.md) | Prices plans on each member's expected cost instead of demographics alone | Model-priced groups outperformed the old basis; lower Medical Expense Ratio |
| [Net Promoter Score Feedback](projects/nps-feedback-classification.md) | Volunteer product manager on the NPS program, plus automated sorting of member feedback | Feedback sorted into 8 categories and 24 subcategories |
| [Arabic Voice Assistant](projects/arabic-voice-assistant.md) | Staff ask questions about prescription data out loud in Arabic and hear the answer | In production; answers in 5–8 s |

### Utilities

| Project | What it is | Impact |
|---|---|---|
| [Fraud and Tampering Detection on Water Meters](projects/water-meter-anomaly-detection.md) | Flags tampering and fraud across a national water utility's meter readings | – |

### Medical AI

| Project | What it is | Impact |
|---|---|---|
| [Surgical Instrument Segmentation](projects/surgical-instrument-segmentation.md) | U-Net on robotic surgery video, with a data audit that turned Dice 0.000 into an honest number | Dice 0.846 ± 0.071 (leave-one-surgery-out) · [code](https://github.com/moh246/surgical-instrument-segmentation) |
| [Pneumonia Detection from Chest X-rays](projects/pneumonia-detection.md) | Fine-tuned VGG16 on NIH ChestX-ray14 with a patient-level split, subgroup analysis and DICOM inference | F1 0.44 (radiologist average 0.387) · [code](https://github.com/moh246/pneumonia-detection-xray) |
| [Chest X-ray Multi-label Classification](projects/chest-xray-multilabel.md) | DenseNet-121 on the NIH Chest X-ray dataset, patient-level split, served with FastAPI in Docker | F1 0.83 |
| [Cephalometric Landmark Loss](projects/cephalometric-landmarks.md) | Geometry-aware loss for 19 landmark heatmaps, using the distances and angles between landmarks | Working loss and training loop, tested on synthetic data · [code](https://github.com/moh246/cephalometric-landmark-loss) |
| [EEG Seizure Detection with Caregiver Alerts](projects/eeg-seizure-detection.md) | SVM on 13 EEG features from CHB-MIT, with a Python service that alerts a caregiver (team project) | ~77% sensitivity; BSc thesis, graded A+ · [code](https://github.com/moh246/eeg-seizure-detection) |

### Computer vision and 3D

| Project | What it is | Impact |
|---|---|---|
| [Real-Time Football Video-Assistant System](projects/football-var-system.md) | Finds and tracks players and the ball on live video and maps them onto the pitch for offside decisions | First release shipped |
| [Facial Expression Retargeting](projects/facial-expression-retargeting.md) | Transfer a person's facial expression to a 3D character with two graph-convolutional VAEs and a latent mapping (team of four) | ITI diploma thesis |

Work done for employers and clients is under NDA, so those pages cover the problem, my role and the impact only.

## Experience

- **Senior AI Engineer** · Banque Misr, Cairo · Oct 2025 – Aug 2026
- **AI Consultant** · Voice assistant for Tawuniya (Saudi insurer), remote · 2026
- **Senior Data Scientist** (+ product management) · Accord Business Group, Dubai · Aug 2024 – Oct 2025<br>
  Fraud and anomaly detection, voice AI and chatbot solution design; wrote business and product requirement documents.
- **Data Scientist / Junior Product Manager** · Reliance Health, Lagos (remote) · Jun 2022 – Aug 2024<br>
  Fraud detection, pricing models, Medical Expense Ratio. Volunteered as product manager on the Net Promoter Score project.
- **Computer Vision Engineer** · IT Gate, Cairo · Oct 2021 – Jun 2022

## Education

- **MSc Data Science – Machine Learning & Generative AI** · FH JOANNEUM, Graz · since 2026
- **Postgraduate Diploma in AI** · ITI / EPITA · Apr 2021 – Jan 2022
- **BSc Mechatronics Engineering** · Helwan University · 2015 – 2020
- **Udacity Nanodegrees** · AI for Healthcare, Agentic AI

## Tools I use

![LangGraph](https://img.shields.io/badge/LangGraph-1C3C3C)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?logo=pytorch&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-337AB7)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?logo=fastapi&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)
![MLflow](https://img.shields.io/badge/MLflow-0194E2?logo=mlflow&logoColor=white)
![Azure](https://img.shields.io/badge/Azure-0078D4)
![OpenTelemetry](https://img.shields.io/badge/OpenTelemetry-425CC7?logo=opentelemetry&logoColor=white)

- **LLMs and agents:** LangGraph, RAG, text-to-SQL, LLM evaluation in CI/CD, OpenTelemetry/Traceloop, Claude Code
- **Deep learning and ML:** PyTorch, XGBoost, U-Net, DenseNet, YOLOv8, graph neural networks
- **Speech and language:** Whisper, XTTS v2, Qwen, BGE-M3, Arabic NLP
- **Medical data:** DICOM, highdicom, EEG (braindecode, CHB-MIT, TUSZ)
- **Serving and MLOps:** FastAPI, Flask, Docker, MLflow, Azure

## Contact

- Email: [ibrahimabdelrahman335@gmail.com](mailto:ibrahimabdelrahman335@gmail.com)
- LinkedIn: [linkedin.com/in/abdelrahman-mohsen-4438991a8](https://www.linkedin.com/in/abdelrahman-mohsen-4438991a8/)
