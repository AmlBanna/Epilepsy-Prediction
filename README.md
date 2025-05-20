# Early Prediction of Epilepsy Using Machine Learning

![Machine Learning](https://img.shields.io/badge/Machine-Learning-blue) ![HealthTech](https://img.shields.io/badge/Health-Tech-green) ![Dataset](https://img.shields.io/badge/Dataset-1774%20rows-yellow)

## 📌 Overview
A predictive model to identify epilepsy risk factors using **21 clinical and lifestyle features** (1774 samples). Designed for healthcare analytics and early diagnosis.

## 🗂 Dataset Structure
| Feature Category        | Variables                                                                 |
|-------------------------|--------------------------------------------------------------------------|
| **Identifiers**         | FirstName, LastName (non-predictive)                                     |
| **Demographics**        | Age, Gender (0=Female, 1=Male)                                           |
| **Medical History**     | Heredity, Diabetes, Asthma, Heart Stroke, Brain Tumor (0-4), Brain Injuries |
| **Lifestyle**           | Drug/Alcohol/JunkFood Consumption, Lack of Sleep                         |
| **Clinical Metrics**    | Weight, Hormonal Imbalance, Blood Pressure (0=Low,1=Medium,2=High)       |
| **Seizure Indicators**  | Seizure Duration (0-3), Fever Frequency (0-2), Stress                    |
| **Target Variable**     | Affected (1=Epilepsy, 0=Healthy)                                         |

## 🔍 Key Features
- **Ordinal Encoding** for multi-class variables (e.g. Brain Tumor stages)
- **Binary Features**: All Yes/No fields mapped to 1/0
- **Comprehensive Risk Factors**: Includes genetic, environmental, and physiological predictors

## 🛠 Suggested Preprocessing
```python
# Example in Python:
df.drop(['FirstName','LastName'], axis=1, inplace=True)  # Remove identifiers
from sklearn.preprocessing import StandardScaler
scaler = StandardScaler()
df[['Age','Weight']] = scaler.fit_transform(df[['Age','Weight']])
```
## 📊 Potential Analyses
Feature importance ranking

Age/Gender distribution analysis

Comorbidity correlations (Diabetes + Hypertension)

Seizure duration vs Brain Tumor stage

## 📜 Ethical Considerations
Patient identifiers should be anonymized in production

Gender bias analysis recommended

Clinical validation required before deployment
