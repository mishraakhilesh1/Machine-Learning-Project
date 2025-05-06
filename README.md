# Machine-Learning-Project
What is the objective of the data analysis? To analyze delivery time and predict delivery time, respectively, sorting time. In the context of the provided dataset, "delivery time" seems to be proxied by the 'episodes' and 'rating' columns.

What models were used and what were their performances? Linear Regression, Ridge, Lasso, and ElasticNet regression models were used. Ridge performed best with the lowest MSE (0.001459), RMSE (0.0382), MAE (0.0252), and highest R-squared (0.9881).

How was the data preprocessed? The data went through several preprocessing steps:

Missing values: Missing values in categorical columns ('genre', 'type') were imputed with the mode, and missing 'rating' values were filled with the median.
Outliers: Outliers in 'episodes' and 'rating' were handled using winsorization.
Ignoring tuples: Rows with missing 'episodes' values after imputation and outlier handling were removed.
Feature Engineering: New features were derived, including genre counts, one-hot encodings for genre and type, an interaction term between episodes and rating, and scaled numerical features.
What were the key hyperparameters used for model optimization? alpha for Ridge and Lasso, and alpha and l1_ratio for ElasticNet were optimized using GridSearchCV.

Data Analysis Key Findings
Model Performance: Ridge Regression outperformed Lasso and ElasticNet, achieving the lowest MSE (0.001459), RMSE (0.0382), and MAE (0.0252), and the highest R-squared (0.9881).
Feature Engineering Impact: The creation of interaction features and one-hot encoding of categorical features ('genre', 'type') likely contributed to the model's performance.
Data Cleaning Effectiveness: Imputing missing values and handling outliers improved data quality, enhancing model training. Removing rows with missing 'episodes' values after imputation seems to have addressed a specific project charter requirement.
Optimal Hyperparameters: GridSearchCV identified optimal hyperparameters for each model: Ridge (alpha = 0.1), Lasso (alpha = 0.001), ElasticNet (alpha = 0.001, l1_ratio = 0.1).
Insights or Next Steps
Explore Non-linear Models: Given the potential non-linear relationships observed in the data, consider exploring non-linear regression models (e.g., decision trees, random forests, support vector regression) to potentially improve prediction accuracy.
Feature Importance Analysis: Analyze feature importance from the best performing models to identify the most influential factors in predicting "delivery time" (represented by 'episodes' in the dataset). This could help refine the feature set and simplify the model.
