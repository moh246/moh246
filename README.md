# Abdelrahman Mohsen

AI engineer based in Graz, Austria. I build LLM agents, RAG and text-to-SQL systems that people use in their daily work, and I'm studying for an MSc in Machine Learning and Generative AI at FH JOANNEUM.

[LinkedIn](https://www.linkedin.com/in/abdelrahman-mohsen-4438991a8/) · [Email](mailto:ibrahimabdelrahman335@gmail.com)

## About me

I've spent five years taking AI from a business question to a working product, in banking, health insurance, utilities and sports. Most of that work is engineering, but I also work on the product side: writing requirements for AI products and working between business teams and engineers. I also teach data science and AI.

A few results I'm proud of:

- AI assistants used by more than 6,000 bank staff, with over 90% of answers rated correct
- Complaint classification accuracy raised from 60% to 92%, which showed about EGP 12M a year of revenue at risk
- About US$35,000 of fraudulent insurance payouts stopped in six months
- The winning proof of concept in a bank's customer-service chatbot tender

I've been reading about regulated medical AI (ISO 13485, IEC 62304, EU MDR and the EU AI Act), and it's where I'd like to grow.

## Professional work

The work I did for employers and clients is under NDA, so there's no code here. Each page covers the problem, what I did and the impact.

### Banking

| Project | What it is | Impact |
|---|---|---|
| [Voice of the Customer Reclassification](professional-work/voc-reclassification.md) | Routes app complaints out of an "Other" bucket to the team that can fix them | Accuracy up from 60% to 92%; about EGP 12M a year of revenue at risk quantified |
| [Agentic Portfolio Analytics](professional-work/agentic-portfolio-analytics.md) | Three AI assistants that answer staff questions from portfolio data, corporate documents and onboarding forms | 6,000+ users; over 90% of answers rated correct |
| [Customer-Service Chatbot Proposal](professional-work/customer-service-chatbot-bid.md) | Solution design and proof of concept for a bank's customer-service chatbot tender | Won the bid |
| [Voice Assistant for ATM Services](professional-work/atm-voice-assistant.md) | Voice assistant for ATM services: speech recognition, request understanding and spoken answers | Project lead |

### Health insurance

| Project | What it is | Impact |
|---|---|---|
| [Claims Fraud Detection](professional-work/claims-fraud-detection.md) | Scores every claim before payout: reject, investigate, or pay | About US$35,000 of fraudulent payouts prevented in six months |
| [Risk-Based Pricing](professional-work/claims-cost-pricing.md) | Prices plans on each member's expected cost instead of demographics alone | Model-priced groups outperformed the old basis; lower Medical Expense Ratio |
| [Net Promoter Score Feedback](professional-work/nps-feedback-classification.md) | Volunteer product manager on the Net Promoter Score program, plus automated sorting of member feedback | Feedback sorted into 8 categories and 24 subcategories |
| [Arabic Voice Assistant](professional-work/arabic-voice-assistant.md) | Staff ask questions about prescription data out loud in Arabic and hear the answer | In production; answers in 5 to 8 seconds |

### Utilities

| Project | What it is | Impact |
|---|---|---|
| [Fraud and Tampering Detection on Water Meters](professional-work/water-meter-anomaly-detection.md) | Flags tampering and fraud across a national water utility's meter readings | Built the end-to-end pipeline |

### Computer vision

| Project | What it is | Impact |
|---|---|---|
| [Real-Time Football Video-Assistant System](professional-work/football-var-system.md) | Finds and tracks players and the ball on live video and maps them onto the pitch for offside decisions | First release shipped |

## Study work

Theses, coursework and technical tasks. The code is linked where I could make it public.

| Project | What it is | Result | Code |
|---|---|---|---|
| [Surgical Instrument Segmentation](study-work/surgical-instrument-segmentation.md) | U-Net on robotic surgery video, with a data audit that turned Dice 0.000 into an honest number | Dice 0.846 ± 0.071 (leave-one-surgery-out) | [repo](https://github.com/moh246/surgical-instrument-segmentation) |
| [Pneumonia Detection from Chest X-rays](study-work/pneumonia-detection.md) | Fine-tuned VGG16 on NIH ChestX-ray14 with a patient-level split, subgroup analysis and DICOM inference (Udacity nanodegree) | F1 0.44 (radiologist average 0.387) | [repo](https://github.com/moh246/pneumonia-detection-xray) |
| [EEG Seizure Detection with Caregiver Alerts](study-work/eeg-seizure-detection.md) | SVM on 13 EEG features from CHB-MIT, with a Python service that alerts a caregiver (BSc thesis, team project) | About 77% sensitivity; graded A+ | [repo](https://github.com/moh246/eeg-seizure-detection) |
| [Cephalometric Landmark Loss](study-work/cephalometric-landmarks.md) | Geometry-aware loss for 19 landmark heatmaps, using the distances and angles between landmarks | Working loss and training loop, tested on synthetic data | [repo](https://github.com/moh246/cephalometric-landmark-loss) |
| [Facial Expression Retargeting](study-work/facial-expression-retargeting.md) | Transfer a person's facial expression to a 3D character with two graph-convolutional VAEs and a latent mapping (ITI diploma thesis, team of four) | Working pipeline on 3D face meshes | |
| [Chest X-ray Multi-label Classification](study-work/chest-xray-multilabel.md) | DenseNet-121 on the NIH Chest X-ray dataset, patient-level split, served with FastAPI in Docker | F1 0.83 | |

## Experience

| Role | Company | When |
|---|---|---|
| Senior Generative AI Engineer | Banque Misr, Cairo | Oct 2025 – Aug 2026 |
| AI Consultant (independent) | Tawuniya, Saudi insurer, remote | 2026 |
| Senior Data Scientist and Product Management | Accord Business Group, Dubai | Aug 2024 – Oct 2025 |
| Data Scientist and Junior Product Manager | Reliance Health, Lagos, remote | Jun 2022 – Aug 2024 |
| Computer Vision Engineer | IT Gate, Cairo | Oct 2021 – Jun 2022 |
| Machine Learning Intern | DevisionX, Cairo | Nov – Dec 2021 |

## Education

- **MSc Data Science – Machine Learning and Generative AI**, FH JOANNEUM, Graz, since 2026
- **Postgraduate Program in AI**, ITI and EPITA, 2021 – 2022
- **BSc Mechatronics Engineering**, Helwan University, Cairo, 2015 – 2020
- **Udacity Nanodegrees:** AI for Healthcare, Agentic AI, AI Product Manager (in progress)

## Skills

- **LLMs and generative AI:** RAG, LangGraph agents, prompt engineering, LoRA fine-tuning, Hugging Face, LLM evaluation, quantisation
- **Machine learning and data:** Python, PyTorch, scikit-learn, pandas, NLP, computer vision, fraud and anomaly detection, statistics, SQL, Snowflake
- **MLOps:** Docker, Kubernetes, CI/CD (GitLab), MLflow, OpenTelemetry, FastAPI, Flask, Azure, Git
- **AI product management:** requirements for AI products, use-case scoping, proof of concept to production, success metrics and AI evaluation
- **Medical data:** DICOM, EEG
- **Languages:** Arabic (native), English (C1), German (beginner)

## Contact

I'm open to AI engineering roles and collaborations. Email is the quickest way to reach me: [ibrahimabdelrahman335@gmail.com](mailto:ibrahimabdelrahman335@gmail.com). I'm also on [LinkedIn](https://www.linkedin.com/in/abdelrahman-mohsen-4438991a8/).
