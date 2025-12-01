
# 📊 Exploratory Data Analysis (EDA) on Heart Disease Dataset

![Language](https://img.shields.io/badge/Language-Python-blue?style=for-the-badge&logo=python)
![Platform](https://img.shields.io/badge/Platform-Google%20Colab-blue?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)
[![LinkedIn](https://img.shields.io/badge/HiramDeep%20Kaur-LinkedIn-blue?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/hiram-deep-227916337/)

---

## 📌 Project Overview

This notebook performs **Exploratory Data Analysis (EDA)** on the **Heart Disease dataset** from UCI repository using Python in **Google Colab**.  

The project focuses on:

- Fetching dataset from `ucimlrepo`  
- Data cleaning and type inspection  
- Descriptive statistics  
- Feature visualization using **histograms, pairplots, and boxplots**  
- Checking correlations with **heatmaps**  

It is designed for **self-learning and hands-on data analysis practice**.

---

## 🔗 Self-Learning Resources

- [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/index.php)  
- [Pandas Documentation](https://pandas.pydata.org/)  
- [Seaborn Documentation](https://seaborn.pydata.org/)  
- [Matplotlib Documentation](https://matplotlib.org/stable/contents.html)  

---

## 📌 Steps Covered

### 1. Library Installation and Dataset Fetching

```python
!pip install ucimlrepo pandas seaborn matplotlib

from ucimlrepo import fetch_ucirepo
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

heart_disease = fetch_ucirepo(id=45)
X = heart_disease.data.features
y = heart_disease.data.targets
data = pd.concat([X, y], axis=1)
````

* Install required libraries
* Fetch dataset from **UCI ML repository**
* Combine features and target into a single dataframe

---

### 2. Data Cleaning

```python
data.isnull().sum()   # Check missing values
data.dtypes          # Inspect data types
```

* Verify **missing values**
* Ensure **correct data types**

---

### 3. Descriptive Statistics

```python
data.describe()
```

* Generate **summary statistics** for all features

---

### 4. Data Visualization

#### a. Histograms

```python
data.hist(figsize=(15, 10))
plt.suptitle('Feature Distributions', y=1.02)
plt.tight_layout()
plt.show()
```

#### b. Pairplot

```python
sns.pairplot(data, hue=y.columns[0])
plt.suptitle('Pairplot of Features', y=1.02)
plt.show()
```

#### c. Boxplots

```python
plt.figure(figsize=(20, 15))
for i, column in enumerate(data.columns[:-1], 1):
    plt.subplot(4, 4, i)
    sns.boxplot(x=y.columns[0], y=column, data=data)
    plt.title(f'Boxplot of {column}')
plt.tight_layout()
plt.show()
```

#### d. Correlation Heatmap

```python
plt.figure(figsize=(12, 10))
sns.heatmap(data.corr(), annot=True, cmap='coolwarm', fmt='.2f')
plt.title('Correlation Heatmap')
plt.show()
```

---

## 👤 Author

**HiramDeep Kaur**
🔗 [LinkedIn Profile](https://www.linkedin.com/in/hiram-deep-227916337/)

---

⭐ If you found this notebook helpful, please **Star** the repository and share with others!

---
