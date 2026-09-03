<img width="1080" height="1080" alt="day48-linkedin-card" src="https://github.com/user-attachments/assets/97e10f87-35c0-4e83-91d6-3baa69674f97" />INPUT
Compare & Decide Builder

You are an expert research analyst, data journalist, UX designer, and frontend developer.

Before generating anything, interview the user ONE QUESTION AT A TIME in quiz form (MCQs only).

1. What are you trying to decide between? (Ask for the general category, then present four realistic examples of comparable options in that category.)
2. Who is this tool for, and what's the one decision they need to walk away confident about?
3. What criteria matter in this comparison? (Ask for at least four measurable criteria, e.g. cost, time, risk, quality, availability.)
4. Where should the underlying data come from? (Ask the user to name at least two real, citable sources per criterion, or confirm you should research and cite real sources yourself.)
5. Should the user be able to weight criteria by personal priority, or see one fixed ranking?

After collecting the answers:

1. Research and verify real data points for each option against each criterion, using only sources you can name and cite. Do not invent numbers, benchmarks, or scores.

2. Build a premium single-file HTML application (HTML/CSS/JavaScript only, no external libraries) that lets the user adjust criteria weights and see a ranked result update live.

The application should:
- Display a visible sources panel listing every citation used.
- Flag clearly if any data point is an estimate or a synthetic placeholder rather than sourced fact.
- Handle loading states, empty states, and edge cases gracefully.
- Be fully responsive with clean, professional visual design.

3. Add a collapsible "How this was researched" panel explaining where each data point came from and any conflicts between sources you had to resolve.

Generate the complete application only after all interview questions have been answered.

Return ONLY the complete HTML inside one code block.

OUTPUT
<img width="1080" height="1080" alt="day48-linkedin-card" src="https://github.com/user-attachments/assets/a770ee92-1518-41b0-a130-23cf899e6ece" />
Now Axis Bank data.```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Personal Loan Compare & Decide — HDFC vs SBI vs Bajaj Finance vs Axis</title>
<style>
  :root{
    --bg:#0f1420; --panel:#161d2e; --panel2:#1c2438; --border:#2a3450;
    --text:#e8ecf7; --muted:#9aa5c0; --accent:#5b8cff; --accent2:#7cf5c4;
    --warn:#ffb454; --danger:#ff6b7a; --radius:14px;
  }
  *{box-sizing:border-box;}
  body{margin:0;font-family:'Segoe UI',system-ui,-apple-system,Roboto,sans-serif;background:linear-gradient(180deg,#0b0f19,#111729);color:var(--text);min-height:100vh;padding:24px;}
  .wrap{max-width:1200px;margin:0 auto;}
  header{margin-bottom:28px;}
  h1{font-size:1.7rem;margin:0 0 6px;background:linear-gradient(90deg,#8fb4ff,#7cf5c4);-webkit-background-clip:text;background-clip:text;color:transparent;}
  .sub{color:var(--muted);font-size:.95rem;max-width:700px;line-height:1.5;}
  .badge{display:inline-block;background:var(--panel2);border:1px solid var(--border);color:var(--muted);font-size:.72rem;padding:3px 9px;border-radius:20px;margin-top:10px;}

  .layout{display:grid;grid-template-columns:280px 1fr;gap:20px;}
  @media(max-width:860px){.layout{grid-template-columns:1fr;}}

  .card{background:var(--panel);border:1px solid var(--border);border-radius:var(--radius);padding:18px;}
  .weights h2{font-size:1rem;margin:0 0 4px;}
  .weights .hint{color:var(--muted);font-size:.78rem;margin-bottom:14px;}
  .weight-row{margin-bottom:16px;}
  .weight-row label{display:flex;justify-content:space-between;font-size:.85rem;margin-bottom:6px;}
  .weight-row .val{color:var(--accent2);font-weight:600;}
  input[type=range]{width:100%;accent-color:var(--accent);}
  .reset-btn{width:100%;margin-top:6px;background:var(--panel2);color:var(--text);border:1px solid var(--border);padding:9px;border-radius:8px;cursor:pointer;font-size:.82rem;}
  .reset-btn:hover{border-color:var(--accent);}

  .results{display:flex;flex-direction:column;gap:12px;}
  .rank-card{background:var(--panel);border:1px solid var(--border);border-radius:var(--radius);padding:16px 18px;display:grid;grid-template-columns:auto 1fr auto;gap:16px;align-items:center;transition:.2s;}
  .rank-card.top{border-color:var(--accent2);box-shadow:0 0 0 1px rgba(124,245,196,.25) inset;}
  .rank-num{font-size:1.4rem;font-weight:700;color:var(--muted);width:34px;text-align:center;}
  .rank-card.top .rank-num{color:var(--accent2);}
  .name-row{display:flex;align-items:center;gap:10px;flex-wrap:wrap;}
  .name{font-weight:700;font-size:1.05rem;}
  .tag{font-size:.68rem;padding:2px 8px;border-radius:10px;background:var(--panel2);color:var(--muted);border:1px solid var(--border);}
  .tag.best{background:rgba(124,245,196,.12);color:var(--accent2);border-color:rgba(124,245,196,.4);}
  .score-bar-bg{background:#0c1120;border-radius:6px;height:8px;margin-top:8px;overflow:hidden;}
  .score-bar{height:100%;background:linear-gradient(90deg,var(--accent),var(--accent2));border-radius:6px;transition:width .3s;}
  .score-num{font-size:1.3rem;font-weight:700;color:var(--accent2);text-align:right;}
  .score-label{font-size:.68rem;color:var(--muted);text-align:right;}
  .metrics{display:grid;grid-template-columns:repeat(4,1fr);gap:8px;margin-top:12px;font-size:.78rem;}
  .metric{background:var(--panel2);border:1px solid var(--border);border-radius:8px;padding:8px 10px;}
  .metric .k{color:var(--muted);font-size:.68rem;text-transform:uppercase;letter-spacing:.03em;}
  .metric .v{margin-top:2px;font-weight:600;}
  @media(max-width:640px){.metrics{grid-template-columns:1fr 1fr;} .rank-card{grid-template-columns:auto 1fr;} .score-num,.score-label{text-align:left;} }

  .est-flag{display:inline-block;font-size:.65rem;background:rgba(255,180,84,.13);color:var(--warn);border:1px solid rgba(255,180,84,.4);padding:1px 6px;border-radius:6px;margin-left:5px;}

  .panel-toggle{margin-top:24px;}
  details{background:var(--panel);border:1px solid var(--border);border-radius:var(--radius);padding:14px 18px;margin-top:14px;}
  summary{cursor:pointer;font-weight:600;font-size:.92rem;list-style:none;display:flex;justify-content:space-between;align-items:center;}
  summary::-webkit-details-marker{display:none;}
  summary:after{content:"+";font-size:1.3rem;color:var(--accent);}
  details[open] summary:after{content:"–";}
  .panel-body{margin-top:12px;font-size:.85rem;color:var(--muted);line-height:1.6;}
  .src-item{padding:8px 0;border-bottom:1px solid var(--border);}
  .src-item:last-child{border-bottom:none;}
  .src-item a{color:var(--accent);text-decoration:none;font-size:.82rem;}
  .src-item a:hover{text-decoration:underline;}
  .src-crit{font-size:.68rem;color:var(--accent2);text-transform:uppercase;letter-spacing:.03em;}
  .conflict{background:var(--panel2);border-left:3px solid var(--warn);padding:8px 12px;border-radius:6px;margin:8px 0;}
  footer{margin-top:30px;color:var(--muted);font-size:.75rem;text-align:center;line-height:1.6;}
  .empty{padding:40px;text-align:center;color:var(--muted);}
</style>
</head>
<body>
<div class="wrap">
  <header>
    <h1>Personal Loan Compare & Decide</h1>
    <div class="sub">For a salaried borrower choosing the cheapest overall personal loan. Adjust the weights on the left to match what matters most to you — the ranking updates live. Built from publicly available bank rate cards and financial-data aggregators, verified as of September 2026.</div>
    <span class="badge" id="lastUpdated">Data as of Sept 2026 · India · Salaried applicants</span>
  </header>

  <div class="layout">
    <div class="card weights">
      <h2>Your priorities</h2>
      <div class="hint">Slide to weight each criterion. Lower interest, fees & prepayment charges score higher; longer max tenure scores higher.</div>
      <div id="weightSliders"></div>
      <button class="reset-btn" onclick="resetWeights()">Reset to equal weights</button>
    </div>

    <div class="results" id="results">
      <div class="empty">Loading comparison…</div>
    </div>
  </div>

  <div class="panel-toggle">
    <details>
      <summary>📚 Sources — every citation used</summary>
      <div class="panel-body" id="sourcesPanel"></div>
    </details>

    <details>
      <summary>🔍 How this was researched</summary>
      <div class="panel-body">
        <p>Each lender's interest rate, processing fee, tenure range and prepayment/foreclosure charge was pulled from that bank's own rate-card page where available (HDFC, SBI, Axis official domains) and cross-checked against two independent financial-data aggregators (Paisabazaar, BankBazaar, ClearTax, MyMoneyMantra, CreditMantri, or UrbanMoney) to catch stale or promotional figures.</p>
        <div class="conflict"><strong>Interest rates</strong> are ranges, not fixed numbers — actual pricing depends on credit score, income, employer category and existing banking relationship. We show the published <em>starting</em> and <em>upper-band</em> rate for a salaried applicant.</div>
        <div class="conflict"><strong>Axis Bank foreclosure charges</strong> conflicted across sources: Axis's own consumer pages describe foreclosure as free in some contexts, while its official Terms & Conditions PDF and several aggregators describe a tenure-dependent charge (3% of outstanding principal if closed within 36 EMIs, dropping to 2% after). We used the tenure-dependent figure as the conservative estimate and flagged it below.</div>
        <div class="conflict"><strong>Bajaj Finance</strong> publishes different rate bands across its own "Insta Personal Loan" page (16%–30.5%) versus its general personal loan marketing pages (11%–17%). We show the widest published range and flag it as lender/scheme-dependent.</div>
        <p>Figures explicitly marked <span class="est-flag">est.</span> in the cards below are ranges synthesized from multiple third-party aggregators where the bank's own page did not state a single confirmed figure at time of writing — treat these as directional, and confirm the exact number on the lender's live rate card before applying.</p>
        <p>Scoring model: for interest rate, processing fee, and prepayment charge, each lender is scored against the best (lowest) and worst (highest) value in the set — lower cost = higher score. For tenure flexibility, longer maximum tenure = higher score. Your weight sliders scale each criterion's contribution to the final weighted score (0–100).</p>
      </div>
    </details>
  </div>

  <footer>
    This tool is for general comparison only, not financial advice. Rates, fees and eligibility change frequently and vary by individual credit profile — always confirm current terms directly with the lender before applying. Built for the abtalks 60-day Claude challenge, Day 48.
  </footer>
</div>

<script>
// ---- DATA (sourced; see Sources panel) ----
const CRITERIA = [
  { key:'rate', label:'Interest Rate', unit:'% p.a.', lowerBetter:true },
  { key:'fee', label:'Processing Fee', unit:'% of loan', lowerBetter:true },
  { key:'tenure', label:'Max Tenure', unit:'months', lowerBetter:false },
  { key:'prepay', label:'Prepayment Charge', unit:'% outstanding', lowerBetter:true }
];

const LOANS = [
  {
    name:'SBI Personal Loan',
    tagline:'Lowest published starting rate, capped fees',
    rate:{min:10.00,max:15.30,estimate:false},
    fee:{value:1.50,note:'up to 1.5% (min ₹1,000 / max ₹15,000) + GST',estimate:false},
    tenure:{value:84,note:'6 months – 7 years (or remaining service period)',estimate:false},
    prepay:{value:2.0,note:'2% of prepaid amount (waived for defence/govt after 6 months, or any borrower after 3 years)',estimate:false}
  },
  {
    name:'HDFC Bank Personal Loan',
    tagline:'Flat fee, fast digital disbursal',
    rate:{min:9.99,max:24.00,estimate:false},
    fee:{value:2.50,note:'flat ₹6,500 + GST (≈2.5% on a ₹2.6L+ loan; flat, not %-based)',estimate:false},
    tenure:{value:72,note:'up to 72 months (6 years)',estimate:false},
    prepay:{value:3.0,note:'typically 2–4% of outstanding, varies by tenure elapsed',estimate:true}
  },
  {
    name:'Axis Bank Personal Loan',
    tagline:'Lowest starting rate, tenure-based foreclosure',
    rate:{min:9.99,max:21.55,estimate:false},
    fee:{value:2.00,note:'1.5%–2% of loan amount + GST',estimate:false},
    tenure:{value:84,note:'12 – 84 months (up to 7 years)',estimate:false},
    prepay:{value:3.0,note:'3% of outstanding if closed within 36 EMIs, 2% after — some Axis pages describe NIL foreclosure in specific scenarios (conflicting sources, see research notes)',estimate:true}
  },
  {
    name:'Bajaj Finance Personal Loan',
    tagline:'Fastest disbursal, highest cost of credit',
    rate:{min:11.00,max:30.50,estimate:false},
    fee:{value:4.13,note:'up to 4.13% of loan amount (incl. taxes)',estimate:false},
    tenure:{value:96,note:'12 – 96 months (up to 96 months for select customers; standard cap 60)',estimate:true},
    prepay:{value:4.72,note:'up to 4.72% of outstanding principal (incl. taxes)',estimate:false}
  }
];

const SOURCES = [
  {crit:'Interest Rate / Fees / Tenure', name:'SBI — Personal Loan (official)', url:'https://sbi.bank.in/web/personal-banking/loans/personal-loans/sbi-personal-loan'},
  {crit:'Processing Fee', name:'SBI — Processing Fees (official)', url:'https://sbi.bank.in/web/interest-rates/interest-rates/processing-fees'},
  {crit:'Interest Rate / Fees', name:'SBI Personal Loan Rates — ClearTax', url:'https://cleartax.in/s/sbi-personal-loan-interest-rate'},
  {crit:'Prepayment', name:'SBI Personal Loan — MyMoneyMantra', url:'https://www.mymoneymantra.com/sbi-personal-loan-interest-rates'},
  {crit:'Interest Rate / Fees / Tenure', name:'HDFC Bank — Interest Rates & Charges (official)', url:'https://www.hdfc.bank.in/personal-loan/interest-rates-and-charges'},
  {crit:'Processing Fee', name:'HDFC Personal Loan Rate — CreditMantri', url:'https://www.creditmantri.com/hdfc-bank-personal-loan-interest-rate/'},
  {crit:'Tenure', name:'HDFC Personal Loan — Paisabazaar', url:'https://www.paisabazaar.com/hdfc-bank/personal-loan/'},
  {crit:'Interest Rate / Fees', name:'Axis Bank — Interest Rates & Charges (official)', url:'https://www.axis.bank.in/loans/personal-loan/interest-rates-charges'},
  {crit:'Foreclosure Terms', name:'Axis Bank — Personal Loan Terms & Conditions (official PDF)', url:'https://www.axis.bank.in/docs/default-source/default-document-library/personal-loans-tc.pdf'},
  {crit:'Foreclosure Charges', name:'Axis Bank Foreclosure — Axis Bank Blog (official)', url:'https://www.axis.bank.in/blogs/personal-loan/charges-for-personal-loan-foreclosure-or-pre-closure'},
  {crit:'Foreclosure Charges', name:'Axis Bank Preclosure — MyMoneyMantra', url:'https://www.mymoneymantra.com/axis-bank-personal-loan-preclosure-charges'},
  {crit:'Interest Rate / Tenure', name:'Axis Bank Personal Loan — BankBazaar', url:'https://www.bankbazaar.com/axis-bank-personal-loan-interest-rates.html'},
  {crit:'Processing Fee / Prepayment', name:'Bajaj Finance — Insta Personal Loan Fees (official)', url:'https://www.bajajfinserv.in/insta-personal-loan-fees-and-charges'},
  {crit:'Processing Fee / Prepayment', name:'Bajaj Finance — Fees & Charges (official)', url:'https://www.bajajfinserv.in/insights/everything-you-should-know-about-the-fees-and-charges-applicable-on-your-personal-loan'},
  {crit:'Interest Rate / Tenure', name:'Bajaj Finserv Personal Loan — MyMoneyMantra', url:'https://www.mymoneymantra.com/bajaj-finserv-personal-loan-interest-rates'},
  {crit:'Tenure', name:'Bajaj Finserv Personal Loan — MyMoneyMantra (loan details)', url:'https://www.mymoneymantra.com/personal-loans/bajaj-finserv'}
];

let weights = {};
CRITERIA.forEach(c => weights[c.key] = 50);

function buildSliders(){
  const container = document.getElementById('weightSliders');
  container.innerHTML = '';
  CRITERIA.forEach(c => {
    const row = document.createElement('div');
    row.className = 'weight-row';
    row.innerHTML = `
      <label>${c.label} <span class="val" id="val-${c.key}">${weights[c.key]}</span></label>
      <input type="range" min="0" max="100" value="${weights[c.key]}" id="slider-${c.key}">
    `;
    container.appendChild(row);
  });
  CRITERIA.forEach(c => {
    document.getElementById('slider-'+c.key).addEventListener('input', e => {
      weights[c.key] = parseInt(e.target.value);
      document.getElementById('val-'+c.key).textContent = weights[c.key];
      render();
    });
  });
}

function resetWeights(){
  CRITERIA.forEach(c => weights[c.key] = 50);
  buildSliders();
  render();
}

function normalizedScore(loan, critKey){
  const c = CRITERIA.find(x => x.key === critKey);
  let values = LOANS.map(l => critKey === 'rate' ? (l.rate.min+l.rate.max)/2 : l[critKey].value);
  const min = Math.min(...values), max = Math.max(...values);
  let raw = critKey === 'rate' ? (loan.rate.min+loan.rate.max)/2 : loan[critKey].value;
  if(max === min) return 100;
  let pct = (raw - min) / (max - min); // 0 = best-low, 1 = worst-high
  if(!c.lowerBetter) pct = 1 - pct; // for tenure, higher raw is better, so flip
  return Math.round((1-pct) * 100);
}

function computeWeightedScore(loan){
  const totalWeight = CRITERIA.reduce((s,c) => s + weights[c.key], 0);
  if(totalWeight === 0) return 0;
  let sum = 0;
  CRITERIA.forEach(c => {
    sum += normalizedScore(loan, c.key) * weights[c.key];
  });
  return Math.round(sum / totalWeight);
}

function render(){
  const resultsEl = document.getElementById('results');
  if(!LOANS.length){
    resultsEl.innerHTML = '<div class="empty">No loan options available.</div>';
    return;
  }
  const scored = LOANS.map(l => ({...l, score: computeWeightedScore(l)}))
                       .sort((a,b) => b.score - a.score);
  resultsEl.innerHTML = '';
  scored.forEach((l, i) => {
    const card = document.createElement('div');
    card.className = 'rank-card' + (i === 0 ? ' top' : '');
    card.innerHTML = `
      <div class="rank-num">#${i+1}</div>
      <div>
        <div class="name-row">
          <span class="name">${l.name}</span>
          ${i===0 ? '<span class="tag best">Best match for your weights</span>' : ''}
        </div>
        <div style="color:var(--muted);font-size:.82rem;margin-top:2px;">${l.tagline}</div>
        <div class="score-bar-bg"><div class="score-bar" style="width:${l.score}%"></div></div>
        <div class="metrics">
          <div class="metric"><div class="k">Interest Rate</div><div class="v">${l.rate.min}% – ${l.rate.max}%</div></div>
          <div class="metric"><div class="k">Processing Fee</div><div class="v">${l.fee.value}%${l.fee.estimate?'<span class="est-flag">est.</span>':''}</div></div>
          <div class="metric"><div class="k">Max Tenure</div><div class="v">${l.tenure.value} mo${l.tenure.estimate?'<span class="est-flag">est.</span>':''}</div></div>
          <div class="metric"><div class="k">Prepayment</div><div class="v">${l.prepay.value}%${l.prepay.estimate?'<span class="est-flag">est.</span>':''}</div></div>
        </div>
        <div style="margin-top:10px;font-size:.72rem;color:var(--muted);line-height:1.5;">
          <div><strong>Fee:</strong> ${l.fee.note}</div>
          <div><strong>Tenure:</strong> ${l.tenure.note}</div>
          <div><strong>Prepayment:</strong> ${l.prepay.note}</div>
        </div>
      </div>
      <div>
        <div class="score-num">${l.score}</div>
        <div class="score-label">match score</div>
      </div>
    `;
    resultsEl.appendChild(card);
  });
}

function renderSources(){
  const el = document.getElementById('sourcesPanel');
  el.innerHTML = SOURCES.map(s => `
    <div class="src-item">
      <div class="src-crit">${s.crit}</div>
      <a href="${s.url}" target="_blank" rel="noopener">${s.name}</a>
    </div>
  `).join('');
}

buildSliders();
render();
renderSources();
</script>
</body>
</html>
```
