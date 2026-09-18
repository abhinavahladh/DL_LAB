README – Deep Learning Lab Experiment 4
Deep CNN Architectures and Transfer Learning
Name: V Abhinav Ahladh | Roll No: 24011101124 | Section: AIDS B | Date: August 30, 2026
Course: CS3807 Deep Learning Laboratory, Shiv Nadar University Chennai

OBJECTIVE
Study the evolution of deep CNN architectures (LeNet-5, AlexNet, VGG16, GoogleNet, ResNet), understand transfer learning, fine-tune pretrained models, and compare classification performance on CIFAR-10.

DATASET
CIFAR-10: 50,000 training images, 10,000 test images, 10 classes, image size 32×32×3. Classes: airplane, automobile, bird, cat, deer, dog, frog, horse, ship, truck.

METHOD

Load and normalize CIFAR-10; display samples and dimensions.

Transfer learning: load pretrained ImageNet weights (VGG16, ResNet50, MobileNetV2), remove classifier, freeze convolutional base, add Global Average Pooling, Dense (ReLU), and Softmax output.

Train with Adam (lr=0.001), batch size 32, 10–20 epochs, categorical crossentropy, early stopping.

Fine-tune: unfreeze last convolution block, train 5–10 more epochs with lower learning rate.

Evaluate: accuracy, precision, recall, F1-score, confusion matrix, classification report.

Additional experiments: Adam vs SGD, learning rate, batch size, epochs, frozen vs fine-tuned layers.

RESULTS
Best model: VGG16 with test accuracy 71.07%.
MobileNetV2: 55.16%. ResNet50: 11.01% (underperformed due to small input size).
VGG16 confusion matrix shows good separation for automobile and ship, but confuses cat/dog and bird/airplane.
Fine-tuning improved VGG16 accuracy from ~60% to ~71%.
Adam outperformed SGD (71% vs ~65%).
Learning rate 0.001 for initial training; 0.0001 for fine-tuning.
Batch size 32 was optimal.

KEY FINDINGS

VGG16 uses only 3×3 filters for parameter efficiency and deeper feature learning.

AlexNet introduced ReLU, dropout, GPU training, and data augmentation.

GoogleNet’s Inception module extracts multi-scale features with fewer parameters.

ResNet uses skip connections to solve vanishing gradients and enable very deep networks.

Transfer learning converges faster because pretrained weights provide good initialization and general features.

Fine-tuning adapts pretrained features to the target domain and improves accuracy.

Dilated convolution expands receptive field without increasing parameters; transpose convolution upsamples spatial dimensions.

CONCLUSION
Transfer learning with VGG16 achieved the highest accuracy (71.07%) on CIFAR-10. Fine-tuning significantly improved performance. Model choice must balance accuracy, parameter count, and computational cost. ResNet50’s poor performance highlights the importance of matching input size to architecture design.

REFERENCES
LeCun et al., 1998; Krizhevsky et al., 2012; Simonyan & Zisserman, 2015; Szegedy et al., 2015; He et al., 2016; Goodfellow et al., 2016; TensorFlow/Keras Documentation.
