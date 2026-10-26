# Experiment-3-Record-Histogram-processing
# Developed By: BUSHPIKA C
# Register Number: 212225230038


## Aim

To obtain a histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255. Also, write a Python program using OpenCV to perform histogram equalization.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Read the grayscale and color images using the `cv2.imread()` function.

### Step 2
Display the grayscale and color images using the `imshow()` function.

### Step 3
Use the `cv2.calcHist()` function to calculate the frequency of pixel intensities in the grayscale image.

### Step 4
Use the `cv2.calcHist()` function to calculate the histograms of the Blue, Green, and Red channels of the color image.

### Step 5
Plot and display the histograms of the grayscale image and color image.

## Program

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('bush.jpeg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()

img_eq = cv2.equalizeHist(img)

plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')

plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()

img = cv2.imread('bush.jpeg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()

plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()

plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()

plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```

## Output

### Input Grayscale Image

<img width="461" height="605" alt="image" src="https://github.com/user-attachments/assets/175a14a3-b9f6-4631-b865-0349945a1a9d" />


### Input Grayscale Image Range

<img width="915" height="545" alt="image" src="https://github.com/user-attachments/assets/cec99458-6212-46ed-a1b7-fa8f2ac9d756" />


### Input Grayscale Image Equalized Histogram

<img width="858" height="617" alt="image" src="https://github.com/user-attachments/assets/c4be2af6-03ec-42ab-ae60-940dbe4b1ebd" />


### Histogram of Grayscale Image and Color Image Channels


<img width="461" height="543" alt="image" src="https://github.com/user-attachments/assets/997afd48-7ad9-4aa2-b2b9-160dc854bd97" />


### Original Image

<img width="311" height="495" alt="image" src="https://github.com/user-attachments/assets/db02607d-0fff-47dd-8152-3412655cdd0a" />


### Equalized Image


<img width="385" height="542" alt="image" src="https://github.com/user-attachments/assets/b08f5490-789b-45d7-a7b8-d4ce4e2c8b56" />


### Equalized Histogram

<img width="817" height="555" alt="image" src="https://github.com/user-attachments/assets/999a5939-b747-490a-98d9-12632fa41595" />


### Final Output of Original Image and Equalized 

<img width="417" height="511" alt="image" src="https://github.com/user-attachments/assets/29fd96d2-2c8b-43f3-8f8d-5e523a9f810b" />

<img width="320" height="528" alt="image" src="https://github.com/user-attachments/assets/d839116f-679a-41f5-9fd4-04f14bbc7eac" />


### Final Output of Original Image and its Histogram Equalized

<img width="660" height="407" alt="image" src="https://github.com/user-attachments/assets/c8c0867a-539e-4059-80e4-4966ae49ff25" />

<img width="686" height="450" alt="image" src="https://github.com/user-attachments/assets/ddc67985-a394-42bb-a168-70170480310e" />


## Result

Thus, the histogram showing the frequency of pixel intensities ranging from 0 to 255 was obtained for the grayscale image and the color image using OpenCV.
