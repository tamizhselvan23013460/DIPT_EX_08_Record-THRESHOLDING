# Name : Tamizhselvan B
# Reg.No : 212223230225
# Exp.No : 8 (  Record-THRESHOLDING )


# THRESHOLDING
# Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

# Software Required
Anaconda - Python 3.7
OpenCV
# Algorithm
## Step1:
Read the input image and convert it into a grayscale image.

## Step2:
Apply Global Thresholding with a threshold value of 127.
   
## Step3:
Apply Adaptive Thresholding using the Gaussian method.
  
## Step4:
Apply Otsu’s Thresholding to automatically select the optimal threshold.

## Step5:
Display and compare the original, global, adaptive, and Otsu thresholded images.


# Program
```py


import cv2
import numpy as np
import matplotlib.pyplot as plt

# Step 2: Read the image and convert to grayscale
image = cv2.imread('Tamizh.jpeg')  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Convert to grayscale

# Original Image
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')

# Step 3: Use Global Thresholding to segment the image
# Apply global thresholding with a threshold value of 127
_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

# Step 4: Use Adaptive Thresholding to segment the image
# Apply adaptive thresholding using Gaussian method
adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)

# Step 5: Use Otsu's method to segment the image
# Apply Otsu's method for optimal thresholding
_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)


# Global Thresholding
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')

# Adaptive Thresholding
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')

# Otsu's Method
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')

# Show the plot
plt.tight_layout()
plt.show()



```


# Output
## Original Image

<img width="206" height="265" alt="image" src="https://github.com/user-attachments/assets/6e3fc2fa-4151-463a-a5cd-272f27e1fc12" />




## Global Thresholding

<img width="261" height="302" alt="image" src="https://github.com/user-attachments/assets/e0439df9-3554-4a7d-874b-cb8d62ed616b" />




## Adaptive Thresholding


<img width="270" height="323" alt="image" src="https://github.com/user-attachments/assets/0e6a070a-de42-4585-99f7-0a9787c4fd85" />



## Optimum Global Thesholding using Otsu's Method


<img width="249" height="306" alt="image" src="https://github.com/user-attachments/assets/22a928d1-747c-4e89-ac69-2ad4be2158af" />



# Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
