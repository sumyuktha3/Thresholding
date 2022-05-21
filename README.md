# Thresholding
## Aim:
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required:
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm:

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

</br>
</br>
</br>

## Program:
## Developed By: S.Sumyuktha Rani
## Register No: 212220230050
```
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale
image=cv2.imread("army.webp",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("army.webp",0)

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

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>


## OUTPUT:

### Original Image and Grayscale Image

![WhatsApp Image 2022-05-20 at 10 54 18 PM](https://user-images.githubusercontent.com/75235818/169642403-72801ae5-38f3-48f4-9774-db930fab04ed.jpeg)

### Global Thresholding

![WhatsApp Image 2022-05-20 at 10 54 18 PM (1)](https://user-images.githubusercontent.com/75235818/169642679-b75c3f41-08a5-469e-9919-2f3ae46101e7.jpeg)

![WhatsApp Image 2022-05-20 at 10 54 18 PM (2)](https://user-images.githubusercontent.com/75235818/169642667-1804a40b-7ebf-4c68-8c24-de913fe90a41.jpeg)

![WhatsApp Image 2022-05-20 at 10 54 18 PM (3)](https://user-images.githubusercontent.com/75235818/169642637-cd2359a6-603a-4edc-916e-d6cfd1387a54.jpeg)

![WhatsApp Image 2022-05-20 at 10 54 18 PM (4)](https://user-images.githubusercontent.com/75235818/169642612-89201e8b-f85b-48f9-a321-db32df9878e3.jpeg)

![WhatsApp Image 2022-05-20 at 10 54 20 PM](https://user-images.githubusercontent.com/75235818/169642584-92d36b75-2609-4bac-ac46-6d53428df345.jpeg)

### Adaptive Thresholding

![WhatsApp Image 2022-05-20 at 10 54 18 PM (5)](https://user-images.githubusercontent.com/75235818/169642537-69db6655-d567-425b-abc1-74e0f439e3a3.jpeg)

![WhatsApp Image 2022-05-20 at 10 54 18 PM (6)](https://user-images.githubusercontent.com/75235818/169642521-1b339585-1fba-435d-abcf-d16998281635.jpeg)

### Optimum Global Thesholding using Otsu's Method

![WhatsApp Image 2022-05-20 at 10 54 20 PM (1)](https://user-images.githubusercontent.com/75235818/169642510-5de3ff5d-25f7-4ab6-9a9d-4c441d661daa.jpeg)

## Result:
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
