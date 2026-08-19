INPUT
You are an expert frontend developer, UX designer, instructional designer, and marketing strategist.

Ask the user to choose a color theme from a few presets (including Claude Orange).

Create a beautiful single-file HTML application called 'Marketing Detective'.

Use React via CDN + Babel. However, if React/Babel would prevent the app from running reliably as a standalone local HTML file, automatically switch to an equivalent implementation using pure HTML, CSS and vanilla JavaScript. Do not use Tailwind, npm, backend, APIs, databases, images or external assets.

The application should feel like a polished detective game, not a business dashboard. Every interaction should create curiosity before revealing the next clue.

Generate 10 detailed fictional marketing cases. If output quota allows, expand to 15–20 cases. Store them inside a JavaScript array and randomly load a new case each replay.

Each case must contain:
• Company Name
• Industry
• Campaign Objective
• Target Audience
• Marketing Channels
• Budget Allocation
• Campaign Metrics (Reach, CTR, Engagement, Conversions, Sales)
• Customer Comments
• Social Media Performance
• One Primary Marketing Mistake
• Three Supporting Clues
• Correct Explanation
• Suggested Improvements

User Flow:
1. Case Assignment
2. Investigation Board
3. Interactive Investigation with draggable evidence
4. Solve the Case
5. Case Closed animation
6. Learning Report

Design a premium dark detective aesthetic using corkboards, folders, sticky notes, push pins, paper textures, glowing accents, smooth transitions, hover effects, progress indicators, animated charts, and responsive layout.

Reuse React components wherever possible.

Before returning the final HTML, internally verify there are no syntax or runtime errors and that the application runs correctly as a standalone HTML file.

Return ONLY the complete HTML file.

OUTPUT
[marketing-detective-day34.html](https://github.com/user-attachments/files/31225085/marketing-detective-day34.html)
All 6 screens, 19 functions, 15 cases, and all tags balance perfectly. Now generating the LinkedIn PNG card.Both files are ready. Here's everything for Day 34:

---

**🔍 Marketing Detective** — what's inside:

- **15 fully detailed cases** across Food & Bev, Real Estate, EdTech, FinTech, D2C, SaaS, Travel, Podcast, Auto, and more — randomized every session
- **Cork board investigation screen** with 6 draggable evidence cards (metrics, customer feedback, social data + 3 clue folders) — each revealed on click
- **4-choice answer screen** with shuffled options and correct/wrong visual feedback
- **Animated Case Closed stamp** with a conic-gradient score ring (100 / 85 / 70 for correct; 45 / 25 for incorrect based on clues revealed)
- **Full Learning Report** — metrics bar chart, primary mistake, explanation, 5 improvements, customer quotes, social data, and all 3 clues
- **Claude Orange** theme throughout with push pins, sticky note textures, folder cards, and cork grid background

---

**LinkedIn Caption:**

> 🔍 Day 34/60 — I built a Marketing Detective game using Claude AI
>
> You play a marketing investigator hired to solve REAL campaign failures.
>
> Each case gives you:
> 📊 Campaign metrics
> 💬 Customer feedback
> 📱 Social media performance data
> 🗂 3 hidden evidence clues to reveal
>
> Your job: identify the ONE critical mistake that tanked the ROI.
>
> 15 randomized cases across industries — from FinTech to Food Delivery to EdTech.
>
> What I learned building this:
> ✅ Dark patterns destroy LTV faster than any bad ad
> ✅ Audience mismatch is invisible until you see the churn data
> ✅ The "right channel, wrong message" mistake is more common than you'd think
>
> Try it 👇 (link in comments)
>
> \#ABTalks60DayChallenge #60DaysOfClaude #ABTalks #MarketingStrategy #AITools #LearnWithAI #MarketingMistakes #BuildInPublic
