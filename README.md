# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import the required libraries.

### Step2
Convert the image from BGR to RGB.

### Step3
Apply the required filters for the image separately.

### Step4
Plot the original and filtered image by using matplotlib.pyplot.

### Step5
End the program

## Program:
### Developed By   : VIGNESH M
### Register Number: 212223240176


### 1. Smoothing Filters

i) Using Averaging Filter
```
import cv2
import numpy as np
import matplotlib.pyplot as 
image = cv2.imread('pcb.webp', cv2.IMREAD_GRAYSCALE)
kernel = np.ones((4, 4), np.float32) / 9
averaged_image = cv2.filter2D(image, -1, kernel)
plt.imshow(averaged_image, cmap='gray')
plt.title("Averaging Filter")
plt.axis('off')
plt.show()



```
ii) Using Weighted Averaging Filter
```Python
weighted_kernel = np.array([[1, 2, 1], 
                            [2, 4, 2], 
                            [1, 2, 1]], np.float32)

weighted_kernel = weighted_kernel / weighted_kernel.sum() 
weighted_image = cv2.filter2D(image, -1, weighted_kernel)  

plt.imshow(weighted_image, cmap='gray')
plt.title("Weighted Averaging Filter")
plt.axis('off')
plt.show()

```
iii) Using Gaussian Filter
```Python

gaussian_image = cv2.GaussianBlur(image, (3, 3), 1)
plt.imshow(gaussian_image, cmap='gray')
plt.title("Gaussian Filter")
plt.axis('off')
plt.show()


```
iv)Using Median Filter
```Python

median_image = cv2.medianBlur(image, 3)
plt.imshow(median_image, cmap='gray')
plt.title("Median Filter")
plt.axis('off')
plt.show()


```

### 2. Sharpening Filters
i) Using Laplacian Linear Kernal
```Python

laplacian_kernel = np.array([[0, 1, 0], [1, -4, 1], [0, 1, 0]], np.float32)
laplacian_image = cv2.filter2D(image, -1, laplacian_kernel)

sharpened_laplacian_image = cv2.add(image, laplacian_image)
plt.imshow(sharpened_laplacian_image, cmap='gray')
plt.title("Laplacian Kernel")
plt.axis('off')
plt.show()
```
ii) Using Laplacian Operator
```Python

laplacian_operator_image = cv2.Laplacian(image, cv2.CV_64F)  # Laplacian operator
laplacian_operator_image = cv2.convertScaleAbs(laplacian_operator_image)  # Convert to absolute values
sharpened_operator_image = cv2.add(image, laplacian_operator_image)

plt.imshow(sharpened_operator_image, cmap='gray')
plt.title("Laplacian Operator")
plt.axis('off')
plt.show()

```

## OUTPUT:
### 1. Smoothing Filters

i) Using Averaging Filter
<img width="251" height="411" alt="Untitled" src="https://github.com/user-attachments/assets/9d205f57-9868-4349-a60d-7ea3883c750f" />



ii)Using Weighted Averaging Filter
<img width="251" height="411" alt="Untitled-1" src="https://github.com/user-attachments/assets/e4af2776-96dc-46c5-a780-845ab6125512" />


iii)Using Gaussian Filter
<img width="251" height="411" alt="Untitled" src="https://github.com/user-attachments/assets/da7b6619-2815-4720-b2c2-d91f0cd9c75d" />


iv) Using Median Filter
<img width="251" height="411" alt="Untitled-1" src="https://github.com/user-attachments/assets/c29d40c8-d631-4051-9d2c-d1f54a8462c5" />




### 2. Sharpening Filters
</br>

i) Using Laplacian Kernal
<img width="251" height="411" alt="Untitled" src="https://github.com/user-attachments/assets/614daa83-958a-4f5f-94f4-a2b20427f3e8" />




ii) Using Laplacian Operator

![Uploading Untitled-1.png…]()



## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
