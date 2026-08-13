INPUT 
Hospital Admission Readiness Simulator
Single-file HTML app. HTML, Tailwind CSS CDN, Vanilla JavaScript.
style: same as previously established
Healthcare simulation design system. Task-first — no dashboard on load.
User plays Hospital Admission Coordinator.
Setup — collect:
- Provider, Attending Physician
- Diagnosis: Acute MI / CHF / Pneumonia / Elective Surgery / Hip Fracture
- Admission Type: Inpatient / Observation / Emergency / ICU / Same-Day Surgery
- PA Status, Admission Date
Observation Status must always show: 'CMS 2-Midnight Rule applies — different cost-sharing, SNF eligibility, and billing than inpatient. Medicare patients require written MOON notification.'
Label all provider/payer names as illustrative training data.
Button: 🏥 Analyze Admission Readiness
Initial Analysis
Generate status for: PA, Insurance, Bed, Documentation, Physician Orders, Consent.
Readiness Score 30–60%. Do not reveal final decision yet.
Score Weighting:
PA Status 25% · Clinical Documentation 20% · Physician Orders 20% · Insurance 15% · Consent 10% · Bed 10%
Denied PA + ICU admission cannot reach 70% from admin tasks alone.
PA Branches:
Approved → continue.
Pending → Follow Up, Upload Docs, Contact Physician.
Denied → Review Reason, Contact Insurance, Submit Appeal.
Successful appeal converts to Approved.
Workflow Actions:
Assign Bed / Verify Insurance / Upload Documentation / Complete Consent / Contact Physician / Notify Nursing / Prepare Patient Arrival
Acute MI and CHF trigger a criteria note:
'InterQual/Milliman thresholds apply — ensure documentation meets medical necessity standards before UR review.'
Timeline milestones:
PA Review → Insurance Verification → Bed Assignment → Documentation → Consent → Patient Arrival → Registration → Clinical Assessment → Admission Complete
Care Coordination Cards:
Attending / Case Manager / Nursing / Utilization Review / Discharge Planner
UR card must name: concurrent review, denial risk identification, InterQual, Milliman.
Risk Tracking:
Documentation Risk / Insurance Risk / Bed Risk / Clinical Risk
Clinical Risk weighted higher for Acute MI, CHF, ICU.
At Readiness ≥ 75% show Governance Snapshot:
'Industry benchmarks (estimates only): PA turnaround 3–5 days · Inpatient denial rate ~8–10% (CMS) · PA rework cost ~$11/transaction (CAQH)'
Final Decision:
≥ 90% → ✅ Admit — full summary.
< 90% → ⚠ Not Ready — missing items, required actions, remaining risks.

OUTPUT
<img width="1200" height="675" alt="day28-hospital-admission-card" src="https://github.com/user-attachments/assets/12174a74-9146-43e5-bee5-d6e4d6e073a4" />
Day 28 PNG card is ready — 1200×675, LinkedIn-optimized. Here's what's on it:

- **Role badge** — Hospital Admission Coordinator
- **5 diagnoses** with color-coded severity indicators
- **All 5 admission types** as inline tags
- **PA Branches** — Approved / Pending / Denied with action summaries
- **7 workflow tasks** with point values
- **Score weighting breakdown** (PA 25%, Docs 20%, etc.)
- **CMS 2-Midnight / MOON** notice strip in purple
- **Governance benchmarks** — 3–5 day PA turnaround, 8–10% denial rate, ~$11 rework cost
- **Final decision thresholds** — ≥90% Admit / <90% Not Ready
- Readiness score ring at 75% sample
- ABTalks branding + Day 28/60 badge + hashtag footer

Ready to post! Want the LinkedIn caption drafted too?
