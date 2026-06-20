# Loan Credit Risk Analysis using IBM SPSS Modeler

## Project Overview

This project focuses on analyzing loan applicants and predicting credit default risk using IBM SPSS Modeler. Financial institutions face significant losses when borrowers fail to repay loans. The objective of this project is to identify high-risk applicants, understand the factors contributing to default, and support data-driven lending decisions.

The analysis was performed using a dataset containing demographic, financial, and loan-related information of applicants. Multiple data mining techniques were applied to uncover patterns, build predictive models, and segment customers based on risk profiles.

## Business Problem

Banks and lending institutions must evaluate whether an applicant is likely to repay a loan before approval. Poor risk assessment can lead to loan defaults, financial losses, and inefficient allocation of credit.

This project addresses the challenge of:

* Predicting whether a borrower is likely to default.
* Identifying the key factors influencing default risk.
* Discovering hidden patterns among high-risk borrowers.
* Segmenting applicants into meaningful risk groups.

## Dataset

The dataset contains information for 50 loan applicants and includes variables such as:

* Age
* Gender
* Income
* Employment Type
* Credit Score
* Loan Amount
* Loan Term
* Interest Rate
* Existing Debts
* Property Ownership
* Marital Status
* Number of Dependents
* Previous Defaults
* Missed Payments
* Debt-to-Income Ratio
* Default Status (Target Variable)

Target Variable:

**Default Status**

* Yes = Borrower defaulted
* No = Borrower did not default

## Tools & Technologies

* IBM SPSS Modeler
* Data Mining Techniques
* Predictive Analytics
* Classification Modeling
* Association Rule Mining
* Clustering Analysis

## Methodology

The project follows the CRISP-DM framework:

1. Data Understanding
2. Data Preparation
3. Data Transformation
4. Modeling
5. Evaluation
6. Business Interpretation

### Data Preparation

* Imported and structured data in SPSS Modeler.
* Defined variable roles and measurement levels.
* Handled missing values using Filler nodes.
* Created derived variables:

  * Credit Score Category
  * Age Group
  * Income Band

### Exploratory Analysis

Visual analysis was performed using:

* Distribution Charts
* Histograms
* Scatter Plots

These helped identify trends between income, debt levels, credit scores, and default behavior.

## Models Implemented

### 1. C5.0 Decision Tree

A supervised machine learning model was used to predict loan default risk.

Key objectives:

* Classify applicants as defaulters or non-defaulters.
* Generate interpretable decision rules.
* Identify the most influential risk factors.

### 2. Apriori Association Rules

Association rule mining was applied to discover relationships between borrower characteristics and default behavior.

Example insights:

* Low credit score combined with previous defaults is strongly associated with loan default.
* Frequent missed payments increase default probability.

### 3. K-Means Clustering

Applicants were segmented into risk groups based on financial characteristics.

Risk Segments:

* Low Risk
* Medium Risk
* High Risk

This helps lenders design targeted lending and monitoring strategies.


## Key Findings

* Previous loan defaults emerged as the strongest predictor of future default.
* Credit score and missed payments significantly influenced risk levels.
* Borrowers with low income and high debt-to-income ratios showed a higher likelihood of default.
* Clustering successfully separated applicants into meaningful risk categories.


## Business Impact

The developed models can help financial institutions:

* Improve loan approval decisions.
* Reduce credit losses.
* Identify high-risk borrowers early.
* Enhance risk management strategies.
* Support data-driven lending policies.


## Conclusion

This project demonstrates how data mining and predictive analytics techniques can be used to assess credit risk and support lending decisions. By combining classification, association rule mining, and clustering, the analysis provides both predictive capability and business insights that can assist financial institutions in managing loan portfolios more effectively.
