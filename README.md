# CIND820-Big-Data-Analytics-Project
CIND820: Big Data Analytics Project

# Tax Risk Profiling with Machine Learning and Firm Governance

This repository contains the full empirical workflow for a machine‑learning–based analysis of corporate tax risk. The project integrates **supervised prediction, governance-based inference, and unsupervised clustering** to identify, explain, and validate persistent tax‑risk profiles among firms.

The analysis is organized around three research questions (RQ1–RQ3) and uses firm‑level financial, ownership, and governance data.

---

## Project Structure

- `Code V6.ipynb`  
  End‑to‑end, cleaned notebook running all analyses (RQ1–RQ3)

- `Code V6.html`  
  Rendered execution output including tables, metrics, and figures

- 'KoTaP_Dataset.csv`  
  Input dataset 

---

## Research Questions

**RQ1 — Prediction:**  
Can firms with high tax risk be identified using financial and governance characteristics?

**RQ2 — Explanation:**  
How do governance mechanisms relate to tax risk across alternative tax definitions and horizons?

**RQ3 — Profiling:**  
Do firms cluster into stable, interpretable tax‑risk profiles based on governance and firm characteristics?

---

## Data and Features

- Firm‑level financial variables (profitability, leverage, liquidity, size, growth)
- Governance and ownership variables (foreign ownership, insider ownership, Big4 auditor, market listing)
- Industry fixed effects
- Multiple tax‑risk measures:
  - Cash and book effective tax rates (CETR, GETR)
  - Persistent tax measures (3‑year and 5‑year averages)
  - Book–tax difference indicators (TSTA, TSDA)

---

## Methods Overview

### RQ1 — Supervised Classification
- Models:
  - Logistic regression (baseline)
  - Logistic regression (class‑weighted)
  - K‑Nearest Neighbors (benchmark)
- Feature selection:
  - Low‑variance filtering
  - High‑correlation pruning
  - Mutual information screening
- Evaluation:
  - Accuracy, precision, recall, F1
  - Confusion matrices
  - TimeSeriesSplit (forward‑looking validation)

**Key insight:**  
Baseline models achieve high accuracy but fail to detect high‑risk firms.  
Class‑weighted models substantially improve high‑risk recall, making them suitable for screening applications.

---

### RQ2 — Governance Models
- Logistic regression with governance and industry controls
- Unweighted (primary specification) and class‑weighted (robustness)
- Focus on coefficient stability and interpretability

**Key findings:**
- Firm size, foreign ownership, and insider ownership consistently reduce tax risk
- Market listing status (KOSPI) is positively associated with certain book‑tax risk measures
- Results are robust across tax definitions and time horizons

---

### RQ3 — Unsupervised Risk Profiling
- Algorithm: K‑Means clustering
- Features:
  - Firm size, ownership, governance, market listing, firm age
- Diagnostics:
  - Elbow method
  - Silhouette score
- Validation:
  - Single‑year tax outcomes
  - Persistent 3‑ and 5‑year tax measures
  - Pre‑ and post‑COVID subsample analysis

**Final choice:**  
Three clusters (k = 3), balancing interpretability and statistical separation.

---

## Main Results

### Predictive Performance (RQ1)
- Unweighted models: high overall accuracy, poor high‑risk detection
- Class‑weighted models: lower accuracy but strong recall for high‑risk firms
- Results stable across time‑series validation

### Governance Effects (RQ2)
- Governance variables exhibit consistent, economically meaningful signs
- Effects robust across models, tax measures, and weighting schemes

### Tax‑Risk Profiles (RQ3)
Three distinct firm profiles emerge:

1. **High‑Risk Cluster**  
   Smaller, weakly governed firms with the lowest effective tax rates

2. **Intermediate Cluster**  
   Moderately sized, mature firms with mixed governance characteristics

3. **Low‑Risk Cluster**  
   Large, well‑governed firms with higher and more stable effective tax rates

Clusters are validated by persistent tax behavior and remain stable across subsamples.

---
