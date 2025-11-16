# 📊 Data Mining Project — Clustering & Claim Prediction (CART, RF, ANN)

This project consists of two major data mining tasks:
1. **Customer Segmentation using Clustering**  
2. **Insurance Claim Prediction using CART, Random Forest, and ANN**

Both parts follow complete data-mining workflows: EDA, preprocessing, model development, evaluation, and business recommendations.

---

# 🧩 Problem 1 — Customer Segmentation (Clustering)

A leading bank wants to segment 210 credit-card users based on spending behavior, advance payments, balance, credit limits, and payment habits. Goal: **define clusters and recommend targeted promotional strategies.**

### 🔍 Steps Performed

#### **1. Exploratory Data Analysis**
- Checked missing values, duplicates (none found)  
- Summary statistics & skewness  
- Frequency plots, boxplots for outlier detection  
- Correlation matrix & pairplot  
- Identified strong correlations among *spending*, *advance payments*, *current balance*, and *credit limit*

#### **2. Scaling**
- StandardScaler (z-score) applied  
- Required because features exist on very different scales

#### **3. Hierarchical Clustering**
- Ward linkages + dendrogram  
- Optimum clusters: **2**  
- Cluster Characteristics:  
  - **Cluster 1:** High spending, high advance payments, high credit limit  
  - **Cluster 2:** Low spending, lower credit limit, moderate payment behavior

#### **4. Agglomerative Clustering**
- Also produced **2 clusters**  
- Results consistent with hierarchical approach

#### **5. K-Means Clustering**
- Elbow curve + silhouette score → **k = 2**  
- Cluster Profiles:  
  - **Cluster 0:** Low spending, low credit limit  
  - **Cluster 1:** High spending, high credit limit, good payment history

### 🧠 Business Insights & Recommendations
- **High-value users:** Offer premium cards, increase limits, loyalty rewards  
- **Low-value users:** Encourage spending via cashback, utility-bill benefits  
- Avoid raising limits for low-spending users (higher risk)  

---

# 🛡️ Problem 2 — Insurance Claim Prediction (CART, RF, ANN)

An insurance firm wants to predict claim status using **tour details of 3000 users** (2861 after removing duplicates). Features include agency, product, destination, commission, sales, duration, and age.

### 🔍 Steps Performed

#### **1. EDA**
- Removed 139 duplicates  
- Dropped “Channel” due to extremely low offline records  
- Visualized distributions, boxplots, count plots  
- Multivariate patterns:  
  - C2B agency sells the most plans (Gold/Silver)  
  - High sales for Asia region  
  - Sales and commission show strong correlation (0.76)

#### **2. Preprocessing**
- Converted categorical variables to numeric  
- Train–test split: **70% / 30%**

#### **3. Models Built**
1. **CART (Decision Tree)**  
2. **Random Forest**  
3. **Artificial Neural Network (MLPClassifier)**  
All models tuned using GridSearchCV.

#### **4. Model Performance Summary**

| Model | Test Accuracy | Test Recall | AUC |
|-------|--------------|-------------|------|
| CART | 77% | 52% | 79.1% |
| Neural Network | 76% | 50% | 80.4% |
| **Random Forest (Best)** | **78%** | **58%** | **81.4%** |

### 🏆 Final Model
**Random Forest** — best overall accuracy, precision, recall, and AUC; most stable on train and test.

### 🧠 Business Insights & Recommendations
- Claims highest for **Airlines + Gold/Silver plans**  
- C2B agency drives most sales but only sells for Asia → expand destinations  
- JZI sells only Bronze plans → needs product training and upsell strategy  
- Promote online channels (vast majority prefer online booking)  
- Use model predictions to upsell insurance based on predicted claim probability  

---

## 🛠️ Tools & Libraries
- Python  
- Pandas, NumPy  
- Scikit-Learn  
- Matplotlib, Seaborn  
- Scipy  

⭐ *If you found this project useful, consider starring the repo!*
