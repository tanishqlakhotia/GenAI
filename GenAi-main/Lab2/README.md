# CSET419 – Introduction to Generative AI

## Lab–2: Training a Basic Generative Adversarial Network (GAN)

---

## Overview

This laboratory exercise focuses on the implementation and training of a **Generative Adversarial Network (GAN)** for synthetic image generation. The lab simulates a real-world scenario where a university’s digital archive has suffered partial data loss, and synthetic data is required to test and validate an AI pipeline before full recovery.

The experiment demonstrates how adversarial learning enables a model to generate realistic images by training two neural networks—the **Generator** and the **Discriminator**—in a competitive framework.

---

## Objective

The primary objective of this lab is to:

* Design and train a basic GAN model.
* Generate realistic synthetic images similar to a chosen dataset.
* Evaluate the quality of generated samples over multiple training epochs.
* Analyze the distribution of generated images using a pre-trained classifier.

fileciteturn0file0

---

## Problem Statement

Due to a partial crash of a digital archive server, a significant number of scanned images are unavailable. Before restoring the archive, synthetic images are required to validate the end-to-end AI processing pipeline. A GAN-based approach is used to simulate realistic image data for this purpose.

---

## Dataset

One of the following datasets is used (only one selected per experiment):

* **MNIST** – Handwritten digit images
* **Fashion-MNIST** – Clothing and fashion item images

The dataset is loaded using standard deep learning libraries such as **TensorFlow/Keras** or **PyTorch/Torchvision** utilities.

---

## Input Parameters

The implementation supports configurable input parameters, either through user input or predefined configuration variables:

| Parameter      | Description                       | Recommended Values |
| -------------- | --------------------------------- | ------------------ |
| dataset_choice | Dataset selection                 | mnist / fashion    |
| epochs         | Number of training epochs         | 30 – 100           |
| batch_size     | Training batch size               | 64 / 128           |
| noise_dim      | Dimension of random noise vector  | 50 / 100           |
| learning_rate  | Optimizer learning rate           | 0.0002             |
| save_interval  | Epoch interval for saving samples | 5                  |

---

## Methodology

### 1. Generator Network

* Accepts random noise vectors as input.
* Transforms noise into synthetic images matching the dataset dimensions.
* Uses fully connected and activation layers to progressively refine image structure.

### 2. Discriminator Network

* Accepts real and generated images as input.
* Classifies images as **real** or **fake**.
* Acts as an adversary to the generator, improving overall image quality.

### 3. Training Process

* Alternating training of the Discriminator and Generator.
* Loss functions computed separately for both networks.
* Images normalized to a consistent range such as [0,1] or [-1,1].

---

## Implementation Details

* Generator output shape exactly matches the dataset image shape.
* Binary Cross-Entropy loss is used for adversarial training.
* Generated samples are saved periodically in grid format (minimum 5×5).
* Training progress is logged epoch-wise.

---

## Expected Outputs

### Output 1: Training Logs

Epoch-wise training details printed in the following format:

```
Epoch 10/50 | D_loss: 0.53 | D_acc: 78.12% | G_loss: 1.24
```

### Output 2: Generated Samples

* Directory: `generated_samples/`
* Periodic image grids saved as:

  * `epoch_05.png`
  * `epoch_10.png`
  * ...

### Output 3: Final Generated Images

* Directory: `final_generated_images/`
* Total images generated: **100 synthetic images**

### Output 4: Label Prediction of Generated Images

* A pre-trained classifier is used to predict labels of the final generated images.
* Label distribution is analyzed and reported to assess realism and diversity.

---

## Results Summary

* The GAN successfully learned the underlying data distribution of the selected dataset.
* Generated images showed progressive improvement in quality across epochs.
* Discriminator accuracy stabilized as Generator performance improved.
* Predicted label distribution closely matched the original dataset, indicating effective generation.

---

## Conclusion

This lab demonstrates the practical application of Generative Adversarial Networks for synthetic data generation. By training a basic GAN on standard image datasets, the experiment highlights adversarial learning, training stability challenges, and evaluation techniques. The results confirm that GANs can effectively generate realistic images suitable for pipeline testing and research experimentation.

---

## Key Learning Outcomes

* Understanding GAN architecture and adversarial training dynamics.
* Hands-on experience with image generation using deep learning frameworks.
* Evaluation of synthetic data using pre-trained classifiers.
* Practical exposure to real-world use cases of generative models.

---

## Author

**Course:** CSET419 – Introduction to Generative AI
**Lab:** Week 2 – Generative Adversarial Networks
