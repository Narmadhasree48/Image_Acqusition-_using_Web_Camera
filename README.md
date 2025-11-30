# Image_Acqusition-_using_Web_Camera
## Aim

To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
## Step 1:
Import OpenCV Package.

## Step 2:
Capture Video from Webcam. Use VideoCapture(0) to access the webcam and start capturing video.
## Step 3:Use cv2.imread to read the video or image
<br>

## Step 4:Use cv2.imshow to show the video
<br>

### Step 5:End the program and close the output video window by pressing 'q'.
<br>

## Program:
``` Python
### Developed By: NARMADHA SREE S
### Register No: 212223240105

## i) Write the frame as JPG file

import cv2
videoCaptureObject = cv2.VideoCapture(0)

while (True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("NewPicture.jpg",frame)
    
    result = False
videoCaptureObject.release()
cv2.DestroyAllWindows()


## ii) Display the video

import cv2
videoCaptureObject = cv2.VideoCapture(0)

while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow('myimage',frame)
    if cv2.waitKey(1) == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()





## iii) Display the video by resizing the window


import cv2
import numpy as np
cap  = cv2.VideoCapture(0)
while True:
    ret,frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8)
    small_frame = cv2.resize(frame,(0,0),fx =0.5, fy = 0.5)
    image[:height//2, :width//2]=small_frame
    image[height//2:, :width//2]=small_frame
    image[:height//2, width//2:]=small_frame
    image[height//2:, width//2:]=small_frame
    cv2.imshow('myimage',image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()



## iv) Rotate and display the video



import cv2
import numpy as np
cap  = cv2.VideoCapture(0)
while True:
    ret,frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8)
    small_frame = cv2.resize(frame,(0,0),fx =0.5, fy = 0.5)
    image[:height//2, :width//2]=cv2.rotate(small_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=small_frame
    image[:height//2, width//2:]=small_frame
    image[height//2:, width//2:]=cv2.rotate(small_frame,cv2.ROTATE_180)
    cv2.imshow('myimage',image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()





```
## Output

### i) Write the frame as JPG image



![Screenshot 2024-04-24 210948](https://github.com/YendluriChandana/Image_Acqusition-_using_Web_Camera/assets/139842204/49626bd1-d36a-4e4d-821f-d05662fda447)



### ii) Display the video


![Screenshot 2024-04-24 211017](https://github.com/YendluriChandana/Image_Acqusition-_using_Web_Camera/assets/139842204/5ad4bd03-3db5-4a7d-afd5-5d6735fcb84e)


### iii) Display the video by resizing the window


![Screenshot 2024-04-24 211039](https://github.com/YendluriChandana/Image_Acqusition-_using_Web_Camera/assets/139842204/21cd959a-2249-476f-9d4d-23ecab3b0db6)




### iv) Rotate and display the video

![Screenshot 2024-04-24 211101](https://github.com/YendluriChandana/Image_Acqusition-_using_Web_Camera/assets/139842204/392b9957-8a45-4d57-80fd-8f89e55a8504)




## Result:
Thus the image is accessed from webcamera and displayed using openCV.
