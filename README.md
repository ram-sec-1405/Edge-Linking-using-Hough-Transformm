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
## program 

```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('/content/ram.png')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
for line in lines:
    x1, y1, x2, y2 = line[0]  # Unpacking the line coordinates
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')
```
## Output

### Input image and grayscale image
<img width="1038" height="621" alt="image" src="https://github.com/user-attachments/assets/4429b836-5479-4c37-bada-ffbc1afc4787" />


### Canny Edge detector output
<img width="392" height="616" alt="image" src="https://github.com/user-attachments/assets/e681e860-8fde-49d6-b7ea-6a48b4af52ed" />


### Display the result of Hough transform
<img width="374" height="618" alt="image" src="https://github.com/user-attachments/assets/c778c149-f399-4982-8060-8b334e3cd723" />

# Result :
Thus,The Python program to detect the lines using Hough Transform run successfully.
