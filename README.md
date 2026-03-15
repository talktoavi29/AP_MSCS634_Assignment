# MSCS_634_Lab_5
# Advanced Big Data and Data Mining

# Overview

This lab explores two clustering algorithms — Agglomerative Hierarchical Clustering and DBSCAN — applied to the Wine dataset from sklearn.datasets. The objective is to understand how each algorithm behaves under different parameter settings, evaluate clustering quality using standard metrics, and compare their strengths and weaknesses on the same dataset.

The following techniques were implemented and evaluated:

- Agglomerative Hierarchical Clustering (Ward Linkage)
- DBSCAN (Density-Based Spatial Clustering of Applications with Noise)

Clustering quality was evaluated using:
- Silhouette Score
- Homogeneity Score
- Completeness Score

Visualizations including scatter plots and a dendrogram were created to interpret clustering behavior.

# Dataset Description

The Wine dataset contains 178 samples and 13 chemical analysis features including:
Alcohol, Malic Acid, Ash, Alcalinity of Ash, Magnesium, Total Phenols, Flavanoids, Nonflavanoid Phenols, Proanthocyanins, Color Intensity, Hue, OD280/OD315 of Diluted Wines, and Proline.

The dataset represents 3 wine cultivars (classes). All features are numeric and there are no missing values. Features were standardized using StandardScaler before clustering since the features have different scales and units.

# Data Exploration

Checked dataset dimensions and summary statistics using .head(), .info(), and .describe().
Verified absence of missing values.
Confirmed 3 true classes with a reasonable distribution across the dataset.

# Hierarchical Clustering

Agglomerative Hierarchical Clustering with Ward linkage was applied with different values of n_clusters (2, 3, 4, 5).

Performance (n_clusters=3):
- Silhouette Score: 0.2774
- Homogeneity Score: 0.7904

n_clusters=3 aligned best with the known 3 wine cultivars. The dendrogram confirmed this by showing large merge distances between the final three groupings, with a natural cut point around distance 25.

Scatter plots for each n_clusters value were generated to visualize how cluster assignments change with different settings.

# DBSCAN Clustering

DBSCAN was applied with several combinations of eps and min_samples to observe their effect on cluster formation.

Parameters tested included eps values of 1.5, 2.0, 2.5, 3.0, 3.5 and min_samples values of 3, 5, 7, 10.

Key observations:
- Small eps values (1.5) produced many noise points and fragmented clusters.
- Large eps values (3.0+) merged most points into a single cluster.
- A moderate combination provided the best balance of cluster count and noise detection.

Evaluation metrics (Silhouette, Homogeneity, Completeness) were computed for the best parameter combination. Noise points (label = -1) were filtered out before computing Homogeneity and Completeness.

Scatter plots highlighting noise points in red were generated for four different parameter combinations.

# Algorithm Comparison

| Algorithm | Clusters | Noise Points | Silhouette |
|-----------|----------|-------------|------------|
| Hierarchical (n=3) | 3 | 0 | 0.2774 |
| DBSCAN (best params) | varies | varies | varies |

Note: Exact values depend on the run. Hierarchical clustering consistently outperformed DBSCAN on this dataset.

Best Algorithm: Hierarchical Clustering (Ward, n=3)

# Key Insights

- Hierarchical clustering with Ward linkage performed well on the Wine dataset due to its compact, globular cluster structure.
- The dendrogram provided useful visual guidance for selecting the number of clusters.
- DBSCAN required significant parameter tuning and was sensitive to eps in particular.
- DBSCAN's noise detection is a useful feature but did not provide a major advantage on this clean dataset.
- The Wine dataset's 13 features create a high-dimensional space that makes density-based methods less effective without dimensionality reduction.
- Standardization was essential — without it, features with larger ranges dominated distance calculations.

# Challenges & Decisions

- Finding the right DBSCAN parameters required trying multiple combinations manually.
- Had to filter out noise-labeled points before computing Homogeneity and Completeness scores for DBSCAN.
- Scatter plots only show the first two features, which may not fully represent the 13-dimensional cluster structure.
- Chose Ward linkage for hierarchical clustering because it minimizes within-cluster variance and works well with globular clusters.

# Conclusion

This lab demonstrates how different clustering algorithms handle the same dataset differently. Hierarchical clustering offered a more straightforward and effective approach for the Wine dataset, while DBSCAN provided useful noise detection capabilities but required more tuning effort.

Key takeaways:
- Algorithm selection should match data characteristics.
- Hierarchical methods work well for compact clusters with explorable cluster counts.
- DBSCAN excels with irregular cluster shapes and noisy data but may underperform in high-dimensional spaces.
- Dimensionality reduction (e.g., PCA) could improve DBSCAN performance and is worth exploring in future work.

# Files
- `Lab5_Clustering.ipynb` - Jupyter notebook with all code, visualizations, and analysis
- `readme.md` - This file
