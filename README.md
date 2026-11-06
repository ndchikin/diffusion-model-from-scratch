# Diffusion Model From Scratch

The goal of this project is to explore different diffusion model architectures and compare their performance on different datasets. The denoising networks, noise-level conditioning, training loop and sampling are implemented from scratch in PyTorch, and the models are compared by FID.

| UNet on FashionMNIST | CelebA |
|:---:|:---:|
| ![UNet samples](animation/UNet.gif) | ![CelebA samples](animation/CelebA.gif) |

**Tech stack:** Python, PyTorch, TorchEval (FID), Jupyter, Google Colab (V100 GPU).

University of Geneva project, autumn 2023, by Jing Wen and Nikolay Chikin.

## Models

- **ResNet / UNet:** the two denoising architectures, without noise-level conditioning.
- **Cond:** noise-level conditioning through conditional batch normalization.
- **Zero:** the conditional model with zero-initialized convolutions.

Lower FID is better.

| Model      | Dataset      | Epochs | Time, sec | Loss  | FID   |
|------------|--------------|--------|-----------|-------|-------|
| ResNet     | FashionMNIST | 50     | 3266      | 0.362 | 32.97 |
| CondResNet | FashionMNIST | 83     | 6106      | 0.344 | 30.75 |
| ZeroResNet | FashionMNIST | 63     | 4634      | 0.345 | 29.86 |
| UNet       | FashionMNIST | 78     | 528       | 0.364 | 30.37 |
| CondUNet   | FashionMNIST | 57     | 490       | 0.355 | 30.77 |
| ZeroUNet   | FashionMNIST | 74     | 637       | 0.351 | 31.02 |
| CelebA     | CelebA       | 50     | 17397     | 0.260 | 35.85 |

Pretrained weights for every model are in the [models](models) directory, and sampling animations for each one are in [animation](animation). Both are stored with [Git LFS](https://git-lfs.com), so run `git lfs install` before cloning to download them.

## How to run

To train and run the models, open the [Training.ipynb](Training.ipynb) notebook. It trains each model, saves its weights and records a sampling animation. It was run on Google Colab with a V100 GPU.
