****Air Pollution Data Analysis and Classification****

Project Overview
This project focuses on analyzing air pollution data across different cities and countries, predicting pollution levels, and classifying them into severity categories. The data contains various air quality indicators like PM2.5, PM10, and NO2, alongside metadata such as country, city, and temporal coverage.

Data Overview
The dataset consists of 32,191 entries, each containing information about:

Country Name
City
Year
Pollutants (PM2.5, PM10, NO2 in μg/m3)
Temporal coverage (%) for PM2.5, PM10, and NO2
Updated Year
After preprocessing, null values for numerical columns were filled with the respective column's mean value, and categorical features like Country Name and City were label-encoded.

Data Preprocessing
Handling Missing Values: Null values in the numerical columns were imputed using the column means.
Encoding Categorical Variables: Categorical columns such as Country Name and City were transformed into numerical labels using LabelEncoder.
Data Binning: The dataset’s PM10 concentration was binned into six categories (Levels 1–6) based on specified thresholds, representing different severity levels of air pollution.
Exploratory Data Analysis (EDA)
To better understand the correlations between features, a heatmap was generated using Seaborn, displaying the relationships among pollutants and other relevant attributes.

Model Building
Decision Tree Classifier:
Model: A Decision Tree Classifier was trained on the dataset to predict pollution severity levels (1–6).
Hyperparameters:
max_depth=3
class_weight='balanced'
Performance: The model achieved an overall weighted accuracy of 99%. However, the classification report indicated challenges with correctly classifying higher pollution levels (Levels 3–6), due to imbalanced class distribution.
K-Nearest Neighbors (KNN) Regressor:
Model: A KNN Regressor was applied to predict the target levels.
Performance: The model achieved an R² score of 0.96, indicating a high degree of accuracy in regression tasks.
Classification Performance
The classification performance was measured using precision, recall, and F1-score. While the model performed well for common categories (Level 1 and 2), it struggled with higher pollution levels due to insufficient data. This imbalance led to undefined metrics for certain levels (Level 5 and Level 6), as indicated by the warnings.

Key Metrics
Decision Tree Accuracy: 99% (Weighted average)
KNN R² Score: 0.96
Visualization
A correlation heatmap was generated to explore the relationships between air quality indicators and to identify highly correlated features.
