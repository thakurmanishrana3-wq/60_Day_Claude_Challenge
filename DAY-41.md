INPUT
# Interactive Learning Studio

You are an expert educator, curriculum designer, instructional designer, subject matter expert, UI/UX designer, and senior frontend developer.

Before generating anything, ask the user the following questions ONE AT A TIME, in MCQ format only, no user typed input (keep that as last option).

1. What kind of Interactive Learning Studio would you like to build?
(Offer domains and subjects.)

2. Continue asking follow-up questions until the requested subject has been narrowed to a topic that can realistically be taught in a single comprehensive interactive tutorial.
Do not stop after identifying only a domain or subject. Use your own judgment to determine when the scope is appropriate.
Example:
Programming → Python → Object-Oriented Programming.

The topic should be broad enough to include multiple related concepts but focused enough to be completely taught within one tutorial.

3. Would you like Claude to automatically structure the tutorial, or would you like to customize its sections?
If the user chooses customization, ask which sections they want included.

After collecting all responses, generate a premium single-page interactive HTML application called 'Interactive Learning Studio'.

The application should teach the selected topic completely rather than creating a learning roadmap or summary. The chosen topic should already be known and must not be requested again inside the HTML.

Begin with an introduction containing learning objectives, estimated completion time, prerequisites (if any), expected outcomes, and a reward system.

Divide the tutorial into four progressively difficult modules, moving from foundational understanding to practical application and mastery.

Each module should include:
- Detailed explanations
- Topic-specific examples
- Analogies
- HTML/CSS/SVG diagrams where appropriate
- Comparisons
- Practical exercises
- Common misconceptions
- Key takeaways
- Interactive elements

After each module, include a 4-question interactive quiz with automatic scoring, instant feedback, explanations for every answer, and a short performance summary before unlocking the next module.

Conclude with:
- Final practical challenge
- Cheat sheet
- Summary notes
- Continue Learning section
- Books
- Documentation
- Research papers (where appropriate)
- Communities
- Practice platforms
- Search keywords
- Additional AI prompts for further learning.

Every lesson, example, analogy, diagram, exercise, quiz, and challenge must be generated specifically for the selected topic.

Generate everything as a single self-contained HTML file using only HTML, CSS, and JavaScript only, without external libraries or frameworks.

Design the interface as a polished commercial learning platform with responsive design, dark mode, smooth animations, progress tracking, quiz scoring, completion tracking, printable notes, and an intuitive user experience.

OUTPUT
[linear-logistic-regression-studio.html](https://github.com/user-attachments/files/31465457/linear-logistic-regression-studio.html)
Got it! Building your **Interactive Learning Studio** on **Linear & Logistic Regression** now — this will take a moment as I craft a full premium tutorial just for you. 🚀Your **Interactive Learning Studio** is ready! 🎉

Here's everything packed inside:

**📖 Introduction**
- Learning objectives, prerequisites, expected outcomes, estimated time (~75 min), and a full badge/XP reward system

**4 Progressive Modules:**
- **Module 1** — Math & intuition: the regression equation, cost functions (MSE), gradient descent, visual diagrams
- **Module 2** — Linear Regression deep dive: assumptions, house price example, sklearn code, RMSE & R² evaluation
- **Module 3** — Logistic Regression: sigmoid function, decision boundary, confusion matrix, Precision/Recall/F1, Python code
- **Module 4** — Mastery: side-by-side comparison table, 4 busted myths, overfitting vs. regularization (L1/L2), decision guide

**🧠 After Each Module:** A 4-question quiz with instant feedback, explanations, XP rewards, and automatic module unlocking (≥75% to proceed)

**🏆 Final Challenge** — End-to-end bank loan prediction pipeline with starter code

**📋 Cheat Sheet** — All formulas, when-to-use guide, search keywords, print-ready

**🔗 Resources** — Books, sklearn docs, communities, practice platforms, and 5 AI prompts for going deeper

**Design highlights:** Dark theme, sticky sidebar nav, SVG diagrams, progress bar, XP counter, badge system, toast notifications, and responsive layout — all in one self-contained HTML file.
