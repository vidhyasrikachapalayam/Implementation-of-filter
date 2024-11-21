# EX 5 Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import necessary libraries (cv2, NumPy, Matplotlib) for image loading, filtering, and visualization.

### Step 2:
Load the image using cv2.imread() and convert it to RGB format using cv2.cvtColor() for proper display in Matplotlib.

### Step 3:
Apply different filters:

1.Averaging Filter: Define an averaging kernel using np.ones() and apply it to the image using cv2.filter2D(). 2.Weighted Averaging Filter: Define a weighted kernel (e.g., 3x3 Gaussian-like) and apply it with cv2.filter2D(). 3.Gaussian Filter: Use cv2.GaussianBlur() to apply Gaussian blur. 4.Median Filter: Use cv2.medianBlur() to reduce noise. 5.Laplacian Operator: Use cv2.Laplacian() to apply edge detection.

### Step 4:
Display each filtered image using plt.subplot() and plt.imshow() for side-by-side comparison of the original and processed images.

### Step 5:
Save or show the images using plt.show() after applying each filter to visualize the effects of smoothing and sharpening.
## Program:
### Developed By   : Vidhyasri
### Register Number: 212222230170
</br>

### 1. Smoothing Filters

i) Using Averaging Filter
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('panda.jpg')
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
```
kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image4 = cv2.filter2D(image2, -1, kernel2)
plt.imshow(image4)
plt.title('Weighted Averaging Filtered')
```
iii) Using Gaussian Filter
```
gaussian_blur = cv2.GaussianBlur(src=image2, ksize=(11,11), sigmaX=0, sigmaY=0)
plt.imshow(gaussian_blur)
plt.title(' Gaussian Blurring Filtered')
```
iv)Using Median Filter
```
median=cv2.medianBlur (src=image2, ksize=11)
plt.imshow(median)
plt.title(' Median Blurring Filtered')

```

### 2. Sharpening Filters
i) Using Laplacian Linear Kernal
```
kernel3 = np.array([[0,1,0], [1, -4,1],[0,1,0]])
image5 =cv2.filter2D(image2, -1, kernel3)
plt.imshow(image5)
plt.title('Laplacian Kernel')
```
ii) Using Laplacian Operator
```
new_image = cv2.Laplacian (image2, cv2.CV_64F)
plt.imshow(new_image)
plt.title('Laplacian Operator')
```

## OUTPUT:
## 1. Smoothing Filters


### i) Using Averaging Filter
![image](https://github.com/user-attachments/assets/d67467a1-857e-49c6-9004-93251ae45362)
![image](https://github.com/user-attachments/assets/302fbe22-02f5-4520-856c-74089b60c8f3)


### ii)Using Weighted Averaging Filter
![image](https://github.com/user-attachments/assets/27eeced1-aa47-4a51-99e9-a05a8e7c9fa4)

### iii)Using Gaussian Filter
![image](https://github.com/user-attachments/assets/0257643e-4581-4ca8-b7ef-b973f817bb69)


### iv) Using Median Filter
![image](https://github.com/user-attachments/assets/c8e37c45-ab12-4e9d-8e46-484606936d0d)

### 2. Sharpening Filters

### i) Using Laplacian Kernal
![image](https://github.com/user-attachments/assets/b8a7984c-d8e3-4b55-9213-88074b48ae32)


### ii) Using Laplacian Operator
![image](https://github.com/user-attachments/assets/0c721598-fe8e-4287-bde0-8ab1f7d1dacc)


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
