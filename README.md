# AP_MSCS634_Assignment

Advanced Big Data and Data Mining
MSCS_634_Lab_3
Clustering Analysis Using K-Means and K-Medoids Algorithms

# Purpose of the Lab

The objective of this lab is to explore and compare two clustering techniques—K-Means and K-Medoids—using the Wine dataset from the sklearn Python library. The lab demonstrates how clustering algorithms group unlabeled data and how evaluation metrics such as Silhouette Score and Adjusted Rand Index (ARI) can be used to assess clustering quality and agreement with ground-truth class labels.

# Dataset

The Wine dataset contains chemical analysis results of wines derived from three different cultivars.
Total samples: 178
Features: 13 numeric attributes
Classes: 3 wine categories
All features were standardized using z-score normalization before applying clustering algorithms.

# Algorithms Implemented

K-Means Clustering (k = 3)
K-Medoids Clustering (k = 3, PAM method)

# Evaluation Metrics

Two metrics were used to evaluate clustering performance:
Silhouette Score – Measures how well-separated and compact clusters are.
Adjusted Rand Index (ARI) – Measures similarity between predicted cluster labels and true class labels.

# Results
Algorithm	Silhouette Score	Adjusted Rand Index (ARI)
K-Means	      0.2849	                 0.8975
K-Medoids	  0.2676                 	 0.7411

# Key Insights

K-Means produced slightly better-defined clusters based on Silhouette Score.
K-Means achieved a much higher ARI, indicating strong agreement with the true wine classes.
K-Medoids performed reasonably well but showed lower alignment with ground truth.

# Observations

The Wine dataset consists primarily of continuous numeric features and forms relatively compact clusters. Because K-Means uses centroids based on mean values, it is well-suited for this type of data. K-Medoids, which selects actual data points as cluster centers, is more robust to outliers but did not outperform K-Means for this dataset.

# When to Use Each Algorithm

K-Means
Best for numeric, well-scaled data.
Performs well when clusters are compact and spherical.
K-Medoids
Preferred when datasets contain outliers.
Useful when cluster centers must correspond to real data points.

# Challenges

Compatibility issues occurred with K-Medoids from sklearn-extra due to NumPy 2.x.
The issue was resolved by using the pyclustering library for K-Medoids implementation.

# Files in Repository

Lab3.ipynb – Jupyter Notebook containing full implementation.
README.md – Lab overview and findings.

# Conclusion

This lab demonstrates how different clustering algorithms behave on the same dataset and highlights the importance of selecting an appropriate method based on data characteristics. K-Means proved to be the better choice for the Wine dataset, while K-Medoids remains valuable in scenarios involving noise or outliers.