# Diffusion Model From Scratch

The goal of this project is to explore different diffusion model architectures and compare their performance on different datasets.

## Pretrained models

Look at [models](models) directory.

| Model      | Dataset      | Epochs | Time, sec | Loss  | FID   |
|------------|--------------|--------|-----------|-------|-------|
| ResNet     | FashionMNIST | 50     | 3266      | 0.362 | 32.97 |
| CondResNet | FashionMNIST | 83     | 6106      | 0.344 | 30.75 |
| ZeroResNet | FashionMNIST | 63     | 4634      | 0.345 | 29.86 |
| UNet       | FashionMNIST | 78     | 528       | 0.364 | 30.37 |
| CondUNet   | FashionMNIST | 57     | 490       | 0.355 | 30.77 |
| ZeroUNet   | FashionMNIST | 74     | 637       | 0.351 | 31.02 |
| CelebA     | CelebA       | 50     | 17397     | 0.260 | 35.85 |

## How to run

To train and run the models look at the [Training.ipynb](Training.ipynb) notebook. It was run on a Google Colab with a V100 GPU.
