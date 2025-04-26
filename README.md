# Lead-Scoring with the Portuguese Bank Marketing Dataset

Companies that run marketing campaigns through call centers need to decide which prospects to call first so that limited time and budget are spent on the contacts most likely to convert.

This project aims to predict whether a bank client will subscribe to a term deposit based on data from direct marketing campaigns conducted via phone calls. The objective is to leverage machine learning to identify potential subscribers more effectively. The analysis uses the Bank Marketing dataset from the UCI Machine Learning Repository, originally described by Moro, Laureano, and Cortez (2011) and can be found at https://archive.ics.uci.edu/dataset/222/bank+marketing

This dataset contains 16 input variables detailing client demographics, account information, and interaction history related to past and current marketing campaigns. Data preparation involved cleaning the dataset and performing exploratory data analysis (EDA) to understand feature distributions and relationships. Categorical variables, such as job type, marital status, and education, were converted into a numerical format using one-hot encoding to make them suitable for modeling.

Three classification algorithms were explored, namely Logistic Regression, Random Forest, and XGBoost. Initial evaluations indicated that XGBoost provided the best baseline performance on this highly imbalanced dataset, where positive subscriptions are relatively rare. To optimize performance, hyperparameter tuning was conducted for both XGBoost and Random Forest using Optuna search. Model robustness and generalization were assessed using Stratified K-Fold Cross-Validation, essential to counter the class imbalance.

The final XGBoost model, trained on the entire dataset with optimized hyperparameters, achieved an overall accuracy of approximately 89% and an AUC score of 0.92. For the minority class the model yielded a precision of 0.51, a recall of 0.73, and an F1-score of 0.60, a reasonable performance in identifying subscribing clients despite the imbalance.

SHAP analysis was employed to interpret the model's predictions and identify the most influential features. Top three factors driving the prediction of whether a client subscribes include the duration of the last contact, the month of the last contact, and whether the client has a housing loan. This project highlights how machine learning models can provide valuable insights for optimizing company marketing efforts.
