# 📊 Student Academic Performance & Behavioral Analysis
An End-to-End Data Engineering, Exploratory Data Analysis (EDA), and Multivariate Statistical Pipeline.

---

## 📌 Project Overview
This project delivers a comprehensive, production-grade exploratory data analysis pipeline examining the socio-economic, demographic, and behavioral drivers behind student academic success. Leveraging a dataset of 649 student records, the pipeline processes data from raw ingestion through complex feature engineering, multi-dimensional cross-tabulations, and advanced statistical visualizations. 

The ultimate goal of this framework is to establish an empirical, data-driven foundation for educational administrators to design early academic intervention frameworks, isolate student risk profiles, and prioritize institutional resources.

---

## 🛠️ Tech Stack & Analytical Ecosystem
* **Language:** Python 3.10+
* **Data Manipulation & Ingestion:** `pandas`, `numpy`
* **Statistical Visualizations:** `seaborn`, `matplotlib`
* **Environment:** Jupyter Notebook / Interactive Python Kernel

---

## 🚀 Key Data Engineering & Feature Architecture
Before executing statistical analysis, the data pipeline implements defensive data hygiene and feature architecture loops to maximize signal and ensure structural integrity:
1. **Deduplication & Sanitization:** Enforces lowercasing and strips trailing whitespaces across all text columns to prevent structural fragmentation.
2. **Composite Metric Engineering:** * `total_alcohol_usage`: Combines weekday (`Dalc`) and weekend (`Walc`) consumption indices to establish a single, comprehensive tracking score.
   * `comprehensive_final_score`: Replaces isolated grading intervals (`G1`, `G2`, `G3`) with a continuous, 3-period mathematical average (scaled out of 20 points).
   * `absences_normalized`: Standardizes high-variance absence tracking metrics for comparative modeling.
3. **Categorical Tiering:** Discretizes student success into three distinct `performance_tier` brackets (`low_performance`, `medium_performance`, `high_performance`) based on strict grade boundaries.

---

## 📉 Analytical Insights & Core Visualizations
The analysis progresses through a logical multi-tiered framework, documented step-by-step with targeted presentation strategies:

### 1. Descriptive Baselines (`.describe()`)
Establishes a foundational statistical summary sheet across all numeric parameters. This step verifies that the student body maps out an average age of `16.74` years and an overall comprehensive grade mean of `11.55` out of 20, confirming a balanced population baseline.

### 2. Demographic Bivariate Testing (`.groupby()`)
Evaluates structural performance gaps across demographic splits:
* **Gender Split:** Female students maintain a slightly higher comprehensive grade average (`11.72`) compared to male peers (`11.31`), accompanied by fractionally lower absenteeism.
* **Geographical Variance:** A distinct performance margin emerges when evaluating student geography. Urban students outpace rural students (`11.73` vs. `10.99`) despite sharing nearly identical baseline absence rates.

### 3. Multivariate Cross-Tabulation (`pd.crosstab()`)
Layers `studytime` and `total_alcohol_usage` simultaneously against `performance_tier` brackets to expose hidden behavioral trade-offs. The matrix uncovers compounding risk profiles (severe grade drops when low study hours intersect with heavy alcohol usage) and highlights key protective thresholds showing how dedicated study hours buffer academic performance against negative lifestyle indicators.

### 4. Correlation Leaderboard (`.corr()`)
Ranks lifestyle factors relative to the core academic KPI (`comprehensive_final_score`) to isolate primary drivers of student outcomes:
* **Primary Positive Driver:** Weekly study time (`+0.231`)
* **Primary Negative Drivers:** Past class failures (`-0.402`) and high alcohol usage (`-0.245`)

### 5. Advanced Visual Dashboard Layout
* **Histogram with KDE Curve:** Visually validates that student grades map out a highly symmetric, statistically sound Gaussian distribution (standard bell curve).
* **Annotated Countplot:** Visually exposes headcount volumes across performance categories, showing that the medium tier forms the overwhelming core of the population (449 records) flanked by isolated high (94) and low (85) risk tails.
* **Feature Correlation Heatmap:** Translates abstract coefficients into a publication-quality `coolwarm` grid, leveraging preattentive visual processing so key statistical insights instantly jump off the page.
* **5-Number Boxplot Series:** Traces variance shifts across weekly study hour blocks, proving that increasing dedicated study time consecutively lifts the performance ceiling while lifting the academic floor.
* **Multivariate Regression Mapping (`lmplot`):** Computes distinct linear regression lines of best fit (y-hat = B_0 + B_1x) alongside 95% confidence intervals to demonstrate the steady, measurable decline in academic trajectories as weekly alcohol consumption scales across both gender demographics.
* **Grouped Bar Charts with Error Bars:** Proves that while a positive correlation exists between maternal education and student success, the urban-rural performance gap persists even when controlling for identical parental education levels.
* **Density Histogram & Rug Plot:** Discovers that student absences follow a heavily right-skewed (positively skewed) distribution, packing the vast majority of records between 0 and 4 absences while using individual bottom rug ticks to isolate chronically truant outliers.
* **Dual-Contour Violin Plots:** Uses shape width and internal dashed quartile indicators to compare complete distribution profiles, offering an elegant view of how social indicators co-vary with academic outcomes.
* **Pairwise Grid Evaluation Matrix (`PairGrid`):** Merges univariate diagonal histograms with bivariate off-diagonal scatter plots into a single macro-lens panel, delivering a mathematically rigorous grand finale to our data discovery phase.