# GANS-assignment1
# Representation Learning with Autoencoders (AE & VAE)

## Overview
This project explores representation learning using Autoencoders (AE) and Variational Autoencoders (VAE) on the Medical MNIST dataset. The objective is to learn compact latent representations, evaluate reconstruction quality, analyze latent space behavior, and generate new samples.

## Dataset
- Dataset: Medical MNIST  
- Image type: Grayscale medical images  
- Classes:
  - AbdomenCT
  - BreastMRI
  - ChestCT
  - CXR
  - Hand
  - HeadCT

Data is loaded using `tf.keras.utils.image_dataset_from_directory` and processed using TensorFlow tf.data pipelines.

## Models

### Autoencoder (AE)
- Convolutional encoder-decoder architecture  
- Latent dimension: 128  
- Loss: Mean Squared Error (MSE)  
- Purpose: Image reconstruction  

### Denoising Autoencoder (DAE)
- Same architecture as AE  
- Input images are corrupted with Gaussian noise  
- Model reconstructs clean images  
- Improves robustness to noise  

### Variational Autoencoder (VAE)
- Probabilistic latent space  
- Encoder outputs:
  - Mean (μ)
  - Log variance (log σ²)  
- Uses reparameterization trick  
- Loss:
  - Reconstruction loss
  - KL divergence  
- Purpose: Structured latent space and data generation  

## Experiments and Results

### Reconstruction
- AE produces sharper reconstructions  
- DAE produces smoother but more robust outputs  
- VAE produces blurrier outputs due to latent regularization  

### Denoising
- DAE successfully removes noise and preserves structure  
- More robust compared to standard AE  

### Generation
- VAE generates new samples by sampling from latent space  
- Generated images capture general structure  

### Latent Space Visualization
- PCA is used for 2D visualization  
- VAE latent space is more continuous and structured  

### Interpolation
- Smooth transitions between latent vectors  
- Indicates meaningful latent representation  

### Loss Analysis
- AE achieves lower loss due to direct reconstruction  
- VAE loss is higher due to KL divergence  
- KL term enforces latent regularization  

## Key Insights
- AE is best for reconstruction  
- DAE improves robustness to noise  
- VAE enables generation and structured latent space  
- There is a trade-off between reconstruction accuracy and latent space organization  

## Technologies Used
- Python  
- TensorFlow / Keras  
- NumPy  
- Matplotlib  
- Scikit-learn  
