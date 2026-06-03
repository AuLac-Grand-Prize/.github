<div align="center">

# 🏥 PharmLink AI

## Vietnam's pharmaceutical AI platform — *Made in Vietnam*

### *Protecting the health of 100 million Vietnamese with AI built by Vietnamese*

![Status](https://img.shields.io/badge/status-in%20development-yellow)
![Engines](https://img.shields.io/badge/AI%20engines-4-blue)
![Market](https://img.shields.io/badge/market-60%2C000%2B%20pharmacies-success)
![Sovereignty](https://img.shields.io/badge/data-stays%20in%20Vietnam-informational)
![Made in](https://img.shields.io/badge/made%20in-Vietnam%20🇻🇳-red)

</div>

---

## Executive summary

**PharmLink AI** is Vietnam's first pharma-domain AI platform — built entirely by Vietnamese engineers and pharmacists, trained on Vietnamese health data, running on infrastructure located in Vietnam, in service of medication safety and national health-data sovereignty.

The product is **four core AI engines** the team fully owns end-to-end, integrated into a software platform that serves **60,000+ pharmacies** with the **potential to reach 100 million Vietnamese citizens** — turning every pharmacy into a smart point of care.

> **Expected impact after 3 years**: prevent 50,000+ dangerous drug-interaction events per year, lift chronic-disease treatment adherence from below 50% to above 75% for 2 million enrolled patients, save thousands of billions of VND in healthcare costs, and bring Vietnam's medication-safety standard closer to that of developed countries.

---

## The problem

Retail pharmacy in Vietnam runs on memory, intuition, and paper — creating risk on three fronts:

| Dimension | What's broken today |
|-----------|---------------------|
| **Health** | Tens of thousands of preventable hospitalizations a year from drug interactions and medication errors; chronic-disease adherence below 50%; unreadable handwriting causing dispensing errors. |
| **Economics** | 60,000+ pharmacies run manually; 10–15% of stock expires unsold; an 8 B USD/year retail sector with low labor productivity. |
| **Data sovereignty** | Foreign health-AI (IBM Watson Health, Google Health, Epic) requires patient data to leave Vietnam or transit overseas clouds. No model understands Vietnamese medical language, doctors' handwriting, or local brand drugs well enough for clinical use. |

**PharmLink AI fills this gap with deep AI technology developed by Vietnamese.**

---

## The four AI engines

| Engine | Job-to-be-done | Core technology | Expected result | Repo |
|--------|----------------|-----------------|-----------------|------|
| 💊 **VietDrug AI** | "Is this combination safe?" | Vietnamese drug Knowledge Graph (2,000+ substances × 50,000+ interaction pairs) + GNN personalization | ≥ 95% recall on high-severity interactions, < 5% false positives, < 200 ms | [Pharma-VietDrugAI](https://github.com/AuLac-Grand-Prize/Pharma-VietDrugAI) |
| 📝 **PrescriptionVision** | "Read this handwritten prescription" | Vision-language model (Qwen2.5-VL) + YOLOv8, 5-stage pipeline → FHIR | ≥ 92% on 500 common drugs, ≥ 85% on 2,000 | [Pharma-PrescriptionVision](https://github.com/AuLac-Grand-Prize/Pharma-PrescriptionVision) |
| 🤖 **PharmaGPT-VN** | "Answer my drug question, with sources" | Vietnamese pharma corpus (10M+ tokens) + RAG with citation enforcement | Beat GPT-4 on VN clinical questions, < 2 s, ~1/10 the cost of foreign APIs | [PharmaGPT-VN](https://github.com/AuLac-Grand-Prize/PharmaGPT-VN) |
| 📈 **DemandForecast AI** | "What should I reorder?" | Time-series ensemble (Prophet/LSTM/TFT) + epidemiology signals | −40% dead stock, −60% sudden stockouts (6-month users) | [Pharma-DemandForecast](https://github.com/AuLac-Grand-Prize/Pharma-DemandForecast) |

Each engine's training data and model weights are **proprietary IP of PharmLink AI** — the Vietnamese drug-interaction knowledge graph, the largest ethically-collected Vietnamese handwritten-prescription dataset, and the highest-quality Vietnamese pharma language corpus.

---

## Platform & users

A single **Pharma Portal** (the workspace) sits on top of the four engines, served to three audiences:

| Audience | Surface | What they get |
|----------|---------|---------------|
| **60,000+ pharmacies** | Web / Tablet — [Pharma-Portal](https://github.com/AuLac-Grand-Prize/Pharma-Portal) | Smart POS, AI Clinical Assistant, Smart Inventory, Patient-Care dashboard, Compliance automation |
| **100M citizens** | Zalo Mini App | Personal health record, smart reminders, 24/7 AI pharmacist Q&A, drug-safety checks, fast delivery, e-vaccine book |
| **Ecosystem partners** | API | MoH reporting, B2B distributor marketplace, fintech, hospital e-prescription gateway, insurance claim processing |

```mermaid
flowchart TD
    U["👩‍⚕️ Pharmacist / 🏥 Pharmacy / 📱 Patient"] --> P["🖥️ Pharma Portal<br/>(Web/Tablet + Zalo Mini App)"]
    P --> G["🚪 API Gateway<br/>Auth · RBAC · rate-limit · audit"]
    G --> E1["💊 VietDrug AI<br/>Drug interactions"]
    G --> E2["📝 PrescriptionVision<br/>Handwritten OCR"]
    G --> E3["🤖 PharmaGPT-VN<br/>Pharma assistant"]
    G --> E4["📈 DemandForecast AI<br/>Demand forecasting"]
    E2 -. drug-name validation .-> E3
```

The Portal never calls an engine directly — everything flows through an **API Gateway** (centralized auth, RBAC, rate limiting, audit). Engines are independent services, each scaling and shipping on its own.

---

## National strategic alignment

PharmLink AI is designed to contribute directly to **five national programs**:

1. **National AI Strategy to 2030** — aiming for Vietnam to be a top-4 ASEAN AI nation; PharmLink registers as a Vietnamese health-AI brand.
2. **National Digital Transformation Program** — digitizing retail pharmacy (95% still run on paper/Excel), feeding the 20%-of-GDP digital-economy target.
3. **Project 06 (digital identity)** — VNeID integration for identity verification on prescription drugs.
4. **MoH national health-data interoperability** — built on the open HL7 FHIR standard so pharmacy data flows back to national systems.
5. **UN SDGs** — directly serving SDG 3 (health), SDG 9 (innovation/infrastructure), SDG 10 (reduced inequality), bringing health-AI to rural and mountainous pharmacies.

---

## Quantified impact

*Conservative scenario — 3 years, 5,000 participating pharmacies:*

| Impact metric | Annual estimate |
|---------------|-----------------|
| Dangerous drug-interaction alerts prevented | **50,000+ events** |
| Hospitalizations avoided | **5,000–10,000** |
| Lives potentially saved | **500–1,000** |
| Chronic patients supported on adherence | **2 million** |
| Adherence improvement | **<50% → >75%** |
| Prescriptions read accurately by AI | **20 million** |
| Dead-stock savings (sector-wide) | **3,000–5,000 billion VND/year** |
| High-quality jobs created (first 3 years) | **500+** |

**Social equity** is the deepest impact: PharmaGPT-VN brings expert-level pharmaceutical advice to every commune — a farmer in Bến Tre with diabetes can get in-depth guidance, adherence reminders, and interaction checks for free via Zalo.

---

## Business model

**Six revenue streams** (not dependent on any single source or government subsidy):

1. **SaaS subscription** (primary) — free up to ~2M VND/month by pharmacy size.
2. **Transaction fee** — 0.5–1% on online orders via the Zalo Mini App.
3. **B2B marketplace commission** — 1–3% on distributor purchases.
4. **Embedded fintech** — revenue share with banks on working-capital loans / BNPL.
5. **Data insights (B2B)** — anonymized market reports for pharma companies and research.
6. **AI API-as-a-service** — open VietDrug AI & PharmaGPT-VN to hospitals, clinics, and other startups.

| Milestone | Pharmacies | Zalo users | ARR (B VND) |
|-----------|-----------:|-----------:|------------:|
| Month 12 | 300 | 50,000 | 0.9 |
| Month 24 | 2,000 | 500,000 | 8 |
| Month 36 | 5,000 | 2,000,000 | 25 |
| Month 60 | 15,000 (VN + ASEAN) | 10,000,000 | 100+ |

---

## Roadmap (18 months)

| Phase | Window | Focus |
|-------|--------|-------|
| **1 — MVP** | Months 1–4 | VietDrug AI (500 drugs) + PrescriptionVision (50K Rx) + POS & Zalo integration; pilot 15 Hanoi pharmacies; form the Scientific Council. |
| **2 — Product-Market Fit** | Months 5–10 | VietDrug AI → 2,000 drugs; PharmaGPT-VN v1; DemandForecast pilot; 500 pharmacies / 100K users; first research paper. |
| **3 — Scale** | Months 11–18 | Cover Hanoi, HCMC, Da Nang; e-prescription with 3–5 hospitals; open AI API; 2,000 pharmacies / 500K users; prepare Indonesia pilot. |

**ASEAN expansion** (Year 3+): Indonesia (30,000+ apotek), Philippines, Myanmar/Cambodia, then Thailand/Malaysia — *"Vietnamese technology for Southeast Asian health."*

---

## Team & governance

- **100% Vietnamese founding team**; 90%+ Vietnamese technical & pharmacist staff; IP and model weights held by a Vietnamese legal entity; training data never leaves Vietnam.
- **Vietnamese Clinical Pharmacist Scientific Council** (7–10 leading experts) validates medical accuracy quarterly — members from Hanoi University of Pharmacy, UMP HCMC, and central hospitals (Bạch Mai, Chợ Rẫy, 108, K).
- **Ecosystem contribution**: partially open-sourcing PharmaGPT-VN for research, AI scholarships, university collaborations, and publishing at international venues (NeurIPS, ACL, EMNLP).

---

## Our commitments

1. **Quality** — no AI medical output reaches production without Scientific Council validation; human-in-the-loop, with clear disclaimers.
2. **Sovereignty** — Vietnamese health data stays in Vietnam; model source and weights belong to a Vietnamese entity.
3. **Inclusion** — the same AI quality from a District 1 pharmacy to a remote border-commune pharmacy.

---

## Repository map

| Repository | What it is |
|------------|-----------|
| [Pharma-Portal](https://github.com/AuLac-Grand-Prize/Pharma-Portal) | Pharmacist-facing web/tablet app (Next.js) |
| [Pharma-VietDrugAI](https://github.com/AuLac-Grand-Prize/Pharma-VietDrugAI) | Drug-interaction engine (Knowledge Graph + GNN) |
| [Pharma-PrescriptionVision](https://github.com/AuLac-Grand-Prize/Pharma-PrescriptionVision) | Handwritten-prescription OCR engine |
| [PharmaGPT-VN](https://github.com/AuLac-Grand-Prize/PharmaGPT-VN) | Vietnamese pharma RAG assistant |
| [Pharma-DemandForecast](https://github.com/AuLac-Grand-Prize/Pharma-DemandForecast) | Demand-forecasting engine |

---

<details>
<summary><b>Tech stack</b> (for engineers)</summary>

- **AI/ML:** PyTorch · PyTorch Geometric · Transformers · Darts · Prophet · LightGBM
- **Backend:** FastAPI · Neo4j · PostgreSQL/TimescaleDB · Qdrant · Redis · MLflow
- **Frontend:** Next.js 14 · React 18 · TypeScript · TailwindCSS
- **Infrastructure:** Docker · on-premise in Vietnam (FPT / Viettel IDC / VNPT), compliant with Decree 13/2023 on personal data protection

</details>

---

<div align="center">

**PharmLink AI** — *Vietnamese intelligence for the health of Vietnam and Southeast Asia.* 🇻🇳

</div>
