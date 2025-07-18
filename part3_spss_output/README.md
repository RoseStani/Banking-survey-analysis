## Part 3: SPSS Outputs & Interpretation

### Objective

The goal of this PCA was to determine the underlying **factors influencing consumers to maintain multiple bank accounts**, especially focusing on **why individuals use secondary banks**. The analysis was conducted using **IBM SPSS** with six Likert-scale survey variables related to bank preferences and behaviors.

---

### (I) PCA Results Summary

####  Sampling Adequacy

| Test | Value | Interpretation |
|------|--------|----------------|
| **KMO** (Kaiser-Meyer-Olkin) | 0.707 | ✅ Acceptable (≥ 0.6); indicates sampling adequacy |
| **Bartlett’s Test of Sphericity** | p < 0.001 | ✅ Significant; data is suitable for factor analysis |

The KMO and Bartlett’s test results suggest that PCA is appropriate for the dataset.
<!-- KMO & Bartlett Test -->
<div align="center">
  <img src="images/pca1.png" width="50%">
</div>

---

#### 📉 Scree Plot & Eigenvalues

Only **one component** had an **Eigenvalue > 1**, explaining **35.7% of total variance**.  
The **Scree Plot** showed a clear "elbow" after the first component, justifying the one-factor solution.
<!-- Scree Plot -->
<div align="center">
  <img src="images/pca4.png" width="50%">
</div>
---

### 🔍 Component Matrix (Factor Loadings)

| Survey Item | Factor 1 Loading | Interpretation |
|-------------|------------------|----------------|
| I use multiple banks to protect my money and data (fraud/security) | **.754** | 🔑 Strongest contributor to the factor |
| Having a secondary bank that is near my home/work with lockers is important | .655 | Convenience & safety |
| I use my secondary bank for specific features (loans, interest, etc.) | .609 | Product-oriented usage |
| I use a secondary bank based on someone's recommendation | .579 | Social influence |
| My primary bank's customer support is slow or unhelpful | .519 | Dissatisfaction with primary bank |
| Would switch to a bank with a better mobile app | .410 | Moderate tech influence |

<!-- Component Matrix -->
<div align="center">
  <img src="images/pca5.png" width="50%">
</div>

**Interpretation**:  
This single extracted component combines concerns around financial security, convenience, specific financial products, social trust, and dissatisfaction.  
It suggests that a blend of **risk management and service gaps in primary banks** influences users to adopt a second bank.

---

### 📈 Communalities

| Item | Extraction (Shared Variance) |
|------|------------------------------|
| I use multiple banks for fraud/security reasons | **.569** |
| Secondary bank convenience (locker & location) | .430 |
| Product-specific use (credit cards, loans) | .371 |
| Based on recommendation (social factor) | .336 |
| Customer service dissatisfaction | .270 |
| Better mobile app | **.168** (lowest) |

<!-- Communalities Table -->
<div align="center">
  <img src="images/pca3.png" width="50%">
</div>

The **mobile app** variable had the **lowest communality** and weakest loading — indicating it's **not a major driver** for using multiple banks in this dataset.

---

### Final Insight: What Drives Multi-Banking?

This PCA suggests a **single underlying factor**—best interpreted as:

> "**Risk & Service Diversification**"  
> Individuals use multiple banks primarily to:
> - ✅ Protect against security and fraud risks  
> - ✅ Access specialized financial features  
> - ✅ Mitigate poor service from their primary bank  
> - ✅ Rely on social trust/recommendations

 **Contrary to assumptions**, **mobile app quality** alone is **not a strong driver** for holding multiple bank accounts.

---


