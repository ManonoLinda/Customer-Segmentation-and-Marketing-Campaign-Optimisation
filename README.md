Customer Segmentation and Campaign Analysis

This repository contains a comprehensive data science project focusing on customer segmentation and marketing campaign optimisation. Using the bank-full.csv dataset, the project identifies distinct customer clusters and evaluates their likelihood of responding positively to a marketing campaign.

📜 Project Overview

Effective customer segmentation allows businesses to design personalised marketing strategies, improving response rates and customer satisfaction. This project uses clustering, machine learning, and feature analysis to profile customers, identify high-response groups, and evaluate campaign effectiveness.

🎯 Objective

To identify customer segments for targeted marketing campaigns and determine which segment has the highest likelihood of responding positively.

📂 Dataset

Source: UCI Bank Marketing Dataset

    Size: 45,211 rows × 17 columns
    Key Features:
        Demographics: Age, job, marital status, education, balance
        Campaign Data: Contact type, duration, times contacted, previous outcomes
        Target Variable: outcome (binary: yes or no)

🔧 Methodology

    Data Preprocessing
        Renamed columns for clarity.
        Categorical features were encoded using one-hot and ordinal encoding.
        Numerical features were scaled for clustering.

    Exploratory Data Analysis (EDA)
        Visualised distributions of key features.
        Identified correlations among numerical variables.

    Clustering
        Used K-Means clustering to group customers into three distinct clusters.
        PCA was applied to visualise clusters in 2D space.

    Cluster Profiling
        Analysed average feature values for each cluster.
        Identified characteristics of each segment.

    Campaign Response Prediction
        Built a Random Forest Classifier to predict campaign outcomes.
        Evaluated model performance using metrics like accuracy, precision, recall, and F1-score.


📊 Results

Cluster Profiling:
Cluster	Average Age	Average Balance	Days Passed Since Last Contact	Campaign Contacts	Positive Outcomes (%)
0	42.29	1,338.62	230.10	2.84	21.5%
1	33.38	1,288.12	225.81	2.65	12.3%
2	55.99	1,795.42	178.20	2.58	33.7%
Cluster Insights:

    Cluster 2: Older customers with higher balances and fewer campaign contacts. This group shows the highest proportion of positive responses.
    Cluster 0: Moderate engagement with an average response rate.
    Cluster 1: Younger customers with the lowest response rates.

Model Performance:

    Accuracy: 88.42%
    Precision: 90% (class 0), 52% (class 1)
    Recall: 97% (class 0), 21% (class 1)
    Silhouette Score (Clustering): 0.083

📌 Key Recommendations

    Focus on Cluster 2:
    Customers in Cluster 2 are the most likely to respond positively. Personalised strategies targeting this group can enhance campaign efficiency.

    Re-engage Cluster 0:
    Moderate response rates indicate potential for improvement through tailored messaging.

💻 Technologies Used

    Python Libraries: Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn
    Machine Learning Models: K-Means Clustering, Random Forest Classifier
    Data Preprocessing: Ordinal and One-Hot Encoding, StandardScaler

🚀 How to Run

    Clone the repository:

git clone https://github.com/your-username/customer-segmentation.git  
cd customer-segmentation  

Install dependencies:

pip install -r requirements.txt  

Run the Jupyter Notebook or Python scripts:

    jupyter notebook notebooks/customer_segmentation.ipynb  

✨ Future Enhancements

    Implement advanced clustering techniques like DBSCAN or Gaussian Mixture Models.
    Explore additional datasets for richer segmentation.
    Develop a web app for interactive customer profiling and campaign management.

🤝 Contributions

Contributions are welcome! Feel free to fork the repository and submit a pull request.

📞 Contact

For questions or suggestions, please reach out:
Nosipho Mfusi
