# CIFAR-10 Classification using CNN
## Introduction
CIFAR-10 is a standard dataset used in computer vision and deep learning for image classification tasks. It consists of 60,000 32x32 colored images divided into 10 classes, with 6,000 images per class. It is a well-studied benchmark for evaluating and comparing image classification algorithms as well as a good starting point for beginners to practice building and training CNNs. 
![tensorflow-keras-cnn-cifar10-architecture](https://github.com/galax19ksh/CIFAR-10-Classification/assets/112553872/1fa281b7-c0c7-4be7-9f57-35f74b86fcce)

* 60,000 small images (32x32 pixels)
* 10 classes (Airplane, Automobile, Bird, Cat, Deer, Dog, Frog, Horse, Ship, Truck)
* 50,000 training images and 10,000 test images
## Platform
Google Colab (T4 GPU)
## Libraries/ Tools
`numpy`, `matplotlib`, `tensorflow`, `keras`

## Preprocessing
* Normalized images into ranges [0,1]
* Implemented one hot label encoding on the target class.
* Training configuration parameters are defined and organised using python dataclasses
## CNN Model Implementation
![image](https://github.com/galax19ksh/CIFAR-10-Classification/assets/112553872/d77eed9c-c24e-4b29-a974-333583bdcd20)
![image](https://github.com/galax19ksh/CIFAR-10-Classification/assets/112553872/43c05285-12bc-4c1e-a123-a454759f5e94)

* Build/Define a network model using `sequential()` and `.add()` methods
* Compile the model with `model.compile()`
* Train the model with `model.fit()`
* Evaluate model performance.

** The model is facing overfitting problem (Compare the training and validation performance). So need regularisation.
## Dropout Model
![image](https://github.com/galax19ksh/CIFAR-10-Classification/assets/112553872/f3061dca-2f0c-44c6-97a0-4051cd37c5b2)
![image](https://github.com/galax19ksh/CIFAR-10-Classification/assets/112553872/b3d506ca-f8f0-4a47-8126-ee9aedfb1ba9)

* Rebuilt the model with `dropout`.
* On evaluation, we notice the performance on validation data are improved (closely aligned with training one). 
* Test Accuracy: 79%


*Original Model*
![image](https://github.com/galax19ksh/CIFAR-10-Classification/assets/112553872/e9885a29-c623-49c7-804b-d3142e30b2a4)
*Dropout Model*
![image](https://github.com/galax19ksh/CIFAR-10-Classification/assets/112553872/5ca1dc7d-60e9-4718-a6a7-6931f3cc4535)

## Prediction and Evaluation
* Now save the model and predict on the test data.
* Test Accuracy on unseen: 83%
![image](https://github.com/galax19ksh/CIFAR-10-Classification/assets/112553872/7c15ec03-57a7-4458-8eff-91aa6d3bc4c6)

* Confusion Matrix as heatmap is plotted below:
  ![image](https://github.com/galax19ksh/CIFAR-10-Classification/assets/112553872/bc16ab18-26d4-41be-b1b2-cbb1c6e986b2)
