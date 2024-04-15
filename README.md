# Employee-Attrition---Data-Mining

INTRODUCTION The choice of an employee attrition dataset for data mining is valuable for organizations as it helps identify key factors contributing to turnover. Analyzing attributes like job satisfaction, compensation, work-life balance, and demographics enables pinpointing influential factors. Predictive modeling using historical data allows organizations to forecast attrition and take proactive measures. Additionally, analyzing employee attrition data aids in developing effective retention strategies, tailoring HR policies, programs, and initiatives to address specific areas like job satisfaction. This can improve workplace culture, provide career development opportunities, and revise compensation plans, ultimately enhancing employee retention.

CHALLENGE & CHOICE TO OVERCOME IT Class imbalance is a challenge that can occur in an employee attrition dataset, where one class (attrition) dominates the other, making it difficult to build accurate predictive models. To address this challenge, the Synthetic Minority Over-sampling Technique (SMOTE) is commonly used. SMOTE generates synthetic samples of the minority class by interpolating between neighboring instances. This technique helps balance the class distribution and provides a more representative dataset for model training.

While SMOTE is a widely used technique for addressing class imbalance, it is important to note that it may not always be the optimal choice for every situation. Because of limited time we couldn't proceed to trying all the potentially better methods.

METHODOLOGY

Data quality check: We performed check for missing values in the dataset.

Exploratory Data Analysis (EDA): We examined the shape of the dataset. Also, inspected the data types of each column. Moreover, calculated basic descriptive statistics. Lastly we plotted histograms for numerical features, Creating separate histograms for the 'Attrition' attribute.

Data preprocessing: We identified and dropped irrelevant columns, scaled numerical attributes. Correlation analysis: Then. created a correlation matrix. Plot a heatmap visualization. Identify the highest correlation value and corresponding attribute names.

One-hot encoding: Encoded categorical attributes. Converted the 'Attrition' column to binary values.

Separate features and target variable: Divided the dataset into independent attributes (X) and the target variable (y).

MODEL TRAINING AND EVALUATION

For the sake of completeness we provide a short description of models we trained using the Augmented Data (SMOTE). Iteratevely we trained the same models using 1. SMOTE with PCA,Non-Augmented (Original data), Non-Augmented with PCA.

1.Logistic Regression 2.Decision Tree 3.Random Forest 4.Gradient Boosting 5.XGBoost Classifier 6.AdaBoost

CLUSTERING

Additionally, we performed Correlation analysis, where we calculated the correlation between each attribute and the target variable 'Attrition'. From the above, we selected the 10 most correlated features and draw a hierarchical clustering using complete linkage. The knowledge derived from it can be utilized in feature selection for further experimentation.

Moreover, in an exploratory spirit we have conducted extensive Clustering Analysis for the best attribute pair (searching through numerical attributes only) and clustering algorithm (K-means, AgglomerativeClustering, and GMM) and for each pair of attribut and clustering algorithm we check the following scores: Silhouette, Calinski-Harabasz and Davies-Bouldin. The attribute pairs with the best scores are stored.

For the best attribute pair and clustering algorithm the predicted cluster labels are obtained. Based on the provided in the dataset ground truth labels we calculated the Accuracy and F1 scores.

As you can observe, we obtained very poor results. Something we should be aware of since the dataset is highly imbalanced.

CONCLUSION

From the above table we evaluate the performance of models (for an imbalanced dataset) based on precision_1 = 0.7, recall_1 = 0.49 and f-1score_1 = 0.57. The best performing model is Logistic Regression on Augmented Data (SMOTE). ROCcurve and Confusion matrix is below