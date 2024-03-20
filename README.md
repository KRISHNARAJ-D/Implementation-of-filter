# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step 1:
Import necessary libraries: OpenCV, NumPy, and Matplotlib.Read an image, convert it to RGB format, define an 11x11 averaging kernel, and apply 2D convolution filtering.Display the original and filtered images side by side using Matplotlib.

### Step 2:
Define a weighted averaging kernel (kernel2) and apply 2D convolution filtering to the RGB image (image2).Display the resulting filtered image (image4) titled 'Weighted Averaging Filtered' using Matplotlib's imshow function.

### Step 3:

Apply Gaussian blur with a kernel size of 11x11 and standard deviation of 0 to the RGB image (image2).Display the resulting Gaussian-blurred image (gaussian_blur) titled 'Gaussian Blurring Filtered' using Matplotlib's imshow function.
### Step 4:
Apply median blur with a kernel size of 11x11 to the RGB image (image2).Display the resulting median-blurred image (median) titled 'Median Blurring Filtered' using Matplotlib's imshow function.

### Step 5 :
Define a Laplacian kernel (kernel3) and perform 2D convolution filtering on the RGB image (image2).Display the resulting filtered image (image5) titled 'Laplacian Kernel' using Matplotlib's imshow function.
### Step 6 :
Apply the Laplacian operator to the RGB image (image2) using OpenCV's cv2.Laplacian function.Display the resulting image (new_image) titled 'Laplacian Operator' using Matplotlib's imshow function.
## Program:
```
Developed By : KRISHNARAJ D
Register Number:212222230070
```

## 1) SMOOTHING FILTERS

#### i) Using Averaging Filter
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('dip 5.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel = np.ones((11,11), np. float32)/121
image3 = cv2.filter2D(image2, -1, kernel)

plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title('Orignal')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title('Filtered')
plt.axis('off')
```
#### ii) Using Weighted Averaging Filter
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('dip 5.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image4 = cv2.filter2D(image2, -1, kernel2)
plt.imshow(image4)
plt.title('Weighted Averaging Filtered')
```
#### iii) Using Gaussian Filter
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('dip 5.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

gaussian_blur = cv2.GaussianBlur(src=image2, ksize=(11,11), sigmaX=0, sigmaY=0)
plt.imshow(gaussian_blur)
plt.title(' Gaussian Blurring Filtered')
```

#### iv) Using Median Filter
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('dip 5.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

median=cv2.medianBlur (src=image2, ksize=11)
plt.imshow(median)
plt.title(' Median Blurring Filtered')
```

## 2) SHARPENING FILTERS
#### i) Using Laplacian Kernal
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('dip 5.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel3 = np.array([[0,1,0], [1, -4,1],[0,1,0]])
image5 =cv2.filter2D(image2, -1, kernel3)
plt.imshow(image5)
plt.title('Laplacian Kernel')
```
#### ii) Using Laplacian Operator
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('dip 5.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

new_image = cv2.Laplacian (image2, cv2.CV_64F)
plt.imshow(new_image)
plt.title('Laplacian Operator')
```

## OUTPUT:
## 1) SMOOTHING FILTERS

#### i) Using Averaging Filter
![dip 1 -5](https://github.com/KRISHNARAJ-D/Implementation-of-filter/assets/119559695/5cf37ce5-1a7d-4946-9119-e11cf7c00698)



#### ii) Using Weighted Averaging Filter
![dip 2](https://github.com/KRISHNARAJ-D/Implementation-of-filter/assets/119559695/06c0df3f-07c5-4b73-853a-6f5a74b89acd)


#### iii) Using Gaussian Filter
![dip 3](https://github.com/KRISHNARAJ-D/Implementation-of-filter/assets/119559695/52004fc3-db34-474f-9b01-cfc100656b5a)


#### iv) Using Median Filter

![dip 4](https://github.com/KRISHNARAJ-D/Implementation-of-filter/assets/119559695/29280dc0-f55e-4e2e-bfb1-dc1bdcb63e67)

## 2) SHARPENING FILTERS

![dip 5](https://github.com/KRISHNARAJ-D/Implementation-of-filter/assets/119559695/1d5fa2ba-a6dc-4bf1-9237-e0296d96d35c)


#### ii) Using Laplacian Operator
![dip 6](https://github.com/KRISHNARAJ-D/Implementation-of-filter/assets/119559695/506f81d6-5fac-4466-8878-f11206531ef8)



## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
