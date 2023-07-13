# Variational Autoencoder (VAE) for Generating Faces

This project presents a Variational Autoencoder (VAE) trained on the CelebA dataset for 50 epochs. The model can generate novel images of faces, demonstrating impressive results. Two additional features are also provided: a function to display the distribution of the latent space variables and another to manipulate novel images by performing arithmetic in the latent space.

## Table of Contents

- [Background](#background)
- [Project Description](#project-description)
- [Results](#results)
- [Usage](#usage)
- [Future Work](#future-work)
- [Contributing](#contributing)
- [License](#license)

## Background

A Variational Autoencoder (VAE) is a type of generative model that's excellent for learning a compressed representation of input data. It achieves this by encoding the data into a lower-dimensional latent space and then decoding it back. This project uses a VAE to generate novel face images.

## Project Description

The model is trained on the CelebA dataset, a large-scale face attributes dataset with more than 200,000 celebrity images, each with 40 attribute annotations. The training was performed for 50 epochs.

This project also includes two additional features:
- A function to display the distribution of the latent space variables. This helps to understand the distribution of the latent space learned by the VAE.
- A function to manipulate novel images by performing arithmetic in the latent space. This feature allows users to generate novel faces with specified attributes by manipulating the latent variables.

## Results

![image](https://github.com/DimensionDweller/VAE_Implimentation/assets/75709283/37f83e55-d0cc-4ab8-a044-2afff01beb69)


---

## Latent Space Distribution

![image](https://github.com/DimensionDweller/VAE_Implimentation/assets/75709283/984ee222-1070-4da2-9b78-20b1cc282bad)


One of the key aspects of Variational Autoencoders, which distinguishes them from regular autoencoders, is the "reparametrization trick", an elegant method to allow backpropagation through a random node.

In a VAE, the encoder doesn't output an explicit code or representation. Instead, it produces parameters (means and variances) of a set of Gaussian distributions. The actual latent code is then sampled from these distributions. This is where the "reparametrization trick" comes in: instead of sampling from the Gaussian distribution directly, which is a stochastic process and thus not differentiable, we sample from a unit Gaussian and then reparametrize to obtain the sample from the desired distribution. This process allows us to retain differentiability in the network, which is essential for backpropagation.

The latent space distributions shown above demonstrate this property. Ideally, each of these distributions should resemble a standard Gaussian distribution, which is a result of the VAE's training objective. The VAE's loss function includes a Kullback-Leibler (KL) divergence term, which measures how much one probability distribution differs from a second, expected probability distribution. In this case, the KL divergence encourages the latent variable distributions to follow a standard Gaussian distribution.

## Usage

<Add instructions on how to use your code, how to run the training, and how to generate and manipulate images>

## Future Work

<Discuss any plans for future improvements or features>

## Contributing

<Add instructions for how others can contribute to your project>

## License

<Add information about the license>

