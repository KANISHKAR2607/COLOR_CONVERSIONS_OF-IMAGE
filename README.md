# COLOR_CONVERSIONS_OF-IMAGE

## AIM


#### To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv) To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.


## Software Required:

### Anaconda - Python 3.7

## Algorithm:


### Step 1

Choose an image and save it as a filename.jpg 

### Step 2

Use imread(filename, flags) to read the file.


### Step 3

Use imshow(window_name, image) to display the image.

### Step 4

Use imwrite(filename, image) to write the image.

### Step 5

End the program and close the output image windows.


### Step 6

Convert BGR and RGB to HSV and GRAY

### Step 7

Convert HSV to RGB and BGR

### Step 8

Convert RGB and BGR to YCrCb

### Step 9

Split and Merge RGB Image


### Step 10

Split and merge HSV Image

 python
Developed By: KANISHKAR M
Register Number: 212222240044


#### IMAGE 

![WhatsApp Image 2024-02-13 at 08 22 58_654ca387](https://github.com/KANISHKAR2607/COLOR_CONVERSIONS_OF-IMAGE/assets/118886772/c9ec43be-c35a-4cbb-91e4-abaea3ee631b)


## Program:


### (i) Read and display the image
``` py
#Read and display the image
import cv2
image=cv2.imread('exp1.jpg',1)
image=cv2.resize(image,(200,325))
cv2.imshow('KANISHKAR',image)
cv2.waitKey(0)
cv2.destroyAllWindows()

```

### Output:

![image](https://github.com/KANISHKAR2607/COLOR_CONVERSIONS_OF-IMAGE/assets/118886772/4afb154d-9e78-4981-9f4e-2a21f0cb341a)


## Program:

### (ii) Write the image

```py
#Write the image
import cv2
image=cv2.imread('exp1.jpg',0)
cv2.imwrite('demos.jpg',image)
```

### Output

![image](https://github.com/KANISHKAR2607/COLOR_CONVERSIONS_OF-IMAGE/assets/118886772/462c4bb1-d793-468b-842e-9f2fa5e0fdfb)


## Program:

### (iii) Shape of the Image

```py
#Shape of the Image
import cv2
image=cv2.imread('exp1.jpg',1)
print(image.shape)

```

### Output

![image](https://github.com/KANISHKAR2607/COLOR_CONVERSIONS_OF-IMAGE/assets/118886772/a8e6ab3b-d8ec-45ba-8beb-b11bd4478fa4)



## Program:

### (iv) Access rows and columns
```py
#Access rows and columns
import random
import cv2
image=cv2.imread('exp1.jpg',1)
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

### Output

![image](https://github.com/KANISHKAR2607/COLOR_CONVERSIONS_OF-IMAGE/assets/118886772/7b594820-61e3-4884-bd31-96c959a4bd39)



## Program:

### (v) Cut and paste portion of image
```py
#Cut and paste portion of image
import cv2
image=cv2.imread('exp1.jpg',1)
image=cv2.resize(image,(400,400))
tag =image[150:200,110:160]
image[110:160,150:200] = tag
cv2.imshow('partimage1',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### Output

![image](https://github.com/KANISHKAR2607/COLOR_CONVERSIONS_OF-IMAGE/assets/118886772/70e5f610-c3e5-43fc-83c8-427150297f15)


## Program:

### (vi) BGR and RGB to HSV and GRAY
```py
#BGR and RGB to HSV and GRAY
import cv2
img = cv2.imread('exp1.jpg',1)
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
### Original Image

![image](https://github.com/KANISHKAR2607/COLOR_CONVERSIONS_OF-IMAGE/assets/118886772/945f9cfa-4ae4-4efe-a50e-c5988dfa4119)


### Output

![image](https://github.com/KANISHKAR2607/COLOR_CONVERSIONS_OF-IMAGE/assets/118886772/7db5be3c-41a0-4fb0-8061-5ed7423f2632)


## Program:

### (vii) HSV to RGB and BGR

```py
#HSV to RGB and BGR
import cv2
img = cv2.imread('exp1.jpg')
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

### Original HSV

![image](https://github.com/KANISHKAR2607/COLOR_CONVERSIONS_OF-IMAGE/assets/118886772/44529ae0-3956-4018-a138-35c3a427b41e)


### Output


![image](https://github.com/KANISHKAR2607/COLOR_CONVERSIONS_OF-IMAGE/assets/118886772/d58e2620-c2ff-4371-9709-82327e1c16aa)


## Program:

### (viii) RGB and BGR to YCrCb
```py

#RGB and BGR to YCrCb
import cv2
img = cv2.imread('exp1.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```

### Output


![image](https://github.com/KANISHKAR2607/COLOR_CONVERSIONS_OF-IMAGE/assets/118886772/3856ba4c-a2c3-44e2-94e5-4a49a913e14e)


## Program:

### (ix) Split and merge RGB Image
```py
#Split and merge RGB Image
import cv2
img = cv2.imread('exp1.jpg',1)
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
### Output

#### Channels

![image](https://github.com/KANISHKAR2607/COLOR_CONVERSIONS_OF-IMAGE/assets/118886772/4ad7d95a-3c50-443f-b342-7f5ead729520)


#### Merged RGB


![image](https://github.com/KANISHKAR2607/COLOR_CONVERSIONS_OF-IMAGE/assets/118886772/1d219980-ac93-4940-ab20-deb47f5906a8)


## Program:

### (x) Split and merge HSV Image
```py
#Split and merge HSV Image
import cv2
img = cv2.imread("exp1.jpg",1)
img = cv2.resize(img,(300,200))
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

### Output

### Merged HSV

![image](https://github.com/KANISHKAR2607/COLOR_CONVERSIONS_OF-IMAGE/assets/118886772/20844066-4618-4bd1-ae49-5457f89c33e1)



### Splitted

![image](https://github.com/KANISHKAR2607/COLOR_CONVERSIONS_OF-IMAGE/assets/118886772/f4b282bb-e555-4e70-b417-37ae828b1daa)



## Result:
#### Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.
