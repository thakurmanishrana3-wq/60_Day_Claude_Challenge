INPUT
Skill Name: brain-dump-action-planner

Description: Transform messy notes, meeting transcripts, voice memos, brainstorming sessions, and stream-of-consciousness thoughts into structured summaries, action plans, decisions, open questions, and task lists. Organize information clearly without inventing, assuming, or filling gaps. Preserve all names, dates, numbers, and terminology exactly as provided.

Instructions:

## Output Requirement

For Full Breakdown, Transcript Mode, and Merge Mode, generate the output as a complete interactive HTML artifact.

Requirements:

* Output a self-contained HTML artifact starting with <style>.
* Use a modern dashboard layout.
* Mobile responsive.
* Use cards, sections, badges, tables, and visual indicators.
* Do not use markdown.
* Use clean typography and strong visual hierarchy.
* Highlight important items using colored status badges.
* Make action items visually prominent.
* Use collapsible sections for long notes.
* Output only the HTML artifact.

### Required Sections

1. Summary

* Short overview of the note, meeting, transcript, or brain dump.

2. Key Takeaways

* Display as cards or structured highlights.

3. Action Items

* Interactive table containing:
* Task
* Owner
* Deadline
* Status

4. Open Questions

* Display unresolved topics and pending decisions.

5. Risks / Blockers

* Display dependencies, blockers, risks, and concerns.

6. Conflicts

* Display conflicting deadlines, owners, decisions, or information.

7. Additional Notes

* Supporting context that does not fit elsewhere.

8. Source Information (Merge Mode only)

* Display merged sources.

### Status Badges

Use:

* 🔴 High Priority
* 🟠 Medium Priority
* 🟢 Low Priority
* ⚠️ Conflict
* ❓ Open Question
* ✅ Completed
* ⏳ Pending

### Missing Information

If information is missing display:

'Not specified'

Never invent values.

### Transcript Mode

Include:

* Speaker Summary
* Decisions by Speaker
* Action Items by Speaker
* Attribution Notes when ownership is unclear

Use speaker labels exactly as provided.

### Merge Mode

Include:

* Duplicate Items Section
* Conflict Resolution Review Section
* Source Note

Never automatically resolve conflicts.

### Design Goals

The final artifact should feel like:

* Notion
* ClickUp
* Linear
* Asana
* Airtable
* Modern Project Dashboard

Use responsive cards, clean tables, section headers, badges, hover effects, soft shadows, and dashboard-style layouts.

Everything displayed must come directly from the provided notes.

Never add, infer, assume, predict, estimate, or complete missing information.

Generate the complete HTML directly starting with <style>.

OUTPUT
<img width="1080" height="1080" alt="day18-brain-dump-planner" src="https://github.com/user-attachments/assets/afbaca70-2a61-4bae-9469-b2bbf6cc604f" />
Now let me build the skill file and then the demo artifact + LinkedIn visual.Now let me build the full interactive HTML demo app:Now let's build the LinkedIn visual card:Day 18 is fully done. Here's what was built:

---

**🧠 Brain Dump → Action Planner** — 3 deliverables:

**1. Interactive HTML App** (`brain-dump-action-planner.html`)
- 4 modes: Full Breakdown, Transcript, Merge, Quick Summary
- Left panel: mode selector, 3 pre-loaded samples (project kickoff, meeting transcript, product brainstorm), free-text input
- Right panel: live Claude-powered dashboard with collapsible sections — Summary, Key Takeaways, Action Items table (task / owner / deadline / priority badge), Open Questions, Risks & Blockers, Conflicts, Additional Notes
- Transcript Mode adds Speaker Breakdown with per-speaker decisions + action items
- Merge Mode adds Source Information + Duplicate Items sections
- Priority badges: 🔴 High / 🟠 Medium / 🟢 Low / ✅ Completed
- **Never invents data** — missing fields display "Not specified" exactly as the skill specifies

**2. LinkedIn PNG Card** (`day18-brain-dump-planner.png`)
- Dark theme, Day 18/60 badge, ABTalks branding
- All 4 mode pills, 4 output section chips, the "never invents" trust callout

**3. Skill File** (`brain-dump-action-planner-SKILL.md`)
- Full spec with invocation modes, output rules, badge legend, design goals — ready to drop into any Claude Project

---

**Suggested LinkedIn post hook:**
> *Your meeting notes are full of gold — and completely unreadable.*
> 
> Day 18 of #60DaysOfClaude: I built a Brain Dump → Action Planner that turns messy notes into a structured dashboard. 4 modes: full breakdown, transcript (with speaker attribution), merge (flags conflicts, never resolves them), and quick summary.
> 
> The rule I'm most proud of: **it never invents a single word.** Every action item, owner, and deadline comes directly from your input.
