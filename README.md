# Thresholding of Images
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:

Load the necessary packages.
<br>

### Step2:

Read the Image and convert to grayscale.
<br>

### Step3:

Use Global thresholding to segment the image.
<br>

### Step4:

Use Adaptive thresholding to segment the image.
<br>

### Step5:

Use Otsu's method to segment the image.
<br>

### Step6:

Display the results.
<br>
## Program

```
Developed by: DHARSHINI D.S
Reg no:212221230022
```

```
# Load the necessary packages
import numpy as np
import matplotlib.pyplot as plt
import cv2

# convert to grayscale
image = cv2.imread("mick.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("mick.jpg",0)

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
<br>
https://github.com/Dharshini-DS/Thresholding/blob/main/1.png
![1](https://github.com/Dharshini-DS/Thresholding/blob/main/1.png)
<br>

### Global Thresholding
<br>
![2](https://github.com/Dharshini-DS/Thresholding/assets/93427345/27b96f8b-a8e6-4e3f-9dda-d93215bf457a)
<br>
![3](https://github.com/Dharshini-DS/Thresholding/assets/93427345/391f25a3-d970-410d-9554-07a2554145ec)
<br>
![4](https://github.com/Dharshini-DS/Thresholding/assets/93427345/f956395f-80aa-43b8-a5b2-a750baa9ac7b)
<br>
![5](https://github.com/Dharshini-DS/Thresholding/assets/93427345/45a46e96-6e99-40fc-ad95-2a9af72989c1)
<br>
![6](https://github.com/Dharshini-DS/Thresholding/assets/93427345/903b770a-2899-44e1-8ea2-e3e2af03783b)
<br>

### Adaptive Thresholding
<br>
![7](https://github.com/Dharshini-DS/Thresholding/assets/93427345/a3ae3800-0c32-4d48-8ae8-04c7227fa164)
<br>
![8](https://github.com/Dharshini-DS/Thresholding/assets/93427345/e5447a09-bf46-42cf-a010-5069a5a8fc09)
<br>

### Optimum Global Thesholding using Otsu's Method
<br>
![9](https://github.com/Dharshini-DS/Thresholding/assets/93427345/caadae35-4eb0-4c08-8d06-30cee505eeff)
<br>


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

