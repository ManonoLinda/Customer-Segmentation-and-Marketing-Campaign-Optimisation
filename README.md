# Customer Segmentation and Marketing Campaign Optimisation  
## Bank Marketing Dataset (UCI)

---

## Project Overview

This project applies unsupervised machine learning to segment bank customers based on demographic and behavioural characteristics using the UCI Bank Marketing Dataset.

The objective is to identify customer groups with differing probabilities of subscribing to a term deposit and translate these insights into actionable marketing strategies that improve campaign effectiveness and resource allocation.

Customer segmentation is performed **without using the campaign outcome variable during clustering**, ensuring that discovered segments reflect underlying behavioural structure rather than supervised prediction effects. Subscription outcomes are analysed only after segmentation to evaluate commercial value.

---

## Business Objective

Marketing campaigns often apply uniform outreach strategies across heterogeneous customer populations. This results in:

- Excessive contact costs  
- Customer fatigue  
- Inefficient allocation of marketing resources  

This project demonstrates how behavioural segmentation can support:

- Targeted marketing strategies  
- Improved campaign conversion rates  
- Reduced operational marketing costs  
- Better return on marketing investment  

---

## Dataset

**Source:** UCI Machine Learning Repository  
**Dataset:** Bank Marketing Dataset  

The dataset contains customer demographic information, financial indicators, and historical campaign interaction data used to analyse subscription behaviour for term deposits.

---

## Methodology

### 1. Feature Engineering

Behaviourally meaningful features were constructed to improve clustering quality.

- The `pdays` variable was decomposed into:
  - `previously_contacted`
  - `pdays_value`
- Highly skewed financial and campaign variables were transformed using logarithmic scaling.
- A signed logarithmic transformation was applied to account balances.

These steps reduce distortion caused by outliers and improve distance-based learning.

---

### 2. Categorical Encoding

Categorical variables were transformed using **frequency encoding** rather than one-hot encoding to:

- Reduce dimensionality  
- Avoid sparse feature expansion  
- Stabilise similarity measurements  

---

### 3. Feature Scaling

Numerical variables were standardised using `StandardScaler` to ensure equal contribution across features.

---

### 4. Dimensionality Reduction

Principal Component Analysis (PCA) was applied prior to clustering, retaining approximately **80 percent of total variance**.

This improves clustering performance by:

- Removing correlated noise  
- Mitigating high-dimensional effects  
- Enhancing geometric separation between customers  

All clustering, evaluation, and visualisation were performed in PCA space.

---

### 5. Customer Segmentation

Customer groups were identified using **K-Means clustering**.

The number of clusters was selected using:

- Silhouette Score  
- Davies-Bouldin Index  
- Elbow Method  

Cluster stability was validated using the **Adjusted Rand Index (ARI)** across multiple random initialisations.

---

## Model Evaluation

| Metric | Value | Interpretation |
|------|------|---------------|
| Silhouette Score | 0.6256 | Strong separation between segments |
| Davies-Bouldin Index | 0.5870 | Compact and distinct clusters |
| Calinski-Harabasz Index | 60,500+ | Strong structural segmentation |
| Stability (ARI) | 1.0 | Fully stable clustering |

---

## Customer Segments

### Cluster C0 - Low Engagement Segment
- Customers: 36,954  
- Share: 81.7%  
- Subscription Rate: 9.16%  

**Characteristics**
- Broad customer population  
- Lower response despite repeated outreach  
- Represents majority marketing expenditure  

**Business implication**
This segment generates limited return relative to outreach effort.

---

### Cluster C1 - High Propensity Segment
- Customers: 8,257  
- Share: 18.3%  
- Subscription Rate: 23.07%  

**Characteristics**
- Financially engaged customers  
- Stronger response to campaign contact  
- More than double the conversion rate of Cluster C0  

**Business implication**
This segment delivers disproportionate campaign value.

---

## Business Value

The segmentation enables data-driven marketing optimisation.

### Target High Propensity Customers
- Prioritise personalised outreach  
- Increase follow-up intensity  
- Allocate experienced sales resources  

### Optimise Low Engagement Outreach
- Reduce excessive contact frequency  
- Deploy lower-cost communication channels  
- Minimise campaign fatigue  

Expected outcomes include improved conversion efficiency and reduced campaign costs.
