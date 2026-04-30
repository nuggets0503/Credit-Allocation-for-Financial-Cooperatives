# 💰 Strategic Credit Allocation for Financial Cooperatives

> **Prescriptive Analytics:** Utilizing Linear Programming to solve the "Coop-Balance 2026" optimization problem—maximizing interest income while adhering to strict institutional risk thresholds.

## 📌 Executive Summary
Financial cooperatives face a dual-mandate challenge: maximizing returns for member dividends while fulfilling social mandates and protecting equity. This project provides a data-driven framework for a provincial Credit Cooperative to allocate **$5,000,000** in new loanable funds across three segments: Micro-Enterprise, Agricultural, and Personal loans. 

Using the `PuLP` library in Python, this model identifies the "Golden Mix" that yields the highest return without exceeding a 3.5% expected default loss.

---

## 🏗️ The Mathematical Model

### **1. Objective Function**
Maximize Total Expected Annual Interest Income ($Z$):
$$Z = 0.07a_1 + 0.11b_2 + 0.16c_3$$

Where:
* $a_1$: Low-Risk Micro-Enterprise Allocation
* $b_2$: Medium-Risk Agricultural Allocation
* $c_3$: High-Risk Personal/Emergency Allocation

### **2. Constraints**
* **Total Budget:** $a_1 + b_2 + c_3 \le 5,000,000$
* **Risk (Max Default):** $0.015a_1 + 0.045b_2 + 0.090c_3 \le 175,000$
* **Social Mandate:** $b_2 \ge 1,250,000$ (Min 25% to Agriculture)
* **Risk Exposure:** $c_3 \le 1,000,000$ (Max 20% to High-Risk)

---

## 🚀 Optimization Results
The model identified an optimal strategy that generates **$483,333.33** in annual income.

| Loan Segment | Optimal Allocation | % of Portfolio |
| :--- | :--- | :--- |
| **Micro-Enterprise** | $1,666,666.70 | 33.3% |
| **Agricultural** | $3,333,333.30 | 66.7% |
| **Personal/Emergency** | $0.00 | 0.0% |

### **Key Analytical Insight**
The **Maximum Risk** constraint is **binding**. The model fully utilized the $175,000 allowable risk capacity. Interestingly, the high default rate of Personal Loans (9%) makes them mathematically unviable compared to the balanced yield of the Agricultural and Micro-enterprise sectors under current conditions.

---

## 🛠️ Tech Stack
* **Language:** Python
* **Optimization Library:** [PuLP](https://coin-or.github.io/pulp/) (Linear Programming)
* **Environment:** Jupyter Notebook / Anaconda

---

## 💡 Strategic Recommendations for the Board
1.  **Capital Efficiency:** Prioritize the Agricultural sector; it currently serves as the "engine" of the cooperative, satisfying social mandates while offering the best risk-adjusted return.
2.  **Risk Mitigation:** Entry into the Personal Loan market is currently contraindicated. To make this segment viable, the coop must either lower the default rate via stricter credit scoring or increase the risk tolerance threshold.
