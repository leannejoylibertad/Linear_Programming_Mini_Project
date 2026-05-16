# Linear_Programming_Mini_Project
Budget optimization using Linear Programming (PuLP) to maximize advertising reach across TV, Social Media, Radio, and Print — FreshSip campaign case study 🔥


# 📊 Mini-Project on Linear Programming — Marketing Analytics

**Author:** Leanne Joy P. Libertad  
**Course:** Analytics Tech  
**Section:** BSIS 3B  
**Date:** May 2026  

---

## 📌 Project Overview

This project applies **Linear Programming (LP)** using Python's `PuLP` library to solve a real-world **marketing budget optimization problem**. The goal is to determine the optimal allocation of a ₱500,000 advertising budget across four media channels to **maximize total audience reach** — while satisfying all business constraints defined by the client.

The analytics domain covered is **Marketing Analytics**, specifically the sub-problem of **media mix optimization**: a common challenge faced by marketing analysts and business strategists.

---

## 🧠 Problem Statement

> *"How should a company split its monthly advertising budget across TV, social media, radio, and print to maximize total audience reach without overspending on any single channel?"*

**Business Context:**  
You are a marketing analyst at **BrandBoost Philippines**, handling the campaign of **FreshSip** — a local juice drink brand launching a new product line. The client has approved a ₱500,000 monthly budget to be distributed across four advertising channels available in the Philippine market.

---

## 📺 Advertising Channels

| Channel | Variable | Cost Model | Reach per ₱1 Spent | Audience |
|---|---|---|---|---|
| TV (National) | x₁ | ₱2,000/spot | 0.80 impressions | Broad, mass market |
| Social Media (Meta/TikTok) | x₂ | ₱500/campaign set | 2.50 impressions | Youth, 18–35 |
| Radio | x₃ | ₱800/spot | 1.20 impressions | Commuters, provincial |
| Print (Broadsheet/Tabloid) | x₄ | ₱1,500/ad | 0.50 impressions | Adults, 30–55 |

---

## 🎯 Objective Function

**Maximize** total audience reach (impressions):

```
Maximize Z = 0.80·x₁ + 2.50·x₂ + 1.20·x₃ + 0.50·x₄
```

Where the coefficients represent impressions earned per peso spent on each channel.

---

## 📐 Constraints

| # | Rule | Mathematical Form |
|---|---|---|
| 1 | Total budget limit | x₁ + x₂ + x₃ + x₄ ≤ 500,000 |
| 2 | Minimum TV spend (brand visibility) | x₁ ≥ 80,000 |
| 3 | Minimum Social Media spend (digital presence) | x₂ ≥ 60,000 |
| 4 | Print budget cap (lowest reach channel) | x₄ ≤ 100,000 |
| 5a–5d | Channel balance — no single channel > ₱250,000 | x₁, x₂, x₃, x₄ ≤ 250,000 |
| 6 | Non-negativity | x₁, x₂, x₃, x₄ ≥ 0 |

---

## ✅ Optimal Solution

The LP solver returned the following **optimal budget allocation**:

| Channel | Allocation | Impressions Earned |
|---|---|---|
| TV (National) | ₱80,000 | 64,000 |
| Social Media | ₱250,000 | 625,000 |
| Radio | ₱170,000 | 204,000 |
| Print | ₱0 | 0 |
| **TOTAL** | **₱500,000** | **893,000 impressions** |

> **Maximum Total Audience Reach = 893,000 impressions**

Social Media was maximized to its channel cap (₱250,000) because it delivers the highest return at 2.50 impressions per peso. Print was excluded entirely as it has the lowest efficiency at 0.50 impressions per peso.

---

## 📈 Business Impact

- Reaching **893,000 Filipinos** from a single month's campaign is roughly equivalent to the entire population of Cebu City.
- At a conservative **1% conversion rate**, that's ~8,930 potential customers.
- At ₱35 per bottle of FreshSip, that alone could generate **over ₱312,000 in sales revenue**.
- A naive **equal-split allocation** (₱125,000 per channel) would have yielded only ~625,000 impressions — meaning LP delivered **268,000 more impressions at zero additional cost**.

---

## 🔬 Verification

All constraints were manually verified after the LP solution:

```python
TotalSpent       = 80,000 + 250,000 + 170,000 + 0  # = 500,000 ✅ ≤ 500,000
TVSpend          = 80,000                            # ✅ ≥ 80,000
SocialMediaSpend = 250,000                           # ✅ ≥ 60,000
PrintSpend       = 0                                 # ✅ ≤ 100,000
MaxSingleChannel = 250,000                           # ✅ ≤ 250,000
```

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| Python 3 | Programming language |
| [PuLP](https://coin-or.github.io/PuLP/) | Linear Programming solver |
| Jupyter Notebook | Interactive development environment |

---

## 📂 Repository Structure

```
📁 lp-marketing-analytics/
├── README.md                                           ← You are here
└── LP_Mini_Project_Leanne_Joy_Libertad.ipynb          ← Main notebook
```

---

## 🚀 How to Run

1. **Clone the repository**
   ```bash
   git clone https://github.com/YOUR_USERNAME/lp-marketing-analytics.git
   cd lp-marketing-analytics
   ```

2. **Install the required library**
   ```bash
   pip install pulp
   ```

3. **Launch Jupyter Notebook**
   ```bash
   jupyter notebook
   ```

4. **Open** `LP_Mini_Project_Leanne_Joy_Libertad.ipynb` and run all cells.

---

## 📚 Reference

Ghosh, D. P. (2018). Application of linear programming for direct marketing media mix optimization model: A case study of a company promoting its IT training services. *International Research Journal of Engineering and Technology (IRJET), 5*(4), 3343–3348. https://www.irjet.net/archives/V5/i4/IRJET-V5I4754.pdf

---

## 📝 License

This project was created for academic purposes as part of an Analytics Tech course (BSIS 3B, May 2026).


