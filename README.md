# CIND820-Big-Data-Analytics-Project
CIND820: Big Data Analytics Project


## Repository Contents

The repository consists of the following files:

- **`Campbell_Douglas_FinalReport.ipynb`**  
  Main Jupyter Notebook containing all data preparation, model estimation, evaluation, and visualizations for Research Questions 1–3.

- **`Campbell_Douglas_FinalReport.html`**  
  HTML export of the notebook for easy viewing without running code.

- **`KoTaP_Dataset (1).csv`**  
  Input dataset containing firm‑level financial, governance, and tax variables.

- **`Appendix_DataOutputSummary_Final.xlsx`**  
  Excel appendix summarizing model results, governance coefficients, clustering outputs, and computational diagnostics.



## How to Reproduce the Results

### 1. Software Requirements

The analysis was conducted using Python (version ≥ 3.8) and the following packages:

- pandas  
- numpy  
- scikit‑learn  
- matplotlib  
- psutil  
- jupyter  

All computations are executed within the Jupyter Notebook environment.

---

### 2. Running the Analysis

1. Open `Campbell_Douglas_FinalReport.ipynb` in Jupyter Notebook or JupyterLab.
2. Ensure `KoTaP_Dataset (1).csv` is located in the same directory as the notebook.
3. Run all cells from top to bottom.

The notebook performs:
- Data cleaning and preprocessing  
- Label construction using train‑sample quantiles  
- Model estimation for governance‑based classifiers  
- Risk profiling via K‑means clustering  
- Visualization and diagnostic reporting  

---

## Outputs

Running the notebook reproduces:

- Printed model performance summaries in the notebook output
- Figures (elbow plots, silhouette plots, PCA projections)
- An Excel appendix (`Appendix_DataOutputSummary_Final.xlsx`) containing:
  - Classification performance metrics
  - Governance variable coefficients
  - Cluster profiles and tax outcomes
  - Computational timing and memory diagnostics

The HTML file provides a static, fully rendered version of the results.

---

## Notes on Reproducibility

- Train/test splits are time‑based (pre‑2020 vs. post‑2020).
- Label thresholds are computed using training data only.
- All preprocessing steps are implemented within scikit‑learn pipelines.
- Random seeds are fixed where applicable (e.g., clustering).
- All reported results can be regenerated deterministically from the notebook.
