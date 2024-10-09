# Cyberattack Detection Using Machine Learning

## Project Overview
In this project, the goal is to detect cyberattacks by analyzing network traffic data using machine learning algorithms. The dataset contains various network-related features such as flow duration, protocol type, flag numbers, and statistical values like the mean, max, and standard deviation of network packet properties. The target variable is a binary classification between **benign** and **attack** traffic.

Two machine learning models were employed in this task:
1. **Logistic Regression**
2. **Random Forest Classifier**

These models were chosen to provide a balance between interpretability (Logistic Regression) and prediction power (Random Forest).

## Data Preprocessing
Before model training, several preprocessing steps were applied:
- Handling missing data and outliers.
- Label encoding for binary features.
- Scaling numerical features using `StandardScaler` to ensure that all features are on the same scale.
- Splitting the dataset into training and testing sets (80% training, 20% testing).

## Models and Results

### Logistic Regression
The **Logistic Regression** model is a simple yet effective model that predicts the probability of a network session being an attack. It works well with large datasets but may not handle complex relationships as well as tree-based methods. The results are as follows:

- **Accuracy:** 98.88%
- **Precision (Attack):** 0.78
- **Recall (Attack):** 0.73
- **F1-Score (Attack):** 0.75
- **Confusion Matrix:**
    - True Positives (Attacks detected): 15,941
    - False Positives: 4,367
    - False Negatives (Missed attacks): 6,024
    - True Negatives: 907,399

### Random Forest Classifier
The **Random Forest Classifier** is an ensemble method that combines multiple decision trees to improve performance. It is particularly effective for complex datasets with non-linear relationships. The results are significantly better:

- **Accuracy:** 99.75%
- **Precision (Attack):** 0.94
- **Recall (Attack):** 0.96
- **F1-Score (Attack):** 0.95
- **Confusion Matrix:**
    - True Positives (Attacks detected): 21,037
    - False Positives: 1,389
    - False Negatives (Missed attacks): 928
    - True Negatives: 910,377

## Comparison of Models
The performance of **Random Forest** was superior to **Logistic Regression** in nearly all metrics. While Logistic Regression provided a strong baseline with an accuracy of **98.88%**, it struggled with detecting attacks, as evidenced by its lower recall (73%) and higher number of false negatives (6,024). This means that Logistic Regression was less reliable in identifying cyberattacks, which could be critical in real-world cybersecurity settings.

On the other hand, **Random Forest** achieved an impressive **99.75% accuracy** and significantly reduced the number of false negatives (only 928 missed attacks). Its higher precision (94%) and recall (96%) demonstrate that it is better suited for detecting attacks in this dataset, offering a more reliable solution for cyberattack detection.

## Conclusion
In conclusion, while Logistic Regression offers simplicity and interpretability, it is not as effective as Random Forest in detecting cyberattacks. For this dataset, Random Forest provides a much more robust model with higher accuracy and fewer false negatives, making it the preferred choice for cyberattack detection tasks.

