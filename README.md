## EXP. 5 – IMPLEMENTATION OF FILTERS USING OPENCV

## NAME  : Rubasri R
## REG NO : 212224240139

## Aim

To implement different smoothing and sharpening filters using OpenCV and Python to enhance image quality and display the filtered images for comparison.

## Software Requirements

- Python
- Jupyter Notebook
- OpenCV
- NumPy
- Matplotlib

## Filters Implemented

### Smoothing Filters
1. Average Filter
2. Weighted Average Filter
3. Gaussian Filter
4. Median Filter

### Sharpening Filters
1. Laplacian Kernel
2. Laplacian Operator

## Algorithm

1. Import the required libraries: OpenCV, NumPy, and Matplotlib.
2. Read the input image using `cv2.imread()`.
3. Convert the image from BGR to RGB format.
4. Apply the Average Filter using a custom kernel.
5. Apply the Weighted Average Filter using a weighted kernel.
6. Apply the Gaussian Filter using `cv2.GaussianBlur()`.
7. Apply the Median Filter using `cv2.medianBlur()`.
8. Apply the Laplacian Kernel using `cv2.filter2D()`.
9. Apply the Laplacian Operator using `cv2.Laplacian()`.
10. Display the original and processed images separately.

## Implementation

### 1. Import Libraries

```python
import cv2
import matplotlib.pyplot as plt
import numpy as np
```

### 2. Read the Input Image

```python
image1 = cv2.imread("Image.png")
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)
```

## OUTPUT:
<img width="348" height="413" alt="Screenshot 2026-10-30 160311" src="https://github.com/user-attachments/assets/bd52fc51-cae6-4730-94b8-66ef2f2f1c6c" />


### 3. Average Filter

```python
kernel = np.ones((11,11), np.float32)/169
image3 = cv2.filter2D(image2, -1, kernel)

plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()
```

## OUTPUT:
<img width="791" height="463" alt="image" src="https://github.com/user-attachments/assets/c6a0abf2-206d-4b6a-8dbb-00b4fce48547" />


### 4. Weighted Average Filter

```python
kernel1 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16

image3 = cv2.filter2D(image2, -1, kernel1)

plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```

## OUTPUT:
<img width="613" height="355" alt="image" src="https://github.com/user-attachments/assets/370badd8-1f1b-4482-8fa6-04ab96c942a2" />


### 5. Gaussian Filter

```python
gaussian_blur = cv2.GaussianBlur(image2, (33,33), 0, 0)

plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```

## OUTPUT:
<img width="552" height="334" alt="image" src="https://github.com/user-attachments/assets/f6e095d0-9850-4fb3-a7b0-452e4ac5682c" />


### 6. Median Filter

```python
median = cv2.medianBlur(image2, 13)

plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()
```

## OUTPUT:
<img width="891" height="449" alt="image" src="https://github.com/user-attachments/assets/43a16d16-e42a-4473-8cba-cd9ec387528d" />

### 7. Laplacian Kernel

```python
kernel2 = np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])

image3 = cv2.filter2D(image2, -1, kernel2)

plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```

## OUTPUT:
<img width="600" height="348" alt="image" src="https://github.com/user-attachments/assets/ada8e670-477e-411b-bc8d-a0485fdbacd9" />


### 8. Laplacian Operator

```python
laplacian = cv2.Laplacian(image2, cv2.CV_64F)

plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1,2,2)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```

## Output

<img width="522" height="344" alt="image" src="https://github.com/user-attachments/assets/859bfa94-8e35-4ee7-bbe1-7c626f75f030" />


## Result

Thus, different smoothing and sharpening filters were successfully implemented using OpenCV and Python. Smoothing filters reduce noise, while sharpening filters enhance image edges and details.
