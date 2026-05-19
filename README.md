#  Lane Detection

##  Aim

To implement a basic lane detection pipeline using OpenCV by completing missing code segments at specified locations.

---

## Learning Objective

* Understand each stage of image processing
* Learn how to build a complete computer vision pipeline
* Practice writing code in guided sections

##  Software Used

* Anaconda – Python 3.7
* Jupyter Notebook / VS Code
* OpenCV (cv2)
* NumPy
* Matplotlib

---

##  Algorithm 


- Step 1:  Import Libraries

- Step 2: Read the Image

- Step 3: Convert to Grayscale


- Step 4: Display Images

- Step 5: Thresholding

- Step 6: Region of Interest (ROI)


- Step 7: Edge Detection (Canny)


-  Step 8: Gaussian Blur

- Step 9: Hough Transform
  
- Step 10: Lane Detection Logic

##  Developed By

* **Name:** AMIRTHA VARSHINI M
* **Register No:** 212224230017


## Program
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
```python
# Step 2: Load the image using imread() from cv2 module
image = cv2.imread('lan_img1.jpg')  # Replace 'image.jpg' with your image path

```
```python
# Step 3: Convert the image to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
```
```python
# Input image and grayscale image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
```
```python
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
```
```python
# Step 4: Using Canny operator from cv2, detect the edges of the image
edges = cv2.Canny(gray_image, 50, 150)  # Canny edge detection with threshold values 50 and 150
```
```python
# Canny Edge Detector output
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
```
```python
# Step 5: Using the HoughLinesP(), detect line coordinates for every point in the image
# The parameters of HoughLinesP are: image, resolution, threshold, minLineLength, maxLineGap
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
```
```python
# Step 6: Using a for loop, draw the lines on the original image using the detected coordinates
# The lines variable contains the endpoints of the detected lines
for line in lines:
    x1, y1, x2, y2 = line[0]  # Unpacking the line coordinates
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)  # Draw green lines with thickness of 2
```
```python
# Display the result of Hough Transform (Image with lines)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')
```


##  Expected Output

### Original image
<img width="515" height="321" alt="download" src="https://github.com/user-attachments/assets/dfb6ebe3-2258-4a2c-8c98-77ea1ecb4b89" />

### Grayscale image
<img width="515" height="321" alt="download" src="https://github.com/user-attachments/assets/555b9350-50c1-407b-80c1-73df4d2c9eba" />

### Cannny Edge Detection

<img width="515" height="321" alt="download" src="https://github.com/user-attachments/assets/3b63a796-67ef-4f93-a10b-1ce85f7b1afb" />

### Final lane detection output

<img width="515" height="321" alt="download" src="https://github.com/user-attachments/assets/7568db29-0d98-4421-8ff9-8d20d26d2d30" />

---

## Result

Thus, the lane detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.

---
