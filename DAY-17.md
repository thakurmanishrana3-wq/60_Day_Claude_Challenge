INPUT
## Details
- Vehicle : [YOUR VEHICLE MODEL]
- Fuel    : [Petrol/Diesel/CNG/E85/EV]
- Usage   : [City/Highway/Mixed/Fleet]
- KM/month: [e.g. 1000]
- Car Age : [e.g. 3 yrs]
## Role
Data analyst. Read attached CSV → compute metrics → output one HTML dashboard. HTML only, no explanation.
## Compute (group by Fuel_Type)
1. Avg Cost/km        = Fuel_Cost_INR ÷ Distance_km
2. Avg CO₂/km         = CO2_emitted_kg ÷ Distance_km
3. Avg Maintenance/km = Maintenance_Cost_INR ÷ Distance_km
4. Avg Refuel time    = Refuel_Recharge_time_min
5. Age buckets: New(0-2y) Mid-life(3-5y) Aged(6-9y) Old(10+y)
   → show Cost/km and Maint/km per bucket. Mark [CAR AGE] yrs.
6. E85 Paradox:
   - Pump saving    = ((Petrol_price−E85_price)/Petrol_price)×100
   - Running penalty= ((E85_cpkm−Petrol_cpkm)/Petrol_cpkm)×100
   - Break-even     = (E85_mileage÷Petrol_mileage)×Petrol_price
7. E85 Score/10: cost=4pt CO₂=3pt refuel=2pt maint=1pt
## Dashboard (no CDN, pure SVG charts, CSS in <style>, JS in <script>)
Dark navy #0a0f1e, glassmorphism. Colours: E85=amber Petrol=blue Diesel=grey CNG=green EV=purple.
1. Header — '[YOUR VEHICLE] · [FUEL] · Age:[CAR AGE]y · [KM/month]km/mo'
2. KPI Cards (5) — your fuel cost/km | E85 cost/km | E85 premium vs Petrol | break-even price | your monthly cost
3. SVG bar chart: Cost/km per fuel | SVG doughnut: CO₂/km per fuel (hover tooltips)
4. SVG line chart: Cost/km vs age (0-12y) per fuel. Vertical line at [CAR AGE].
5. SVG gauge: E85 score/10 (CSS animated). One verdict sentence.
6. Fuel cards: highlight [FUEL] with glow. Each: 2 pros ✅ 2 cons ❌ best-for 🚗
Output: <!DOCTYPE html> only. All numbers from CSV. Responsive 375px–1440px.

OUTPUT
<img width="1080" height="1080" alt="day17_fuel_dashboard" src="https://github.com/user-attachments/assets/47601250-697a-4c55-8735-c3c5ec70c46a" />
Your **Day 17 PNG** is ready — 1080×1080px, LinkedIn-ready! Here's what's packed in:

- **Header** — Day 17 badge, ABTalks branding, dashboard title
- **5 KPI cards** — cost/km, E85 cost, pump saving, break-even, monthly cost
- **Bar chart** — cost/km per fuel (Petrol highlighted with border)
- **Doughnut chart** — CO₂/km split with % labels + legend
- **E85 Paradox row** — pump saving, running penalty, break-even side by side
- **E85 Gauge** — animated-style arc showing 6.4/10 with score breakdown (Cost/CO₂/Refuel/Maint)
- **5 Fuel cards** — pros ✓ / cons ✗ per fuel, Petrol glowing as "You"
- **Footer** — ABTalks 60 Days challenge branding

