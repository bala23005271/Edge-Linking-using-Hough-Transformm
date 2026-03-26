# EX-07 EDGE LINKING HOUGH TRANSFORM
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read image and convert it to grayscale image.

### Step2:
Find the edges in the image using canny detector and display.

### Step3:
Detect points that form a line using HoughLinesP.

### Step4:
Draw lines on the image.

### Step5:
Display the result.

## Program:
```
DEVELOPED BY: BALA MURUGAN S
REGISTER NUMBER: 212223230027
```

### Read image and convert it to grayscale image
```PY
import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("VI.jpeg",0)
img_c=cv2.imread("VI.jpeg",1)
img_c=cv2.cvtColor(img_c,cv2.COLOR_BGR2RGB)
gray=cv2.cvtColor(img,cv2.COLOR_GRAY2RGB)
gray = cv2.GaussianBlur(gray,(3,3),0)
plt.figure(figsize=(13,13))
plt.subplot(1,2,1)
plt.imshow(img_c)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gray)
plt.title("Gray Image")
plt.axis("off")
plt.show()
```
### Find the edges in the image using canny detector and display
```PY
canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```
### Detect points that form a line using HoughLinesP
```PY
lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)
```
### Draw lines on the image
```PY
for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_c,(x1,y1),(x2,y2),(255,0,0),3)
```
### Display the result
```PY
plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()
```
## Output

### Input image and grayscale image
<img width="404" height="516" alt="Screenshot 2026-03-26 200550" src="https://github.com/user-attachments/assets/451b8674-7903-4b0b-8ac8-63e4af9d836d" />

<img width="425" height="531" alt="Screenshot 2026-03-26 200556" src="https://github.com/user-attachments/assets/934f399d-549b-4291-b44e-039677b354bf" />


<br>

### Canny Edge detector output

<img width="404" height="525" alt="Screenshot 2026-03-26 200640" src="https://github.com/user-attachments/assets/ac760e42-485a-4d46-bd41-242f6e96418c" />


<br>

### Display the result of Hough transform
<img width="396" height="531" alt="Screenshot 2026-03-26 200727" src="https://github.com/user-attachments/assets/62817c3d-b60d-4976-aff6-14f514673d52" />

<br>

## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
