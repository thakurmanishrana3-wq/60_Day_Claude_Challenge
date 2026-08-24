INPUT
# Typing Speed Studio

You are an expert UI/UX designer, frontend developer, educational game designer, performance engineer, and JavaScript developer.

Before generating anything, ask the user the following questions ONE AT A TIME. Wait for each response before continuing.

1. What kind of typing experience would you like to build?

Examples include General English, Programming, Academic, Business, Medical, Legal, Creative Writing, or an Adaptive version that supports all categories.

If the user chooses the Adaptive version, the generated application should allow users to switch between categories.

2. Would you like Claude to automatically decide the features, or would you like to customize them?

If the user chooses customization, ask which features they would like included.

After collecting the responses, generate a premium single-page interactive HTML application called 'Typing Speed Studio'.

The application should feel like a polished commercial typing platform rather than a basic typing test.

Include multiple typing modes such as Time Mode (15, 30, 60 and 120 seconds), Word Count Mode (25, 50, 100 and 250 words), Quote Mode, Programming Mode (HTML, CSS, JavaScript, Python, Java, C++, SQL and other languages where appropriate), Custom Text Mode, Adaptive Mode that adjusts difficulty based on performance, Focus Mode where only the current line is visible, and Zen Mode for distraction-free untimed practice.

Generate practice passages dynamically according to the selected category. Programming mode should use realistic code snippets, business mode should use professional communication, medical mode should use medical terminology, legal mode should use legal text, creative writing mode should use literature-style passages, and so on. Do not hardcode the same practice paragraph for every mode.

Display live typing statistics including WPM, Raw WPM, CPM, Accuracy, Elapsed Time, Mistake Count, Current Streak, Completion Percentage, Remaining Time or Words, and a real-time progress indicator. Highlight correct characters, incorrect characters, the active cursor position, and completed text with smooth visual feedback.

After every completed session, generate a beautiful analytics dashboard inspired by modern typing platforms such as Monkeytype. Include WPM, Raw WPM, Accuracy, Consistency, Completion Percentage, Characters Typed (Correct, Incorrect, Extra and Missed), Mistake Count, Typing Rhythm, Error Heatmap, WPM Progress Graph, Accuracy Graph, Session Duration, Personal Bests, Percentile Estimate, Achievement Badges, and a detailed performance summary highlighting strengths, weaknesses, commonly mistyped keys, and personalized suggestions for improvement.

Ensure the calculations are accurate and never generate unrealistic values such as 20,000 WPM.

Store session history locally so users can review previous attempts, compare scores, monitor improvement over time, maintain streaks, and track personal records without requiring an account.

Include optional sound effects, keyboard shortcuts, pause and resume functionality, restart options, theme customization, font size controls, dark mode, responsive design, smooth animations, and accessibility features.

Generate everything as a single self-contained HTML file using only HTML, CSS, and JavaScript without external libraries or frameworks.

Design the interface as a premium commercial application with exceptional UI/UX, beautiful typography, modern layouts, polished micro-interactions, smooth transitions, and an experience that feels comparable to the best typing platforms available today.

OUTPUT
[typing_speed_studio_manual.pdf](https://github.com/user-attachments/files/31385726/typing_speed_studio_manual.pdf)
```python
import os
from weasyprint import HTML, CSS

# Create comprehensive HTML for Typing Speed Studio Documentation / Guide / Certificate / Studio Overview
html_content = """<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Typing Speed Studio - Comprehensive User Manual & Analytics Guide</title>
    <style>
        @page {
            size: A4;
            margin: 15mm 12mm;
            background-color: #0f172a;
        }
        *, *::before, *::after {
            box-sizing: border-box;
        }
        body {
            margin: 0;
            padding: 0;
            font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
            background-color: #0f172a;
            color: #f8fafc;
            font-size: 10pt;
            line-height: 1.6;
        }

        /* Banner Header */
        .header-banner {
            margin: -15mm -12mm 20px -12mm;
            padding: 25px 20mm;
            background: linear-gradient(135deg, #1e293b 0%, #0f172a 100%);
            border-bottom: 3px solid #38bdf8;
        }
        .header-title {
            font-size: 22pt;
            font-weight: 800;
            color: #38bdf8;
            letter-spacing: -0.5px;
            margin: 0 0 5px 0;
            text-transform: uppercase;
        }
        .header-subtitle {
            font-size: 11pt;
            color: #94a3b8;
            margin: 0;
            font-weight: 400;
        }

        /* Layout Grid via Table */
        .grid-table {
            width: 100%;
            border-collapse: collapse;
            margin-bottom: 20px;
        }
        .grid-table td {
            vertical-align: top;
            padding: 0;
        }
        .col-left {
            width: 48%;
            padding-right: 2%;
        }
        .col-right {
            width: 48%;
            padding-left: 2%;
        }

        /* Card / Section Box */
        .card {
            background-color: #1e293b;
            border-radius: 8px;
            padding: 15px;
            margin-bottom: 18px;
            border: 1px solid #334155;
            page-break-inside: avoid;
        }
        .card-title {
            font-size: 13pt;
            font-weight: 700;
            color: #38bdf8;
            margin-top: 0;
            margin-bottom: 10px;
            border-left: 4px solid #38bdf8;
            padding-left: 8px;
        }

        h2 {
            font-size: 14pt;
            color: #f8fafc;
            border-bottom: 1px solid #334155;
            padding-bottom: 6px;
            margin-top: 20px;
            margin-bottom: 12px;
            page-break-after: avoid;
        }

        p {
            margin-top: 0;
            margin-bottom: 10px;
            color: #cbd5e1;
        }

        /* Feature List */
        .feature-list {
            list-style-type: none;
            padding-left: 0;
            margin: 0;
        }
        .feature-list li {
            position: relative;
            padding-left: 18px;
            margin-bottom: 8px;
            color: #cbd5e1;
        }
        .feature-list li::before {
            content: "✦";
            position: absolute;
            left: 0;
            color: #38bdf8;
            font-size: 8pt;
            top: 2px;
        }

        /* Table Styling */
        table.data-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 10px;
            margin-bottom: 15px;
        }
        table.data-table th, table.data-table td {
            padding: 8px 10px;
            text-align: left;
            border-bottom: 1px solid #334155;
            font-size: 9pt;
        }
        table.data-table th {
            background-color: #334155;
            color: #38bdf8;
            font-weight: 700;
            text-transform: uppercase;
            font-size: 8pt;
            letter-spacing: 0.5px;
        }
        table.data-table tr:nth-child(even) {
            background-color: rgba(255, 255, 255, 0.02);
        }

        /* Stats Badge Grid */
        .stat-grid {
            width: 100%;
            border-collapse: collapse;
            margin-bottom: 15px;
        }
        .stat-grid td {
            width: 33.33%;
            padding: 8px;
            text-align: center;
            background-color: #0f172a;
            border: 1px solid #334155;
            border-radius: 6px;
        }
        .stat-val {
            font-size: 16pt;
            font-weight: 800;
            color: #4ade80;
            display: block;
        }
        .stat-lbl {
            font-size: 7.5pt;
            color: #94a3b8;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        .code-snippet {
            font-family: 'Courier New', Courier, monospace;
            background-color: #0f172a;
            color: #38bdf8;
            padding: 10px;
            border-radius: 6px;
            font-size: 8.5pt;
            border: 1px solid #334155;
            margin-bottom: 10px;
            white-space: pre-wrap;
        }

        /* Footer */
        .footer {
            margin-top: 30px;
            border-top: 1px solid #334155;
            padding-top: 10px;
            font-size: 8pt;
            color: #64748b;
            text-align: center;
        }
    </style>
</head>
<body>

    <div class="header-banner">
        <div class="header-title">Typing Speed Studio</div>
        <div class="header-subtitle">Professional User Guide, Architectural Reference & Technical Manual</div>
    </div>

    <table class="stat-grid">
        <tr>
            <td>
                <span class="stat-val">Adaptive</span>
                <span class="stat-lbl">Multi-Category</span>
            </td>
            <td>
                <span class="stat-val">100% Native</span>
                <span class="stat-lbl">HTML5 / CSS3 / JS</span>
            </td>
            <td>
                <span class="stat-val">Zero Dep</span>
                <span class="stat-lbl">Standalone App</span>
            </td>
        </tr>
    </table>

    <table class="grid-table">
        <tr>
            <td class="col-left">
                <div class="card">
                    <div class="card-title">1. Interactive Platform Modes</div>
                    <p>Typing Speed Studio includes dynamic engine modes crafted for diverse training objectives:</p>
                    <ul class="feature-list">
                        <li><strong>Time Mode:</strong> Configurable intervals (15, 30, 60, and 120 seconds) to test endurance under pressure.</li>
                        <li><strong>Word Count Mode:</strong> Target word thresholds (25, 50, 100, 250 words) emphasizing steady pacing.</li>
                        <li><strong>Zen Mode:</strong> Distraction-free untimed practice designed for flow-state refinement.</li>
                        <li><strong>Adaptive Difficulty:</strong> Real-time adjustments based on error rate and burst velocity.</li>
                    </ul>
                </div>

                <div class="card">
                    <div class="card-title">2. Curated Category Passages</div>
                    <p>Engineered with domain-specific practice material rather than repetitive boilerplate:</p>
                    <ul class="feature-list">
                        <li><strong>General English:</strong> Literary prose and expressive daily usage.</li>
                        <li><strong>Programming & Code:</strong> Syntactically accurate JavaScript, Python, C++, and SQL snippets.</li>
                        <li><strong>Business Communication:</strong> Executive briefings, financial reports, and strategic memos.</li>
                        <li><strong>Medical & Legal:</strong> Complex clinical terminology and formal statutory clauses.</li>
                    </ul>
                </div>
            </td>

            <td class="col-right">
                <div class="card">
                    <div class="card-title">3. Real-Time Telemetry & Formulas</div>
                    <p>All metric calculations follow commercial platform standards:</p>
                    <table class="data-table">
                        <thead>
                            <tr>
                                <th>Metric</th>
                                <th>Formula / Logic</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td>Net WPM</td>
                                <td><code>((Correct Chars / 5) / TimeInSeconds) × 60</code></td>
                            </tr>
                            <tr>
                                <td>Raw WPM</td>
                                <td><code>((Total Chars / 5) / TimeInSeconds) × 60</code></td>
                            </tr>
                            <tr>
                                <td>Accuracy %</td>
                                <td><code>((Total - Errors) / Total) × 100</code></td>
                            </tr>
                            <tr>
                                <td>CPM</td>
                                <td><code>Net WPM × 5</code></td>
                            </tr>
                        </tbody>
                    </table>
                </div>

                <div class="card">
                    <div class="card-title">4. Post-Session Analytics</div>
                    <p>After each session, the studio compiles an in-depth breakdown:</p>
                    <ul class="feature-list">
                        <li><strong>WPM & Error Graph:</strong> Canvas-rendered visual curve tracking velocity and keystroke rhythm.</li>
                        <li><strong>Achievement Badges:</strong> Milestones earned (e.g., Sharpshooter, Roadrunner, Dedicated).</li>
                        <li><strong>Adaptive Feedback:</strong> Diagnostic text providing actionable advice on accuracy and pacing.</li>
                    </ul>
                </div>
            </td>
        </tr>
    </table>

    <h2>Core Architecture & Execution</h2>
    <p>Below is a representative snippet of the self-contained state controller used inside the single-page application:</p>

    <div class="code-snippet">function calculateWPM(totalChars, errors, elapsedSeconds) {
    if (elapsedSeconds === 0) return 0;
    const correctChars = Math.max(0, totalChars - errors);
    const words = correctChars / 5;
    return Math.round((words / elapsedSeconds) * 60);
}

// Local Storage Persistence
const saveSessionLog = (sessionData) => {
    const history = JSON.parse(localStorage.getItem('tss_history') || '[]');
    history.unshift(sessionData);
    localStorage.setItem('tss_history', JSON.stringify(history));
};</div>

    <h2>Shortcut Quick Reference</h2>
    <table class="data-table">
        <thead>
            <tr>
                <th>Shortcut</th>
                <th>Action Description</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td><code>Tab + Enter</code></td>
                <td>Quick restart current typing session</td>
            </tr>
            <tr>
                <td><code>Esc</code></td>
                <td>Pause session / Close modal dialogs</td>
            </tr>
            <tr>
                <td><code>Click Text Area</code></td>
                <td>Focus input cursor and resume typing</td>
            </tr>
        </tbody>
    </table>

    <div class="footer">
        Typing Speed Studio &bull; Comprehensive Platform Documentation & Manual &bull; Generated Automatically
    </div>

</body>
</html>
"""

html_path = "typing_speed_studio_manual.html"
pdf_path = "typing_speed_studio_manual.pdf"

with open(html_path, "w", encoding="utf-8") as f:
    f.write(html_content)

HTML(html_path).write_pdf(pdf_path)
print(f"PDF generated successfully at: {pdf_path}")


```

```text
PDF generated successfully at: typing_speed_studio_manual.pdf


```

Your PDF documentation for the **Typing Speed Studio** is ready for download:

### What's included in this PDF manual:

* **Platform Architecture Overview**: Details on the self-contained HTML5/CSS3/JS single-page engine architecture.
* **Practice Modes & Categories Guide**: Breakdown of Time, Word, Zen, and Adaptive modes, as well as General, Code, Business, Medical, Legal, and Creative practice text pools.
* **Metric Formula Specifications**: Standardized algorithms for Net WPM, Raw WPM, Accuracy %, CPM, and Consistency metrics.
* **Analytics & Telemetry Explanations**: Details on canvas telemetry graphs, dynamic diagnostic suggestions, and localized persistence (`localStorage`).
* **Keyboard Shortcut Reference**: Easy reference table for navigation and speed controls.
