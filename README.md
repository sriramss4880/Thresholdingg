## EX 08 : THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
Anaconda - Python 3.7
OpenCV
## Algorithm
 Step1: Load the necessary packages.

Step2: Read the Image and convert to grayscale.

 Step3: Use Global thresholding to segment the image.

 Step4: Use Adaptive thresholding to segment the image.

 Step5: Use Otsu's method to segment the image and display the results.

# Program
```
Developed By : SRIRAM S S
Reg.No : 212222230150
```
## Load the necessary packages
```python
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
## Read the Image and convert to grayscale
```python
image = cv2.imread('mountain.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('mountain.jpg',0)
```
## Use Global thresholding to segment the image
```python
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
## Use Adaptive thresholding to segment the image
```python
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
Use Otsu's method to segment the image
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
## Display the results
```python
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
## Original Image
![image](https://github.com/KothaiKumar/Thresholdingg/assets/121215739/999416e0-ffc2-44a6-9e86-7744ecdb196d)

## Global Thresholding
![image](https://github.com/KothaiKumar/Thresholdingg/assets/121215739/542dd5e0-1091-4ab1-adb7-cd9fcb5b7f4a)
![image](https://github.com/KothaiKumar/Thresholdingg/assets/121215739/560791b3-b4e5-4362-82b6-0500912438dc)
![image](https://github.com/KothaiKumar/Thresholdingg/assets/121215739/77e7452f-0b8c-45d6-87e9-b12d7d372a89)
![image](https://github.com/KothaiKumar/Thresholdingg/assets/121215739/b4998b74-bbe9-4f68-97c7-86c7381b7aca)
![image](https://github.com/KothaiKumar/Thresholdingg/assets/121215739/61c5580e-8dd1-41da-aee3-95c820be8a91)

## Adaptive Thresholding
![image](https://github.com/KothaiKumar/Thresholdingg/assets/121215739/19d68b8f-d22e-42d0-b5ca-d90c551702b5)
![image](https://github.com/KothaiKumar/Thresholdingg/assets/121215739/42ce2a57-f94a-49ca-adf7-76beb04e24b3)

## Optimum Global Thesholding using Otsu's Method
![image](https://github.com/KothaiKumar/Thresholdingg/assets/121215739/dd54652d-7999-440c-8f69-77f520086d71)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
