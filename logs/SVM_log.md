# SVM Log

**Name:** Abdulaziz Aloufi  
**Student ID:** C00266252  
**Module:** Data Science & Machine Learning 2  

## Notebook / Topic
`SVM.ipynb` – Support Vector Machine classification

## Purpose
This notebook implements Support Vector Machine (SVM) classification as one of the main semester 2 machine learning topics. The aim was to predict student performance category using AI usage and academic-related features.

## Work Completed
The following work has been completed:

- loaded the dataset about AI and student performance
- checked dataset structure and missing values
- filled missing values in `ai_tools_used` and `ai_usage_purpose` with `"Unknown"`
- selected `performance_category` as the target
- removed columns not suitable for prediction:
  - `student_id`
  - `final_score`
  - `passed`
- encoded categorical columns using `LabelEncoder`
- split the data into training and test sets
- scaled the features using `StandardScaler`
- trained an initial SVM classifier with the `rbf` kernel
- evaluated the model using:
  - accuracy
  - classification report
  - confusion matrix
- compared multiple kernels:
  - linear
  - rbf
  - poly
  - sigmoid
- selected the best-performing kernel
- trained and evaluated the final model

## Changes / Alterations Made
During development, I made the following changes:

- reused the semester 2 dataset from the previous notebooks for consistency
- selected `performance_category` as a 3-class target
- filled missing categorical values with `"Unknown"`
- scaled the features because SVM is sensitive to feature magnitudes
- compared multiple kernels instead of relying on one default kernel

## Practical Impact of Changes
These changes improved the notebook in the following ways:

- using a consistent dataset makes comparison across notebooks easier
- filling missing values allowed all rows to remain in the dataset
- scaling improved model training and stability
- comparing different kernels made the final model choice more evidence-based

## Results
- initial RBF kernel accuracy: **0.8413**
- kernel comparison results:
  - linear: **0.8450**
  - rbf: **0.8413**
  - poly: **0.8094**
  - sigmoid: **0.8363**
- best kernel: **linear**
- final model accuracy: **0.8450**

The model performed best on the `Medium` and `Low` classes and less well on the `High` class, which is likely affected by class imbalance.

## Analysis / Reflection
This notebook gave me a strong supervised learning example for the semester 2 portfolio. It was useful to compare SVM against KNN on the same dataset, and SVM achieved better overall performance.

The notebook also showed that kernel choice matters, even if the difference here was not huge, and that the linear kernel performed slightly better than the others.

## Next Steps
Before the final submission, I plan to:

- review whether tuning `C` or `gamma` would improve performance further
- refine the written interpretation of the results
- improve notebook presentation where needed