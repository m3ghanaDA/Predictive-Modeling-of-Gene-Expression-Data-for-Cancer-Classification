# Gene Expression Cancer Classification and Clustering Analysis

## 📌 Project Overview

This project applies a range of **supervised** and **unsupervised machine learning techniques** to a high-dimensional **Gene Expression Cancer Dataset**. The objective is to explore gene expression patterns, identify meaningful clusters, and build predictive models capable of classifying cancer types as **Invasive** or **Noninvasive**.

The analysis was conducted using **RStudio** and includes data preprocessing, dimensionality reduction, clustering, classification, model evaluation, and comparative performance analysis.

---

## 🎯 Objectives

- Explore and preprocess high-dimensional gene expression data.
- Reduce dimensionality using Principal Component Analysis (PCA).
- Apply clustering techniques to identify hidden structures in the data.
- Build classification models for cancer type prediction.
- Compare model performance using statistical evaluation metrics.
- Identify the most effective machine learning approach for this dataset.

---

## 📊 Dataset Information

**Dataset:** Gene Expression Cancer Dataset

### Dataset Characteristics

- **Samples (Patients):** 78
- **Genes (Features):** 4,948
- **Cancer Classes:**
  - Invasive (34 samples)
  - Noninvasive (44 samples)

### Project Subset

A random subset of **2,000 genes** was selected for analysis.

| Description | Dimension |
|------------|-----------|
| Original Dataset | 78 × 4948 |
| Subset for Clustering | 78 × 2000 |
| Subset for Classification | 78 × 2001 |

---

## 🛠️ Technologies Used

- R
- RStudio
- PCA
- K-Means Clustering
- Hierarchical Clustering
- Logistic Regression
- Linear Discriminant Analysis (LDA)
- Quadratic Discriminant Analysis (QDA)
- K-Nearest Neighbors (KNN)
- Random Forest
- Support Vector Machine (SVM)
- Decision Trees

### R Libraries

```r
zoo
ggplot2
plotly
caret
glmnet
MASS
randomForest
e1071
factoextra
cluster
purrr
ggpubr
rpart
doParallel
```

---

## 🔍 Data Preprocessing

The following preprocessing steps were performed:

- Missing value detection
- Mean imputation for missing values
- Duplicate feature detection
- Zero-value feature inspection
- Distribution analysis
- Scaling evaluation
- Feature validation

### Missing Values

- Total missing values found: **77**
- Imputed using column means

### Data Quality Checks

✔ No duplicate columns

✔ No zero-value columns

✔ Consistent feature scaling

---

## 📉 Dimensionality Reduction

### Principal Component Analysis (PCA)

PCA was applied to:

- Reduce dimensionality
- Mitigate multicollinearity
- Improve computational efficiency

### Results

- Original Features: 2000 genes
- Reduced Components: 78 PCs
- First 4 principal components retained for modeling

Benefits:

- Reduced feature space
- Lower correlation among predictors
- Improved visualization and model performance

---

## 🔬 Unsupervised Learning

### 1. K-Means Clustering

Applied on:

- All PCA scores
- First four principal components

#### Findings

- Best performance achieved with:
  - **K = 6**
- Lower Within-Cluster Sum of Squares (WCSS)
- Improved separation using PCA-transformed data

### Evaluation Metric

```text
WCSS (Within Cluster Sum of Squares)
```

---

### 2. Hierarchical Clustering

Methods evaluated:

- Complete Linkage
- Average Linkage
- Single Linkage

#### Best Method

**Complete Linkage**

Agglomerative Coefficient:

```text
0.6644
```

### Silhouette Analysis

| Clusters | Silhouette Score |
|-----------|----------------|
| 2 | 0.472 |
| 3 | 0.297 |
| 4 | 0.341 |
| 5 | 0.315 |
| 6 | 0.256 |

#### Optimal Number of Clusters

```text
2 Clusters
```

### Conclusion

Hierarchical Clustering outperformed K-Means in:

- Stability
- Cluster separation
- Interpretability

---

## 🤖 Supervised Learning Models

### Logistic Regression

Regularization:

- LASSO (L1)

#### Results

| Metric | Value |
|----------|--------|
| Accuracy | 100% |
| Sensitivity | 100% |
| Specificity | 100% |

---

### Linear Discriminant Analysis (LDA)

#### Results

| Metric | Value |
|----------|--------|
| Sensitivity | 66.67% |
| Specificity | 75.00% |
| Misclassification Rate | 28% |

---

### Quadratic Discriminant Analysis (QDA)

#### Results

| Metric | Value |
|----------|--------|
| Sensitivity | 50.00% |
| Specificity | 58.33% |
| Misclassification Rate | 42% |

---

### K-Nearest Neighbors (KNN)

Optimal parameter:

```text
k = 13
```

#### Results

| Metric | Value |
|----------|--------|
| Accuracy | 64.29% |
| Sensitivity | 33.33% |
| Specificity | 87.50% |

---

### Random Forest

Optimal parameter:

```text
mtry = 6
```

#### Results

| Metric | Value |
|----------|--------|
| Accuracy | 64.29% |
| Sensitivity | 50.00% |
| Specificity | 75.00% |

---

### Support Vector Machine (SVM)

#### Results

| Metric | Value |
|----------|--------|
| Accuracy | 50.00% |
| Sensitivity | 0.00% |
| Specificity | 87.50% |

---

### Decision Tree

#### Results

| Metric | Value |
|----------|--------|
| Accuracy | 100% |
| Sensitivity | 100% |
| Specificity | 100% |

---

## 📈 Model Comparison

### Unsupervised Learning

| Model | Performance |
|---------|-------------|
| K-Means | Good |
| Hierarchical Clustering | Best |

### Supervised Learning

| Model | Accuracy |
|---------|-----------|
| Logistic Regression | 100% |
| Decision Tree | 100% |
| LDA | Moderate |
| Random Forest | Moderate |
| KNN | Moderate |
| QDA | Fair |
| SVM | Poor |

---

## 🏆 Best Models

### Clustering

✅ Hierarchical Clustering (Complete Linkage)

Reasons:

- Higher stability
- Better cluster separation
- Optimal with only 2 clusters

### Classification

✅ Logistic Regression

✅ Decision Tree

Reasons:

- Perfect accuracy
- Zero misclassification
- Excellent sensitivity and specificity

---



## 🚀 How to Run

### Clone Repository

```bash
git clone https://github.com/m3ghanaDA/gene-expression-cancer-analysis.git

cd gene-expression-cancer-analysis
```

### Open in RStudio

```r
MA321 r code.Rmd
```

### Install Required Packages

```r
install.packages(c(
  "zoo",
  "ggplot2",
  "plotly",
  "caret",
  "glmnet",
  "MASS",
  "randomForest",
  "e1071",
  "factoextra",
  "cluster",
  "purrr",
  "ggpubr",
  "rpart",
  "doParallel"
))
```

### Knit R Markdown File

```r
rmarkdown::render("MA321 r code.Rmd")
```

---

## 📚 References

1. James, G., Witten, D., Hastie, T., Tibshirani, R. (2023). *An Introduction to Statistical Learning with Applications in R (2nd Edition)*.

2. Everitt, B., Hothorn, T. *An Introduction to Applied Multivariate Analysis with R*.

---

## 👥 Team Members

- Aida A. M. Arouri
- Melek Kuru
- Omar Ijaz
- Sham Lalwani
- Meghana Dhongadi Ashoka

### Supervisor

**Dr. Berthold Lausen**

University of Essex

---

## 📄 License

This project is intended for academic and educational purposes.

---
⭐ If you found this project useful, consider giving the repository a star.
