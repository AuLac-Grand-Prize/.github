<div align="center">

# 🏥 PharmLink AI

### The operating system for Vietnam's retail pharmacies

*One platform that helps pharmacies sell safely, read prescriptions instantly, answer drug questions reliably, and stock smarter — powered by four purpose-built AI engines.*

![Status](https://img.shields.io/badge/status-in%20development-yellow)
![Engines](https://img.shields.io/badge/AI%20engines-4-blue)
![Users](https://img.shields.io/badge/market-60%2C000%2B%20pharmacies-success)
![Made in](https://img.shields.io/badge/made%20in-Vietnam%20🇻🇳-red)

</div>

---

## TL;DR

PharmLink AI is a B2B SaaS platform for Vietnamese pharmacies. The **Portal** is the daily workspace pharmacists use (point-of-sale, inventory, patient care, compliance). Behind it, **four AI engines** remove the most error-prone and time-consuming parts of the job: checking drug interactions, reading handwritten prescriptions, answering clinical questions in Vietnamese, and forecasting what to reorder. The goal: **safer dispensing and less waste, with zero extra effort from the pharmacist.**

---

## The problem

Retail pharmacy in Vietnam runs on memory, intuition, and paper. That creates four costly gaps:

| Pain point | Impact today |
|------------|--------------|
| **Drug interactions are missed** | Tens of thousands of avoidable hospitalizations per year; manual lookup is too slow at the counter. |
| **Handwritten prescriptions are misread** | "Guessing" a doctor's handwriting is a leading cause of dispensing errors. |
| **No trustworthy Vietnamese drug assistant** | Foreign LLMs miss local brand names and push patient data to overseas clouds. |
| **Inventory is ordered by gut feel** | 10–15% of stock expires unsold — an estimated 3,000–5,000 billion VND wasted industry-wide each year. |

---

## Who it's for

- **Independent pharmacies (60,000+ in Vietnam)** — the primary buyer; tablet-first, often on slow networks.
- **Pharmacists & counter staff** — daily users who need answers in seconds, not workflows to learn.
- **Pharmacy chains & hospitals** — multi-site operations needing compliance and analytics.
- **Patients** — reached indirectly via care reminders and a Zalo Mini App.

---

## The product

A single **Portal** (the workspace) sits on top of **four AI engines** (the intelligence). Each engine maps to a concrete job-to-be-done:

### 🖥️ Pharma Portal — the pharmacist's workspace
POS, smart inventory (FEFO, expiry alerts), patient-care dashboard, and compliance reporting in one tablet-first app. Vietnamese & English. This is where every other capability surfaces.
→ [Pharma-Portal](https://github.com/AuLac-Grand-Prize/Pharma-Portal)

### 💊 VietDrug AI — "Is this combination safe?"
Real-time, personalized drug-interaction alerts (age, kidney/liver function, history) in under 200 ms, right inside the cart.
*Knowledge Graph + Graph Neural Network.*
→ [Pharma-VietDrugAI](https://github.com/AuLac-Grand-Prize/Pharma-VietDrugAI)

### 📝 PrescriptionVision — "Read this prescription for me"
Snap a photo of a handwritten prescription; it returns structured, validated medication data ready to auto-fill the cart.
*Vision-language model (Qwen2.5-VL) + detection (YOLOv8), 5-stage pipeline.*
→ [Pharma-PrescriptionVision](https://github.com/AuLac-Grand-Prize/Pharma-PrescriptionVision)

### 🤖 PharmaGPT-VN — "Answer my drug question, with sources"
A 24/7 Vietnamese pharmacist assistant that answers from a vetted corpus and **always cites its sources**, refusing to guess when evidence is thin.
*Retrieval-augmented generation with citation enforcement and guardrails.*
→ [PharmaGPT-VN](https://github.com/AuLac-Grand-Prize/PharmaGPT-VN)

### 📈 DemandForecast AI — "What should I reorder?"
30-day demand forecasts per product, turned into concrete reorder suggestions — factoring in seasonality, disease outbreaks, and weather.
*Time-series ensemble (Prophet / LightGBM / TFT / N-HiTS).*
→ [Pharma-DemandForecast](https://github.com/AuLac-Grand-Prize/Pharma-DemandForecast)

---

## How it works

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

The Portal never calls an engine directly — everything flows through an **API Gateway** that centralizes authentication, access control, rate limiting, and audit logging. Engines are independent services, so each can scale and ship on its own.

---

## Success metrics

| Goal | Target | Why it matters to the user |
|------|--------|----------------------------|
| Catch dangerous interactions | ≥ 95% recall | Patient safety — the core promise. |
| Read prescriptions accurately | ≥ 92% on common drugs | Eliminates manual re-keying and guesswork. |
| Trustworthy answers | 100% of clinical answers cite a source | Builds pharmacist trust; no hallucinated advice. |
| Reduce dead stock | −40% | Direct margin recovery for the pharmacy. |
| Stay fast at the counter | ≤ 200 ms interaction lookup | Fits real dispensing workflow. |

---

## Roadmap (high level)

| Phase | Focus |
|-------|-------|
| **Now** | Portal core (POS, inventory) + VietDrug AI interaction checks. |
| **Next** | PrescriptionVision OCR + Patient-Care dashboard. |
| **Later** | PharmaGPT-VN assistant + DemandForecast reorder automation. |
| **Vision** | Offline-capable PWA, multi-site chains, and federated learning across pharmacies. |

> Status: in active development. Each engine and the Portal live in their own repository (linked above).

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
- **Infrastructure:** Docker · on-premise in Vietnam, compliant with Decree 13/2023 on personal data protection

</details>

---

<div align="center">

**PharmLink AI** — *Connecting data, making medication safe for every Vietnamese.* 🇻🇳

</div>
