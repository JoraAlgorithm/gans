# Simplest_Gan.ipynb
## Objective

The code is designed to implement the generator part of a Generative Adversarial Network (GAN). The primary goal is to generate synthetic data samples that resemble a target distribution, with a focus on generating MNIST-like images.

## Generator Architecture

- **Input:** The generator takes a random noise vector of size 100 as input.
- **Output:** The output of the generator has the same dimensionality as MNIST images, which is 28x28 pixels.

# Generator and Discriminator Architectures

### Model Architecture

The Generator consists of multiple fully connected (linear) layers, followed by LeakyReLU activations and a final Tanh activation.

- Linear Layer 1: Input size 100, output size 256 with LeakyReLU activation.
- Linear Layer 2: Input size 256, output size 512 with LeakyReLU activation.
- Linear Layer 3: Input size 512, output size 1024 with LeakyReLU activation.
- Linear Layer 4: Input size 1024, output size 784 with Tanh activation.

## Discriminator Architecture

The Discriminator is designed to distinguish between real and generated data samples in GANs.

- Input: The discriminator takes an input of dimension 784, representing an image.

### Model Architecture

The Discriminator consists of multiple fully connected (linear) layers, followed by LeakyReLU activations and a final Sigmoid activation.

- Linear Layer 1: Input size 784, output size 1024 with LeakyReLU activation.
- Linear Layer 2: Input size 1024, output size 512 with LeakyReLU activation.
- Linear Layer 3: Input size 512, output size 256 with LeakyReLU activation.
- Linear Layer 4: Input size 256, output size 1 with Sigmoid activation.

## Forward Method

The `forward` method defines the forward pass of the generator. It sequentially passes the input noise vector through the layers defined in the model architecture.

## GAN Training

GAN training involves both a generator and a discriminator network. The generator aims to generate realistic samples to fool the discriminator, while the discriminator learns to distinguish real from fake samples. Appropriate loss functions (e.g., adversarial loss) and optimizers (e.g., Adam) are used for training.

## Normalization and Activation

- Batch normalization is applied to stabilize training and improve convergence.
- LeakyReLU activation functions are used in hidden layers to introduce non-linearity.
- The Tanh activation function in the output layer scales the generator's output to the desired output range.


## Dependencies

The code is dependent on the PyTorch deep learning framework.

## Hyperparameters

Hyperparameters like learning rates, batch sizes, and the number of training epochs are not specified in the provided code and would need to be set based on the specific use case.
