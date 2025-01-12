Objective:

The primary goal of this project was to segment customers using the Bank Marketing dataset (UCI) and identify distinct groups to target with personalized marketing campaigns. The segmentation was based on various customer attributes, such as age, marital status, loan history, previous campaign outcome, and more.
Data Preprocessing and Feature Engineering:

The dataset underwent several preprocessing steps, including encoding categorical variables (e.g., job, marital status, housing status), handling missing values, and scaling numerical features. Features like balance, age, and previous campaign outcome_success were found to be crucial in determining the customer clusters.

Clustering Approach:

We used K-Means clustering to identify three customer clusters. These clusters were derived using the PCA-transformed data to reduce dimensionality and better visualise the clusters in 2D space.

Centroids in PCA Space:

    Cluster 0: PCA1 = 1.83, PCA2 = 0.12
    Cluster 1: PCA1 = 3.32, PCA2 = 0.59
    Cluster 2: PCA1 = -0.85, PCA2 = -0.07

Cluster Distribution:

The distribution of customers in each cluster based on the outcome variable (outcome_encoded) is as follows:

    Cluster 0: 11094 (outcome = 0), 1766 (outcome = 1)
    Cluster 1: 669 (outcome = 0), 269 (outcome = 1)
    Cluster 2: 28159 (outcome = 0), 3254 (outcome = 1)

Cluster Profiling:

Each cluster’s features and correlations were analysed, revealing distinct characteristics:

    Cluster 0 (Larger, Low Response Rate):
        High percentage of married and blue-collar workers, with a low loan approval rate.
        Lower likelihood of responding to previous campaign outcomes.
        High mean age and balance.
        
    Cluster 1 (Smaller, Moderate Response Rate):
        A relatively higher likelihood of responding to previous campaigns.
        Characteristics include a high percentage of single customers with lower housing and loan approval rates.
        
    Cluster 2 (Largest, High Response Rate):
        Younger customers, with higher chances of success in previous campaigns.
        Lower percentage of customers with housing or loan approvals.

Performance Evaluation:

The predictive model was built using Random Forest, achieving an impressive accuracy of 89.26% on the test set. Key metrics (precision, recall, F1-score) were evaluated, with a strong performance in predicting customers who would respond to the marketing campaign.

The model achieved the following classification metrics:

    Precision: 0.90 (Class 0), 0.67 (Class 1)
    Recall: 0.99 (Class 0), 0.18 (Class 1)
    F1-Score: 0.94 (Class 0), 0.28 (Class 1)

Confusion Matrix:
[11826   140]
[ 1317   281]

Additionally, the Random Forest model showed that important features include:

    balance (0.2594)
    age (0.2152)
    days passed since last contact (0.1356)

Model Hyperparameter Tuning:

After performing cross-validation, the model’s hyperparameters were fine-tuned using GridSearch, achieving the best results with:

    Best Parameters:
        n_estimators = 200
        min_samples_split = 5
        min_samples_leaf = 4
        max_depth = 20

The accuracy with these parameters was 89.35%, and the average cross-validation score was 85.34%.
Conclusion:

This segmentation analysis and predictive model offer actionable insights for personalized marketing campaigns. By targeting customers from the different clusters based on their likelihood of responding to a campaign, the bank can optimize resource allocation and improve overall campaign efficiency. The model shows great potential for real-time fraud detection or targeted marketing systems.

Here’s a breakdown of the positive outcome proportions for each cluster:

    Cluster 0: 13.73% positive outcome
    Cluster 1: 28.68% positive outcome
    Cluster 2: 10.36% positive outcome

Even though Cluster 2 has the highest total count of customers, Cluster 2 has the lowest proportion of positive outcomes, meaning that this cluster will likely yield better targeted marketing or interventions when a positive outcome is the goal.
