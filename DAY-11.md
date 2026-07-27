INPUT 
# ATS Resume Optimizer & Resume Generator
Input:
* Existing Resume
* Target Job Description
Task:
Rewrite the resume for maximum ATS alignment and recruiter relevance while maintaining 100% factual accuracy.
Rules:
* Never invent experience, projects, employers, certifications, dates, metrics, or skills.
* Only optimize, reorganize, and rephrase existing content.
* Use relevant JD keywords naturally.
* Keep ATS-friendly formatting.
Output:
1. ATS Match Score
2. Gap Analysis
   * Missing Keywords
   * Missing Skills
   * Improvement Opportunities
3. Updated Resume
Return the complete rewritten resume as a professional resume document using the following structure:
# FULL NAME
Phone | Email | LinkedIn | GitHub
## PROFESSIONAL SUMMARY
## SKILLS
## EXPERIENCE
## PROJECTS
## EDUCATION
## CERTIFICATIONS
## ACHIEVEMENTS
The resume should be fully formatted, ready to copy into Word, Google Docs, FlowCV, Overleaf, or Canva without additional editing.

OUTPUT
[ats_resume_optimizer.html](https://github.com/user-attachments/files/30399427/ats_resume_optimizer.html)
This is a great Day 11 artifact idea — an AI-powered ATS Resume Optimizer! I'll build this as an interactive Claude-powered app where users paste their resume + job description and get back a full analysis.Here's your Day 11 interactive app! Here's what it does:

**Input** — two text areas side by side: current resume + target job description.

**Output** — three things:
1. Three metric cards: ATS match score, keyword coverage, recruiter relevance (color-coded green/yellow/red)
2. Gap analysis — tagged pills showing missing keywords, weak skills, and improvement opportunities
3. Full optimized resume — ready to copy into Word, Google Docs, or FlowCV

**The rules baked into the prompt** — Claude never invents experience, projects, metrics, or skills. It only rephrases and reorganizes using JD keywords naturally, exactly as your spec defined.

You can test it with Manish's resume by pasting the text + any software developer JD. Great Day 11 topic — this is the kind of real-world Claude use case your audience can immediately apply.
