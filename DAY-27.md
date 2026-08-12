INPUT
Prior Authorization Story Simulator
Single-file HTML app. HTML, Tailwind CSS CDN, Vanilla JavaScript.
Use createElement + appendChild for every new chat bubble. Never call innerHTML = on the chat container.
Design: same as previously established.
Characters
👦 Rahul — patient. Appears left.
👧 Priya — healthcare operations specialist. Appears right.
Narrators and doctors appear as centered italic text only, never chat bubbles.
Story — 8 scenes with append-only chat feed and progress bar:
1. Doctor Visit — Rahul visits City Medical Center. Dr. Patel diagnoses Rheumatoid Arthritis, prescribes Humira.
2. Insurance Roadblock — Dr. Patel's office submits PA directly to StarCare Health (payer). No pharmacy involved. Flow: Provider → PA Request → Payer. Approved PA is saved on file permanently.
3. What is PA? — Priya explains in plain language. Include: step therapy isn't just bureaucracy — for aggressive diagnoses, delays can affect disease progression. Cite: 'AMA 2023 PA Survey: PA causes treatment delays in the majority of cases.'
4. Insurance Review — Priya walks through what StarCare Health checks: eligibility, clinical documentation, ICD-10 diagnosis match, step therapy history. Explain why each matters.
5. Denial — Denied: missing step therapy documentation. Denial ≠ permanent. Priya notes the system side: 'PA denials cost physician offices 2+ staff hours to resolve.'
6. Appeal — Gather documents, Letter of Medical Necessity, formal appeal filing.
7. Approval — PA approved, saved on file. Reference number issued. No repeat PA needed for Humira.
8. Takeaways — Two perspectives: Patient (what Rahul learned) + System (how health systems track denial rate, appeal rate, resolution time).
After each scene show 2 choices that influence dialogue and progression.
Label StarCare Health as an illustrative example throughout.
Beginner-friendly language.
Healthcare education design system.

OUTPUT
[prior-auth-simulator.html](https://github.com/user-attachments/files/30982312/prior-auth-simulator.html)
Now I have everything I need. Let me build this app:Here's Day 27 — the Prior Authorization Story Simulator! Here's what's built in:

**Structure**
- 8 scenes with a progress bar + 8 dot indicators that turn blue (active) → green (done)
- Every scene uses `createElement` + `appendChild` only — no `innerHTML =` on the feed, as specified
- Rahul 👦 always left, Priya 👧 always right, narrators appear as centered italics only

**Interactions**
- 2 choices per scene that actually branch the dialogue — Priya says something different depending on your pick (e.g., "why does PA exist" vs "what does StarCare check" gives different Scene 2 openers)
- Choices are disabled during rendering, re-enabled after each scene completes

**Visual cards used**
- Blue `info-card` for neutral facts
- Red `denial-card` for the denial moment
- Green `success-card` for approval
- Yellow `stat-pill` for the AMA citation and operational stats
- Flow diagram for the Provider → PA Request → Payer → Decision workflow

**Content accuracy**
- StarCare Health labeled as illustrative throughout
- AMA 2023 PA Survey stat placed in Scene 3
- Step therapy, ICD-10, LMN, peer-to-peer, external review — all explained in beginner language
- Takeaways end card has both Patient and System (denial rate, appeal rate, resolution time, overturn rate) perspectives
