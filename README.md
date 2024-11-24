# Cancer Type Classification Using Gene Expression Data

## 1. Problem Definition
### Objective
Develop machine learning models to classify cancer types (invasive vs. noninvasive) using gene expression data.

### Dataset
- **Source**: "Gene Expression Cancer" dataset.
- **Size**: 78 samples (patients) × 4948 genes.
- **Classes**: Invasive and Noninvasive cancer.

---

## 2. Data Collection
### Data Characteristics
- **Features**: Gene expression levels for 4948 genes.
- **Labels**: Binary (invasive or noninvasive cancer).

---

## 3. Data Preprocessing
### Steps
- **Missing Values**: Imputed 77 missing values with column means.
- **Scaling**: Normalized all features for uniform scaling.
- **Duplicates and Zero-Values**: Verified none were present.

---

## 4. Exploratory Data Analysis (EDA)
### Dimensionality Reduction
- **PCA**: Reduced data to 78 principal components, selecting the top 4 to capture most variance.
- **High-Variance Genes**: Applied t-tests to highlight genes differentiating cancer types.

---

## 5. Unsupervised Learning
### 5.1 K-means Clustering
- **Goal**: Cluster genes and patients based on expression patterns.
- **Results**:
  - Optimal clusters (genes): 6.
  - Clustering patients was ineffective due to high similarity.

### 5.2 Hierarchical Clustering
- **Goal**: Visualize gene clustering with dendrograms.
- **Results**:
  - Complete linkage with two clusters outperformed K-means.
  - Validated by silhouette scores.

---

## 6. Supervised Learning
### Models and Performance
1. **Logistic Regression**:
   - Regularization: L1 (Lasso).
   - **Accuracy**: 100%, **Sensitivity**: 100%, **Specificity**: 100%.

2. **Decision Tree**:
   - **Accuracy**: 100%, **Sensitivity**: 100%, **Specificity**: 100%.

3. **Linear Discriminant Analysis (LDA)**:
   - **Accuracy**: 72%, **Sensitivity**: 67%, **Specificity**: 75%.

4. **Quadratic Discriminant Analysis (QDA)**:
   - **Accuracy**: 54%, **Sensitivity**: 50%, **Specificity**: 58%.

5. **K-Nearest Neighbors (K-NN)**:
   - Optimal k: 13.
   - **Accuracy**: 64%, **Sensitivity**: 33%, **Specificity**: 88%.

6. **Random Forest**:
   - **Accuracy**: 63%, **Sensitivity**: 50%, **Specificity**: 75%.

7. **Support Vector Machine (SVM)**:
   - **Accuracy**: 50%.

---

## 7. Model Comparison and Selection
### Best Models
- **Logistic Regression**: Perfect accuracy with Lasso regularization.
- **Decision Tree**: Perfect accuracy and interpretability.

### Insights
- Logistic regression and decision trees were the most reliable models, achieving perfect classification performance.

---

## 8. Conclusion
### Key Findings
- Logistic Regression and Decision Trees effectively classify invasive vs. noninvasive cancer types.
- Both models achieved 100% accuracy, sensitivity, and specificity, critical for medical data classification.

---

## 9. Recommendations
1. **Supervised Learning**: Prefer logistic regression and decision trees for labeled gene expression data.
2. **Feature Selection**: Focus on identifying significant genes for more interpretable models.

---

## 10. Future Work
1. **Feature Selection**: Use advanced methods to pinpoint key genes.
2. **Deep Learning**: Explore neural networks for larger, more complex datasets.
3. **Dataset Expansion**: Increase the sample size to validate model robustness.

---
