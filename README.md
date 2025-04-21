# Breast-Cancer-Detection-Model-Comparison

##🔍 Overview

This project focuses on predicting whether a breast cancer tumor is malignant or benign using machine learning techniques. The dataset used is the **Breast Cancer Wisconsin (Diagnostic) dataset**. The task is to classify the diagnosis into two categories: **Malignant (1)** and **Benign (0)**.

##🧠 What I Learned

Throughout this project, I learned several key concepts in machine learning, particularly regarding data preprocessing, feature selection, model training, and evaluation. Here are some of the key takeaways:

- **Data Preprocessing**: Understanding the importance of cleaning data, handling missing values, and scaling features for better model performance. In this case, I used `StandardScaler` to standardize the feature set.
  
- **Feature Selection**: By analyzing the correlation between features using a correlation matrix, I was able to drop highly correlated features. This helped reduce multicollinearity, which can lead to overfitting, and allowed for a more interpretable model. Removing unnecessary features can also improve model performance and training time.

- **Model Evaluation**: I implemented multiple evaluation techniques, such as confusion matrix, classification report, and accuracy score, to assess the performance of the models. I also explored cross-validation to ensure the models generalize well.

- **Model Comparison**: By using both **Logistic Regression** and **Random Forest** models, I compared the performance of both algorithms and gained insights into how different models can perform on the same dataset.

## Data Cleaning and Feature Selection

The dataset contained some irrelevant columns (such as the `id` and `Unnamed: 32` columns) which were dropped to focus on the important features.

The target variable `diagnosis` was initially in textual format (Malignant = M, Benign = B), so I used **LabelEncoder** to convert it into numerical values (0 for Benign and 1 for Malignant).

To identify any highly correlated features, I calculated the correlation matrix. Features with a correlation greater than 0.9 were considered redundant and were dropped. This helps prevent multicollinearity, where multiple features contain the same information, which can negatively affect model performance. By doing this, I reduced the number of features without losing valuable information.
For example, features like `radius_worst` and `radius_mean` had a high correlation, so I dropped the one that was less informative.
  

## Model Training and Evaluation

###📉 Logistic Regression

- **Logistic Regression** was trained and evaluated using the processed data. It performed well in distinguishing between malignant and benign tumors, with an accuracy score that reflected its ability to separate the two classes.
  
- I evaluated the model using:
  - **Confusion Matrix**: This gave insights into the true positives, true negatives, false positives, and false negatives.
  - **Classification Report**: This provided precision, recall, and F1-score to evaluate the performance in more detail.
  - **ROC Curve and AUC**: I computed the Receiver Operating Characteristic (ROC) curve and calculated the Area Under the Curve (AUC) to assess the model’s discriminative ability.

###🌲 Random Forest

**Random Forest**, an ensemble method, was also trained on the same data. It is a more complex model that uses multiple decision trees to classify instances. While Random Forest is often more robust to overfitting, I found that Logistic Regression performed slightly better in this case. I also evaluated Random Forest using the same metrics (confusion matrix, classification report, accuracy) to ensure that I compared both models fairly.

### Cross-Validation

I performed **cross-validation** with Logistic Regression to check its stability across different subsets of the data. The cross-validation scores confirmed that the model performed consistently, and its mean accuracy score provided an indication of its generalization ability.

##⚖️ Comparison of Models

**Logistic Regression** performed better in terms of overall accuracy and evaluation metrics like precision and recall. Given that this is a simpler model, it suggests that Logistic Regression is suitable for this type of problem, especially with fewer features after feature selection. **Random Forest** also performed reasonably well but did not outperform Logistic Regression on this dataset. However, it showed how ensemble methods like Random Forest can handle non-linear relationships and complex patterns.

## 🧾 Final Thoughts

This project provided a comprehensive learning experience in machine learning, from preprocessing data to evaluating and comparing different models. Key steps such as feature selection and model evaluation were crucial in improving model performance.


