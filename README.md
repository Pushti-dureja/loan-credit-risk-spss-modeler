#  Loan Credit Risk Analysis — IBM SPSS Modeler

> "Mini Project · Data Mining & Predictive Analytics" 
> Chandigarh University · MBA Business Analytics

##  Project Overview

This project builds an end-to-end "credit risk prediction pipeline" using IBM SPSS Modeler — a visual, no-code data mining tool. The goal is to predict which loan applicants are likely to default, discover hidden risk patterns, and segment borrowers into meaningful risk profiles using three data mining techniques.

| Algorithm | Type | Purpose |
|--------------------|---------------------------|------------------------------------|
| C5.0 Decision Tree | Supervised Classification | Predict loan default (Yes/No)      |
| Apriori            | Association Rule Mining   | Discover co-occurring risk factors |
| K-Means            | Unsupervised Clustering   | Segment borrowers into risk groups |

---

##  Repository Structure

```
loan-credit-risk-spss-modeler/
│
├── Data/
│   └── loan_credit_risk_data.csv            # 50 applicants · 18 variables
│
├── spss-stream/
│   └── predictive mini project.str          # SPSS Modeler stream (main workflow)
│
├── model-nugget/
│   └── GeneratedModels.gen                  # Exported trained model nuggets
│
├── screenshots/                     # All node screenshots + visuals
│   ├── workflow of stream.jpeg
│   ├── var. file node.jpeg
│   ├── type node.jpeg
│   ├── filler node.jpeg
│   ├── derive node(reclassify).jpeg
│   ├── distribution of default status.jpeg
│   ├── histogram for credit score.jpeg
│   ├── plot of income vs debt to income ratio.jpeg
│   ├── decision tree.jpeg
│   ├── apriori node.jpeg
│   └── k-means node.jpeg
│
├── report/
│   └── Loan_Credit_Risk_SPSS_MiniProject.docx   # Full project report
│
└── README.md

##  Dataset

File: `Data/loan_credit_risk_data.csv`

| Attribute           | Detail                                    |
|---------------------|-------------------------------------------|
| Total Records       | 50 loan applicants                        |
| Total Variables     | 18 (demographic + financial + behavioral) |
| Target Variable     | `DefaultStatus` — Yes / No                |
| Defaulters (Yes)    | 18 records — 36%                          |
| Non-Defaulters (No) | 32 records — 64%                          |

Variables include: Age, Gender, Income, EmploymentType, CreditScore, LoanAmount, LoanTerm, InterestRate, ExistingDebts, PropertyOwnership, MaritalStatus, NumDependents, LoanPurpose, PreviousDefaults, MissedPayments, DebtToIncomeRatio


## SPSS Modeler Workflow

The stream follows the CRISP-DM lifecycle — all steps are connected visually inside the `.str` file.

Var. File Node → Type Node → Filler Node → Derive Node (Reclassify)
                                                      ↓
                        ┌─────────────────────────────┤
                        ↓                             ↓
              Distribution / Histogram /        C5.0 Decision Tree
              Scatter Plot (EDA)                Apriori Rules
                                                K-Means Clustering
                                                      ↓
                                             Analysis Node → Results


##  Key Results

### C5.0 Decision Tree

- Accuracy: ~85–90%
- Top 3 Predictors: `PreviousDefaults` → `CreditScore` → `MissedPayments`

| Metric                            | Value                                                        |
|---------------------------------- |------------------------------------------------------------|
| True Positives (Defaulters caught) | ~15 / 18                                                  |
| True Negatives (Safe applicants)  | ~28 / 32                                                    |
| Top Rule                          |IF PreviousDefaults ≥ 1 AND CreditScore < 600 → Default = YES|

###  Apriori Association Rules

| Rule (IF → THEN)                                                      | Support | Confidence |
|-----------------------------------------------------------------------|---------|------------|
| PreviousDefaults ≥ 1 AND CreditScore = Poor → Default = Yes           | 12%     | 88%        |
| MissedPayments ≥ 2 AND EmploymentType = Self-Employed → Default = Yes | 10%     | 80%        |
| PropertyOwnership = Rented AND Income = Low → Default = Yes           | 14%     | 75%        |
| CreditScore = Excellent AND PreviousDefaults = 0 → Default = No       | 18%     | 95%        |

###  K-Means Clustering (K = 3)

| Cluster   | Risk Level    | Avg. CreditScore|Avg. Income|Default Rate| Action                   |
|-----------|---------------|----------------|------------|-----------|----------------------------|
| Cluster 1 | 🟢 Low Risk   | 750+           | > 70K      | ~5%      | Approve · offer low rates   |
| Cluster 2 | 🟡 Medium Risk| 650–720        | 40–70K     | ~30%     | Approve with conditions     |
| Cluster 3 | 🔴 High Risk  | < 620          | < 40K      | ~75%     | Reject or require guarantor |


##  Business Insights

- PreviousDefaults is the #1 predictor — applicants with even one prior default are significantly more likely to default again.
- CreditScore alone is insufficient — combining it with MissedPayments dramatically improves prediction accuracy.
- Self-employed applicants with 2+ missed payments carry ~80% default probability — a key screening criterion.
- K-Means clusters mapped cleanly onto Low / Medium / High risk, validating the model's practical utility for tiered lending.

##  Tools & Technologies

- Tool: IBM SPSS Modeler
- Methodology: CRISP-DM
- Algorithms: C5.0 Decision Tree · Apriori · K-Means
- Dataset: 50 records × 18 variables

##  How to Open the SPSS Stream

1. Install IBM SPSS Modeler (v18.0 or later)
2. Go to `File → Open Stream`
3. Select `model-file/predictive mini project.str`
4. In the Var. File node, update the file path to point to `Data/loan_credit_risk_data.csv`
5. Click Run ▶ to execute the full pipeline

##  Team

| Name               | Student ID |
|--------------------|------------|
| Pushti             | 25MBA0052  |
| Amit Joshi         | 25MBA20059 |
| Apurv Pratap Singh | 25MBA20054 |

University: Chandigarh University · MBA Business Analytics  
Subject: Data Mining and Predictive Analytics

*This project was built for academic purposes as part of the MBA Business Analytics program.*
