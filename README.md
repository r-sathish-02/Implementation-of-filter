# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
## Step 1:
Import necessary libraries: OpenCV, NumPy, and Matplotlib.Read an image, convert it to RGB format, define an 11x11 averaging kernel, and apply 2D convolution filtering.Display the original and filtered images side by side using Matplotlib.

## Step 2:
Define a weighted averaging kernel (kernel2) and apply 2D convolution filtering to the RGB image (image2).Display the resulting filtered image (image4) titled 'Weighted Averaging Filtered' using Matplotlib's imshow function.

## Step 3:
Apply Gaussian blur with a kernel size of 11x11 and standard deviation of 0 to the RGB image (image2).Display the resulting Gaussian-blurred image (gaussian_blur) titled 'Gaussian Blurring Filtered' using Matplotlib's imshow function.

## Step 4:
Apply median blur with a kernel size of 11x11 to the RGB image (image2).Display the resulting median-blurred image (median) titled 'Median Blurring Filtered' using Matplotlib's imshow function.

## Step 5 :
Define a Laplacian kernel (kernel3) and perform 2D convolution filtering on the RGB image (image2).Display the resulting filtered image (image5) titled 'Laplacian Kernel' using Matplotlib's imshow function.

## Step 6 :

Apply the Laplacian operator to the RGB image (image2) using OpenCV's cv2.Laplacian function.Display the resulting image (new_image) titled 'Laplacian Operator' using Matplotlib's imshow function.

## Program:

### Developed By   : Sathish R
### Register Number:212222230138

### 1. Smoothing Filters

### i) Using Averaging Filter
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('hachiko.jpg')
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
### ii) Using Weighted Averaging Filter
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('hachiko.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image4 = cv2.filter2D(image2, -1, kernel2)
plt.imshow(image4)
plt.title('Weighted Averaging Filtered')





```
### iii) Using Gaussian Filter
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('hachiko.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

gaussian_blur = cv2.GaussianBlur(src=image2, ksize=(11,11), sigmaX=0, sigmaY=0)
plt.imshow(gaussian_blur)
plt.title(' Gaussian Blurring Filtered')








```

### i) Using Laplacian Kernal
```import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('hachiko.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel3 = np.array([[0,1,0], [1, -4,1],[0,1,0]])
image5 =cv2.filter2D(image2, -1, kernel3)
plt.imshow(image5)
plt.title('Laplacian Kernel')









```
### ii) Using Laplacian Operator
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('hachiko.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

new_image = cv2.Laplacian (image2, cv2.CV_64F)
plt.imshow(new_image)
plt.title('Laplacian Operator')









```

## OUTPUT:
### 1. Smoothing Filters
### i) Using Averaging Filter
![image](https://github.com/naren2704/Implementation-of-filter/assets/118706984/e6937eb5-d264-4212-9c74-c8cf698bb5d4)

### ii) Using Weighted Averaging Filter
![image](https://github.com/naren2704/Implementation-of-filter/assets/118706984/8c9e6e77-2cf7-468a-8b10-700dfa201daa)

### iii) Using Gaussian Filter
![image](https://github.com/naren2704/Implementation-of-filter/assets/118706984/f6c5ec16-e304-4c2c-86ef-b34773196810)


### iv) Using Median Filter
![image](https://github.com/naren2704/Implementation-of-filter/assets/118706984/c9fcf12f-8d11-4c50-befc-035e06fc7747)


### 2. Sharpening Filters

### i) Using Laplacian Kernal
![image](https://github.com/naren2704/Implementation-of-filter/assets/118706984/20033a94-e425-4c7f-952d-3bf2586ce56d)


### ii) Using Laplacian Operator
![image](https://github.com/naren2704/Implementation-of-filter/assets/118706984/fa824aab-7fa0-455e-a0be-f84046baa720)


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
