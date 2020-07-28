# MADE Implementation and Experiments

Contains variants of the [Masked Autoencoder for Distribution Estimation (MADE)](https://arxiv.org/abs/1502.03509.pdf) for the MNIST digit dataset and a two-dimensional dataset, respectively.
A write up can be found at [the following link](dosssman.github.io/made/), and the Google Collab Notebooks can be found at [this location](https://drive.google.com/drive/folders/1faDEHMNQnUUrWkIyEr3Vru3Locwq5xng).

The MNIST digit dataset experiment is centered on a standard MADE architecture with continuous values in the [0,1.] range.
The two-dimensional dataset experiments are centered on a custom MADE architecture which allows for sampling discrete values as the output, namely by applying the masking to estimate a probability distribution over discrete variables, while maintain the autoregression property.
## Contents

### Datasets
- [binarized_mnist.npz (MNIST)](https://github.com/mgermain/MADE/releases/download/ICML2015/binarized_mnist.npz)
- distribution.npy (Two-dimensional vectors of discrete values)

### 1_MADE_MNIST.ipynb

MADE for MNIST. Allows for various network architecture, input and connectivity orderings parameterization, as well as sampling process.

### 2_0_TwoDimData_NaiveModel.ipynb

A baseline of a naive model which estimates the distribution of the two-dimensional dataset's elements.

### 2_1_TwoDimData_MADE_OneHot.ipynb

Best perfomaing MADE architecture modeling the elements of the two-dimensional dataset's elements.
This file leverages a one-hot encoding of the input vector, which seems to be the decisive factor in achieving a good results.

### 2_2_TwoDimData_MADE_NormToSoftmax.ipynb

MADE architecture that directly uses the two-dimensional data as input, without normalization.
Achieves the second best reconstruction performance after the one-hot vector variant.

### 2_3_TwoDimData_MADE_NormalizedInput.ipynb

MADE architecture that uses normalized two-dimensional data as input.
This achieves the worst performance of all the variants.
