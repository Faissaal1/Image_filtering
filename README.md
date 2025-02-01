# Image Filtering 

## Description

This project demonstrates the use of various image filtering techniques. It explores loading, displaying, and applying filters to images to enhance their quality or extract specific features.

## Features

- Loading and displaying grayscale images
- Applying smoothing filters (blur, Gaussian, median)
- Edge detection using Sobel and Canny filters
- Using convolution to apply custom filters
- Anisotropic filtering
- Mathematical morphology operations

## Mathematical Formulations

### 1. Convolution

Convolution is a fundamental operation in image filtering, defined as:

$$
G(x, y) = \sum_{i=-k}^{k} \sum_{j=-k}^{k} I(x+i, y+j) \cdot K(i, j)
$$

where:

- \(G(x, y)\) is the filtered image,
- \(I(x+i, y+j)\) is the original image,
- \(K(i, j)\) is the kernel (filter),
- \(k\) determines the kernel size.

### 2. Gaussian Blur

A Gaussian filter is applied using a weighted sum of neighboring pixels:

$$
G(x, y) = \frac{1}{2\pi\sigma^2} \sum_{i=-k}^{k} \sum_{j=-k}^{k} I(x+i, y+j) e^{-\frac{i^2 + j^2}{2\sigma^2}}
$$

where \(\sigma\) controls the amount of blurring.

### 3. Sobel Edge Detection

Sobel filters approximate image gradients:

$$
G_x = \begin{bmatrix} -1 & 0 & 1 \\ -2 & 0 & 2 \\ -1 & 0 & 1 \end{bmatrix} * I, \quad G_y = \begin{bmatrix} -1 & -2 & -1 \\ 0 & 0 & 0 \\ 1 & 2 & 1 \end{bmatrix} * I
$$

The final gradient magnitude is:

$$
G = \sqrt{G_x^2 + G_y^2}
$$

### 4. Canny Edge Detection

Canny edge detection involves:

1. Applying Gaussian blur.
2. Computing image gradients using Sobel filters.
3. Applying non-maximum suppression.
4. Using double thresholding and edge tracking by hysteresis.

### 5. Anisotropic Diffusion

Anisotropic diffusion reduces noise while preserving edges and is defined as:

$$
I_t = \nabla \cdot (c(x, y, t) \nabla I)
$$

where \(c(x, y, t)\) is the diffusion coefficient that varies based on the gradient magnitude to preserve edges.

### 6. Mathematical Morphology

Morphological operations are used for shape analysis and noise removal. The fundamental operations include:

- **Dilation**:

$$
D(I) = I \oplus K = \{z | (K_z \cap I) \neq \emptyset \}
$$

- **Erosion**:

$$
E(I) = I \ominus K = \{z | K_z \subseteq I \}
$$

where \(K\) is the structuring element and \(I\) is the input image.



