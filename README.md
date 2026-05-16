# PriorAuth-Ops: Clinical Claims Intelligence & Revenue Recapture System

## 📊 Executive Summary
In high-volume pharmacy operations, administrative friction in the Prior Authorization (PA) lifecycle represents a severe threat to both patient adherence and enterprise revenue stability. This project delivers a comprehensive, database-driven audit of **10,000 pharmacy claims** to isolate operational bottlenecks, quantify financial exposure, and engineer a data-backed roadmap for automation.

By analyzing historical rejection codes, therapeutic classes, and status changes, this system uncovered a concentrated **$1,197,600 revenue leak** entirely isolated within high-cost specialty drug tiers, driven by 998 abandoned patient therapies.

---

## 💡 Key Insights & Data Discoveries
* **The Specialty Approval Gap:** While Acute and Maintenance drug classes achieved a **100% automated approval rate**, the Specialty drug tier faced a staggering **46.62% rejection/restriction rate**.
* **The "Core Offenders":** Administrative rejections are heavily concentrated within specific high-volume therapeutic lines rather than evenly distributed:
    * **Ozempic:** 25.18% Denial Rate
    * **Keytruda:** 22.88% Denial Rate
    * **Humira:** 22.45% Denial Rate
* **The Walk-Away Threshold:** The primary driver of patient deterrent behavior was the `"Documentation Required"` status code. When a manual PA tracking cycle exceeded a critical 48-hour window without clinical resolution, patient abandonment spiked sharply.

---

## 🛠️ System Architecture & Tech Stack
The project lifecycle mirrors a production enterprise analytics workflow, moving from structured querying to executive visual presentation:

* **Database Engine:** SQL (PostgreSQL/SQLite) for cohort isolation, claim aggregation, and conditional loss-modeling.
* **Business Intelligence:** Tableau for developing interactive dashboard wireframes, clinical exception mapping, and therapeutic denial cross-filtering.
* **Executive Delivery:** Management Consulting-grade strategic slide deck designed for C-suite operational review.

---

## 📉 Financial Impact Modeling
The financial exposure was calculated by isolating abandoned specialty claims and applying weighted therapeutic-class revenue margins:

$$\text{Total Exposure} = \sum (\text{Abandoned Specialty Claims} \times \text{Average Speciality Reimbursement Value})$$

* **Total Identified Revenue Leakage:** \$1,197,600 (Q3 Operational Baseline)
* **Total Patient Impact:** 998 Lost Treatment Cycles
* **Technician Labor Waste:** Estimated 40% of standard operational hours lost to manual phone/fax follow-ups with regional clinics.

---

## 🚀 Strategic Automation Roadmap
To transition operations from manual administrative tracking to proactive clinical automation, this system outlines three core technical interventions:

1.  **Automated ePA Integration:** Deploy integrated electronic Prior Authorization loops directly for the identified "Core Offenders" (Ozempic, Humira) to bypass manual reviewer queues entirely via real-time data exchange.
2.  **The "Clinic Ping" Alert System:** Engineer automated programmatic triggers (SMS/EMR alerts) sent to prescribing regional clinics the moment an inbound claim hits a `"Documentation Required"` flag, gathering missing lab values *before* counter abandonment occurs.
3.  **Financial Triage Guardrails:** Establish an automated dashboard routing protocol that captures specialty counter-denials instantly, aligning patients with Manufacturer Assistance Programs in real-time.

### 📈 Target Return on Investment (ROI)
By automating data capture loops and eliminating clinic telephone tag, the operational target is a **35% recapture rate** of abandoned specialty therapies. This yields a projected net recovery of **+\$419,000 in annual profit** with zero additional patient acquisition costs.

---

## 📁 Repository Structure
```text
├── data/
│   └── mock_claims_10k.csv      # Baseline claims dataset (10,000 simulated entries)
├── sql/
│   ├── schema.sql               # Database definition and index optimizations
│   ├── core_metrics.sql         # Aggregations for drug classes & approval rates
│   └── revenue_leak_audit.sql   # Calculations for financial loss parameters
├── visuals/
│   ├── tableau_workbook.twbx    # Interactive analytics dashboard workbook
│   └── metrics_snapshot.png     # Exported dashboard preview
└── presentation/
    └── Clinical_Claims_Intelligence_System.pptx  # Executive consulting presentation
