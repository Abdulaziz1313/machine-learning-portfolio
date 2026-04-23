# Neural Networks Log

**Name:** Abdulaziz Aloufi  
**Student ID:** C00266252  
**Module:** Data Science & Machine Learning 2  

## Notebook / Topic
`NeuralNetworks.ipynb` – Artificial Neural Network classification

## Purpose
This notebook implements an Artificial Neural Network (ANN) as one of the main semester 2 machine learning topics. The aim was to predict student performance category using AI usage and academic-related features.

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
- trained an initial neural network model
- evaluated the model using:
  - accuracy
  - classification report
  - confusion matrix
- compared multiple hidden layer settings
- selected the best-performing network structure
- trained and evaluated the final model
- plotted the training loss curve

## Changes / Alterations Made
During development, I made the following changes:

- reused the semester 2 dataset from the previous notebooks for consistency
- selected `performance_category` as a 3-class target
- filled missing categorical values with `"Unknown"`
- scaled the features because neural networks train better with scaled input
- compared multiple hidden layer settings instead of using only one network structure

## Practical Impact of Changes
These changes improved the notebook in the following ways:

- using a consistent dataset makes comparison across notebooks easier
- filling missing values allowed all rows to remain in the dataset
- scaling improved model training
- comparing different hidden layer settings made the final network choice more evidence-based
- plotting the loss curve gave a better view of how the model learned over time

## Results
- initial model accuracy with `(50,)`: **0.8169**
- architecture comparison results:
  - `(20,)`: **0.8331**
  - `(50,)`: **0.8169**
  - `(100,)`: **0.8031**
  - `(50, 25)`: **0.7850**
  - `(100, 50)`: **0.7963**
- best architecture: **(20,)**
- final model accuracy: **0.8331**

The final model performed best on the `Medium` and `Low` classes and less well on the `High` class, which is likely influenced by class imbalance.

## Analysis / Reflection
This notebook gave me a neural network implementation for the semester 2 portfolio. It was useful because it moved the portfolio beyond classic machine learning methods like KNN and SVM and into neural-network-based learning.

The results also showed that larger models do not always perform better. In this case, the smaller architecture `(20,)` achieved the best result among the settings I tested.

Some runs produced a convergence warning at 500 iterations, which suggests that more tuning could improve the model further.

## Next Steps
Before the final submission, I plan to:

- test whether increasing `max_iter` improves convergence
- refine the written interpretation of the results
- improve notebook presentation where needed