# KMeans Log

**Name:** Abdulaziz Aloufi  
**Student ID:** C00266252  
**Module:** Data Science & Machine Learning 2  

## Notebook / Topic
`KMeans.ipynb` – k-Means clustering

## Purpose
This notebook implements k-Means clustering as one of the main semester 2 machine learning topics. The aim was to group students into clusters based on AI usage and academic-related features.

## Work Completed
The following work has been completed:

- loaded the dataset about AI and student performance
- checked dataset structure and missing values
- filled missing values in `ai_tools_used` and `ai_usage_purpose` with `"Unknown"`
- removed columns not suitable for clustering:
  - `student_id`
  - `performance_category`
  - `passed`
  - `final_score`
- encoded categorical columns
- scaled the dataset using `StandardScaler`
- used the elbow method to inspect possible values of `k`
- trained a final k-Means model with `k = 3`
- assigned cluster labels to the data
- checked cluster sizes
- compared clusters with the real performance categories
- visualised clusters using PCA
- created a numeric summary of each cluster

## Changes / Alterations Made
During development, I made the following changes:

- reused the semester 2 dataset from the KNN notebook for consistency
- removed direct outcome columns from the clustering features
- encoded categorical features before scaling
- added feature scaling because k-Means is distance-based
- used the elbow method to guide the choice of `k`
- added PCA visualisation to make the clusters easier to interpret
- compared the unsupervised cluster labels with the known performance categories

## Practical Impact of Changes
These changes improved the notebook in the following ways:

- removing output-related columns made clustering more meaningful
- encoding categorical columns made the full dataset usable for clustering
- scaling improved the quality of the distance calculations
- PCA made the clusters easier to visualise
- comparing clusters with real labels helped evaluate whether the clusters were meaningful

## Results
- the elbow plot suggested that the strongest improvement happened at lower values of `k`
- `k = 3` was selected as a reasonable clustering solution
- cluster sizes were:
  - Cluster 0: 2509
  - Cluster 1: 2619
  - Cluster 2: 2872

When compared with `performance_category`, the clusters did not strongly separate the real `Low`, `Medium`, and `High` groups. All three clusters were still dominated by the `Medium` category.

The cluster summary also showed that:
- Cluster 0 and Cluster 1 had `uses_ai = 1.0`
- Cluster 2 had `uses_ai = 0.0`

This suggests that AI usage may be one of the strongest natural dividing points in the dataset.

## Analysis / Reflection
This notebook gave me a clear example of unsupervised learning in the semester 2 portfolio. Unlike KNN, k-Means does not use labels during training, so it was interesting to compare the discovered clusters with the real categories afterwards.

The results showed that the natural clusters in the data do not map strongly onto performance category, but they may still capture meaningful student behaviour patterns, especially around AI usage.

## Next Steps
Before the final submission, I plan to:

- improve the written interpretation of the cluster summaries
- test whether another value of `k` is worth discussing
- refine presentation and explanation in the notebook