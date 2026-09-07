# EXP-5 - Implementation of filter

## Name : Vignesh S
## Register No : 212223230240

## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Using Averaging Filter

### Step2
Using Weighted Averaging Filter

### Step3
Using Gaussian Filter

### Step4
Using Median Filter

### Step5
Using Laplacian Kernal

### Step6
Using Laplacian Operator

## Program: 

### 1. Smoothing Filters
i) Using Averaging Filter

```
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("Meyyappan.jpg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()
```
<img width="712" height="734" alt="image" src="https://github.com/user-attachments/assets/eb093b05-5684-4fc4-856c-343fffd8c9f9" />


ii) Using Weighted Averaging Filter

```
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
image3=cv2.filter2D(image2,-1,kernel1)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```

<img width="504" height="410" alt="image" src="https://github.com/user-attachments/assets/ce08b555-8a60-4556-b1d1-64923a40cf18" />




iii) Using Gaussian Filter

```
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```

<img width="456" height="410" alt="image" src="https://github.com/user-attachments/assets/af40588d-2e9d-4adb-bcac-17684c03488f" />





iv)Using Median Filter

```
median=cv2.medianBlur(image2,13)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()
```
<img width="712" height="734" alt="image" src="https://github.com/user-attachments/assets/08a65a4f-ca0a-4f0a-8dfb-ce8e4b12ce2f" />





### 2. Sharpening Filters

i) Using Laplacian Linear Kernal

```
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```

<img width="456" height="410" alt="image" src="https://github.com/user-attachments/assets/b4e5f802-a210-4b6c-9174-f8335cdd3861" />




ii) Using Laplacian Operator

```
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```

<img width="456" height="410" alt="image" src="https://github.com/user-attachments/assets/80f605fd-5336-43ed-93d4-cba2b1cc0f62" />

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
