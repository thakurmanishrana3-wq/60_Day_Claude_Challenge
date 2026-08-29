INPUT
# Personal Financial Command Center

You are an expert financial planner, budgeting specialist, investment advisor, UI/UX designer, data visualization expert, and senior frontend developer.

Before generating anything, ask the user the following questions ONE AT A TIME in MCQ format only, with typed input only as the last option.

1. Who is this financial dashboard for?
(Offer options such as Student, Salaried Employee, Freelancer, Business Owner, Family, Investor, Retired, etc.)

2. Continue asking follow-up questions until the user's financial profile has been narrowed sufficiently to personalize the dashboard.
Do not stop after identifying only the user type. Use your own judgment to determine when enough information has been collected.

3. Would you like Claude to automatically design the dashboard, or would you like to customize the modules?
If the user chooses customization, ask which financial modules they want included.

After collecting all responses, generate a premium single-page HTML application called **"Personal Financial Command Center."**

The application should help users understand, manage, and improve their financial health through an interactive dashboard rather than acting as a simple expense tracker.

Include an overview dashboard followed by relevant financial modules based on the user's profile. These may include income, expenses, budgets, savings, debt, loans, investments, subscriptions, goals, cash flow, financial insights, calculators, planning tools, reports, and visualizations where appropriate.

Include interactive charts, financial summaries, AI-generated recommendations, "what-if" simulations, progress tracking, and a financial health score tailored to the user's situation.

Conclude with financial tips, planning checklists, useful resources, and additional AI prompts for improving financial literacy.

Generate everything as a single self-contained HTML file using only HTML, CSS, and JavaScript without external libraries or frameworks.

Design the interface as a polished commercial financial platform with responsive design, dark mode, smooth animations, local storage, printable reports, and an intuitive user experience.

OUTPUT
[financial-command-center.html](https://github.com/user-attachments/files/31602174/financial-command-center.html)
Day 42 done — **Personal Financial Command Center**, tailored to a student on allowance with investing as the top priority.

What's inside:
- **Overview** — inflow/outflow, net balance, health score, auto-generated insights
- **Allowance & Spending** ledger with category charts
- **Budget Planner** — adjustable needs/wants/save sliders (defaults 50/30/20) with actual-vs-budget bars
- **Savings Goals** with progress tracking
- **Investing Lab** — plain-language basics, a compound growth simulator, a monthly SIP calculator, and a 3-question risk profile quiz
- **Financial Health Score** — live composite score with a breakdown ring
- **Tips, checklist & resources** with follow-up prompts to keep exploring investing with Claude

All self-contained (no external libs), dark/light toggle, localStorage persistence, and print-to-PDF for the report. Ledger-notebook visual theme with gold/mint accents instead of the usual generic dashboard look.

Want the LinkedIn PNG card and caption next?

