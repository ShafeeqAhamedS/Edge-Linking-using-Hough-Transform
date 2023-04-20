# <p align="center">Edge-Linking-using-Hough-Transform</p>
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the necessary modules for the program.
### Step2:
Load a image using imread() from cv2 module.
### Step3:
Convert the image to grayscale.
### Step4:
Using Canny operator from cv2,detect the edges of the image.
### Step5:
Using the HoughLinesP(),detect line co-ordinates for every points in the images.
### Step 6
Using For loop,draw the lines on the found co-ordinates.
### Step 7
Display the image.

</br>

## Program:
Developed by: **Shafeeq Ahamed. S**
</br>
Register Number: **212221230092**

### Import Libraries
```py
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
### Read Image
```py
image=cv2.imread("road.png",1)

plt.imshow(image)
plt.title('Original')
plt.axis('off')
```
### Convert image to grayscale
```py
gray=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)

plt.imshow(image,cmap="gray")
plt.title('gray')
plt.axis('off')
```

### Smoothen image using Gaussian Filter
```py
img = cv2.GaussianBlur(src = gray, ksize = (15,15), sigmaX=0,sigmaY=0)

plt.imshow(img)
plt.title('EDGES')
plt.axis('off')
```
### Find the edges in the image using canny detector
```py
edges = cv2.Canny(image, 120, 150)
plt.imshow(edges)
plt.title('EDGES')
plt.axis('off')
```
### Detect points that form a line using HoughLinesP
```py
lines=cv2.HoughLinesP(edges,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)
```
# Draw lines on the image
```py
for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(image,(x1,y1),(x2,y2),(0,0,205),2)
```
# Display the result
```py
plt.imshow(image)
plt.title('HOUGH')
plt.axis('off')
```
## Output

### Input image and grayscale image
### Result of Gaussian Filter
### Result of Canny Edge detector
### Result of Hough transform


## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
