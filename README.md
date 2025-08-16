# IBM-Data-Science-Capstone

End-to-end data project analyzing SpaceX Falcon 9 launches to identify drivers of **first-stage landing success** and to build **classification models** that predict success vs. failure. The repo includes **API & scraping**, **data wrangling**, **EDA (viz + SQL)**, **interactive analytics** (Folium & Plotly Dash), and **predictive modeling**, along with a presentation template.

## 🧭 Project Overview

* **Goal:** Understand which factors (payload, orbit, site, booster version, flight number, time) drive landing success, and train a classifier to predict outcomes.
* **Deliverables:**

  * Clean analytics dataset for EDA & modeling
  * Visual EDA (matplotlib/plotly) + SQL insights
  * Folium interactive maps & Plotly Dash dashboard
  * Tuned classifiers with accuracy comparison & confusion matrix
  * Coursera capstone **PowerPoint template** filled with content

---
## 🔄 Reproduce the Pipeline

1. **Collect Data**

   * Run `jupyter-labs-spacex-data-collection-api.ipynb` (SpaceX REST API pulls).
   * Run `jupyter-labs-webscraping.ipynb` (tables from curated pages).
2. **Wrangle & Join**

   * Run `labs-jupyter-spacex-Data wrangling.ipynb` to clean, standardize, engineer features, and **export** a tidy dataset (e.g., `data/spacex_analytics.csv`).
3. **EDA (Viz + SQL)**

   * Visuals: `edadataviz.ipynb`
   * SQL exploration: `DB0201EN-Week3-1-3-SQLmagic.ipynb`, `jupyter-labs-eda-sql-coursera_sqllite.ipynb`
4. **Interactive Analytics**

   * Maps: `lab_jupyter_launch_site_location.ipynb` (Folium screenshots)
   * Dashboard: export to `app.py` **or** run within notebook (Plotly Dash)
5. **Modeling**

   * `SpaceX_Machine Learning Prediction_Part_5.ipynb` trains LR/SVM/KNN/Tree, tunes hyperparameters, compares accuracies, and outputs a **confusion matrix** for the best model.

---

## 📊 Key Analyses & What They Show

* **EDA (Visualization):**

  * Flight Number vs Launch Site → experience/learning effects by site
  * Payload vs Orbit → payload–orbit interaction and “sweet spot” ranges
  * Success Rate by Orbit (bar) → mission profile correlation with landing outcomes
  * Yearly Trend (line) → steady improvement across years

* **EDA (SQL):**

  * Distinct launch sites, prefix filters (e.g., `CCA%`)
  * Aggregates (payload by customer/version)
  * Milestones (first successful ground landing)
  * Outcome counts & ranked outcomes for time windows

* **Interactive:**

  * **Folium:** site markers, colored outcomes, proximity lines/rings
  * **Dash:** success pies (all sites & best site), payload vs outcome scatter with slider

* **Modeling:**

  * Pipeline with encoding/scaling inside CV
  * Hyperparameter tuning per model
  * **Best model** selected by CV accuracy (F1/ROC-AUC as tie-breakers) + test set confirmation

---

## 📝 Presentation

* Use `ds-capstone-template-coursera.pptx` for slides.
* Insert screenshots for:

  * EDA plots (scatter/bar/line)
  * Folium maps (all sites, outcomes, proximities)
  * Dash charts (pies, scatter with slider)
  * Modeling (accuracy bar chart + confusion matrix)

---

## 📦 Data Sources

* **SpaceX REST API** (launches/cores/payloads)
* **Curated web tables** (e.g., mission pages/Wikipedia) for orbit, payload, and outcomes

> This repo contains **code & derived datasets only**. Respect source terms when redistributing.

---

## 🔒 Reproducibility & Notes

* Set random seeds in modeling notebooks for repeatable CV splits.
* Keep an **audit trail** (source URLs, scrape timestamps).
* Avoid data leakage: fit scalers/encoders **only on train** inside a pipeline.
* Consider class imbalance (stratified split, class weights, or sampling).

---

## 🤝 Acknowledgments

* Coursera capstone materials & mentors
* Open-source libraries: pandas, numpy, scikit-learn, folium, plotly, dash
* Community datasets and documentation

---
