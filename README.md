# EX. NO. 10

# OPENING AND CLOSING OPERATIONS USING OPENCV

## AIM

To write a Python program using OpenCV to perform morphological Opening and Closing operations on an image.

The program performs the following operations:

- Morphological Opening
- Morphological Closing

## SOFTWARE REQUIRED

1. Anaconda – Python 3.7
2. Jupyter Notebook / VS Code
3. OpenCV (cv2)
4. NumPy
5. Matplotlib

## ALGORITHM

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Create a binary input image containing foreground objects.

### Step 3:
Display the original image.

### Step 4:
Create a structuring element (kernel) of suitable size.

### Step 5: Opening Operation
- Apply the Opening operation using the structuring element.
- Opening consists of Erosion followed by Dilation.
- Remove small foreground noise while preserving larger objects.
- Display the original and opened images.

### Step 6: Closing Operation
- Apply the Closing operation using the structuring element.
- Closing consists of Dilation followed by Erosion.
- Fill small holes and gaps within foreground objects.
- Display the original and closed images.

### Step 7:
Compare the original, opened, and closed images.

## PROGRAM

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Create a blank image
img = np.zeros((300, 600), dtype=np.uint8)

# Draw white shapes on the image
cv2.rectangle(img, (100, 80), (250, 220), 255, -1)
cv2.circle(img, (400, 150), 70, 255, -1)

# Display original image
plt.figure(figsize=(8, 4))
plt.imshow(img, cmap="gray")
plt.title("Original Image")
plt.axis("off")
plt.show()

# Create a kernel
kernel = np.ones((5, 5), np.uint8)

# Opening operation
opening = cv2.morphologyEx(img, cv2.MORPH_OPEN, kernel)

# Display opening
plt.figure(figsize=(8, 4))
plt.imshow(opening, cmap="gray")
plt.title("Opening")
plt.axis("off")
plt.show()

# Closing operation
closing = cv2.morphologyEx(img, cv2.MORPH_CLOSE, kernel)

# Display closing
plt.figure(figsize=(8, 4))
plt.imshow(closing, cmap="gray")
plt.title("Closing")
plt.axis("off")
plt.show()

# Compare all images
images = [img, opening, closing]
titles = ["Original Image", "Opening", "Closing"]

plt.figure(figsize=(15, 5))

for i in range(len(images)):
    plt.subplot(1, 3, i + 1)
    plt.imshow(images[i], cmap="gray")
    plt.title(titles[i])
    plt.axis("off")

plt.tight_layout()
plt.show()
```

## DEVELOPED BY

**Name:** Mohammed Ameer F

**Register No:** 212225040248

## OUTPUT

### 1. Original Image

- The input image is displayed
  <img width="1061" height="593" alt="image" src="https://github.com/user-attachments/assets/e6815aaa-5a58-4bf9-b660-4f2f3d2c1e33" />


- The image contains foreground objects on a black background.
- The original image serves as the source for morphological processing.

### 2. Opening Operation

- Original image and opened image are displayed side by side.
  <img width="1298" height="370" alt="image" src="https://github.com/user-attachments/assets/a6b3234f-e8f4-4bec-8878-e64f8a5866fc" />

- Opening removes small foreground noise.
- Thin protrusions and isolated pixels are eliminated.
- Object boundaries become smoother.

### 3. Closing Operation

- Original image and closed image are displayed side by side.
  <img width="1383" height="428" alt="image" src="https://github.com/user-attachments/assets/f4a271dc-71eb-48ba-a868-570631ec6510" />

- Closing fills small holes and gaps.
- Broken regions may be connected.
- Object boundaries become more continuous.

### 4. Comparison of All Operations

- The original, opened, and closed images are displayed side by side.
  <img width="1325" height="265" alt="image" src="https://github.com/user-attachments/assets/ba102124-d63b-42fd-9c05-03466d9a57cd" />

- The effects of both operations can be compared.

## APPLICATIONS

### Opening

- Noise removal in binary images.
- Separation of connected objects.
- Preprocessing for object detection.

### Closing

- Filling small holes in objects.
- Connecting nearby components.
- Enhancing segmented regions.

## ADVANTAGES

### Opening

- Removes unwanted foreground noise.
- Preserves major object structures.
- Improves segmentation quality.

### Closing

- Restores object continuity.
- Eliminates small background gaps.
- Improves object representation.

## RESULT

Thus, the morphological operations **Opening** and **Closing** are successfully implemented using OpenCV.
