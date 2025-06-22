# Marketing-Campaign-Customer-Segmentation-Project-using-Unsupervised-Learning

This project applies unsupervised machine learning to segment customers based on behavioral and demographic features using the **Kaggle Marketing Campaign Dataset**. The goal is to identify distinct customer groups to help businesses tailor their **marketing strategies, loyalty programs, and promotional campaigns**.

---

## 📁 Dataset Overview

- **Source**: [[Kaggle - Marketing Campaign Data](https://www.kaggle.com/datasets/imakash3011/customer-personality-analysis](https://www.kaggle.com/datasets/ahsan81/superstore-marketing-campaign-dataset))
- **Size**: 2,240 rows × 29 columns
- **Features** include:
  - **Demographics**: `Income`, `Education`, `Marital Status`, `Year of Birth`
  - **Behavioral**: `Recency`, `Spending` on various product categories, `date of customer`, `Complaint`, and `Response` to campaigns

---

## ⚙️ Workflow Summary

### 🧹 1. Data Preprocessing
- Handled missing values (`Income`)
- Derived customer `Age`, `Created Customer Days, family-size, total-purchase` Spendingper-Purchase
- Scaled features using `StandardScaler`
- Applied PCA for 2D visualization

### 🤖 2. Clustering Techniques Tested
| Algorithm           | Silhouette Score | Clusters Found | Interpretability |
|---------------------|------------------|----------------|------------------|
| **KMeans**          | **0.792**        | 4              | ✅ High           |
| Hierarchical        | 0.792            | 4              | ✅ Medium         |
| Gaussian Mixture    | 0.792            | 4              | 🔶 Medium         |
| DBSCAN              | 0.776            | 5              | ❌ Low            |

✅ **KMeans was selected** as the final model due to:
- High silhouette score
- Balanced cluster sizes
- Simple and intuitive centroids

---

## 📊 Clustering Visualizations

### 🔹 PCA-Based Cluster Comparison

![Clustering PCA](reports/download%20(2).png)
![download (2)](https://github.com/user-attachments/assets/8518687d-7d22-4c04-83b4-98cf82104151)


---

### 🔹 Business Insights from Final KMeans Clusters

![Business Insights](reports/download%20(3).png)
![download (3)](https://github.com/user-attachments/assets/07df2706-9e39-40d6-b549-083b8bf15ec6)


---

## 💡 Business Insights

| Cluster | Income Level | Spending | Segment Type         | Recommendation                        |
|--------:|:-------------|:---------|:----------------------|:---------------------------------------|
| 1       | High         | Highest  | Premium Customers     | Focus loyalty, upselling, email promos |
| 3       | Mid-High     | Good     | Growth Segment        | Target new offers, bundling            |
| 0       | Low-Mid      | Low      | Budget Conscious      | Discounts, referral incentives         |
| 2       | Low          | Lowest   | At-Risk Customers     | Re-engagement, feedback survey         |

- 📌 All segments show similar recency → suggests timing is uniform across customers.
- 📈 Future work: Integrate **RFM segmentation** or build a **recommendation engine** for deeper personalization.

---



