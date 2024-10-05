# Implementation-of-filter

## Aim:

To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:

Anaconda - Python 3.7

## Algorithm:

### Step1

Import necessary libraries: OpenCV, NumPy, and Matplotlib.Read an image, convert it to RGB format, define an 11x11 averaging kernel, and apply 2D convolution filtering.Display the original and filtered images side by side using Matplotlib 

### Step2

 Decide on the type of filter you want to apply based on your desired outcome. Some common filters include:

a. Averaging filter

b. Gaussian filter

c. Median filter

d. Laplacian filter

### Step3

A filter kernel is a small matrix that is applied to each pixel in the image to produce the filtered result. The size and values of the kernel determine the filter's behavior. For example, an averaging filter kernel has all elements equal to 1/N, where N is the kernel size.

### Step4

Use the library's functions to apply the filter to the image. The filtering process typically involves convolving the image with the filter kernel.

### Step5

Visualize the filtered image using a suitable method (e.g., OpenCV's imshow, Matplotlib). Save the filtered image to a file if needed.

## Program:

### Developed By   : mahalashmi k

### Register Number:212222240057

### 1. Smoothing Filters

i) Using Averaging Filter
```

import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('eren.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel = np.ones((11,11), np. float32)/121
image3 = cv2.filter2D(image2, -1, kernel)

plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title('Orignal')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title('Filtered')
plt.axis('off')
```
output

![eren1](https://github.com/user-attachments/assets/58fe4f0e-6cf5-450a-9709-0dbd13efbe1e)

ii) Using Weighted Averaging Filter

```Python
kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image4 = cv2.filter2D(image2, -1, kernel2)
plt.imshow(image4)
plt.title('Weighted Averaging Filtered')
```
output

![eren 2](https://github.com/user-attachments/assets/1865b20a-6391-4d9c-a419-7c0e9bf0622a)

iii) Using Gaussian Filter
```Python
gaussian_blur = cv2.GaussianBlur(src=image2, ksize=(11,11), sigmaX=0, sigmaY=0)
plt.imshow(gaussian_blur)
plt.title(' Gaussian Blurring Filtered')
```
output

![eren 3](https://github.com/user-attachments/assets/1bf945b7-c441-4524-abe9-e43d59e6a1b9)

iv)Using Median Filter
```Python
median=cv2.medianBlur (src=image2, ksize=11)
plt.imshow(median)
plt.title(' Median Blurring Filtered')
```
output

![eren 4](https://github.com/user-attachments/assets/8abed898-1a44-474d-8499-80767eaf528a)

### 2. Sharpening Filters
i) Using Laplacian Linear Kernal
```Python
kernel3 = np.array([[0,1,0], [1, -4,1],[0,1,0]])
image5 =cv2.filter2D(image2, -1, kernel3)
plt.imshow(image5)
plt.title('Laplacian Kernel')
```
output

![eren 5](https://github.com/user-attachments/assets/cddc9184-72d1-4a10-877a-837236da5aa2)

ii) Using Laplacian Operator
```Python
new_image = cv2.Laplacian (image2, cv2.CV_64F)
plt.imshow(new_image)
plt.title('Laplacian Operator')
```
output

![eren 6](https://github.com/user-attachments/assets/817f0296-a188-423d-bb4d-4e43dfe082b2)

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
