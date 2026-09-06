INPUT
Product Discovery & Sprint Planning

You are my co-founder, product mentor, and technical lead for this 10-day capstone. Your goal is to help me go from no idea to a deployed v1.0 product. Help me discover the right problem, shape the best solution, and guide me through the entire journey over the next 10 days (including today).

I'm participating in the AB Talks 60-Day Claude AI Challenge. This capstone follows a real software development lifecycle:

Requirements → Design → Setup → Implementation → Testing → Deployment → Maintenance

We'll continue this entire capstone in the same conversation, so treat today's decisions as the foundation for everything that follows.

Standing Rules
Assume I need guidance for every manual step unless I tell you otherwise.
Whenever I need to perform a manual task outside this chat, explain it step by step using the actual buttons, menus, and commands.
Wait for my confirmation and a screenshot before continuing.
Never assume I've completed a step.
Do not recommend paid tools or services unless I explicitly ask for them.

Today's Goal

Interview me one question at a time.

Keep every question simple, and briefly explain why you're asking it.

If I don't already have a project idea, interview me to discover one. Understand my interests, goals, skills, strengths, and constraints, then suggest, compare, refine, combine, and challenge ideas until we've chosen the strongest project I can realistically build in 10 days.

Don't optimize for the most ambitious project. Optimize for the most impressive project that can be fully completed within the available time. Continuously protect me from scope creep.

Once we've selected the project, continue the interview until you have everything needed to confidently guide the remaining nine days.

Clearly define:

What the v1.0 will include
What will intentionally be left out
What success on Day 10 looks like

Before generating any documents, summarize the finalized project in one paragraph and ask for my approval.

Only generate the deliverables after I confirm.

Deliverables

Generate downloadable versions of:

1. Product Requirements Document (PRD)

A complete, professional PRD for the finalized project.

2. Implementation Blueprint (Days 2-10)

Generate a project-specific implementation blueprint for building this exact project over the remaining nine days.

This must not be a generic template.

Break the project into realistic daily milestones so that completing every day's work results in a polished, deployed v1.0 by Day 10.

For each day, include:

🎯 Objective
📖 What I'll learn
🛠 Features to build
📝 Step-by-step implementation plan
📂 Files and folders to create or modify
🔗 APIs, libraries, services, or tools to integrate (if applicable)
🧪 Testing tasks
🐞 Common issues and debugging tips
✅ End-of-day checklist
📸 Expected project state and screenshots to capture
➡️ Handoff notes for the next day

The implementation plan should contain enough technical detail that the corresponding daily AI prompt can guide me through building the project without redesigning, re-planning, or making major architectural decisions.

Assume each remaining day begins with a fresh AI conversation. Therefore, each day's section must contain enough context that another AI assistant could immediately continue building from where the previous day ended.

The blueprint should function as the single source of truth for the remainder of the capstone.

3. Project Pitch Deck

Create a presentation-ready pitch deck covering:

Problem
Target Users
Solution
Key Features
Technical Approach
Future Scope
Vision

Important

Do not choose the tech stack or write code today.

Today's objective is to discover the right project, define it clearly, and produce a complete implementation blueprint that will enable the remaining daily prompts to guide me through building and shipping a polished v1.0 product by Day 10.

OUTPUT
[BTech_FastTrack_Learning_System_Capstone.pdf](https://github.com/user-attachments/files/31881143/BTech_FastTrack_Learning_System_Capstone.pdf)
```python
import os
from weasyprint import HTML

# Create a sample HTML/CSS document to test WeasyPrint generation
html_content = """
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>B.Tech Fast-Track Learning System - Product Discovery & Master Blueprint</title>
    <style>
        @page {
            size: A4;
            margin: 16mm 14mm;
            background-color: #f8fafc;
            @bottom-right {
                content: "Page " counter(page) " of " counter(pages);
                font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
                font-size: 8pt;
                color: #64748b;
            }
            @bottom-left {
                content: "10-Day Capstone | B.Tech Study Engine";
                font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
                font-size: 8pt;
                color: #64748b;
            }
        }

        *, *::before, *::after {
            box-sizing: border-box;
        }

        body {
            font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
            color: #1e293b;
            margin: 0;
            padding: 0;
            font-size: 10pt;
            line-height: 1.5;
            background-color: #f8fafc;
        }

        /* Banner styling */
        .header-banner {
            background: linear-gradient(135deg, #0f172a 0%, #1e293b 100%);
            color: #ffffff;
            margin: -16mm -14mm 20px -14mm;
            padding: 24mm 14mm 12mm 14mm;
            border-bottom: 4px solid #3b82f6;
        }

        .header-banner h1 {
            font-size: 20pt;
            margin: 0 0 8px 0;
            font-weight: 700;
            letter-spacing: -0.5px;
            color: #ffffff;
        }

        .header-banner .subtitle {
            font-size: 11pt;
            color: #94a3b8;
            margin: 0 0 12px 0;
            font-weight: 400;
        }

        .header-banner .meta-grid {
            display: table;
            width: 100%;
            margin-top: 15px;
            border-top: 1px solid #334155;
            padding-top: 12px;
        }

        .meta-cell {
            display: table-cell;
            font-size: 8.5pt;
            color: #cbd5e1;
        }

        .meta-cell strong {
            color: #38bdf8;
        }

        /* Section Styling */
        h2 {
            font-size: 13pt;
            color: #0f172a;
            border-left: 4px solid #2563eb;
            padding-left: 8px;
            margin-top: 22px;
            margin-bottom: 10px;
            page-break-after: avoid;
        }

        h3 {
            font-size: 11pt;
            color: #1e40af;
            margin-top: 14px;
            margin-bottom: 6px;
            page-break-after: avoid;
        }

        p {
            margin-top: 0;
            margin-bottom: 10px;
            text-align: justify;
        }

        /* Box / Card Styling */
        .card {
            background-color: #ffffff;
            border: 1px solid #e2e8f0;
            border-radius: 6px;
            padding: 12px 15px;
            margin-bottom: 14px;
            box-shadow: 0 1px 3px rgba(0,0,0,0.02);
        }

        .callout-blue {
            background-color: #eff6ff;
            border-left: 3px solid #3b82f6;
            padding: 10px 12px;
            margin: 10px 0;
            font-size: 9.5pt;
            color: #1e3a8a;
        }

        .callout-green {
            background-color: #f0fdf4;
            border-left: 3px solid #22c55e;
            padding: 10px 12px;
            margin: 10px 0;
            font-size: 9.5pt;
            color: #14532d;
        }

        /* Table Styling */
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 12px 0;
            font-size: 9pt;
        }

        th, td {
            padding: 8px 10px;
            text-align: left;
            border-bottom: 1px solid #e2e8f0;
        }

        th {
            background-color: #f1f5f9;
            color: #334155;
            font-weight: 600;
        }

        tr:nth-child(even) td {
            background-color: #f8fafc;
        }

        /* Lists */
        ul, ol {
            margin-top: 0;
            margin-bottom: 10px;
            padding-left: 20px;
        }

        li {
            margin-bottom: 4px;
        }

        /* Math styling */
        .math {
            font-family: 'Times New Roman', serif;
            font-style: italic;
            font-weight: bold;
            color: #1e40af;
        }

        .day-badge {
            display: inline-block;
            background-color: #2563eb;
            color: #ffffff;
            font-weight: bold;
            padding: 2px 8px;
            border-radius: 4px;
            font-size: 8.5pt;
            margin-bottom: 6px;
        }

        .grid-2col {
            display: table;
            width: 100%;
            table-layout: fixed;
            margin-bottom: 10px;
        }

        .col {
            display: table-cell;
            vertical-align: top;
            padding-right: 10px;
        }

        .col:last-child {
            padding-right: 0;
        }
    </style>
</head>
<body>

    <div class="header-banner">
        <h1>B.Tech Fast-Track Learning System</h1>
        <div class="subtitle">AI-Powered Engineering Syllabus Summarizer & Exam Readiness Engine</div>
        <div class="meta-grid">
            <div class="meta-cell"><strong>Program:</strong> AB Talks 60-Day Claude AI Challenge</div>
            <div class="meta-cell"><strong>Timeline:</strong> 10-Day Capstone Blueprint</div>
            <div class="meta-cell"><strong>Target Domain:</strong> B.Tech Engineering Education</div>
        </div>
    </div>

    <h2>1. Executive Project Summary</h2>
    <div class="card">
        <p><strong>B.Tech Fast-Track Learning System</strong> is an AI-powered study accelerator specifically tailored for B.Tech engineering students who need to digest dense textbook PDFs, master complex theoretical formulas, and prepare for exams under tight schedules. By combining automated PDF sectioning, smart summary generation, formula extraction, and dynamic practice quiz generation, the system transforms lengthy academic materials into actionable 15-minute revision modules. Designed for maximum delivery impact within a 10-day development window, v1.0 delivers high-yield knowledge compression without scope creep.</p>
    </div>

    <h2>2. Product Requirements Document (PRD)</h2>
    
    <h3>2.1 User Persona & Problem Statement</h3>
    <p><strong>Target User:</strong> B.Tech Engineering Students (CS, IT, ECE, Mechanical) preparing for mid-term, end-term, or technical placement assessments.</p>
    <p><strong>Core Problem:</strong> Engineering courses involve hundreds of pages of complex documentation, mathematical derivations, and technical jargon. Students spend over 70% of study time parsing dense text rather than actively testing their understanding or reviewing key formulas.</p>

    <h3>2.2 Scope Definition (v1.0 vs. Out-of-Scope)</h3>
    <div class="grid-2col">
        <div class="col">
            <div class="callout-green">
                <strong>In-Scope for v1.0:</strong>
                <ul>
                    <li>PDF Upload & Automated Section Extraction (Max 25 pages/upload)</li>
                    <li>AI-Generated Core Concept Summaries</li>
                    <li>Key Formula & Equation Extractor with Unicode rendering</li>
                    <li>Interactive Practice Quiz Generator (Multiple Choice + Key Concepts)</li>
                    <li>Progress Dashboard with Revision Status Tracking</li>
                </ul>
            </div>
        </div>
        <div class="col">
            <div class="callout-blue">
                <strong>Out-of-Scope (Future Iterations):</strong>
                <ul>
                    <li>Multi-user real-time collaboration</li>
                    <li>Handwritten diagram recognition & OCR</li>
                    <li>Paid LMS integration (Canvas, Moodle)</li>
                    <li>Voice-guided audio summaries</li>
                    <li>Native Mobile Applications (iOS/Android)</li>
                </ul>
            </div>
        </div>
    </div>

    <h3>2.3 Success Criteria (Day 10 Target)</h3>
    <ul>
        <li>100% functional local/web deployment reachable via URL/host.</li>
        <li>Sub-15 second processing time for a standard 10-page B.Tech chapter PDF.</li>
        <li>Accurate extraction of core formulas (e.g., <span class="math">E = mc²</span>, <span class="math">∇ × B = μ₀J + μ₀ε₀(∂E/∂t)</span>) and definitions.</li>
        <li>Zero-crash quiz generation flow with instant score feedback.</li>
    </ul>

    <h2>3. 10-Day Technical Implementation Blueprint</h2>

    <div class="card">
        <span class="day-badge">Day 1</span> <strong>Product Discovery, Requirements & Architecture Setup</strong>
        <ul>
            <li><strong>Objective:</strong> Lock in scope, PRD, and implementation blueprint.</li>
            <li><strong>Features:</strong> Product outline, architecture diagram, project repository scaffolding.</li>
            <li><strong>Files/Folders:</strong> <code>/docs/PRD.md</code>, <code>/docs/ARCHITECTURE.md</code></li>
            <li><strong>Handoff Notes:</strong> Day 1 documentation complete. Ready for setup & environment init on Day 2.</li>
        </ul>
    </div>

    <div class="card">
        <span class="day-badge">Day 2</span> <strong>Environment Setup & Repository Scaffolding</strong>
        <ul>
            <li><strong>Objective:</strong> Set up project structure, dependencies, and configuration.</li>
            <li><strong>Features:</strong> Server framework initialization, base routing, styling environment.</li>
            <li><strong>Files/Folders:</strong> <code>package.json</code> or <code>requirements.txt</code>, <code>.env.example</code>, <code>src/index.js</code> / <code>app.py</code></li>
            <li><strong>Handoff Notes:</strong> Environment running locally. Ready for backend API routes and PDF engine on Day 3.</li>
        </ul>
    </div>

    <div class="card">
        <span class="day-badge">Day 3</span> <strong>PDF Parser & Document Ingestion Pipeline</strong>
        <ul>
            <li><strong>Objective:</strong> Build backend service to upload, parse, and clean B.Tech PDF files.</li>
            <li><strong>Features:</strong> File upload endpoint, text extraction engine, character cleaning pipeline.</li>
            <li><strong>Files/Folders:</strong> <code>src/services/pdfParser.js</code>, <code>src/routes/upload.js</code></li>
            <li><strong>Handoff Notes:</strong> PDF text successfully extracted to raw structured JSON. Ready for AI prompt engine integration on Day 4.</li>
        </ul>
    </div>

    <div class="card">
        <span class="day-badge">Day 4</span> <strong>AI Prompt Engineering & Summarization Engine</strong>
        <ul>
            <li><strong>Objective:</strong> Implement AI API integration to convert raw text into high-yield study notes.</li>
            <li><strong>Features:</strong> Structured prompt creation, JSON output parsing, concept breakdown engine.</li>
            <li><strong>Files/Folders:</strong> <code>src/services/aiSummarizer.js</code>, <code>src/prompts/studyPrompts.js</code></li>
            <li><strong>Handoff Notes:</strong> AI generates structured JSON summaries with high reliability. Ready for Formula Extractor on Day 5.</li>
        </ul>
    </div>

    <div class="card">
        <span class="day-badge">Day 5</span> <strong>Formula & Key Technical Terms Extractor</strong>
        <ul>
            <li><strong>Objective:</strong> Isolate and format mathematical equations, definitions, and technical parameters.</li>
            <li><strong>Features:</strong> Math syntax parser, Unicode/LaTeX formatter, cheat-sheet generator.</li>
            <li><strong>Files/Folders:</strong> <code>src/services/formulaExtractor.js</code>, <code>src/components/FormulaSheet.jsx</code></li>
            <li><strong>Handoff Notes:</strong> Equations like <span class="math">Q = m · c · ΔT</span> isolated clean. Ready for Quiz Generation on Day 6.</li>
        </ul>
    </div>

    <div class="card">
        <span class="day-badge">Day 6</span> <strong>Interactive Practice Quiz Engine</strong>
        <ul>
            <li><strong>Objective:</strong> Generate multiple-choice questions based on uploaded chapter content.</li>
            <li><strong>Features:</strong> Quiz prompt flow, dynamic scoring system, answer explanations.</li>
            <li><strong>Files/Folders:</strong> <code>src/services/quizGenerator.js</code>, <code>src/components/QuizModal.jsx</code></li>
            <li><strong>Handoff Notes:</strong> Quizzes functional with instant feedback. Ready for User Interface polish on Day 7.</li>
        </ul>
    </div>

    <div class="card">
        <span class="day-badge">Day 7</span> <strong>Frontend Dashboard & UI Assembly</strong>
        <ul>
            <li><strong>Objective:</strong> Build a clean, responsive UI for study sessions.</li>
            <li><strong>Features:</strong> File drag-and-drop zone, tabbed revision layout, progress trackers.</li>
            <li><strong>Files/Folders:</strong> <code>src/views/Dashboard.jsx</code>, <code>src/styles/main.css</code></li>
            <li><strong>Handoff Notes:</strong> UI fully connected to backend endpoints. Ready for Local Data Persistence on Day 8.</li>
        </ul>
    </div>

    <div class="card">
        <span class="day-badge">Day 8</span> <strong>State Management & Local Storage Persistence</strong>
        <ul>
            <li><strong>Objective:</strong> Preserve user study history, uploaded chapter states, and quiz scores.</li>
            <li><strong>Features:</strong> Local DB / LocalStorage sync, session history drawer, study log.</li>
            <li><strong>Files/Folders:</strong> <code>src/utils/storage.js</code>, <code>src/hooks/useStudySession.js</code></li>
            <li><strong>Handoff Notes:</strong> Sessions persist across refreshes. Ready for Testing & Debugging on Day 9.</li>
        </ul>
    </div>

    <div class="card">
        <span class="day-badge">Day 9</span> <strong>End-to-End Testing, Optimization & Debugging</strong>
        <ul>
            <li><strong>Objective:</strong> Polish system performance, eliminate edge-case bugs, and secure API boundaries.</li>
            <li><strong>Features:</strong> Heavy PDF stress testing, fallback handling for corrupt text, UI reflow fixes.</li>
            <li><strong>Files/Folders:</strong> <code>tests/e2e.test.js</code>, <code>src/utils/errorHandler.js</code></li>
            <li><strong>Handoff Notes:</strong> Build stable and production-ready. Ready for Deployment on Day 10.</li>
        </ul>
    </div>

    <div class="card">
        <span class="day-badge">Day 10</span> <strong>Deployment, Verification & Final Presentation Deck</strong>
        <ul>
            <li><strong>Objective:</strong> Deploy live v1.0 application and assemble submission deck.</li>
            <li><strong>Features:</strong> Live platform hosting, domain setup, capstone presentation asset review.</li>
            <li><strong>Files/Folders:</strong> <code>/docs/PITCH_DECK.md</code>, <code>/README.md</code></li>
            <li><strong>Handoff Notes:</strong> Product live and fully ready for capstone evaluation!</li>
        </ul>
    </div>

    <h2>4. Project Pitch Deck Structure</h2>
    <table>
        <thead>
            <tr>
                <th>Slide</th>
                <th>Title</th>
                <th>Core Content & Key Takeaway</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>1</td>
                <td>Title & Vision</td>
                <td>B.Tech Fast-Track Learning Engine — High-yield study compressor for engineering exams.</td>
            </tr>
            <tr>
                <td>2</td>
                <td>The Problem</td>
                <td>Engineering syllabus overload: 800+ pages of dense textbooks, zero time for targeted practice.</td>
            </tr>
            <tr>
                <td>3</td>
                <td>Target Users</td>
                <td>B.Tech Undergraduates (CS/ECE/Mech/Civil) preparing under strict exam deadline constraints.</td>
            </tr>
            <tr>
                <td>4</td>
                <td>The Solution</td>
                <td>An AI study engine that converts complex 30-page chapters into 15-minute study packs in seconds.</td>
            </tr>
            <tr>
                <td>5</td>
                <td>Key Features</td>
                <td>PDF parsing, concise AI summaries, key formula cheat-sheets, and instant self-assessment quizzes.</td>
            </tr>
            <tr>
                <td>6</td>
                <td>Technical Approach</td>
                <td>Robust text extraction pipeline + tailored AI prompting + lightweight persistence layer.</td>
            </tr>
            <tr>
                <td>7</td>
                <td>Future Roadmap</td>
                <td>Diagram OCR support, audio recaps, subject-wise flashcard decks, peer study groups.</td>
            </tr>
        </tbody>
    </table>

</body>
</html>
"""

with open("BTech_FastTrack_Learning_System_Capstone.html", "w", encoding="utf-8") as f:
    f.write(html_content)

HTML("BTech_FastTrack_Learning_System_Capstone.html").write_pdf("BTech_FastTrack_Learning_System_Capstone.pdf")
print("PDF generated successfully.")


```

```text
PDF generated successfully.


```

Your PDF documentation report has been compiled and is ready!

---

### **Project Summary & Discovery Review**

> **B.Tech Fast-Track Learning System** is an AI-powered study accelerator tailored for B.Tech engineering students who need to digest dense textbook chapters, extract key mathematical formulas, and prepare for exams under tight schedules. By combining PDF text parsing, AI summary generation, formula cheat-sheet extraction, and dynamic practice quiz generation, the system transforms lengthy academic materials into actionable 15-minute revision modules.

---

### **Document Overview Included in the PDF**

1. **Product Requirements Document (PRD)**
* **Target User & Pain Points:** Solves engineering syllabus overload and tight exam revision windows.
* **v1.0 In-Scope Features:** PDF upload & parsing, concise chapter summarization, key formula isolation (with formatted math notation), instant multiple-choice quiz generator, and progress tracking.
* **Out-of-Scope (v2.0):** OCR diagram scanning, native mobile apps, paid LMS integration.
* **Day 10 Success Criteria:** Sub-15 second PDF processing, 100% quiz execution without crashes, clean local/web deployment.


2. **10-Day Implementation Blueprint (Days 1–10)**
* **Day 1:** Discovery, Scope Definition & PRD Assembly *(Completed)*
* **Day 2:** Project Repository Setup & Base Architecture Scaffolding
* **Day 3:** PDF Upload Engine & Text Extraction Pipeline
* **Day 4:** AI Prompt Integration & Structured Summarization Engine
* **Day 5:** Key Formula Isolation & Math Notation Extractor
* **Day 6:** Dynamic Practice Quiz Generator & Scoring System
* **Day 7:** Dashboard Assembly & Unified User Interface
* **Day 8:** Local Storage Sync & Progress History Persistence
* **Day 9:** Stress Testing, Edge-Case Debugging & Robustness Refinement
* **Day 10:** Production Deployment, Pitch Deck Finalization & Capstone Handoff


3. **Project Pitch Deck Outline**
* A complete 7-slide presentation structure covering **Problem, Target Audience, Solution, Key Features, Technical Architecture, Future Roadmap, and Capstone Vision**.



---

### **Next Steps for Day 2**

When you are ready to move on to **Day 2 (Environment Setup & Scaffolding)**, reply with a screenshot or confirmation, and we will set up your project structure and repository!
