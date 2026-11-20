# EXPERIMENT 8 – THRESHOLDING
## Name : Raha Priya Dharshini M
## Reg No.:212224240124


## Aim
To implement different image thresholding techniques using OpenCV and Python, including Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding.

## Software Requirements
- Python
- OpenCV
- NumPy
- Matplotlib
- Jupyter Notebook


## Procedure

1. Import the required libraries: OpenCV, NumPy, and Matplotlib.
2. Read the input image using `cv2.imread()`.
3. Convert the original image into a grayscale image using `cv2.cvtColor()`.
4. Apply **Global Thresholding** using `cv2.threshold()` with a threshold value of 127.
5. Apply **Adaptive Thresholding** using `cv2.adaptiveThreshold()` with Gaussian adaptive thresholding.
6. Apply **Otsu's Thresholding** using `cv2.THRESH_OTSU`.
7. Display the original image and all three thresholded images using Matplotlib.
8. Compare the results of the different thresholding techniques.

## Code:
```

import cv2
import numpy as np
import matplotlib.pyplot as plt

# Step 1: Read the image and convert to grayscale
image = cv2.imread('myfoto.jpg')

if image is None:
    raise FileNotFoundError("myfoto.jpg not found")

gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Step 2: Apply Global Thresholding
_, global_thresholded = cv2.threshold(
    gray_image, 127, 255, cv2.THRESH_BINARY
)

# Step 3: Apply Adaptive Thresholding
adaptive_thresholded = cv2.adaptiveThreshold(
    gray_image,
    255,
    cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
    cv2.THRESH_BINARY,
    11,
    2
)

# Step 4: Apply Otsu's Thresholding
_, otsu_thresholded = cv2.threshold(
    gray_image,
    0,
    255,
    cv2.THRESH_BINARY + cv2.THRESH_OTSU
)

# Step 5: Display Original Image
plt.figure(figsize=(12, 9))

plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Original Image")
plt.axis('off')

# Step 6: Display Global Thresholding
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')

# Step 7: Display Adaptive Thresholding
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')

# Step 8: Display Otsu's Method
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')

plt.tight_layout()
plt.show()
```

## Output

**1. Original Image and Thresholding Results**

<img width="1356" height="302" alt="image" src="https://github.com/user-attachments/assets/22af8712-f21c-4595-b991-0546b5286f24" />


**2. Final Output**

<img width="1350" height="587" alt="image" src="https://github.com/user-attachments/assets/e3afc2c0-55fc-4318-8e30-11dac71b212d" />


## Result
Thus, Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding were successfully implemented using OpenCV and Python.
