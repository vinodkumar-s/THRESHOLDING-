## EX-08 THRESHOLDING
### Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.


### Software Required
1. Anaconda - Python 3.7
2. OpenCV
 
### Algorithm
#### Step1:
Load the necessary packages.
#### Step2:
Read the Image and convert to grayscale.
#### Step3:
Use Global thresholding to segment the image.
#### Step4:
Use Adaptive thresholding to segment the image.
#### Step5:
Use Otsu's method to segment the image and display the results.
### Program
```python
DEVELOPED BY: VINOD KUMAR S
REGISTER NO: 212222240116
```
#### Load the necessary packages
```python
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
#### Read the Image and convert to grayscale
```python
image = cv2.imread("CAT.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("CAT.jpg",0)
```
#### Use Global thresholding to segment the image
```python
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
#### Use Adaptive thresholding to segment the image
```python
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
#### Use Otsu's method to segment the image 
```python
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
#### Display the results
```python
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
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

### Output
#### Original Image
![Screenshot 2024-04-12 214136](https://github.com/vinodkumar-s/THRESHOLDING-/assets/113497226/4af0a5b1-7d6c-4d64-8628-782501502439)

#### Global Thresholding

![Screenshot 2024-04-12 214232](https://github.com/vinodkumar-s/THRESHOLDING-/assets/113497226/c9f35965-b5bc-4618-9e40-18b876d111ee)

![Screenshot 2024-04-12 214318](https://github.com/vinodkumar-s/THRESHOLDING-/assets/113497226/d275697d-473a-4989-a726-46d947fdce78)

![Screenshot 2024-04-12 214334](https://github.com/vinodkumar-s/THRESHOLDING-/assets/113497226/edd1f6c4-d2c5-4554-8f25-ad7ced57cd1f)

![Screenshot 2024-04-12 214351](https://github.com/vinodkumar-s/THRESHOLDING-/assets/113497226/721d3df4-3e29-4f04-84da-58c108381c94)

![Screenshot 2024-04-12 214503](https://github.com/vinodkumar-s/THRESHOLDING-/assets/113497226/98725933-305e-424c-ac56-d5b8ca5ae367)

#### Adaptive Thresholding

![Screenshot 2024-04-12 214525](https://github.com/vinodkumar-s/THRESHOLDING-/assets/113497226/4a90a844-6818-4dcd-bde7-b03d0daf73a9)

![Screenshot 2024-04-12 214540](https://github.com/vinodkumar-s/THRESHOLDING-/assets/113497226/55065218-c443-47a6-b5a8-33b1cad9c3cc)

#### Optimum Global Thesholding using Otsu's Method
![Screenshot 2024-04-12 214601](https://github.com/vinodkumar-s/THRESHOLDING-/assets/113497226/6dab3a68-f0eb-45d9-893c-da14df47a784)


### Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.


