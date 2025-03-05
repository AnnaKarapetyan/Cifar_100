# CIFAR-100 Classification Project

## Dataset Overview

The CIFAR-100 dataset consists of 60,000 32x32 color images in 100 different classes. These classes are divided into:

- 100 fine classes (specific categories such as 'apple', 'dog', 'cat', etc.).
- 20 coarse classes (broader categories such as 'animals', 'vehicles', etc.).

There are 50,000 training images and 10,000 testing images.

## Project Overview

In this project, two approaches are explored for solving the CIFAR-100 classification task, each using different methods for handling coarse and fine classes.

### Approach 1 (Model 1):
The first approach uses a single deep learning model to directly predict one of the 100 fine-grained classes from the CIFAR-100 dataset. This model, referred to as **Model1**, is trained on the entire dataset with 100 fine-grained classes as output labels.

### Approach 2 (Model 2):
The second approach breaks the problem down into two parts. First, it predicts the coarse class (superclass) of an image, and then predicts the fine-grained class within that superclass. This approach is split into two models:
- **Model2_1**: A model that predicts the superclass (20 coarse classes).
- **Model2_2**: For each superclass, a smaller model predicts the fine-grained class within that superclass. Note that these smaller models are not included in the repository since they are small and easy to train.

The trained versions of **Model1** and **Model2_1** are provided in this repository. The smaller models (for each subclass) are not provided, as they are straightforward to train and were not included due to their simplicity.

## Tools Used

- **ImageDataGenerator (datagen)**: Used for real-time data augmentation during training (shifting, flipping, etc.).
- **TensorFlow & Keras**: For building, training, and evaluating deep learning models.
- **EarlyStopping**: A callback used to stop training early if validation accuracy doesn't improve.

## Requirements

- TensorFlow 2.x
- Keras
- NumPy
- Matplotlib
