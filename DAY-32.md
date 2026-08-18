INPUT
Think Like a Marketing Strategist: Grow This Brand:

You are an expert frontend developer, UX designer, marketing strategist, and instructional designer.

Build a complete single-file HTML app called: "Think Like a Marketing Strategist: Grow This Brand"

The goal is to teach beginners how marketers think, not just generate marketing content. Every section should explain "What is this?" and "Why does it matter?" in simple language.

Requirements

Output ONLY one HTML file

React via CDN + Babel JSX

HTML, CSS and JavaScript only

No Tailwind, npm, backend or APIs

Runs offline

Responsive

Dark modern UI

Replayable with randomized businesses

Flow

Welcome screen introducing marketing strategy.

Let the user choose:

🏢 Use My Own Business

🙋 Build My Personal Brand ← if someone doesn't have a business, this lets them use their own name, expertise, and story as the brand

🎲 A New Client Has Arrived (randomly generate a business with industry, audience, budget, competitors and marketing challenge)

Teach the user to understand the business/brand and its audience. For personal brands, the "product" is the person's expertise and story. Replace "competitors" with "people in your space you admire."

Ask the user to choose the best social media platforms. Explain why each platform is or isn't suitable. For personal brands, weight LinkedIn, X/Twitter, YouTube, and newsletters more heavily.

Generate multiple content pillars. The user must choose only three. For personal brands, include pillars like Thought Leadership, Personal Story, Behind the Scenes, and Audience Education. Explain how each supports different goals.

Build a simple 30-day content roadmap showing weekly goals and strategy (not individual posts). For personal brands, Week 1 should focus on defining POV and optimizing bio/profile.

Generate one unexpected marketing event. For personal brands this could be: a viral post, a podcast invite, a public disagreement, someone copying your content, or a sudden follower spike. Let the user respond and explain consequences.

End with a Growth Report containing:

Audience Understanding

Platform Strategy

Content Strategy

Growth Potential

Best Decision

Biggest Mistake

Three Marketing Lessons

For personal brands, lessons should reference personal branding principles like authenticity, consistency, and niche clarity.

After every major section, include a "How to ask Claude" card with a reusable prompt so users learn prompt engineering while learning marketing. For personal brand mode, the prompts should reference the person's name and niche instead of a company.

Use reusable React components with useState. Add smooth transitions, cards, progress indicators and ensure every button works.

OUTPUT
[day32-marketing-strategist.html](https://github.com/user-attachments/files/31165227/day32-marketing-strategist.html)
The file already exists from the previous message — it's the complete Day 32 app. Let me present it:Here's everything packed into your Day 32 file. Here's what's inside:

**3 Brand Modes**
- 🏢 Own Business — custom input form
- 🙋 Personal Brand — name + expertise + story + target audience, with adapted copy throughout
- 🎲 Random Client — 8 pre-built businesses (D2C pet supplies, craft coffee, mental wellness app, sustainable packaging, etc.) that randomize on each play

**Full 7-step flow with progress indicator**
1. Welcome → Mode Select → Setup → Audience Map → Platform Strategy → Content Pillars → 30-Day Roadmap → Unexpected Event → Growth Report

**Smart platform cards** — sorted by fit (Strong/Good/Low) based on whether you're in business or personal brand mode, with a why-it-works and why-it-doesn't explanation per platform

**8 content pillars per mode** — business pillars (Education, Social Proof, BTS, Entertainment, Product, Values, Collabs, UGC) and personal pillars (Thought Leadership, Personal Story, BTS, Education, Tools, Collabs, Wins, Hot Takes) — user picks exactly 3

**Fully mode-aware** — personal brand roadmap starts Week 1 with "POV & Profile," all event copy, report language, lessons, and Claude prompts reference the person's name and niche

**Claude Prompt Cards** after every section — copyable prompts that users can paste directly into Claude, teaching prompt engineering alongside marketing

**Growth Report** with animated score ring, metric bars, Best Decision / Watch Out For cards, and 3 tailored lessons

---

**LinkedIn Caption for Day 32:**

> Day 32/60 — I built a marketing strategy simulator 🧠📱
>
> Not a "generate content" tool. A *think like a strategist* tool.
>
> Most people post randomly and wonder why nothing grows. This app teaches the actual order marketers work in:
>
> Audience first → Platform choice → Content pillars → 30-day roadmap → Crisis response
>
> 3 modes:
> 🏢 Your own business
> 🙋 Your personal brand (if you don't have a business yet — this is for you)
> 🎲 Random client drop — practice marketing a brand you've never seen
>
> After every section? A copyable Claude prompt so you're learning prompt engineering *while* learning strategy.
>
> Built with: React (CDN), vanilla JS, zero backend — runs fully offline.
>
> Drop in the comments: what's your biggest marketing question right now? 👇
>
> #ABTalks60DayChallenge #60DaysOfClaude #ABTalks #MarketingStrategy #PersonalBranding #AITools #BuildInPublic #ReactJS #Day32
