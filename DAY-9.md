INPUT

PROMPT 1 — Build MVP
Build a complete single-file HTML application called NutriScope.
Requirements:
Profile Inputs:
Age, gender, Height, Weight, Activity Level, Dietary Preference (Vegetarian, Non-Vegetarian, Eggetarian).
Food Logging:
Add Food, Quantity, Unit, Editable Table, Remove Entry.
Food Database:
Include 20 common foods only:
Rice, Roti, Dal, Paneer, Curd, Chana, Rajma, Banana, Apple, Milk, Oats, Bread, Egg, Chicken, Fish, Potato, Poha, Idli, Dosa, Spinach.
Track:
Calories, Protein, Carbs, Fat, Fiber, Iron, Calcium, Vitamin C, Vitamin D, Vitamin B12.
Calculations:
Energy, Macro Targets, Micronutrient Targets, Percentage Completion.
Dashboard:
Energy Progress, Macro Chart, Top Deficiencies, Top Excesses, Nutrient Table.
Recommendations:
Food additions, food swaps, portion adjustments based on dietary preference.
Design:
Premium SaaS UI, Mobile Responsive, Chart.js, Dark Theme, Modern Cards, No Backend, Single HTML File.
Return only the complete HTML code.
PROMPT 2 — Enhance Application
Enhance the existing NutriScope application.
Add:
CSV Upload, 40 more foods, Additional micronutrients, 2-day meal planner, Risk Analysis, Educational Disclaimer, Nutrition Sources, Better Charts, Advanced Recommendations.
Return the updated HTML only.

OUTPUT
[NutriScope (1).html](https://github.com/user-attachments/files/30370919/NutriScope.1.html)
I'll build both versions together — MVP first, then the enhanced version in one comprehensive file. Let me craft this properly.Here's your complete **NutriScope** — a single 1,578-line HTML file (~76KB) combining both prompts into one polished build. Here's what's packed inside:

**Profile & Targets**
- Full BMR/TDEE calculation (Mifflin-St Jeor), BMI classification, goal-adjusted calorie targets
- Macro splits and ICMR-RDA micronutrient targets

**Food Log**
- 60-food database (original 20 + 40 extras across grains, legumes, proteins, vegetables, fruits, nuts, dairy, fats)
- Editable table with inline quantity/unit updates, meal tagging, remove entries
- CSV import with template download

**Dashboard**
- 4 stat cards + energy/macro progress bars with colour-coded completion badges
- Macro doughnut chart + micronutrient radar chart (Chart.js)
- Top deficiencies and excesses panels

**2-Day Meal Planner** — drag items into breakfast/lunch/snack/dinner slots for each day with running calorie totals

**Smart Recommendations** — diet-aware suggestions (veg/egg/nonveg) for food additions, swaps, portion adjustments

**Risk Analysis** — BMI risk, anaemia, bone health, B12 (critical veg flag), cardiovascular, fiber warnings with low/medium/high tiers

**Nutrition Info tab** — full food database table, nutrient guide (macros + micros), and data sources (ICMR-NIN 2020, USDA, WHO)

All dark-themed, mobile-responsive, no backend required.
