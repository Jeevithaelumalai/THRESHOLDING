# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages

### Step2:
Read the Image and convert to grayscale.

### Step3:
Use Global thresholding to segment the image.

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image.

### Step6:
Display the results.
## Program
#### DEVELOPED BY : JEEVITHA.E
#### REG NO : 212222230054

# Load the necessary packages
```

import cv2
import numpy as np
import matplotlib.pyplot as plt
```

# Read the Image and convert to grayscale
```
image=cv2.imread("dip9.jpeg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("dip9.jpeg",0)
```

# Use Global thresholding to segment the image
```
ret,thresh_white1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_white2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_white3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_white4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_white5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```


# Use Adaptive thresholding to segment the image
```
ret,thresh_white6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```

# Use Otsu's method to segment the image 
```
thresh_white7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_white8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```

# Display the results
```
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_white1,thresh_white2,thresh_white3,thresh_white4,thresh_white5,thresh_white6,thresh_white7,thresh_white8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()




```
## Output

### Original Image
![image](https://github.com/Jeevithaelumalai/THRESHOLDING/assets/118708245/3d44f6bc-59dc-4648-be02-713b19ef9dae)


### Global Thresholding
![image](https://github.com/Jeevithaelumalai/THRESHOLDING/assets/118708245/ca1f8a48-558c-46b7-bdd3-a69bee0d1d0f)
![image](https://github.com/Jeevithaelumalai/THRESHOLDING/assets/118708245/110dcf3a-1856-4c19-9e5f-41fa450026a6)
![image](https://github.com/Jeevithaelumalai/THRESHOLDING/assets/118708245/eedfb179-017e-4805-97a2-5e983a95bcf4)
![image](https://github.com/Jeevithaelumalai/THRESHOLDING/assets/118708245/7af585a6-467b-4a84-829c-eada2292b0af)
![image](https://github.com/Jeevithaelumalai/THRESHOLDING/assets/118708245/67ca55a2-ef70-43aa-ab6e-334172cbad24)


### Adaptive Thresholding
![image](https://github.com/Jeevithaelumalai/THRESHOLDING/assets/118708245/338ed8dc-4a07-40e3-b585-37cf06cab539)
![image](https://github.com/Jeevithaelumalai/THRESHOLDING/assets/118708245/06babee5-9710-4336-9ad9-37100409259a)


### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/Jeevithaelumalai/THRESHOLDING/assets/118708245/92cd0f7c-5f08-424a-8f56-00c8b8c2af85)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

