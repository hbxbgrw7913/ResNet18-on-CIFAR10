## CIFAR-10 Image Classification Project

This project aims to build a neural network to evaluate the CIFAR-10 dataset, which consists of 60,000 32x32 color images in 10 classes, with 6,000 images per class. The goal is to achieve an accuracy greater than 45% on the test set.

### Introduction

The CIFAR-10 dataset is a widely used benchmark for image classification tasks. Some notable benchmark results on this dataset include:

- 78.9% Accuracy | [Deep Belief Networks; Krizhevsky, 2010](https://www.cs.toronto.edu/~kriz/conv-cifar10-aug2010.pdf)
- 90.6% Accuracy | [Maxout Networks; Goodfellow et al., 2013](https://arxiv.org/pdf/1302.4389.pdf)
- 96.0% Accuracy | [Wide Residual Networks; Zagoruyko et al., 2016](https://arxiv.org/pdf/1605.07146.pdf)
- 99.0% Accuracy | [GPipe; Huang et al., 2018](https://arxiv.org/pdf/1811.06965.pdf)
- 98.5% Accuracy | [Rethinking Recurrent Neural Networks and other Improvements for ImageClassification; Nguyen et al., 2020](https://arxiv.org/pdf/2007.15161.pdf)

### Dataset

The CIFAR-10 dataset is loaded using the `torchvision.datasets.CIFAR10` class. The dataset is split into training and test sets, and data loaders are created for each set using `torch.utils.data.DataLoader`.

The following transformations are applied to the data:

**Training Transformations**:
- `RandomRotation(30)`: Randomly rotates the image by up to 30 degrees.
- `RandomResizedCrop(224)`: Randomly crops and resizes the image to 224x224 pixels.
- `RandomHorizontalFlip()`: Randomly flips the image horizontally.
- `ToTensor()`: Converts the image to a PyTorch tensor.
- `Normalize(mean, std)`: Normalizes the image using the provided mean and standard deviation values.

**Test Transformations**:
- `Resize(255)`: Resizes the image to 255x255 pixels.
- `CenterCrop(224)`: Crops the center 224x224 region from the image.
- `ToTensor()`: Converts the image to a PyTorch tensor.
- `Normalize(mean, std)`: Normalizes the image using the provided mean and standard deviation values.

### Usage

1. Clone the repository and navigate to the project directory.
2. Install the required dependencies (PyTorch, torchvision, etc.).
3. Run the Jupyter Notebook or Python script containing the code.
4. The code will load the CIFAR-10 dataset, apply the specified transformations, and create data loaders for training and testing.
5. You can then proceed to build and train your neural network model using the provided data loaders.

### Utilities

The provided code includes a `show5` function that displays the first five images from a given data loader along with their corresponding labels. This function can be useful for visualizing and exploring the dataset.

### Contributing

Contributions to this project are welcome. If you find any issues or have suggestions for improvements, please open an issue or submit a pull request.

### License

This project is licensed under the [MIT License](LICENSE).

### Acknowledgments

- The CIFAR-10 dataset is provided by the Canadian Institute for Advanced Research (CIFAR).
- The code utilizes the PyTorch library for building and training neural networks.
