# Implementation-of-Erosion-and-Dilation
## Aim
To implement Erosion and Dilation using Python and OpenCV.
## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step-1:
Create a black image of size 100x600 pixels.
### Step-2:
Use a specified font to write the word "Lifestyle" on the image at a defined position.
### Step-3:
Show the image containing the text without axis labels.
### Step-4:
Define a structuring element for morphological operations (e.g., a cross-shaped kernel).
### Step-5:
Apply erosion to the image using the defined structuring element to reduce the size of white regions.
### Step-6:
Apply dilation to the original image using the same structuring element to increase the size of white regions.
 
## Program:
```
Developed By: Samakash R S
Reg.No: 212223230182
```
``` Python
# Import the necessary packages
import numpy as np
import cv2
import matplotlib.pyplot as plt

# Create the Text using cv2.putText
def load_img():
    blank_img = np.zeros((600,950), dtype=np.uint8)
    front = cv2.FONT_HERSHEY_SIMPLEX
    cv2.putText(blank_img, text='SAMAKASH', org=(50, 300), fontFace=front, 
                fontScale=5, color=(255, 255, 255), thickness=25, lineType=cv2.LINE_AA)
    return blank_img

def display_img(img):
    fig=plt.figure(figsize=(12,10))
    ax=fig.add_subplot(111)
    ax.imshow(img,cmap='gray')
    plt.show()

img = load_img()
display_img(img)
```
![alt text](<Screenshot 2025-05-06 082947.png>)

```
# Create the structuring element
kernal = np.ones((5,5),dtype=np.uint8)
```
```
# Erode the image

ero = cv2.erode(img,kernal,iterations = 2)
display_img(ero)

```
### Display the Eroded Image

![alt text](<Screenshot 2025-05-06 082959.png>)

```
# Dilate the image
dil = cv2.dilate(img,kernal,iterations = 3)
display_img(dil)

```
### Display the Dilated Image

![alt text](<Screenshot 2025-05-06 083008.png>)

## Result
Thus the generated text image is eroded and dilated using python and OpenCV.
