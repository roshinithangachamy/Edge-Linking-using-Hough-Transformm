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

```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('Qn_7_.jpg')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
```
## Grayscale image
```
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
```
## Canny Edge detector output
```
edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
```
## Display the result of Hough transform
```
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
for line in lines:
    x1, y1, x2, y2 = line[0]  # Unpacking the line coordinates
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)  # Draw green lines with thickness of 2
# Display the result of Hough Transform (Image with lines)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')
```
### Name: T.Roshini
### Reg No: 212223230175
## Output:

### Input image and grayscale image
<img width="572" height="430" alt="image" src="https://github.com/user-attachments/assets/2a8a9534-7f1e-4484-9ba5-c87011b3362b" />

<img width="627" height="425" alt="image" src="https://github.com/user-attachments/assets/48f0310c-1c94-41a7-8657-318afb7a9816" />

### Canny Edge detector output
<img width="623" height="433" alt="image" src="https://github.com/user-attachments/assets/19c20828-3ed5-4f1c-b695-761d47b918d3" />

### Display the result of Hough transform
<img width="621" height="420" alt="image" src="https://github.com/user-attachments/assets/3b1c5429-9d30-4921-8988-12aff2a40dd4" />

## Result:
 Thus the python program to detect the lines using Hough Transform was successfully completed.
