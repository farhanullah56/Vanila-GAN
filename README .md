# Vanilla GAN: Fake Face Generator

A Generative Adversarial Network (GAN) built from scratch in PyTorch. It learns from real celebrity faces and generates new face images of people who do not exist.

> All generated images in this project are AI-generated. They are not real people.

## Results

Generated faces after training:

| Early training | Middle of training | Final result |
|:---:|:---:|:---:|
| ![Epoch 1](images/epoch_01.png) | ![Epoch 25](images/epoch_25.png) | ![Final](images/final.png) |

*The images become sharper as training goes on.*

## How It Works

A GAN has two neural networks that train against each other:

- **Generator:** takes random noise and turns it into a fake image.
- **Discriminator:** looks at an image and decides if it is real or fake.

The generator tries to fool the discriminator. The discriminator tries to catch the generator. Both get better over time, and the fake images look more and more real.

```
Random noise --> Generator --> Fake image --\
                                             >--> Discriminator --> Real or Fake?
                          Real image -------/
```

## Dataset

This project uses the **CelebA** dataset (about 200,000 celebrity face images).

- Download: https://mmlab.ie.cuhk.edu.hk/projects/CelebA.html
- The dataset is **not included** in this repository because it is too large.
- Put the images in a folder named `img_align_celeba/` next to the notebook.

## Model and Training Details

| Item | Value |
|---|---|
| Framework | PyTorch |
| Image size | [64 x 64] |
| Noise vector size | [100] |
| Batch size | [128] |
| Epochs | [50] |
| Optimizer | [Adam, learning rate 0.0002] |
| Loss function | [Binary Cross Entropy] |
| Hardware | [Google Colab GPU / local GPU / CPU] |

*(Replace the values in brackets with your own settings from the notebook.)*

## Installation

1. Clone the repository:

```bash
git clone https://github.com/farhanullah56/Vanila-GAN.git
cd Vanila-GAN
```

2. Install the requirements:

```bash
pip install torch torchvision matplotlib numpy jupyter
```

3. Download CelebA and put it in `img_align_celeba/` (see the Dataset section).

## How to Run

```bash
jupyter notebook vanila_gan.ipynb
```

Then run all the cells from top to bottom.

## Project Structure

```
Vanila-GAN/
├── vanila_gan.ipynb    # model, training loop, and results
├── images/             # generated sample images
└── README.md
```

## What I Learned

- How a generator and a discriminator train against each other.
- Why GAN training can be unstable (for example, one network becoming too strong).
- How to load and prepare an image dataset in PyTorch.
- How to track training by saving sample images at each epoch.

## Limitations and Future Work

- The images are small and can be blurry, because this is a basic (vanilla) GAN.
- Next, I want to try a **DCGAN** (convolutional layers) for better image quality.
- I also want to try a larger image size and longer training.

## Author

**Farhan ullah**
GitHub: [farhanullah56](https://github.com/farhanullah56)
