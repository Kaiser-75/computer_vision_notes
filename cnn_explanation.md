# Convolutional Neural Network (CNN): Layers, Operations, and Calculations

## 1. Overview

Convolutional Neural Networks (CNNs) are a class of deep learning models commonly used for **image classification**, **object detection**, and other **computer vision tasks**. A CNN extracts features from images using convolutional layers, reduces dimensions with pooling layers, and classifies outputs through dense (fully connected) layers.

---

## 2. CNN Layers

### 2.1 Convolutional Layer

- The **Convolutional Layer** applies **filters** (kernels) to the input image to extract features like edges, textures, and shapes.
- Each filter slides over the input image and performs an **element-wise multiplication** followed by summation (dot product).

**Formula to Calculate Output Dimensions**:

\[
\text{Output Size} = \left\lfloor \frac{\text{Input Size} - \text{Filter Size} + 2 \times \text{Padding}}{\text{Stride}} \right\rfloor + 1
\]

- **Input Size**: Height and width of the input image (\( H_{\text{in}}, W_{\text{in}} \)).
- **Filter Size** (\(F\)): Size of the convolution kernel.
- **Padding** (\(P\)):
   - **Valid**: \(P = 0\) (no padding).
   - **Same**: \(P = \frac{F - 1}{2}\) (keeps output size same as input for stride = 1).
- **Stride** (\(S\)): Step size for the filter movement.
- **Output Depth**: Equal to the number of filters used.

---

### 2.2 Activation Function

- After convolution, a **non-linear activation function** (e.g., ReLU) is applied to introduce non-linearity.
- **ReLU (Rectified Linear Unit)** formula:

\[
f(x) = \max(0, x)
\]

---

### 2.3 Pooling Layer

- The **Pooling Layer** reduces the dimensions of feature maps while retaining important features.
- Common methods:
   - **Max Pooling**: Takes the maximum value from each window.
   - **Average Pooling**: Takes the average of all values in the window.

**Formula to Calculate Output Dimensions**:

\[
\text{Output Size} = \left\lfloor \frac{\text{Input Size} - \text{Pool Size}}{\text{Stride}} \right\rfloor + 1
\]

---

### 2.4 Flatten Layer

- The **Flatten Layer** converts the 3D feature maps into a **1D vector** for dense layers.

**Example**:
Input: \( 4 \times 4 \times 16 \) → Flattened: \( 1 \times 256 \)

---

## 3. Example: Simple CNN Architecture

Below is a simple CNN architecture with step-by-step dimension calculations:

| **Layer**               | **Input**        | **Operation**                | **Output**        |
|--------------------------|------------------|-----------------------------|-------------------|
| Input                   | \(28 \times 28 \times 1\) | -                           | \(28 \times 28 \times 1\) |
| Convolutional (5x5, 6)   | \(28 \times 28\) | Stride 1, Padding: Valid      | \(24 \times 24 \times 6\) |
| MaxPooling (2x2)         | \(24 \times 24 \times 6\) | Pooling, Stride 2           | \(12 \times 12 \times 6\) |
| Convolutional (5x5, 16)  | \(12 \times 12\) | Stride 1, Padding: Valid      | \(8 \times 8 \times 16\)  |
| MaxPooling (2x2)         | \(8 \times 8 \times 16\) | Pooling, Stride 2           | \(4 \times 4 \times 16\)  |
| Flatten                  | \(4 \times 4 \times 16\) | Flatten operation           | \(1 \times 256\)          |
| Fully Connected          | \(1 \times 256\) | Dense Layer (120 neurons)    | \(1 \times 120\)          |
| Output                   | \(1 \times 120\) | Softmax (10 classes)         | \(1 \times 10\)           |

---

## 4. Conclusion

This file explains the structure and calculations of a simple CNN architecture. By combining convolution, activation, pooling, and fully connected layers, CNNs extract hierarchical features from images and make predictions effectively.

---

**Feel free to use or modify this explanation for your learning or projects!** 🚀
