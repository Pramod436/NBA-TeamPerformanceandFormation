# NBA Team Performance & Lineup Formation Analysis

[![Python 3.8+](https://img.shields.io/badge/Python-3.8+-3776AB?style=flat&logo=python&logoColor=white)](https://www.python.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-ML_Pipeline-F7931E?style=flat&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![pandas](https://img.shields.io/badge/pandas-Data_Analysis-150458?style=flat&logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebooks-F37626?style=flat&logo=jupyter&logoColor=white)](https://jupyter.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

A comprehensive data science and machine learning framework designed to evaluate 22 years of NBA player performance statistics (2000–2022), perform unsupervised player clustering into functional archetypes, and predict optimal 5-player lineup combinations that maximize team impact scores.

---

## 👥 Authors & Collaborators

* **Pramod Nair** — Email: `pnair16@asu.edu` | GitHub: [@Pramod436](https://github.com/Pramod436)
* **Ansh Motwani** — Email: `ansh.motwani.2@gmail.com` | GitHub: [@AnshMotwani](https://github.com/AnshMotwani)
* **Ishan Mehta** — GitHub: [@mehtaishan205](https://github.com/mehtaishan205)
* **Namita Ravi** — GitHub: [@ravinamita](https://github.com/ravinamita)

---

## 📌 Executive Summary

Modern basketball analytics has evolved beyond traditional positions (Point Guard, Shooting Guard, Small Forward, Power Forward, Center) toward role-based functional archetypes. This project builds an end-to-end data analytics and predictive modeling pipeline to:

1. **Dimensionality Reduction**: Reduce 50+ complex statistical features to 13 principal components using **PCA**, capturing over 95% of overall data variance.
2. **Unsupervised Player Clustering**: Segment NBA players into 10 distinct operational clusters using **K-Means** and **Hierarchical Clustering**, validated via Elbow and Silhouette analysis.
3. **Supervised Impact Score Modeling**: Train a **Random Forest Regressor** to predict team impact scores based on player archetype compositions.
4. **Combinatorial Lineup Optimization**: Evaluate all possible 5-player team formations to determine optimal lineup synergy and peak performance scores.

---

## 🏗️ Pipeline Architecture

```text
┌─────────────────────────────────────────────────────────────────┐
│              Raw NBA Player Statistics (2000–2022)              │
│       (Offensive/Defensive Ratings, Net Ratings, Usage %)       │
└────────────────────────────────┬────────────────────────────────┘
                                 │
                                 v
┌─────────────────────────────────────────────────────────────────┐
│            Feature Engineering & Preprocessing (EDA)            │
│         (Standardization, Handling Outliers & Nulls)            │
└────────────────────────────────┬────────────────────────────────┘
                                 │
                                 v
┌─────────────────────────────────────────────────────────────────┐
│             Principal Component Analysis (PCA)                  │
│       (50+ Features ──> 13 Principal Components, >95% Var)      │
└────────────────────────────────┬────────────────────────────────┘
                                 │
                                 v
┌─────────────────────────────────────────────────────────────────┐
│              Unsupervised Player Clustering                     │
│    ┌───────────────────────────┐   ┌────────────────────────┐   │
│    │    K-Means Clustering     │   │Hierarchical Clustering │   │
│    │     (10 Archetypes)       │   │    (Dendrogram/Agglo)   │   │
│    └───────────────────────────┘   └────────────────────────┘   │
└────────────────────────────────┬────────────────────────────────┘
                                 │
                                 v
┌─────────────────────────────────────────────────────────────────┐
│        Supervised Predictive Modeling & Lineup Synergy          │
│            (Random Forest Regressor ──> Impact Score)           │
└────────────────────────────────┬────────────────────────────────┘
                                 │
                                 v
┌─────────────────────────────────────────────────────────────────┐
│             Optimal 5-Player Lineup Selection                   │
└─────────────────────────────────────────────────────────────────┘
```

---

## 📊 Dataset & Metrics

The project analyzes comprehensive player statistics spanning **2000–2022 NBA seasons**:

* **Advanced Performance Metrics:** Offensive Rating (`ORtg`), Defensive Rating (`DRtg`), Net Rating (`NetRtg`), Assist Percentage (`AST%`), Rebound Percentage (`TRB%`).
* **Usage & Efficiency Statistics:** Usage Rates (`USG%`), Turnover Rate (`TOV%`), Steal Rate (`STL%`), Block Rate (`BLK%`), True Shooting Percentage (`TS%`).
* **Temporal Tracking:** Year-over-year player progression and multi-season performance trends.

---

## 🧮 Machine Learning Methodology

### 1. Feature Engineering & PCA
* Standardized 50+ raw features to eliminate scaling bias.
* Applied Principal Component Analysis (PCA), identifying **13 principal components** that retain **95%+ cumulative explained variance**.
* Reduced noise while preserving non-linear player variance.

### 2. Clustering & Archetype Identification
* Evaluated **K-Means** vs. **Agglomerative Hierarchical Clustering**.
* Determined optimal cluster count ($K=10$) via **Elbow Method** and **Silhouette Score analysis**.
* Grouped players into 10 tactical roles (e.g., Elite Playmakers, 3-and-D Specialists, Paint Protectors, High-Usage Scoring Wings).

### 3. Predictive Modeling & Optimization
* Trained a **Random Forest Regressor** to predict team impact metrics.
* Conducted combinatorial evaluation of candidate 5-player formations to find lineup synergies with maximum projected impact.

---

## 📈 Key Results & Metrics

* **Model R² Score:** `0.4446`
* **Mean Squared Error (MSE):** `33.4351`
* **Top Contributing PCA Features:**
  * `PCA_1`: **14.03%**
  * `PCA_2`: **11.18%**
  * `PCA_6`: **10.78%**
* **Clustering Outcome:** Successfully grouped players into 10 stable, interpretable operational archetypes.

---

## 📂 Repository Structure

```text
NBA-TeamPerformanceandFormation/
├── Dataset/                     # Raw and cleaned NBA datasets (2000-2022)
│   ├── all_data.csv             # Primary player dataset
│   ├── EDA.ipynb                # Exploratory Data Analysis notebook
│   └── *.xlsx                   # Processed data tables
├── code/                        # Clustering analysis & visualization
│   ├── Clustering.ipynb         # K-Means and Hierarchical Clustering notebook
│   ├── elbow_plot.png           # K-Means Elbow plot output
│   └── silhouette_score_*.png   # Silhouette analysis visualizations
├── mastercode/                  # Predictive modeling pipeline
│   ├── model.ipynb              # Random Forest training & evaluation
│   └── *.xlsx                   # Feature-engineered dataset files
├── results/                     # Optimal team formation outputs
│   ├── Merge.ipynb              # Consolidation & lineup merging script
│   └── *.xlsx                   # Cluster assignment tables
├── src/                         # Modular production package structure
│   ├── components/              # Ingestion, transformation, training modules
│   ├── pipeline/                # End-to-end training and prediction pipelines
│   ├── exception.py             # Custom error handling
│   └── logger.py                # Logging utility
├── requirements.txt             # Python package dependencies
├── setup.py                     # Python package installer
├── LICENSE                      # MIT License
└── README.md                    # Project documentation
```

---

## 🚀 Quick Start Guide

### 1. Prerequisites & Environment Setup
Clone your fork and install dependencies:
```bash
git clone https://github.com/Pramod436/NBA-TeamPerformanceandFormation.git
cd NBA-TeamPerformanceandFormation

# Install dependencies
pip install -r requirements.txt
pip install -e .
```

### 2. Execution Order

#### Step 1: Exploratory Data Analysis
```bash
cd Dataset
jupyter notebook EDA.ipynb
```

#### Step 2: Unsupervised Clustering (PCA & K-Means / Hierarchical)
```bash
cd ../code
jupyter notebook Clustering.ipynb
```

#### Step 3: Predictive Model Training (Random Forest)
```bash
cd ../mastercode
jupyter notebook model.ipynb
```

#### Step 4: Results Merge & Optimal Lineup Evaluation
```bash
cd ../results
jupyter notebook Merge.ipynb
```

---

## 💡 Practical Applications

* **NBA Front Office Analytics:** Evaluate free-agent synergy and complement existing core players.
* **Lineup Optimization:** Identify high-efficiency 5-player lineups based on functional balance.
* **Fantasy Sports Analytics:** Build data-driven fantasy rosters leveraging projected impact scores.

---

## 📜 License

This project is licensed under the [MIT License](LICENSE).