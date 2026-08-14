INPUT
You are an expert frontend developer, UX designer, game designer, and supply chain consultant.
Build it so a complete beginner can play it — plain language, context before every decision, 'why does this matter' explanations, and guidance that makes you feel smart rather than lost.
Build a complete single-file HTML app named 'Operation Lifeline: Supply Chain Crisis Lab'.
Requirements:
• Output ONLY one HTML file.
• React via CDN + Babel JSX.
• Plain HTML, CSS, and JavaScript only.
• No Tailwind, npm, backend, APIs, images, or external assets.
• Must run offline by opening the HTML file.
• No placeholders or incomplete features.
Flow:
1. Welcome screen with title, subtitle, and 'Start Simulation'.
2. Generate a random fictional company (industry, revenue, factories, warehouses, suppliers, inventory days, lead time, countries) displayed as modern cards.
3. Generate one random crisis (factory fire, supplier bankruptcy, port strike, cyberattack, flood, raw material shortage, political conflict, shipping delay) with urgency and business impact.
4. War Room: Present six response actions. The player chooses three. Simulate consequences by updating Cost, Inventory, Profit, Delivery Speed, and Customer Satisfaction using animated progress bars.
5. Negotiation: Branching supplier negotiation with four rounds. Each choice affects Trust, Price, and Lead Time. Display a negotiation score.
6. CEO Boardroom: Five multiple-choice leadership questions. Score executive decision-making.
7. AI Strategy: Let the player choose two AI investments from Demand Forecasting, Inventory Optimization, Supplier Risk Monitoring, Warehouse Vision, and Procurement Copilot. Show expected business impact.
8. Final Dashboard: Display Overall Crisis Score (0-100), Leadership, Negotiation, Resilience, Cost Control, Risk Management, and Customer Satisfaction. Include personalized feedback, biggest mistake, best decision, expert recommendation, and lessons learned.
Design:
• Premium dark theme inspired by enterprise dashboards.
• Responsive.
• Rounded cards.
• Smooth transitions.
• Hover effects.
• Progress bars.
• Modern typography.
• Replay button.
• Every playthrough should randomize companies, crises, values, and outcomes.
Structure the React code into reusable components using useState. Ensure every button works, there are no console errors, and the final response contains only the complete HTML code inside a single code block.

OUTPUT
[operation-lifeline.html](https://github.com/user-attachments/files/31059466/operation-lifeline.html)
Now let me build this comprehensive single-file HTML app:**Day 29 is done — here's what's packed into Operation Lifeline:**

---

**🎮 Full game flow (8 screens):**
1. **Welcome** — branded hero with feature chips and "Start Simulation"
2. **Company Profile** — randomized name, industry, revenue, factories, warehouses, suppliers, countries
3. **Crisis Alert** — one of 8 crisis types with animated live alert banner, revenue-at-risk calculation
4. **War Room** — pick 3 of 8 shuffled actions; each shows exact stat deltas (cost, inventory, profit, delivery, satisfaction)
5. **Consequences** — animated progress bars reveal the real impact of your choices with expert insights
6. **4-Round Negotiation** — branching choices affect Trust, Price, Lead Time with a final negotiation score + grade
7. **CEO Boardroom** — 5 randomized leadership questions with scored feedback and auto-advance
8. **AI Strategy** — pick 2 of 5 AI investments with real business impact explanations
9. **Final Dashboard** — overall score (0–100), 6 dimension bars, best/worst decision, expert recommendation, lessons

**Design highlights:** Enterprise dark theme, shimmer-animated progress bars, selection pulse effects, crisis alert scanline animation, conic-gradient score ring, responsive grid layout, stage tracker pip bar throughout.

---

**LinkedIn Post Copy:**

> 🚨 Day 29/60 — I built a Supply Chain Crisis Simulator
>
> Your company just got hit by a Factory Fire. Port Strike. Cyberattack.
> What do you do in the next 60 minutes?
>
> Operation Lifeline puts you in the hot seat as Chief Supply Chain Officer:
>
> ⚔️ War Room → Pick 3 response actions with real trade-offs
> 🤝 Supplier Negotiation → 4 rounds that test your trust-building skills
> 👔 CEO Boardroom → 5 leadership decisions scored like a consulting case
> 🤖 AI Strategy → Invest in tools that prevent the next crisis
>
> Every playthrough randomizes the company, crisis, and outcomes.
>
> No code needed to play — opens in any browser, runs offline.
>
> Built with React + Vanilla JS in a single HTML file. Zero dependencies.
>
> 🔗 Link in comments
>
> #60DaysOfClaude #ABTalks60DayChallenge #SupplyChain #ABTalks #AIProjects
