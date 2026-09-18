Single Layer Perceptron for Binary Classification
Course: CS3807 Deep Learning Laboratory
Program: B.Tech AI & DS, Semester V
Shiv Nadar University Chennai, AY 2026–27

OBJECTIVE
Implement a Single Layer Perceptron from scratch for binary classification. Understand the perceptron learning algorithm, activation functions, training visualization, and performance evaluation on a real-world dataset.

DATASET
Banknote Authentication Dataset (UCI ML Repository).
Instances: 1372. Features: 4 (Variance, Skewness, Curtosis, Entropy).
Classes: 0 = Authentic, 1 = Forged. Missing values: None.

METHOD

Load data using Pandas; check shape, missing values, info, and statistics.

Perform EDA: histograms, correlation heatmap, scatter plot (Variance vs Skewness), boxplots.

Preprocess: normalize features with MinMaxScaler; split 80% train / 20% test (1097 / 275).

Implement Perceptron from scratch: weight/bias initialization, step activation, forward propagation, perceptron learning rule, error/weight/bias history.

Train with learning rate 0.01 and 20 epochs. Errors drop from 166 to about 31.

Evaluate using accuracy, precision, recall, F1-score, and confusion matrix.

Compare learning rates: 0.001, 0.01, 0.1.

Additional tasks: AND, OR, NOT, XOR gates; Step vs Sigmoid; effect of normalization.

KEY RESULTS
Accuracy: 0.9745
Precision: 0.9478
Recall: 1.0
F1-score: 0.9732
Confusion Matrix: TN=141, FP=7, FN=0, TP=127
Final Weights: [-0.1464, -0.1322, -0.1521, 0.0161]
Final Bias: 0.196

PLOTS AND INFERENCE
Histograms show skewed features and separated classes.
Heatmap shows no strong feature correlations.
Scatter plot shows classes are approximately linearly separable.
Weight and bias evolution show stable convergence.
Learning rate 0.01 is best; 0.1 is unstable, 0.001 is slow.
Confusion matrix shows very few misclassifications.
XOR does not converge because it is not linearly separable.
AND, OR, and NOT gates converge successfully.
Step activation is unsuitable for deep learning because it is non-differentiable.

CONCLUSION
The Single Layer Perceptron achieved about 97.45% accuracy on the Banknote Authentication dataset. It performs well for linearly separable data but fails on XOR. Learning rate 0.01 gave the best balance of speed and stability.

REFERENCES
Rosenblatt, 1958; Goodfellow et al., 2016; Bishop, 2006; Haykin, 2009; UCI Banknote Authentication Dataset; Scikit-learn Documentation.
