# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
### Step1:
Import the necessary packages.

### Step2:
Create the Text using cv2.putText.

### Step3:
Create the Global thresholding to segment the image.

### Step4:
Create Adaptive thresholding to segment the image.

### Step5:
Otsu's method to segment the image.

### Step6:
End the program.

## Program
```
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale
image=cv2.imread("cat.jpeg")
plt.imshow(image)
plt.title('original image')
plt.axis('off')
gray_img=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
plt.imshow(gray_img,'gray')
plt.title('Gray image')
plt.axis('off')

# Use Global thresholding to segment the image
ret,thresh_img1=cv2.threshold(gray_img,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(gray_img,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(gray_img,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(gray_img,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(gray_img,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image
thresh_img7=cv2.adaptiveThreshold(gray_img,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(gray_img,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 
ret,thresh_img6=cv2.threshold(gray_img,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[gray_img,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]

for i in range(0,9):
    plt.figure(figsize=(5,5))
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
![dip9_2](https://github.com/Thirukaalathessvarar-S/THRESHOLDING/assets/121166390/79a45350-a6b8-4b74-9e97-b06aab84c75b)

### Global Thresholding

![dip9_3](https://github.com/Thirukaalathessvarar-S/THRESHOLDING/assets/121166390/4468e694-abfe-4dd9-a595-0dbc6e8e8afb)

![dip9_4](https://github.com/Thirukaalathessvarar-S/THRESHOLDING/assets/121166390/9f3d0b52-f0f4-44ae-bdd9-2030129a856e)

![dip9_5](https://github.com/Thirukaalathessvarar-S/THRESHOLDING/assets/121166390/2deb04c4-83de-4da3-9d78-118e1a885f4e)

![dip9_6](https://github.com/Thirukaalathessvarar-S/THRESHOLDING/assets/121166390/92298f08-4300-4cd3-9fa6-ea99fc5122f4)

![dip9_7](https://github.com/Thirukaalathessvarar-S/THRESHOLDING/assets/121166390/5a921c09-36dc-4521-bae7-6c725700b5ff)

### Adaptive Thresholding

![dip9_10](https://github.com/Thirukaalathessvarar-S/THRESHOLDING/assets/121166390/e1e7cd3c-dce5-489b-a989-428c9527a55b)

![dip9_9](https://github.com/Thirukaalathessvarar-S/THRESHOLDING/assets/121166390/b42d606a-1e7d-4775-81c7-7efb48b4b0f8)

### Optimum Global Thesholding using Otsu's Method
![dip9_8](https://github.com/Thirukaalathessvarar-S/THRESHOLDING/assets/121166390/a2391652-be0e-4b07-ab17-f7a707322d61)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

