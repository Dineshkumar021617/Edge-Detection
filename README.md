# Edge-Detection
## Aim:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the necessary modules.
### Step2:
For performing edge detection on a image use sobel,canny laplacian operations.
### Step3:
Display all the images with their respective edge detected images.
 
## Program:

``` Python
# Import the packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load the image, Convert to grayscale and remove noise
image1=cv2.imread ('rubix.png') 
gray = cv2.cvtColor(image1,cv2.COLOR_BGR2GRAY)
plt.title('GRAY IMAGE')
plt.imshow(gray,cmap = 'gray')

# SOBEL EDGE DETECTOR
img = cv2.GaussianBlur(gray,(3,3),0)
sobelx = cv2.Sobel(gray,cv2.CV_64F,1,0,ksize=5)
sobely = cv2.Sobel(gray,cv2.CV_64F,0,1,ksize=5)
sobelxy =cv2.Sobel(gray,cv2.CV_64F,1,1,ksize=5)
plt.figure(1)
plt.subplot(2,2,1)
plt.imshow(gray,cmap = 'gray')
plt.title('Original')
plt.axis("off")

plt.subplot(2,2,2)
plt.imshow(sobelx,cmap='gray')
plt.title('sobelx')
plt.axis("off")

plt.subplot(2,2,3)
plt.imshow(sobely,cmap='gray')
plt.title('sobely')
plt.axis("off")

plt.subplot(2,2,4)
plt.imshow(sobelxy,cmap='gray')
plt.title('sobelxy')
plt.axis("off")
plt.show()

# LAPLACIAN EDGE DETECTOR
laplacian = cv2.Laplacian(gray,cv2.CV_64F)
plt.imshow(laplacian,cmap='gray')
plt.title('laplacian')
plt.axis("off")
plt.show()

# CANNY EDGE DETECTOR
canny_edges = cv2.Canny(gray, 120, 150)
plt.imshow(canny_edges,cmap='gray')
plt.title('canny_edges')
plt.axis("off")
plt.show()

```
## Output:
### SOBEL EDGE DETECTOR
![Screenshot (201)](https://user-images.githubusercontent.com/75234807/168870333-828ee7e0-5330-4b6f-8611-8ef648871405.png)

### LAPLACIAN EDGE DETECTOR
![SS 2](https://user-images.githubusercontent.com/75234807/168870387-322457f9-324a-404b-a5af-ceeb53f08827.png)

### CANNY EDGE DETECTOR
![Screenshot (202)](https://user-images.githubusercontent.com/75234807/168870349-2e32e55e-12b9-4438-b2a3-5a96b6905798.png)

## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
