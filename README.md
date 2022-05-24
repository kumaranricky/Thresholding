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


## <br><br>Program
/*
developed by: Kumaran.B <br>
reg no : 212220230026
*/
```python
# Load the necessary packages
import cv2
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale
img=cv2.imread("track1.jpg",1)
img=cv2.resize(img,(500,400))
g_img=cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow("Original image",img)
cv2.imshow("Gray image",g_img)
cv2.waitKey(0)
cv2.destroyAllWindows()

# Use Global thresholding to segment the image
ret,thresh_img1=cv2.threshold(g_img,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(g_img,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(g_img,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(g_img,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(g_img,100,255,cv2.THRESH_TRUNC)
cv2.imshow("Original image",img)
cv2.imshow("ThresholdBinary",thresh_img1)
cv2.imshow("ThresholdBinaryinv",thresh_img2)
cv2.imshow("Thresholdtozero",thresh_img3)
cv2.imshow("Thresholdtozeroinv",thresh_img4)
cv2.imshow("Thresholdtrunc",thresh_img5)
cv2.waitKey(0)
cv2.destroyAllWindows()

# Use Adaptive thresholding to segment the image
thresh_img6=cv2.adaptiveThreshold(g_img,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img7=cv2.adaptiveThreshold(g_img,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
cv2.imshow("Original image",img)
cv2.imshow("AdaptiveThresholdMean",thresh_img6)
cv2.imshow("AdaptiveThresholdGaussian",thresh_img7)
cv2.waitKey(0)
cv2.destroyAllWindows()

# Use Otsu's method to segment the image 
ret,thresh_img8=cv2.threshold(g_img,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
cv2.imshow("Original image",img)
cv2.imshow("Otsu Thresholding",thresh_img8)
cv2.waitKey(0)
cv2.destroyAllWindows()
```


## Output

### Original Image and Gray Image
![Screenshot (237)](https://user-images.githubusercontent.com/75243072/170051767-fe6912dd-4dc8-4d6e-9210-e0644a523e32.png)

### Global Thresholding
![Screenshot (236)](https://user-images.githubusercontent.com/75243072/170051808-b272e135-1410-480d-9c3a-a71f485c46ff.png)

### Adaptive Thresholding
![Screenshot (240)](https://user-images.githubusercontent.com/75243072/170051868-4a880c95-1c93-48ae-94d2-74b8f26496a2.png)

### <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>Optimum Global Thesholding using Otsu's Method
![Screenshot (241)](https://user-images.githubusercontent.com/75243072/170052016-0467bbe0-d34c-4487-be21-0834e31d1c4a.png)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

