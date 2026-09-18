README – Deep Learning Lab Experiment 5
Effect of Initialization, Regularization, Optimization and Transfer Learning on CNN Performance
Course: CS3807 Deep Learning Laboratory, Shiv Nadar University Chennai

OBJECTIVE
Study weight initialization, regularization, optimization algorithms, CNN hyperparameters, transfer learning, fine-tuning and 5-fold cross-validation using MobileNetV2 on Oxford-IIIT Pet.

DATASET
Oxford-IIIT Pet: 37 cat/dog breeds, RGB images resized to 224×224×3. Train = 3680, Test = 3669. Normalized for pretrained models. Test set kept untouched during hyperparameter selection.

METHOD
MobileNetV2 used for all studies. “From scratch” means random weights; “transfer learning/fine-tuning” uses ImageNet weights. BatchNorm studies clone MobileNetV2 replacing BN with identity.

KEY EXPERIMENTS AND RESULTS
Weight Initialization: Zero, Random Normal, Xavier, He. He best validation accuracy = 0.1236; Xavier = 0.1101; Random Normal = 0.1101; Zero = 0.0163 (chance). Zero fails due to symmetry.

Regularization: No Reg, L2, Dropout, BatchNorm. BatchNorm best validation accuracy = 0.1712; No Reg = 0.1413 (overfits); L2 = 0.1223; Dropout 0.5 = 0.1372.

BatchNorm: Example x=[2,4,6,8], mean=5, var=5, normalized=[-1.342,-0.447,0.447,1.342]. BN stabilizes and accelerates convergence.

Optimizers: SGD, Momentum, RMSProp, Adam. Adam best validation accuracy = 0.1644; RMSProp = 0.1535; Momentum = 0.1087; SGD = 0.0543.

Hyperparameters: LR 10^-3 better than 10^-4. Batch 16 best. Dropout 0.25 optimal.

Transfer Learning: Feature extraction reached validation accuracy 0.9212. Fine-tuning with LR 10^-5 reached 0.8302. Extended sweep: LR 10^-4 + partial unfreeze best = 0.9090; frozen base = 0.8560; LR 10^-5 frozen base = 0.1318 (underfits).

5-Fold Cross-Validation: Configurations C1–C4. C1 best mean = 0.1223 ± 0.0146; C3 smallest SD = 0.0085 but underfits. Final selected model = C1: MobileNetV2 from scratch, He init, BatchNorm, Dropout 0.25, LR 10^-3. Test accuracy = 0.1284; Precision = 0.1377; Recall = 0.1284; F1 = 0.1125; Params = 2,305,381; Training time = 251.8 s. Fine-tuned MobileNetV2 (LR 10^-4, partial unfreeze, val 0.9090) is promising but not final because full CV + test sequence not completed.

CONCLUSION
CNN performance strongly depends on initialization, regularization, optimizer and hyperparameters. He, BatchNorm and Adam gave best from-scratch results. From-scratch MobileNetV2 struggles on 37 fine-grained breeds. Transfer learning and fine-tuning provide massive gains. 5-fold CV selected C1 as stable final model.

REFERENCES
Goodfellow et al., Deep Learning; Ioffe & Szegedy, Batch Normalization; Sandler et al., MobileNetV2; Parkhi et al., Oxford-IIIT Pet; TensorFlow/Keras Documentation.

