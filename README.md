Customer Segmentation and Marketing Campaign Optimisation using the Bank Marketing Dataset
Project Overview

This project applies unsupervised machine learning techniques to segment bank customers using the UCI Bank Marketing Dataset. The objective is to identify customer groups exhibiting different propensities to subscribe to a term deposit and to translate these findings into actionable marketing insights.

Customer segmentation is performed without incorporating the campaign outcome variable during clustering to ensure that discovered segments reflect underlying behavioural structure rather than supervised prediction effects. Subscription outcomes are analysed only after segmentation to evaluate performance differences across customer groups.

The analysis demonstrates how customer segmentation can support targeted marketing strategies, improve campaign efficiency, and optimise allocation of marketing resources.

Data Preprocessing
Feature Engineering

Several preprocessing steps were implemented to ensure meaningful distance-based clustering.

Behavioural Features

The pdays variable was decomposed into:

previously_contacted, indicating prior campaign interaction

pdays_value, representing time since last contact

This preserves behavioural information while avoiding distortion caused by placeholder values.

Transformation of Skewed Variables
Financial and campaign-related variables exhibit significant skewness. Logarithmic transformations were applied to:

account balance

campaign contact frequency

previous campaign interactions

These transformations reduce the influence of extreme observations and improve clustering performance.

Categorical Encoding
Categorical variables such as job, marital status, education, and previous campaign outcome were encoded using frequency encoding to reduce dimensionality and stabilise distance calculations.

Feature Scaling
Numerical features were standardised using a Standard Scaler prior to clustering.

Dimensionality Reduction

Principal Component Analysis (PCA) was applied to retain approximately 80% of total variance before clustering. This reduces noise, mitigates high-dimensional effects, and improves separation between customer groups.

All clustering, evaluation, and visualisation steps were performed consistently in PCA-transformed space.

Clustering Methodology

Customer segmentation was conducted using K-Means clustering.

The number of clusters was determined using:

Silhouette Score

Davies–Bouldin Index

Elbow Method

Cluster robustness was evaluated by repeating clustering across multiple random initialisations and measuring agreement using the Adjusted Rand Index (ARI), indicating stable and reproducible segmentation.

Model Evaluation
Metric	Result	Interpretation
Silhouette Score	~0.38	Good separation between clusters
Davies–Bouldin Index	~0.88	Compact and distinct clusters
Calinski–Harabasz Index	High	Strong cluster structure
Stability (ARI)	1.0	Highly stable segmentation
Segment Insights

The analysis identified two primary customer segments with materially different campaign response behaviour.

Cluster C0 — Low-Engagement Segment

Represents approximately 80% of customers

Subscription rate around 9%

Broad demographic composition

Lower responsiveness despite repeated campaign contact

This segment represents the general customer base generating relatively low marketing return.

Cluster C1 — High-Propensity Segment

Represents approximately 20% of customers

Subscription rate around 23%

Higher financial engagement

Stronger response to marketing outreach

This segment contributes disproportionately to successful subscriptions.

Business Recommendations

Target High-Propensity Customers

Prioritise marketing resources toward Cluster C1

Apply personalised communication strategies

Increase follow-up efforts where appropriate

Optimise Outreach to Low-Engagement Customers

Reduce excessive contact frequency

Use lower-cost communication channels

Apply stricter targeting criteria

Targeted allocation of marketing effort can improve conversion efficiency while reducing unnecessary campaign costs.
