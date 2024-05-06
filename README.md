# Thresholding of Images
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step 1:

Load the necessary packages.

### Step 2:

Read the Image and convert to grayscale.

### Step 3:

Use Global thresholding to segment the image.

### Step 4:

Use Adaptive thresholding to segment the image.

### Step 5:

Use Otsu's method to segment the image.

### Step 6:

Display the results.

## Program

```python

PROGRAM DEVELOPED BY: EVANGELIN.S
REG NUMBER: 212221230025

# Load the necessary packages

import numpy as np
import matplotlib.pyplot as plt
import cv2

# Read the Image and convert to grayscale

image = cv2.imread("image1.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("image1.jpg",0)

# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)


# Use Adaptive thresholding to segment the image

thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 

ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results

titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()

```
## Output

### Original Image

![image](https://github.com/Evangelin-Ruth/Thresholdingg/assets/94219798/764cbe19-aedb-4435-bcc6-719ced64b3b3)

### Global Thresholding


![image](https://github.com/Evangelin-Ruth/Thresholdingg/assets/94219798/e09ba15d-3faa-46c7-a148-27e58a800d7e)

![image](https://github.com/Evangelin-Ruth/Thresholdingg/assets/94219798/1e19a4d1-c36a-4f1e-abb0-164791a5d633)
![image](https://github.com/Evangelin-Ruth/Thresholdingg/assets/94219798/5fe9273b-954e-47db-8c6a-62dbce0e8089)


### Adaptive Thresholding

![image](https://github.com/Evangelin-Ruth/Thresholdingg/assets/94219798/7408bcce-53dc-4e29-8c27-541f05d201f8)


### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/Evangelin-Ruth/Thresholdingg/assets/94219798/4ed4d7f9-d458-4e70-b2f3-d3823236b0b9)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
