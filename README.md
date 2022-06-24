# EX.NO : 08
# DATE :

# <p align="center">Edge Linking using Hough Transform</p>
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
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

## Program:
```Python

# Read image and convert it to grayscale image

import cv2
import matplotlib.pyplot as plt
import numpy as np
image=cv2.imread("image3.jpg")
image1=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
cv2.imshow("GRAY_IMAGE",image1)
cv2.waitKey(0)
cv2.destroyAllWindows()

# Find the edges in the image using canny detector and display

canny_edges=cv2.Canny(image1,120,150)
plt.imshow(canny_edges,cmap='gray')
plt.title('Canny Edges')
plt.xticks([])
plt.yticks([])

# Detect points that form a line using HoughLinesP

lines=cv2.HoughLinesP(canny_edges,1,np.pi/180,threshold = 80,minLineLength=50,maxLineGap=250)

# Draw lines on the image

for line in lines:
    x1,y1,x2,y2= line[0]
    cv2.line(image,(x1,y1),(x2,y2),(0,255,0),3)

# Display the result

plt.imshow(image,cmap='gray')
plt.title('image')
plt.xticks([])
plt.yticks([])

```
## Output

### Input image and grayscale image

<img width="225" alt="image" src="https://user-images.githubusercontent.com/75235554/169635230-79137adb-6558-46fc-acee-bb1caaaa1d2b.png">

<img width="225" alt="image" src="https://user-images.githubusercontent.com/75235554/169635157-c176430e-5ef5-45bf-8d43-bf17d4e6b6fd.png">


### Canny Edge detector output
<img width="192" alt="image" src="https://user-images.githubusercontent.com/75235554/169635278-fc2b4349-0cfa-4391-98b5-d94e8a1b6a34.png">

### Display the result of Hough transform
<img width="170" alt="image" src="https://user-images.githubusercontent.com/75235554/169635294-a902a7d6-74df-4ae2-9c76-79982515978b.png">

## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
