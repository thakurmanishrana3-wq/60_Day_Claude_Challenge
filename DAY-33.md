INPUT
You are an expert frontend developer, UX designer, instructional designer, and media literacy analyst.

Ask the user to choose a color theme from a few options (including Claude Orange).

Create a beautiful single-file HTML application called 'Media Integrity Analyzer'.

Use pure vanilla CSS and JS. No Tailwind, npm, backend, APIs, images, or external assets. Everything must work offline in one HTML file.

The goal is to teach media literacy through interactive discovery, not test prior knowledge. The experience should feel like a guided lesson where users learn by observing, thinking, and then revealing the answer.

Make it interactive.

Before each challenge, briefly explain the concept in simple language, why it matters, and how it applies to everyday life.

Challenge 1: Headline Detective
- Generate a fictional news headline and matching article.
- Ask: Would you click this? (Yes / Maybe / No)
- Ask the user to identify exaggerated or misleading parts.
- Reveal the Headline Accuracy Score, highlighted mismatches, explanation, fair rewritten headline, and key takeaway.

Challenge 2: Emotion Detector
- Generate a fictional social media post, reel caption, or article excerpt.
- Ask how it made the user feel and which words influenced that feeling.
- Reveal the target audience, intended emotional response, manipulation technique, highlighted emotional phrases, neutral rewrite, and key takeaway.

Display live Media Integrity metrics:
- Headline Accuracy
- Source Reliability
- Emotional Manipulation
- Audience Targeting

Finish with a Media Integrity Dashboard containing:
- Overall Media Integrity Score
- What the user learned
- Biggest red flag
- Three practical media literacy habits
- Replay with completely new scenarios

Design a premium editorial-style dark interface with smooth animations, progress indicators, hover effects, modern cards, and responsive layout.

Ensure there are zero syntax errors.

Return ONLY the complete HTML inside one code block.

OUTPUT
[media-integrity-analyzer.html](https://github.com/user-attachments/files/31165851/media-integrity-analyzer.html)
Now let me build this. The design plan: newspaper/editorial dark theme with a distinct "truth vs. manipulation" visual language — ink-black base, paper-white text, with a forensic red accent (not generic green/acid). Typography is a bold condensed display face for headlines, system serif for body. The signature element: a live "integrity meter" that pulses like a vital sign monitor.Here's your **Day 33 — Media Integrity Analyzer** 🎯

---

### What's inside the file:

**Theme Picker** — 5 choices including Claude Orange, Midnight Violet, Editorial Red, Forensic Green, and Signal Blue. Each themes the entire app via CSS variables.

**Live Metrics Dashboard** — 4 animated ring meters (Headline Accuracy, Source Reliability, Emotional Manipulation, Audience Targeting) that fill in real-time as you complete each challenge.

**Challenge 1 · Headline Detective**
- 3 rotating fictional scenarios (coffee aging, diet blogger, finance leak)
- Click intent question + free-text observation field
- Reveals: accuracy score bars, color-highlighted mismatches with tooltips, fair rewritten headline, key takeaway

**Challenge 2 · Emotion Detector**
- Fictional viral social posts with emotional manipulation baked in
- Emotion chip selectors + free-text trigger word input
- Reveals: target audience, manipulation technique, emotionally highlighted post text, neutral rewrite

**Media Integrity Dashboard**
- Animated overall score ring with counter
- What you learned, biggest red flag, 3 practical habits
- Replay button picks a fresh random scenario

---

### Suggested LinkedIn caption:

> **Day 33/60 — Media Integrity Analyzer 🔍**
>
> Built a tool that teaches media literacy through *doing*, not reading.
>
> Pick your theme → Analyze a fake headline → Detect emotional manipulation → Get your Media Integrity Score.
>
> Most people share content they've never read past the headline. This tool shows you *exactly* why that happens — and how to stop it.
>
> 🔗 Try it (link in comments)
>
> \#ABTalks60DayChallenge #60DaysOfClaude #ABTalks #MediaLiteracy #FakeNews #CriticalThinking #BuildInPublic
