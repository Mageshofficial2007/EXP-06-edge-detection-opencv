# EXP-06-edge-detection-opencv

## NAME : MAGESH BOOPATHI.M
## REG.NO : 212224230145


## AIM
This project demonstrates various edge detection techniques using Python and OpenCV. Different edge detection operators are applied to identify object boundaries, intensity changes, and important image features for computer vision and image processing applications.

## Features

- Load and display an input image
- Convert image to grayscale
- Apply Sobel Edge Detection
- Apply Prewitt Edge Detection
- Apply Roberts Edge Detection
- Apply Laplacian Edge Detection
- Apply Canny Edge Detection
- Display all edge-detected outputs for comparison

---

## Technologies Used

- Python 3.7+
- OpenCV (`cv2`)
- NumPy
- Matplotlib
- Jupyter Notebook / VS Code

---

## Edge Detection Techniques

### Sobel Edge Detector
Detects edges in horizontal and vertical directions using image gradients.

### Laplacian Edge Detector
Uses second-order derivatives to detect rapid intensity variations.

### Canny Edge Detector
A multi-stage edge detection technique that produces clean and thin edges.

---

## Algorithm

1. Import the required libraries
2. Read the input image using OpenCV
3. Convert the image to grayscale
4. Apply Gaussian Blur for noise reduction
5. Apply Sobel edge detection
6. Apply Prewitt edge detection
7. Apply Roberts edge detection
8. Apply Laplacian edge detection
9. Apply Canny edge detection
10. Display all outputs using Matplotlib

---
## Applications

- Computer Vision
- Medical Image Processing
- Object Detection
- Image Segmentation
- Autonomous Systems
- Surveillance Systems

---
## programm
## EDGE-DETECTION
    ### •SOBEL EDGE DETECTOR
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load the image
image = cv2.imread('Chess.jpg')


# Convert the image to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Syntex
# dst = cv.Sobel(src, ddepth, dx, dy[, dst[, ksize[, scale[, delta[, borderType]]]]])

# Apply Sobel operator

sobelx  = cv2.Sobel(src = gray_image, ddepth = cv2.CV_64F, dx = 1, dy = 0, ksize = 3) 
sobely  = cv2.Sobel(src = gray_image, ddepth = cv2.CV_64F, dx = 0, dy = 1, ksize = 3)

sobelx = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=3)  # Sobel X
sobely = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=3)  # Sobel Y
sobel_combined = cv2.magnitude(sobelx, sobely)

plt.figure(figsize = (12, 16))
plt.subplot(321); plt.axis('on'); plt.imshow(image[:,:,::-1]); plt.title('Original')
plt.subplot(322); plt.axis('on'); plt.imshow(gray_image, cmap='gray');plt.title('Grayscale') 
plt.subplot(323); plt.axis('on'); plt.imshow(sobelx);plt.title('Sobel-X Edge Map')
plt.subplot(324); plt.axis('on'); plt.imshow(sobely);plt.title('Sobel-Y Edge Map');

```
## output
<img width="1147" height="830" alt="Screenshot 2026-08-08 192144" src="https://github.com/user-attachments/assets/0841acff-6124-4a87-a81c-5600bc76dfc8" />

```python
plt.figure(figsize = (12, 16))
plt.axis('off'); plt.imshow(sobel_combined, cmap='gray' ); plt.title('sobel_combined ');
```
## output
<img width="1051" height="779" alt="Screenshot 2026-08-08 192206" src="https://github.com/user-attachments/assets/2de39d51-72a9-4959-8ac8-5bb7d899fbc2" />

## LAPLACIAN EDGE DETECTOR
```python
# Convert the image to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Apply Laplacian operator
laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)
plt.figure(figsize = (12, 16))
plt.subplot(121); plt.axis('off'); plt.imshow(gray_image, cmap='gray'); plt.title('Inputimage (Gray Image)')

plt.subplot(122);plt.imshow(laplacian, cmap='gray');plt.axis('off'); plt.title('Output Image (laplacian)');
```

## output
<img width="1034" height="378" alt="Screenshot 2026-08-08 192221" src="https://github.com/user-attachments/assets/aea7cf5f-fd21-4a99-883e-59634aa9e560" />

## CANNY EDGE DETECTOR

```python

img = cv2.imread('urban.jpg')

# Convert to grayscale.
img_gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

edges = cv2.Canny(img_gray, threshold1 = 180, threshold2 = 200)

plt.figure(figsize = (12,16))
plt.subplot(221); plt.axis("off"); plt.imshow(img[:,:,::-1]); plt.title('Original') 
plt.subplot(222); plt.axis("off"); plt.imshow(img_gray, cmap='gray');      plt.title('Grayscale')
```

## output
<img width="1098" height="355" alt="Screenshot 2026-08-08 192301" src="https://github.com/user-attachments/assets/0ae7c31d-ea99-4f5c-b207-12491cc93f68" />

```python
plt.figure(figsize = (12,16))
plt.axis("off"); plt.imshow(edges,cmap='gray');plt.title('Canny Edge Map');
```

<img width="1015" height="633" alt="Screenshot 2026-08-08 192313" src="https://github.com/user-attachments/assets/29498584-e602-43fe-8a05-6cc38b9c0c7b" />

## Result

The implementation successfully demonstrates multiple edge detection techniques using OpenCV. Each operator highlights edges differently based on gradient and intensity variations, helping improve feature extraction and image analysis.

