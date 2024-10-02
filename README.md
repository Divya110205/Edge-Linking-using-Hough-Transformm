#  EX-7 Edge-Linking-using-Hough-Transformm
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

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

## Program:
### Developed By : DIVYA.A
### Register Number : 212222230034
```

# Read image and convert it to grayscale image
import cv2
import numpy as np
r=cv2.imread('image.jpeg',-1)
gray=cv2.cvtColor(r,cv2.COLOR_BGR2GRAY)
img = cv2.GaussianBlur(gray,(3,3),0)
cv2.imshow('original',r)
cv2.waitKey(0)
cv2.destroyAllWindows()
cv2.imshow('gray',gray)
cv2.waitKey(0)
cv2.destroyAllWindows()


# Find the edges in the image using canny detector and display
canny_edges = cv2.Canny(img, 50, 120)
cv2.imshow('canny',canny_edges)
cv2.waitKey(0)
cv2.destroyAllWindows()


# Detect points that form a line using HoughLinesP
lines =cv2.HoughLinesP(canny_edges, 1, np.pi/180,threshold = 15, minLineLength =5 ,
maxLineGap = 7)



# Draw lines on the image
for line in lines:
 x1,y1,x2,y2 = line[0]
 cv2.line(r, (x1,y1),(x2,y2),(255,0,0),3)



# Display the result
cv2.imshow('hough_detected',r)
cv2.waitKey(0)
cv2.destroyAllWindows()
```


## Output:

### Input image and grayscale image
![Screenshot 2024-10-02 180545](https://github.com/user-attachments/assets/cd4c7118-330d-44f1-9860-624d9f9efd12)

![Screenshot 2024-10-02 180555](https://github.com/user-attachments/assets/add7ce90-3450-4bcd-85be-f0341d17b4cc)

### Canny Edge detector output
![Screenshot 2024-10-02 180604](https://github.com/user-attachments/assets/04f2d649-97a0-4e72-8d8e-5d8ef97a11b8)

### Display the result of Hough transform
![Screenshot 2024-10-02 180612](https://github.com/user-attachments/assets/e7af5491-54c1-45d2-9fd3-3f70f0a7e8a6)

## Result:
Thus the program is written with Python and OpenCV to detect lines using Hough transform.
