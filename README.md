# cv-lab-7
image filtering

# CV Lab – Image Filtering Using Convolution

## 1. Aim
To perform image filtering using a 3×3 convolution kernel in OpenCV and display the filtered image.

## 2. Objective
- To read an image in grayscale format.
- To understand image filtering using a convolution kernel.
- To apply a 3×3 filter to an image using OpenCV.
- To observe the changes in the filtered image.

## 3. Libraries Used
- **OpenCV (`cv2`):** Used for reading and filtering images.
- **NumPy (`numpy`):** Used to create the convolution kernel.
- **Matplotlib (`matplotlib.pyplot`):** Used to display the input and filtered images.

## 4. Input Image

/content/spy x family.jpg

The input image used in this experiment is `spy x family.jpg`. The image is converted into grayscale before applying the filtering operation.

## 5. Description
Image filtering is an image processing technique used to modify an image or extract important features. Convolution is one of the methods used to perform image filtering.

In this experiment, a 3×3 kernel is applied to the grayscale image using the `cv2.filter2D()` function. The kernel is designed to highlight vertical intensity changes and edges in the image.

The input and filtered images are displayed side by side using Matplotlib to observe the filtering effect.

## 6. Algorithm
1. Import OpenCV, NumPy, and Matplotlib libraries.
2. Read the input image in grayscale format.
3. Define a 3×3 convolution kernel.
4. Set the padding and stride variables.
5. Apply image filtering using `cv2.filter2D()`.
6. Display the original grayscale image.
7. Display the filtered image.
8. Compare both images to observe the filtering effect.

## 7. Code
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Give your image path here
image_path = r"/content/spy x family.jpg"

# Read image
image = cv2.imread(image_path, cv2.IMREAD_GRAYSCALE)

# Kernel
kernel = np.array([
    [1, 0, -1],
    [1, 0, -1],
    [1, 0, -1]
])

# Padding and Stride
padding = 1
stride = 1

# Apply convolution
filtered_image = cv2.filter2D(
    image,
    -1,
    kernel,
    borderType=cv2.BORDER_CONSTANT
)

# Display images
plt.figure(figsize=(10, 4))

plt.subplot(1, 2, 1)
plt.imshow(image, cmap="gray")
plt.title("Input Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(filtered_image, cmap="gray")
plt.title("Filtered Image")
plt.axis("off")

plt.show()
```

## 8. Output
The output displays two images:

  
The filtered image highlights vertical intensity changes and edge features.

![Output](output.png)

## 9. Result
Image filtering was successfully performed on the grayscale image using a 3×3 convolution kernel and the OpenCV library.

## 10. Conclusion
Thus, image filtering using convolution was implemented successfully. The experiment demonstrates how a convolution kernel can be used to highlight edges and features in an image.
