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
image=cv2.imread('eiffle.jpg',1)
image=cv2.resize(image,(400,300))
cv2.imshow('Eiffle Tower',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### Output:
![Screenshot 2024-02-20 224729](https://github.com/rakesh9339/COLOR_CONVERSIONS_OF-IMAGE/assets/121115650/97efe288-567c-4ba3-a338-a83c58ae0d84)


### ii)Write the image
```python
import cv2
image=cv2.imread('eiffle.jpg',0)
cv2.imwrite('test.jpg',image)
```

#### Output:
![Screenshot 2024-02-20 224827](https://github.com/rakesh9339/COLOR_CONVERSIONS_OF-IMAGE/assets/121115650/8af9c8ec-ef1a-459a-95a0-9ba3b74fdb06)



### iii)Shape of the Image
```python
import cv2
image=cv2.imread('eiffle.jpg',1)
print(image.shape)
```
#### Output:
![Screenshot 2024-02-20 224859](https://github.com/rakesh9339/COLOR_CONVERSIONS_OF-IMAGE/assets/121115650/5bd3bdf5-5479-48ee-9ae1-6d191eb8f131)


### iv)Access rows and columns
```python
import random
import cv2
image=cv2.imread('eiffle.jpg',1)
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
![Screenshot 2024-02-20 225005](https://github.com/rakesh9339/COLOR_CONVERSIONS_OF-IMAGE/assets/121115650/d3803358-1142-4552-8cc7-96f942dd475d)



### v)Cut and paste portion of image
```python
import cv2
image=cv2.imread('eiffle.jpg',1)
image=cv2.resize(image,(400,400))
tag =image[150:200,110:160]
image[110:160,150:200] = tag
cv2.imshow('image1',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### Output:
![Screenshot 2024-02-20 225045](https://github.com/rakesh9339/COLOR_CONVERSIONS_OF-IMAGE/assets/121115650/79538511-2970-4872-a235-3bf2dd420cfd)



### vi) BGR and RGB to HSV and GRAY
```python
import cv2
img = cv2.imread('eiffle.jpg',1)
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
![Screenshot 2024-02-20 225154](https://github.com/rakesh9339/COLOR_CONVERSIONS_OF-IMAGE/assets/121115650/af69ace8-4e19-4bf1-a570-8d604376cb91)



### vii) HSV to RGB and BGR
```python
import cv2
img = cv2.imread('eiffle.jpg')
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
![Screenshot 2024-02-20 225258](https://github.com/rakesh9339/COLOR_CONVERSIONS_OF-IMAGE/assets/121115650/7775c682-e243-49a5-8f40-0b386c2d974f)



### viii) RGB and BGR to YCrCb

```python
import cv2
img = cv2.imread('eiffle.jpg')
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

![Screenshot 2024-02-20 225341](https://github.com/rakesh9339/COLOR_CONVERSIONS_OF-IMAGE/assets/121115650/db705783-0fb0-4411-a971-86a1c1b1bc20)


### ix) Split and merge RGB Image
```python
import cv2
img = cv2.imread('eiffle.jpg',1)
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
![Screenshot 2024-02-20 225426](https://github.com/rakesh9339/COLOR_CONVERSIONS_OF-IMAGE/assets/121115650/1ddc4dce-40d6-4d5a-be19-39413ba08e8b)


### x) Split and merge HSV Image
```python
import cv2
img = cv2.imread("eiffle.jpg",1)
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

![Screenshot 2024-02-20 225642](https://github.com/rakesh9339/COLOR_CONVERSIONS_OF-IMAGE/assets/121115650/bd20f712-95c8-48d3-a6dd-0e9730e57825)




## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.
