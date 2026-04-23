# Deep Learning & Transformers Log

**Name:** Abdulaziz Aloufi  
**Student ID:** C00266252  
**Module:** Data Science & Machine Learning 2  

## Notebook / Topic
`DeepLearning_Transformers.ipynb` – Deep learning classification using TensorFlow/Keras

## Purpose
This notebook implements a deep learning model as part of the semester 2 topic "Deep Learning & Transformers". The aim was to predict student performance category using AI usage and academic-related features.

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
- converted the target labels into one-hot encoding
- built and trained an initial deep learning model
- evaluated the model using:
  - accuracy
  - classification report
  - confusion matrix
- compared multiple deep learning architectures
- plotted loss and accuracy curves

## Changes / Alterations Made
During development, I made the following changes:

- reused the same semester 2 dataset for consistency
- used TensorFlow/Keras instead of `MLPClassifier`
- converted targets to one-hot encoding for multi-class classification
- added dropout layers to reduce overfitting
- used early stopping to improve training control
- compared multiple deep learning architectures instead of using only one fixed model

## Practical Impact of Changes
These changes improved the notebook in the following ways:

- using TensorFlow/Keras made this notebook more distinct from the earlier neural network notebook
- one-hot encoding made the output suitable for softmax classification
- dropout reduced overfitting risk
- early stopping helped stop training when validation performance stopped improving
- architecture comparison made model selection more evidence-based
- loss and accuracy curves helped visualise the learning process

## Results
The initial deep learning model achieved the best overall result:

- initial model accuracy: **0.8406**

Its class-level performance was:
- High: precision **0.73**, recall **0.68**, f1-score **0.70**
- Low: precision **0.83**, recall **0.85**, f1-score **0.84**
- Medium: precision **0.86**, recall **0.86**, f1-score **0.86**

Architecture comparison results:
- `[32, 16]`: **0.7150**
- `[64, 32]`: **0.7669**
- `[128, 64]`: **0.8375**
- `[64, 32, 16]`: **0.7650**

The best alternative architecture tested was `[128, 64]`, but it did not outperform the initial model. A later retraining of `[128, 64]` produced a lower result, showing that deep learning training can vary between runs.

## Analysis / Reflection
This notebook provides the deep learning part of the semester 2 portfolio. It moves the work beyond classic machine learning and beyond the earlier simple ANN implementation.

Because the dataset is tabular rather than sequential, a dense deep learning model was more suitable than a transformer model in this case. Transformers are generally more appropriate for text, sequence, or attention-based tasks.

The notebook also showed that larger architectures do not always improve results, and that performance can vary between training runs.

## Next Steps
Before the final submission, I plan to:

- refine the interpretation of the results
- improve the written explanation of why deep learning was used here
- consider setting fixed seeds more carefully to reduce variation between runs
