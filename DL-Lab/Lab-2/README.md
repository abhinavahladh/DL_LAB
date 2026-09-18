README – Deep Learning Lab Experiment 2
Multi-Layer Perceptron (MLP) for Multi-Class Image Classification
Course: CS3807 Deep Learning Laboratory
Program: B.Tech AI & DS, Semester V
Shiv Nadar University Chennai, AY 2026–27

OBJECTIVE
Implement an MLP using TensorFlow/Keras on Fashion-MNIST for multi-class image classification. Learn image preprocessing, flattening, model construction, training, evaluation, and automated hyperparameter optimization.

DATASET
Fashion-MNIST: 60,000 training images, 10,000 test images, 10 classes, image size 28×28. Balanced dataset with ~6,000 samples per class.

METHOD

Load dataset and explore: sample images, class distribution.

Preprocess: flatten 28×28 to 784, normalize pixel values by /255, convert labels to one-hot.

Build baseline MLP: 784 → Dense(128, ReLU) → Dense(64, ReLU) → Dense(10, Softmax). Compile with Adam, categorical crossentropy, accuracy.

Train baseline: 20 epochs, batch size 32, validation split 0.2.

Evaluate baseline: accuracy, precision, recall, F1, confusion matrix.

Hyperparameter optimization: RandomizedSearchCV with 3-fold CV, 15 candidates. Search space: hidden layers 1–3, neurons 32–256, learning rate 0.1/0.01/0.001, batch size 16–128, epochs 10–30, optimizer SGD/Adam/RMSprop, activation ReLU/Tanh/Sigmoid, dropout 0.0/0.2/0.5.

Retrain optimized model and compare with baseline.

Generate mandatory plots: sample images, class distribution, accuracy/loss curves, confusion matrix, hyperparameter search results, baseline vs optimized comparison.

BASELINE RESULTS
Accuracy: 0.8809
Precision: 0.8837
Recall: 0.8809
F1-score: 0.8807
Confusion matrix shows confusion between visually similar classes (pullover vs coat, shirt vs T-shirt), but good performance on sandals and bags.

BEST HYPERPARAMETERS
Hidden Layers: 3
Hidden Neurons: 128
Learning Rate: 0.001
Batch Size: 16
Activation: tanh
Epochs: 20
Dropout: 0.0
Optimizer: Adam
CV Accuracy: 0.8797

OPTIMIZED MODEL RESULTS
Accuracy: 0.8729
Precision: 0.8740
Recall: 0.8729
F1-score: 0.8731

PLOTS AND INFERENCE
Training accuracy rises while validation plateaus around 88%, indicating overfitting. Validation loss increases after epoch 8. Optimized model shows similar pattern. Hyperparameter search shows deeper models with moderate neurons perform better; learning rate 0.001 is optimal. Baseline slightly outperforms optimized model.

DISCUSSION
Randomized Search was used for hyperparameter tuning. Best configuration used 3 hidden layers, 128 neurons, tanh activation, LR 0.001, batch 16, no dropout. Optimization did not improve over baseline; simpler baseline was already effective. Learning rate and number of layers had greatest impact. Grid Search is exhaustive but slow; Randomized Search is faster and finds good configurations.

RECOMMENDATION
Use the baseline MLP: 2 hidden layers (128, 64), ReLU, Adam, LR 0.001, batch 32. It is simple, fast, and achieves ~88% accuracy.

CONCLUSION
MLP achieved strong performance on Fashion-MNIST. Hyperparameter tuning did not always improve results. Baseline simplicity often beats overcomplication.

REFERENCES
Goodfellow et al., Deep Learning; Bishop, Pattern Recognition and Machine Learning; Haykin, Neural Networks and Learning Machines; Fashion-MNIST Dataset; TensorFlow/Keras Documentation.


