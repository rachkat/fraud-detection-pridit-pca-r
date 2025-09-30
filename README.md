# Fraud Detection with PRIDIT & PCA in R

![Made with R](https://img.shields.io/badge/Made%20with-R-blue?logo=r) 
![License: MIT](https://img.shields.io/badge/License-MIT-green) 
![Status: Complete](https://img.shields.io/badge/Status-Complete-brightgreen)

---

## Executive Summary  

This repository showcases two connected projects on **fraud detection and risk analysis in auto insurance claims**, developed during my Master’s program in Data Analytics (SNHU, DAT 610: Optimization and Risk Assessment). Together, these papers demonstrate a progression from foundational data cleaning and Basel II risk alignment to advanced unsupervised fraud detection methods using **PRIDIT scoring** and **Principal Component Analysis (PCA)** in R.  

1. **[Evaluation of Undercover Losses from Company XYZ’s Legacy Fraud Identification Process (PDF)](./Evaluation-of-Undercover-Losses-from-Company-XYZ’s-Legacy-Fraud-Identification-Process.pdf)**  
   - Focuses on cleaning and analyzing a claims dataset in R.  
   - Converts raw claim and paid amount variables into usable numeric form.  
   - Maps dataset features (claims, suspicion scores, RIDIT-transformed indicators) to **Basel II operational, credit, market, and reputational risk categories**.  
   - Establishes the foundation for linking raw claims data to organizational risk management frameworks.  

2. **[Proactive Identification of Loss for Company XYZ (PDF)](./Proactive-Identification-Of-Loss-For-Company-XYZ.pdf)**  
   - Builds directly on the first analysis by applying **PRIDIT (Principal Component Analysis of RIDIT scores)** and **PCA** to enhance fraud detection.  
   - Compares PRIDIT to logistic regression, Wilcoxon tests, and clustering, highlighting its advantages in **unsupervised anomaly detection**.  
   - Uses PCA to reduce dimensionality, prioritize suspicious claims, and create interpretable fraud risk scores.  
   - Provides actionable recommendations for integrating these methods into Company XYZ’s fraud detection system.  

Taken together, these projects illustrate the complete analytics pipeline:  
- **From data preparation and risk alignment** (Paper 1)  
- **To unsupervised fraud detection and dimensionality reduction** (Paper 2).  

This progression highlights both **technical fluency in R programming** and the ability to **translate analytics into actionable business insights** aligned with Basel II frameworks. For recruiters, this work demonstrates strengths in **data cleaning, unsupervised modeling, and risk analytics**, while emphasizing my capacity to deliver insights that matter for decision-making in fraud detection and operational risk management.  

---
## Presentation Materials  

To complement the written papers, I also prepared a presentation summarizing key findings:  
- [Slides (PPTX, visuals only)](https://github.com/rachkat/fraud-detection-pridit-pca-r/raw/main/ERM-XYZ.pptx)— designed for presentations.
- [Slides with Speaker Notes (PDF)](./risk-management.pdf) — detailed explanations for self-study.  
 

---

## Table of Contents  

1. [Project 1: Evaluation of Undercover Losses](#project-1-evaluation-of-undercover-losses-from-company-xyzs-legacy-fraud-identification-process)  
2. [Project 2: Proactive Identification of Loss](#project-2-proactive-identification-of-loss-for-company-xyz)  
3. [Technologies & Tools](#technologies--tools)  
4. [Key Skills Demonstrated](#key-skills-demonstrated)  
5. [Results Highlights](#results-highlights)  
6. [Reproducibility](#reproducibility)  
7. [License](#license)  
8. [Tags](#tags)  

---

## Project 1: Evaluation of Undercover Losses from Company XYZ’s Legacy Fraud Identification Process  

### Objective  
To evaluate Company XYZ’s legacy fraud identification system by analyzing auto accident personal injury claims in R. The project involved **data cleaning, exploratory analysis, alignment with Basel II risk categories, and initial analytic methods in R**.  

### Key Steps  
1. **Data Ingestion & Cleaning**  
   - Loaded the CSV file `DAT 610 Auto Accident Personal Injury Claims file.csv` into RStudio.  
   - Converted incorrectly classified variables (`CLAIM_AMOUNT` and `PAID_AMOUNT`) from factors to numeric by removing dollar signs/commas using `gsub()` and `as.numeric()`.  
   - Verified structure using `str()` to confirm conversion.  

2. **Summary Statistics**  
   - Applied `summary()` to produce descriptive statistics for all columns.  
   - Explored suspicious claim score variables (`Claim Suspicion Score`, IND_01–IND_20, RIDIT_01–RIDIT_20).  

3. **Content Description**  
   - Dataset included:  
     - **Claim Number & Policy ID**: unique identifiers.  
     - **Claim Amount & Paid Amount**: financial details.  
     - **Claim Suspicion Score (1–5)**: suspicion ranking.  
     - **Indicator Variables (IND_01–IND_20)**: predictive metrics tied to fraud suspicion.  
     - **RIDIT Variables (RIDIT_01–RIDIT_20)**: transformed indicator values for statistical modeling.  

4. **Business Use Cases**  
   - Fraud detection: flagging irregular patterns in claim vs. paid amounts.  
   - Underwriting: assessing policyholder reliability using claims history.  
   - Forecasting: predicting likelihood and severity of future claims.  

5. **Basel II Risk Alignment**  
   - **Operational Risk**: analyzed claim handling efficiency and fraud detection.  
   - **Credit Risk**: evaluated policyholder reliability via claims history.  
   - **Liquidity Risk**: modeled payout obligations for cash flow planning.  
   - **Reputational Risk**: emphasized importance of consistent, fair claim handling.  
   - Incorporated Basel II guidance on using **internal loss data** for operational risk (Operational Risk Management, Ch. 3–4).  

6. **R Methods for Risk Analysis**  
   - Applied descriptive statistics, regression, and visualization as tools for organizational risk frameworks.  
   - Highlighted how **quantitative risk analysis in R** supports decision-making under uncertainty (ISACA, 2021).  

### Key Insight  
By cleaning the claims file and aligning it with Basel II, Company XYZ gains a **structured, data-driven risk framework**. Fraud detection improves through suspicion scoring, while operational risk management benefits from accurate, standardized internal loss data.  

---

## Project 2: Proactive Identification of Loss for Company XYZ  

### Objective  
To validate and apply the **PRIDIT scoring methodology** and **Principal Component Analysis (PCA)** to strengthen fraud detection. Compared PRIDIT with logistic regression, Wilcoxon testing, and clustering to evaluate accuracy and robustness in fraud identification.  

### PRIDIT Scoring  
- **Definition**: Principal Component Analysis of RIDIT scores, an unsupervised method for classifying fraud risk.  
- **Strengths**:  
  - Does not require labeled fraud data (unsupervised).  
  - Captures high-dimensional, complex relationships.  
  - Produces metric-level scores for each claim.  

- **Comparison with Alternatives**:  
  - Logistic regression: strong for binary outcomes, but limited with high-dimensional unlabeled data.  
  - Wilcoxon test: only compares two groups; lacks multidimensional insight.  
  - Clustering: lacks detailed metric-level fraud scores.  

### PCA Application  
- Standardized RIDIT-transformed variables.  
- Applied `prcomp()` in R to reduce dimensionality.  
- Interpreted results through screeplots, factor maps, and scatterplots of PCA scores.  
- PCA confirmed that the first few components explained most of the variance (Component 1 ≈ 7.6%).  

### Figures  
- **Figure 1**: Loading data and calculating RIDIT-ized variables.  
- **Figure 2**: Viewing RIDIT-ized variables.  
- **Figure 3**: Confirming directionality for PRIDIT scoring method.  
- **Figure 4**: PCA summary showing variance explained.  
- **Figure 5–7**: Screeplot, factor map, scatterplots of PCA scores.  

### Business Application  
- Enhances Company XYZ’s fraud detection by prioritizing claims for investigation.  
- Enables efficient allocation of resources, reducing costs from fraudulent payouts.  
- Supports ongoing monitoring and integration with **operational risk frameworks**.  

### Key Insight  
PRIDIT + PCA provide **robust, unsupervised fraud detection**, outperforming traditional supervised methods where labeled data is unavailable. By incorporating PCA-driven components into claims analysis, Company XYZ improves accuracy in identifying fraudulent behavior while aligning with Basel II risk frameworks.  

---

## Technologies & Tools  

- **RStudio / R 4.2.1**  
- **R Packages**: `scatterplot3d`, `car`, `stats`  
- **Statistical Methods**: PRIDIT scoring, PCA, regression modeling  
- **Frameworks Referenced**: Basel II operational risk  

---

## Key Skills Demonstrated  

- **Data Cleaning & Preparation**: Converting raw factors to numeric, managing structured claim datasets.  
- **Unsupervised Learning**: Applied PRIDIT and PCA to high-dimensional data.  
- **Risk Alignment**: Mapping claims to Basel II categories (operational, credit, reputational).  
- **Analytical Thinking**: Evaluating methods (PRIDIT vs logistic regression vs Wilcoxon) for fraud detection.  
- **Business Translation**: Turning technical results into actionable fraud detection strategies.  

---

## Results Highlights  

- Converted and standardized claims data to enable accurate analysis.  
- Identified fraud indicators via suspicion scores, RIDIT-ized variables, and PCA outputs.  
- Showed that **PRIDIT outperformed traditional supervised methods** when labeled fraud data was unavailable.  
- Determined that **collision, bodily injury, and reputational risks** are key categories for monitoring under Basel II frameworks.  

---

## Reproducibility  
- Environment: **RStudio, R version 4.2.1**  
- Key Packages: `scatterplot3d`, `car`, `stats`  
- Data: Course-provided claims file (confidential, not publicly shared).  
- Methods: Fully documented in PDFs with screenshots of code and output.  

---

## License  
This project is shared for **educational and portfolio purposes** under the **MIT License**.  
You are free to use, copy, and adapt the work with proper attribution.  

---

## Tags  
`r, pridit, ridit, pca, fraud-detection, insurance, basel-ii, risk-management, operational-risk, data-science, statistics, portfolio, regression, unsupervised-learning`  

