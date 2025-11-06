Lab 2: Classification Using KNN and RNN Algorithms


Overview

This lab focuses on implementing and comparing two classification algorithms — K-Nearest Neighbors (KNN) and Radius Neighbors (RNN) — using the Wine Dataset from the sklearn library.
The dataset contains 178 samples, 13 chemical features, and 3 distinct classes of wine.
The objective is to analyze how varying hyperparameters (number of neighbors for KNN and radius size for RNN) influence model accuracy and to visualize the comparison between the two algorithms.


Objectives

To understand the working principles of KNN and RNN classifiers.

To evaluate model performance by tuning hyperparameters.

To compare algorithmic efficiency and discuss when each model performs best.



Steps Performed

Step 1: Load and Prepare the Dataset

Loaded the Wine dataset using sklearn.datasets.load_wine().

Conducted basic exploration:

Number of samples: 178

Number of features: 13

Number of classes: 3

Split the data into 80% training (142 samples) and 20% testing (36 samples) sets.

Checked class distribution to ensure balanced representation across categories.


Step 2: Implement K-Nearest Neighbors (KNN)

Trained a KNN classifier with different k values: [1, 5, 11, 15, 21].

Evaluated accuracy on the test set for each k.

Observation:
Accuracy improved as k increased, stabilizing around 80.56%, indicating that moderate neighborhood sizes yield more reliable classification.


Step 3: Implement Radius Neighbors (RNN)

Trained a Radius Neighbors Classifier with radius values: [350, 400, 450, 500, 550, 600].

Evaluated accuracy for each radius value.

Observation:
RNN accuracy declined as the radius increased, suggesting that smaller neighborhoods provide more discriminative classification boundaries for this dataset.


Step 4: Visualize and Compare Results

Created line plots for KNN (accuracy vs. k) and RNN (accuracy vs. radius).

Visualization clearly showed that KNN outperformed RNN across all parameter settings.

Summary Statistics:

Best KNN Accuracy: 80.56% (k = 5)

Best RNN Accuracy: 72.22% (radius = 350)


Key Insights

KNN Performance:

Performed consistently well with accuracies above 77%.

Optimal neighborhood size was around k = 5, balancing bias and variance effectively.

RNN Performance:

Accuracy decreased as radius increased due to excessive inclusion of distant, less relevant points.

Works best with a smaller radius but was less stable than KNN.


Model Comparison:

KNN outperformed RNN by approximately 8% in accuracy.

KNN’s discrete neighborhood approach handled varying class densities better than the fixed-radius approach.


Challenges and Decisions

Radius Tuning: Selecting appropriate radius values was challenging due to dataset scaling.

No Neighbors Found Error: For small radius values, the model occasionally encountered empty neighborhood cases, requiring error handling.

Parameter Sensitivity: KNN required less fine-tuning compared to RNN, which was more sensitive to feature scaling and neighborhood density.



Conclusion

The K-Nearest Neighbors (KNN) algorithm achieved higher accuracy and stability compared to Radius Neighbors (RNN) on the Wine dataset.

KNN is generally preferable when dataset density varies across regions, while RNN may be suitable for uniformly distributed datasets with properly scaled features.
