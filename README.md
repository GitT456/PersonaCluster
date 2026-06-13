#  PersonaCluster

### Big Five Personality Clustering Using Machine Learning

![Python](https://img.shields.io/badge/Python-3.11-blue)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Clustering-orange)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Models-green)
![Status](https://img.shields.io/badge/Status-Completed-success)

---

## ✨ Overview

**PersonaCluster** is a machine learning project focused on clustering participants based on their **Big Five personality traits**.

The project uses responses from the **Big Five Personality Test** dataset and applies unsupervised learning algorithms to discover hidden personality patterns among participants.

The five main personality traits used in this project are:

* 🔹 **Extraversion**
* 🔹 **Neuroticism**
* 🔹 **Agreeableness**
* 🔹 **Conscientiousness**
* 🔹 **Openness**

---

## 🎯 Project Goal

The main goal of this project is to group people into meaningful personality clusters using unsupervised machine learning.

Since this is a clustering problem, there is no target label. Instead, the models try to find natural patterns in the data based on participants’ personality scores.

---

## 📊 Dataset

The dataset used in this project is the **Big Five Personality Test** dataset from Kaggle.

Dataset link:
https://www.kaggle.com/datasets/tunguz/big-five-personality-test

The dataset contains responses to **50 personality questions** based on the Big Five model.

Each trait is represented by 10 questions:

| Trait             | Columns      |
| ----------------- | ------------ |
| Extraversion      | EXT1 - EXT10 |
| Neuroticism       | EST1 - EST10 |
| Agreeableness     | AGR1 - AGR10 |
| Conscientiousness | CSN1 - CSN10 |
| Openness          | OPN1 - OPN10 |

---

## 🧩 Workflow

The project follows these main steps:

1. Load the dataset
2. Select the 50 personality question columns
3. Perform exploratory data analysis
4. Clean invalid and missing responses
5. Apply response time cleaning
6. Apply reverse scoring for negatively worded questions
7. Create the five Big Five personality scores
8. Standardize the data
9. Apply clustering algorithms
10. Evaluate and compare the models
11. Visualize the clusters using PCA

---

## 🧹 Data Preprocessing

Several preprocessing steps were applied to improve the quality of the data:

* Removed invalid answers outside the 1 to 5 range
* Removed missing personality responses
* Removed suspicious response times
* Applied reverse scoring to negatively worded questions
* Created five final personality features from the original 50 questions
* Standardized the final features using `StandardScaler`

---

## 🤖 Applied Models

Three clustering algorithms were used:

### 1. K-Means

K-Means was used as the main clustering algorithm.
The number of clusters was set to **4**, inspired by common Big Five personality clustering research.

### 2. DBSCAN

DBSCAN was tested as a density-based clustering algorithm.
However, it mostly placed participants into one dominant cluster and created only a few very small clusters.

### 3. Mean-Shift

Mean-Shift was also tested because it can automatically detect the number of clusters.
However, it struggled to find balanced and clearly separated personality groups.

---

## 📈 Evaluation Metrics

The clustering models were evaluated using:

| Metric                  | Meaning                                                |
| ----------------------- | ------------------------------------------------------ |
| Silhouette Score        | Measures how well-separated the clusters are           |
| Davies-Bouldin Score    | Lower values indicate better clustering                |
| Calinski-Harabasz Score | Higher values usually indicate better-defined clusters |

---

## 🏆 Results

The results showed that **K-Means** was the most suitable algorithm for this dataset.

Although the Silhouette Score was not very high, K-Means created more balanced and interpretable personality groups compared to DBSCAN and Mean-Shift.

DBSCAN and Mean-Shift were less effective because the Big Five personality traits are continuous and do not form strongly separated density-based clusters.

---

## 🔍 Cluster Analysis

After applying K-Means, each cluster was analyzed based on the average values of the five Big Five traits.

This helped understand the general personality pattern of each group.

Example cluster interpretation:

| Cluster   | General Pattern                                       |
| --------- | ----------------------------------------------------- |
| Cluster 0 | Balanced personality traits                           |
| Cluster 1 | Lower extraversion and openness                       |
| Cluster 2 | Higher conscientiousness and openness                 |
| Cluster 3 | Lower neuroticism and more stable personality pattern |

---

## 🖼️ Visualization

PCA was used to reduce the final five personality features into two dimensions for visualization.

This made it easier to visually inspect how participants were grouped by the clustering algorithms.

---

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-Learn
* Google Colab / Kaggle Notebook

---

## ✅ Conclusion

In this project, K-Means, DBSCAN, and Mean-Shift were applied to cluster participants based on their Big Five personality traits.

The results showed that **K-Means was the best clustering algorithm** for this dataset because it produced more balanced and interpretable personality groups.

DBSCAN and Mean-Shift were less effective, as they mostly placed participants into one dominant cluster or generated very small clusters.

Therefore, K-Means was selected as the final model for personality clustering in this project.

---

## 🚀 Project Name

**PersonaCluster**
A simple and interpretable clustering project based on Big Five personality traits.
