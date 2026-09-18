README – Deep Learning Lab Experiment 3
Convolutional Neural Networks for Image Classification
Course: CS3807 Deep Learning Laboratory
Program: B.Tech AI & DS, Semester V
Shiv Nadar University Chennai, AY 2026–27

OBJECTIVE
Understand CNN principles by implementing convolution, pooling, feature-map visualization, and image classification using TensorFlow/Keras.

DATASET
CIFAR-10: 50,000 training images, 10,000 test images, 10 classes, image size 32×32×3. Perfectly balanced with 5,000 samples per class.

METHOD

Load CIFAR-10; display sample images, dataset dimensions, and class distribution.

Implement convolution layer; compare 3×3, 5×5, and 7×7 kernels.

Study stride 1/2 and padding Same/Valid; compute output sizes using N_out = ((N − F + 2P)/S) + 1.

Visualize at least 8 feature maps after first Conv2D layer.

Compare Max Pooling and Average Pooling (2×2, stride 2).

Build CNN: Input → Conv → ReLU → MaxPool → Conv → ReLU → MaxPool → Flatten → Dense → Softmax.

Train with Adam, batch size 32, max 20 epochs, early stopping patience 5 with restore best weights.

Evaluate Accuracy, Precision, Recall, F1-score, Confusion Matrix, Classification Report.

Additional: ReLU vs Sigmoid, filter count 16/32/64, all 10 kernels applied to one image.

KEY RESULTS

Kernel size: Same padding + stride 1 keeps 32×32. Larger kernels capture broader context but use more parameters.

Stride/padding: S1+Same = 32×32; S2+Same = 16×16; S1+Valid = 30×30; S2+Valid = 15×15.

Feature maps: 8 filters learn distinct low-level features such as edges, blobs, and colours.

Max vs Average Pooling: both reduce 32×32 to 16×16. Max val acc ≈ 0.687; Average ≈ 0.691. Max converges faster.

ReLU vs Sigmoid: ReLU reaches ≈ 0.71 validation accuracy; Sigmoid ≈ 0.62. ReLU avoids vanishing gradients.

Filter count: 16 → 0.6744; 32 → 0.7132; 64 → 0.7052. Best at 32; 64 overfits.

CNN training: training accuracy ≈ 0.83, validation accuracy plateaus near 0.70; overfitting observed. Early stopping stopped at epoch 9.

Confusion matrix is strongly diagonal. Main confusions: cat ↔ dog, deer ↔ horse. Truck, ship, automobile are well separated.

Parameter calculation: Conv2D(16, 3×3, RGB) = 448 params; Conv2D(64, 3×3, RGB) = 1,792 params.

MANDATORY PLOTS
Sample images, class distribution, kernel-size effect, stride/padding output sizes, feature maps, max vs average pooling, training/validation accuracy, training/validation loss, confusion matrix, ReLU vs Sigmoid, filter-count effect, all kernels applied.

CONCLUSION
CNNs exploit local connectivity, weight sharing, and hierarchical feature learning, giving fewer parameters than MLPs. The model achieved about 70% validation accuracy on CIFAR-10, with overfitting after a few epochs. ReLU, max pooling, and 32 filters gave the best balance in these experiments. Early stopping and further regularization would improve generalization.

REFERENCES
Goodfellow et al., Deep Learning; Bishop, Pattern Recognition and Machine Learning; Haykin, Neural Networks and Learning Machines; TensorFlow Documentation; CIFAR-10 Dataset Documentation.
