# Rheumatoid Arthritis Dietary Patterns Analysis

Project overview
- This repository explores dietary patterns derived from food frequency data using Latent Class Analysis (LCA) and evaluates associations between those patterns and rheumatoid arthritis (RA) activity (DAS28 score) using OLS regression, adjusting for clinical covariates. Analyses are presented in Jupyter Notebooks for reproducibility.

Key components
- Data cleaning and variable construction from dietary and clinical data.
- Application of Latent Class Analysis to identify dietary pattern classes.
- Post-hoc labeling and characterization of classes by food consumption probabilities.
- Regression analyses (OLS) of DAS28 on class membership and covariates (age, sex, medication, BMI, etc.).
- Sensitivity analyses and robustness checks.

Repository structure
- notebooks/ — analysis notebooks with step-by-step workflow.
- data/ — guidance and placeholder for clinical and dietary data (not included if sensitive).
- results/ — regression tables, class-probability plots, and figures.

Data
- Expected data includes: participant_id, food frequency variables, DAS28 score, and clinical covariates (age, sex, BMI, medication, disease duration).
- Ensure all human-subject data is handled according to IRB approvals and data-sharing agreements; do not commit identifiable or sensitive patient data to public repositories.

Getting started
1. Clone the repository:
   git clone https://github.com/<owner>/Rheumatoid-Arthritis.git
2. Create environment:
   python -m venv .venv
   source .venv/bin/activate
3. Install dependencies:
   pip install -r requirements.txt
4. Place the (de-identified) dataset in data/raw/ and open notebooks:
   jupyter lab

Choosing tools for LCA
- R option (recommended for mature LCA tools):
  - Use R packages such as poLCA, tidyLPA, or Mplus (if licensed).
  - Workflows: run LCA in R and import class assignments into Python notebooks for regression.
- Python option:
  - Use GaussianMixture or custom mixture models for approximate LCA behavior.
  - Consider `latentpy` or `sklearn.mixture` as practical alternatives.

Notebooks and analyses
- 01-data-prep.ipynb — cleaning, variable creation and descriptive stats.
- 02-lca-or-mixture.ipynb — run LCA or mixture models, choose number of classes using BIC/AIC.
- 03-class-characterization.ipynb — visualize class-specific consumption patterns and prevalence.
- 04-regression-analysis.ipynb — OLS regressions of DAS28 on class membership with covariate adjustment.
- 05-sensitivity.ipynb — alternative model specifications, stratified analyses.

Interpreting results
- Present class distributions and item-response probabilities with clear labels.
- Report regression coefficients, standard errors, and model diagnostics (residual plots, multicollinearity checks).
- For causal claims, be explicit about limitations — these are observational associations.

Ethical & privacy considerations
- Do not publish traceable patient data.
- Remove or anonymize any personal identifiers before pushing data to the repository.

Reproducibility
- Set random seeds for modeling.
- Record package versions (e.g., in requirements.txt or environment.yml).

License & contact
- Add a LICENSE file consistent with institutional policies.
- For data access requests, contact the data owner following the repository’s data access instructions.
