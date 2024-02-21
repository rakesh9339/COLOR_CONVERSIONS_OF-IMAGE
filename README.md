# COLOR_CONVERSIONS_OF-IMAGE
## AIM
To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Choose an image and save it as a filename.jpg ,
### Step2:
Use imread(filename, flags) to read the file.
### Step3:
Use imshow(window_name, image) to display the image.
### Step4:
Use imwrite(filename, image) to write the image.
### Step5:
End the program and close the output image windows.
### Step6:
Convert BGR and RGB to HSV and GRAY
### Step7:
Convert HSV to RGB and BGR
### Step8:
Convert RGB and BGR to YCrCb
### Step9:
Split and Merge RGB Image
### Step10:
Split and merge HSV Image

##### Program:
### Developed By: Rakesh 
### Register Number: 212222230115

### i) Read and display the image
```python
import cv2
image=cv2.imread('pig.jpg',1)
image=cv2.resize(image,(400,300))
cv2.imshow('Piggy-Friends',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### Output:
![Screenshot 2024-02-15 165803](https://github.com/DARIOGEORGE/COLOR_CONVERSIONS_OF-IMAGE/assets/118704873/6a07ffe6-2794-48a7-93ae-c0a1113380be)

### ii)Write the image
```python
import cv2
image=cv2.imread('pig.jpg',0)
cv2.imwrite('test.jpg',image)
```

#### Output:
![Screenshot 2024-02-15 165920](https://github.com/DARIOGEORGE/COLOR_CONVERSIONS_OF-IMAGE/assets/118704873/297cf426-9b6a-4bef-932b-0c425b490d90)


### iii)Shape of the Image
```python
import cv2
image=cv2.imread('pig.jpg',1)
print(image.shape)
```
#### Output:
![Screenshot 2024-02-15 170006](https://github.com/DARIOGEORGE/COLOR_CONVERSIONS_OF-IMAGE/assets/118704873/21485061-53a9-46bb-b3e1-4e404a8d7278)

### iv)Access rows and columns
```python
import random
import cv2
image=cv2.imread('pig.jpg',1)
image=cv2.resize(image,(400,400))
for i in range (150,200):
    for j in range(image.shape[1]):
        image[i][j]=[random.randint(0,255),
        random.randint(0,255),
        random.randint(0,255)] 
cv2.imshow('part image',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

#### Output:
![Screenshot 2024-02-15 170055](https://github.com/DARIOGEORGE/COLOR_CONVERSIONS_OF-IMAGE/assets/118704873/7330e096-908c-46f9-a410-4adfe4ea2f5d)



### v)Cut and paste portion of image
```python
import cv2
image=cv2.imread('pig.jpg',1)
image=cv2.resize(image,(400,400))
tag =image[150:200,110:160]
image[110:160,150:200] = tag
cv2.imshow('image1',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### Output:
![Screenshot 2024-02-15 170141](https://github.com/DARIOGEORGE/COLOR_CONVERSIONS_OF-IMAGE/assets/118704873/23ecb4d9-6c0a-465e-a201-3dd7d1d6a131)



### vi) BGR and RGB to HSV and GRAY
```python
import cv2
img = cv2.imread('pig.jpg',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)

hsv1 = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('BGR2HSV',hsv1)

hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsv2)

gray1 = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow('BGR2GRAY',gray1)

gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',gray2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### Output:
![Screenshot 2024-02-15 170429](https://github.com/DARIOGEORGE/COLOR_CONVERSIONS_OF-IMAGE/assets/118704873/11e1b4fc-0c2c-4af5-82aa-eb5c4e1a777f)



### vii) HSV to RGB and BGR
```python
import cv2
img = cv2.imread('pig.jpg')
img = cv2.resize(img,(300,200))

img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)

RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)

BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### Output:
![Screenshot 2024-02-15 170657](https://github.com/DARIOGEORGE/COLOR_CONVERSIONS_OF-IMAGE/assets/118704873/2d46eb3c-f370-466c-8c49-03a38c44737f)



### viii) RGB and BGR to YCrCb

```python
import cv2
img = cv2.imread('pig.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### Output:
![Screenshot 2024-02-15 170819](https://github.com/DARIOGEORGE/COLOR_CONVERSIONS_OF-IMAGE/assets/118704873/97ff62a8-494a-4bc6-b0c6-356882618722)



### ix) Split and merge RGB Image
```python
import cv2
img = cv2.imread('pig.jpg',1)
img = cv2.resize(img,(300,200))

R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]

cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)

merged = cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### Output:
![Screenshot 2024-02-15 171013](https://github.com/DARIOGEORGE/COLOR_CONVERSIONS_OF-IMAGE/assets/118704873/9a76446f-55ef-4334-b83f-5ba4e96fddaf)


### x) Split and merge HSV Image
```python
import cv2
img = cv2.imread("pig.jpg",1)
img = cv2.resize(img,(200,200))
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)

H,S,V=cv2.split(img)

cv2.imshow('Hue',H)
cv2.imshow('Saturation',S)
cv2.imshow('Value',V)

merged = cv2.merge((H,S,V))
cv2.imshow('Merged',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### Output:

![Screenshot 2024-02-15 171154](https://github.com/DARIOGEORGE/COLOR_CONVERSIONS_OF-IMAGE/assets/118704873/64de5fd5-1da7-4b9f-b077-102845904712)




## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.
