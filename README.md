# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step 1:
Import necessary libraries: OpenCV, NumPy, and Matplotlib.Read an image, convert it to RGB format, define an 11x11 averaging kernel, and apply 2D convolution filtering.Display the original and filtered images side by side using Matplotlib.

### Step 2:
Define a weighted averaging kernel (kernel2) and apply 2D convolution filtering to the RGB image (image2).Display the resulting filtered image (image4) titled 'Weighted Averaging Filtered' using Matplotlib's imshow function.

### Step 3:
Apply Gaussian blur with a kernel size of 11x11 and standard deviation of 0 to the RGB image (image2).Display the resulting Gaussian-blurred image (gaussian_blur) titled 'Gaussian Blurring Filtered' using Matplotlib's imshow function.

### Step 4:
Apply median blur with a kernel size of 11x11 to the RGB image (image2).Display the resulting median-blurred image (median) titled 'Median Blurring Filtered' using Matplotlib's imshow function.

### Step 5:
Define a Laplacian kernel (kernel3) and perform 2D convolution filtering on the RGB image (image2).Display the resulting filtered image (image5) titled 'Laplacian Kernel' using Matplotlib's imshow function.

### Step 6:
Apply the Laplacian operator to the RGB image (image2) using OpenCV's cv2.Laplacian function.Display the resulting image (new_image) titled 'Laplacian Operator' using Matplotlib's imshow function.
## Program:
### Developed By : SABARI S
### Register Number : 212222240085

### 1. Smoothing Filters
i) Using Averaging Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('tree.jpg')
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
ii) Using Weighted Averaging Filter
```Python
kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image4 = cv2.filter2D(image2, -1, kernel2)
plt.imshow(image4)
plt.title('Weighted Averaging Filtered')

```
iii) Using Gaussian Filter
```Python
gaussian_blur = cv2.GaussianBlur(src=image2, ksize=(11,11), sigmaX=0, sigmaY=0)
plt.imshow(gaussian_blur)
plt.title(' Gaussian Blurring Filtered')
```
iv)Using Median Filter
```Python
median=cv2.medianBlur (src=image2, ksize=11)
plt.imshow(median)
plt.title(' Median Blurring Filtered')
```

### 2. Sharpening Filters
i) Using Laplacian Linear Kernal
```Python
kernel3 = np.array([[0,1,0], [1, -4,1],[0,1,0]])
image5 =cv2.filter2D(image2, -1, kernel3)
plt.imshow(image5)
plt.title('Laplacian Kernel')
```
ii) Using Laplacian Operator
```Python
new_image = cv2.Laplacian (image2, cv2.CV_64F)
plt.imshow(new_image)
plt.title('Laplacian Operator')
```

## OUTPUT:
### 1. Smoothing Filters
#### i) Using Averaging Filter
![{A85C09B7-C574-47B3-B741-6F1D3CE048AF}](https://github.com/user-attachments/assets/9e7198f9-bf12-41e8-8342-b7a357b8591c)

#### ii)Using Weighted Averaging Filter
![{3D0468FF-BDC8-4088-8C1F-0DC0446DFC9A}](https://github.com/user-attachments/assets/ccac18fe-c3e5-4471-85a2-0853822361dd)

#### iii)Using Gaussian Filter
![{17AB0D36-0848-4FC0-AFA4-9EB93DDD3C7E}](https://github.com/user-attachments/assets/3384a6db-850f-4f4b-9055-24c51c84e969)

#### iv) Using Median Filter
![{06A1623F-3535-4AF9-AE87-1404712D25AD}](https://github.com/user-attachments/assets/d02969ed-5d59-43f4-8338-16b5f66ec1b0)

### 2. Sharpening Filters

#### i) Using Laplacian Kernal
![{C060BB18-0CBE-4A96-B28F-8BD41BC15317}](https://github.com/user-attachments/assets/c0a4935b-d69a-4eba-8ede-6f7fc5bd2198)

#### ii) Using Laplacian Operator
![{F61EB6E5-0B9E-4F57-8461-82E1CA44B1FA}](https://github.com/user-attachments/assets/0dc76b5a-1b4b-456b-b665-13e7d84b9a7f)

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
