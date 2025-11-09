# VagusPredict

**Evidence-weighted forecasting.**  
This repository powers [vaguspredict.com](https://vaguspredict.com) — a public, data-driven dashboard that applies Bayesian superforecasting to assess the probability of Vladimir Putin remaining in power through December 2026.

---

## 📊 Overview

VagusPredict combines geopolitical analysis and quantitative modeling.  
Each update incorporates new evidence across six weighted categories:

| Category | Description |
|-----------|--------------|
| **Military** | Operational tempo, attrition, adaptation, logistics |
| **Economy / Energy** | Inflation, production, sanctions, energy infrastructure |
| **Elite / Institutions** | Cohesion, purges, chain-of-command stability |
| **Domestic / Public** | Morale, mobilization, information control, protests |
| **External / Diplomatic** | Foreign support, sanctions, alliances |
| **Symbolic / Context** | Prestige, propaganda, historic analogs |

Each category contributes a **Bayes Factor (BF)**.  
The posterior odds are updated weekly using the formula:  

> **O = O₀ × Π (BFᵢ)**  
> **P = O / (1 + O)**  

---

## 🗂️ Site Structure
/

--index.html # homepage

--about.html # methodology page

--dashboard/
             index.html # forecast dashboard
           
--data/
        forecast.json # update this file weekly
      
--css/
       site.css # global styling
     
--CNAME # contains: vaguspredict.com

## 🔄 Updating the Forecast

To post a new forecast cycle:

1. Edit **`data/forecast.json`**
   ```json
   {
     "as_of": "2025-11-08",
     "current_prob_pct": 90,
     "base_rate_pct": 10,
     "total_bf_product": "4.5",
     "posterior_odds": "6.08",
     "buckets": [ ... ],
     "triggers": [ ... ]
   }
   
Commit and push changes.
GitHub Pages will rebuild automatically.
The dashboard will refresh on next load.

🧠 Methodology

All Bayes Factors are derived from open-source intelligence and verifiable data (ISW, Reuters, Euromaidan Press, UK MoD, U.S. Treasury, etc.).
Correlation penalties (0.90–0.95) prevent double-counting; economic multipliers are capped to avoid runaway compounding.
The model is descriptive, not prescriptive — it measures stress on regime stability, not moral judgment or ideology.

⚙️ Technical Notes

Static HTML + CSS + vanilla JS (no frameworks)
Hosted on GitHub Pages
Custom domain via Squarespace DNS
All content auto-renders from forecast.json

📜 License

Source code © 2025 VagusPredict.
Content licensed under the MIT License

“Math says resilience wins.”
