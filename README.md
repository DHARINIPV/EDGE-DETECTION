# EDGE-DETECTION
## Aim:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the necessary modules for the program.

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale

### Step4:
Using Sobel operator from cv2,detect the edges of the image.

### Step5:

Using Laplacian operator from cv2,detect the edges of the image and Using Canny operator from cv2,detect the edges of the image.

## Program and Output:
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load the image
image = cv2.imread('d.jpg')  # Replace with your image path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Original Image
plt.figure(figsize=(7,3))
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/b14efb26-73e5-475b-8f19-a8c4acb35ca1)

### SOBEL EDGE DETECTOR
```python
sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  # Sobel in x direction
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  # Sobel in y direction
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  # Combine both directions
plt.figure(figsize=(7,3))
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/51774ed8-3b5d-4d36-a86a-9bb5cdbe937e)

### LAPLACIAN EDGE DETECTOR
```python
laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)
plt.figure(figsize=(7,3))
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/9cc63626-4fa0-4007-9ee7-5fcb43a2736f)

### CANNY EDGE DETECTOR
```python
canny_edges = cv2.Canny(gray_image, 50, 150)
plt.figure(figsize=(7,3))
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/72ce3227-9800-4276-b3a7-8e6c773c79bb)

## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
