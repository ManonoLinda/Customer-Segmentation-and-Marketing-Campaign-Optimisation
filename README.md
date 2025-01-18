Customer Segmentation and Campaign Success Analysis using Bank Marketing Dataset
Project Overview

This project leverages the Bank Marketing Dataset (UCI) to perform customer segmentation and identify the segments most likely to subscribe to a term deposit. The primary goal is to analyse customer characteristics, apply clustering techniques, and provide actionable insights to improve marketing strategies for the bank. By understanding customer behaviour, this project helps predict whether a customer will subscribe to a term deposit (variable y) based on a variety of demographic and behavioural features.

Table of Contents

    Project Overview
    Data Preprocessing
    Clustering Analysis
    Results and Insights
    Key Insights
    Evaluation Metrics
    Recommendations
    Installation
    Usage
    Technologies Used
    License

Data Preprocessing
Feature Engineering and Transformation:

    Outlier Handling: Outliers in the balance and campaign columns were replaced with the 95th percentile values.
    Binarisation of previous and pdays: These features were transformed into binary values, with non-zero values converted to 1 and zero values left as 0.
    One-Hot Encoding: Categorical variables such as job, marital, and housing were transformed using one-hot encoding.
    Standardisation: Numerical features like age, balance, and campaign were standardised using a Standard Scaler.
    Ordinal Encoding: The education feature was ordinally encoded based on its importance.

Clustering Analysis
Clustering Algorithm:

    KMeans Clustering: The optimal number of clusters was determined using the Silhouette Score and the Elbow Method, with the final model yielding five clusters.
    Cluster Profiling: Each cluster was analysed to understand the characteristics of the customers, and key patterns were identified in terms of subscription likelihood.

Results and Insights
Subscription Analysis:

    Cluster 3: The premium customer segment with the highest likelihood to subscribe to a term deposit. They have higher balances, tertiary education, and a lower frequency of previous contacts.
    Cluster 2: Customers with moderate balances who are somewhat likely to subscribe to a term deposit. They are middle-aged and have a history of engagement.
    Cluster 4: The least likely to subscribe, with low balances and frequent contact history. A targeted and less frequent approach is recommended.

Key Insights:

    Cluster 3 has the largest percentage of 'yes' subscriptions, making it the most valuable segment for targeted marketing campaigns.
    Cluster 2 shows potential for conversion, with middle-aged customers and moderate balances.
    Cluster 4 should be engaged with more personalized and less frequent marketing offers due to lower conversion rates.

Evaluation Metrics:

    Silhouette Score: 0.307 — Indicates reasonably well-separated clusters.
    Davies-Bouldin Index: 1.277 — Suggests distinct clusters.
    Calinski-Harabasz Index: 14,934.82 — Further supports the clustering quality.

Recommendations:

    Target Cluster 3: Focus on high-value marketing offers such as premium services and long-term savings for customers with higher balances and tertiary education.
    Engage Cluster 2: Market financial growth, savings, and investment options to middle-aged customers with moderate balances.
    Optimise Contact for Cluster 4: Reduce the frequency of contacts and implement personalised offers to improve conversion rates.

Installation

To run the project locally, follow these steps:

    Clone the repository:

git clone https://github.com/ManonoLinda/Customer-Segmentation-and-Marketing-Campaign-Optimisation.git

Navigate to the project directory:

cd bank-marketing-segmentation

Install the required dependencies:

    pip install -r requirements.txt

Usage

To run the analysis and generate the results:

    Execute the main script:

    python segmentation_analysis.py

    The script will:
        Load and preprocess the data.
        Apply KMeans clustering.
        Evaluate the clustering performance.
        Output visualisations and insights.

Technologies Used

    Python: The main programming language used for data analysis and clustering.
    Pandas: For data manipulation and analysis.
    NumPy: For numerical computations.
    Matplotlib & Seaborn: For visualisation of results.
    Scikit-Learn: For clustering and data preprocessing.
    Jupyter Notebook: Used for exploratory analysis and visualisation.
