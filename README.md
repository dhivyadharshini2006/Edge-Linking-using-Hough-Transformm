# Edge-Linking-using-Hough-Transformm
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
```python
#Name:Dhivya Dharshini B
#Reg no:212223240031
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread(r"girl.png")
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

plt.figure(figsize=(12, 8))

plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Input Image")
plt.axis('off')

plt.subplot(2, 2, 2)
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')

edges = cv2.Canny(gray_image, 50, 150)

plt.subplot(2, 2, 3)
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')

lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)

plt.subplot(2, 2, 4)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Result of Hough Transform")
plt.axis('off')

plt.tight_layout()
plt.show()
```
## Output

### Input image and grayscale image
<img width="663" height="299" alt="image" src="https://github.com/user-attachments/assets/1bf04d9c-9554-4d19-9845-cab389dea249" />


### Canny Edge detector output
<img width="308" height="300" alt="image" src="https://github.com/user-attachments/assets/a06910b9-249f-4410-b4ca-bce03b48197d" />


### Display the result of Hough transform
<img width="200" height="288" alt="image" src="https://github.com/user-attachments/assets/d88f3f3a-1e1c-4488-8327-1803336672db" />

## Result
Thus the Edge Linking using Hough Transformm using python and OpenCV.
