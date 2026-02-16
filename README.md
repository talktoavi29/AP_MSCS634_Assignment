# AP_MSCS634_Assignment
Advanced Big Data and Data Mining
# MSCS 634 – Lab 2: Classification Using KNN and RNN Algorithms

## Purpose
The purpose of this lab is to explore and compare the performance of K-Nearest Neighbors (KNN) and Radius Neighbors (RNN) classifiers using the Wine dataset from the sklearn library. The lab demonstrates how model parameters affect classification accuracy and helps identify suitable values for optimal performance.

## Dataset
The Wine dataset contains chemical analysis results of wines from three different classes. Each instance includes multiple numerical features describing chemical properties and a class label.

## Methodology
- Loaded the Wine dataset from sklearn.
- Performed basic exploration and examined class distribution.
- Split data into 80% training and 20% testing sets.
- Implemented KNN using k values: 1, 5, 11, 15, and 21.
- Implemented RNN using radius values: 350, 400, 450, 500, 550, and 600.
- Recorded accuracy for each parameter setting.
- Visualized accuracy trends using line plots.

## Key Insights
- KNN accuracy varies with different k values, showing sensitivity to parameter selection.
- RNN accuracy remains relatively stable across radius values.
- KNN achieved slightly higher accuracy than RNN for this dataset.
- Smaller radius values performed marginally better for RNN.

## Challenges and Decisions
Selecting appropriate parameter ranges required experimentation. Default distance metrics were used to maintain consistency. No additional preprocessing was required since the dataset is clean and well-structured.

## Conclusion
This lab demonstrates how parameter tuning influences nearest-neighbor classifiers and highlights practical differences between KNN and RNN. Understanding these behaviors is essential for selecting appropriate models in real-world classification tasks.