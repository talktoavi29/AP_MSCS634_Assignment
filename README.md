# MSCS_634_Lab_6
# Advanced Big Data and Data Mining

# Overview

This lab explores association rule mining using the Apriori and FP-Growth algorithms applied to the Online Retail Dataset from the UCI Machine Learning Repository. The objective is to identify frequent itemsets in transactional data, generate meaningful association rules, and compare the performance and output of both algorithms.

The following techniques were implemented and evaluated:

- Apriori Algorithm
- FP-Growth Algorithm

Association rules were evaluated using:
- Support
- Confidence
- Lift

Visualizations including bar plots, heatmaps, and scatter plots were created using Seaborn to interpret the mined patterns and insights.

# Dataset Description

The Online Retail Dataset contains 541,909 transaction records from a UK-based online retailer covering the period December 2010 to December 2011. Each record includes an invoice number, product description, quantity, unit price, customer ID, and country.

After cleaning (removing cancelled orders, missing values, and zero-quantity rows) and filtering to UK-only transactions, the data was converted into a one-hot encoded basket format where each row represents a transaction and each column represents whether an item was purchased.

# Data Exploration

Checked dataset dimensions and summary statistics.
Removed cancelled orders, missing descriptions, and invalid quantities.
Visualized the top 20 most frequently purchased items using a Seaborn barplot.
Created an item co-occurrence heatmap for the top 15 items to identify strong pairwise associations.

# Frequent Itemset Mining Using Apriori

Applied the Apriori algorithm with min_support=0.03 to identify frequent itemsets.
Visualized the top 15 frequent itemsets by support value using a Seaborn barplot.

Note: Apriori works by generating candidate itemsets level by level and pruning those below the support threshold at each pass through the dataset.

# Frequent Itemset Mining Using FP-Growth

Applied the FP-Growth algorithm with the same min_support=0.03 threshold.
Visualized the top 15 frequent itemsets by support value using a Seaborn barplot.

Both algorithms produced identical frequent itemsets, confirming consistent results. FP-Growth was faster because it compresses the dataset into an FP-tree and mines it directly without generating candidate itemsets at each step.

# Generating and Analyzing Association Rules

Generated association rules from both algorithms using min_confidence=0.5.
Rules were analyzed using support, confidence, and lift metrics.
Visualized confidence vs. lift using scatter plots for both Apriori and FP-Growth results.
Created a support vs. confidence scatter plot with lift encoded as point size to identify the strongest rules.

Rules with lift values significantly greater than 1.0 indicate genuine associations rather than coincidental co-purchases.

# Algorithm Comparison

| Metric           | Apriori | FP-Growth |
|--------          |---------|-----------|
| Itemsets Found   | Same    | Same      |
| Rules Generated  | Same    | Same      |
| Speed            | Slower  | Faster    |

FP-Growth was faster because it avoids the repeated database scans that Apriori requires, instead building a compact FP-tree structure in memory.

# Key Insights

- Both algorithms found the same frequent itemsets and generated identical association rules.
- Items like different color variations of the same product showed strong association rules with high lift values.
- High-lift rules (lift >> 1.0) indicate genuine buying patterns rather than coincidental co-purchases.
- FP-Growth scales better for larger datasets due to its compressed tree-based approach.
- The Online Retail Dataset contains many low-frequency items, making the choice of min_support threshold critical.

# Challenges & Decisions

- The full dataset was too large for one-hot encoding, so transactions were filtered to UK-only to keep the basket matrix manageable in memory.
- Finding the right min_support threshold required experimentation — too low produced thousands of itemsets, too high produced none.
- Had to install the mlxtend library separately since it is not included in Google Colab by default.
- Some item descriptions contained leading/trailing whitespace which caused duplicate entries until cleaned.

# Conclusion

This lab demonstrates how association rule mining can uncover hidden purchasing patterns in transactional data. Both Apriori and FP-Growth are effective tools for this task, producing identical results but with different computational efficiency. FP-Growth is the better choice for larger datasets due to its speed advantage.

Key takeaways:
- Association rule mining reveals item relationships that are not obvious from raw transaction data.
- Support, confidence, and lift provide complementary views of rule quality.
- FP-Growth outperforms Apriori in speed, especially as dataset size grows.
- Proper data cleaning and threshold selection are critical for meaningful results.

# Files
- `Lab6_Association_Rules.ipynb` - Jupyter notebook with all code, visualizations, and analysis
- `README.md` - This file
