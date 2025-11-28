<h1 align=center>Thresholding using OpenCV</h1>

## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
Anaconda - Python 3.7
OpenCV
## Algorithm
### Step1:
Load the necessary packages.

### Step2:
Read the Image and convert to grayscale.

### Step3:
Use Global thresholding to segment the image.

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.
## Program
```py
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread("owl.jpg")

image_gray = cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)

#CONVERT THE COLOR FROM BGR TO RGB
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
#plt.imshow(image)
plt.title("Original Image")
plt.axis("off")

ret,thresh_dipt1=cv2.threshold(image_gray,100,255,cv2.THRESH_BINARY)
plt.imshow(thresh_dipt1)
plt.axis("off")

adaptive_threshold=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 1)
plt.imshow(adaptive_threshold,cmap="gray")
plt.axis("off")

ret, otsu_threshold = cv2.threshold(image_gray, 25, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)
plt.imshow(otsu_threshold)
plt.axis("off")
```

# Output
### 1. Original Image
<img width="521" height="471" alt="image" src="https://github.com/user-attachments/assets/5df1bb15-e202-4899-90bb-ec6201d74fab" />

### 2. Global Theresholding
<img width="541" height="451" alt="image" src="https://github.com/user-attachments/assets/e31bd31e-dec0-44e0-aa88-8becb8106fdf" />


### 3. Adaptive Thresholding
<img width="502" height="459" alt="image" src="https://github.com/user-attachments/assets/13d24059-3bf3-4363-b3d8-0a00cc3f65dd" />


### 4. Optimum Global Thesholding using Otsu's Method
<img width="502" height="445" alt="image" src="https://github.com/user-attachments/assets/0a45fdcb-71e7-43e0-a788-82baefa2baf8" />


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
