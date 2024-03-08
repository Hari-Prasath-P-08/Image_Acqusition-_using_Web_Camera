# Image_Acqusition-_using_Web_Camera
## Aim:

To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used:

Anaconda - Python 3.7

## Algorithm:

### Step 1:
Import the cv2 and numpy package.

### Step 2:
Read the Video frame using the cv2.VideoCapture(0)

### Step 3:
Write the image using imwrite().

### Step 4:
Display the frame using the imshow().

### Step 5:
Divide the frame into halves and assign the smaller frame

## Program:

### Developed By: HARI PRASATH. P
### Register No: 212223230070

### i) Write the frame as JPG file

``` Python
import cv2
obj = cv2.VideoCapture(0)
while(True):
    cap,frame = obj.read()
    cv2.imshow('Video.jpg',frame)
    cv2.imwrite("Phone.jpg",frame)
    if cv2.waitKey(1) == ord('q'):
        break
obj.release()
```

### ii) Display the video

``` Python
import cv2
img = cv2.VideoCapture(0)
while(True):
    imagee,frame = img.read()
    cv2.imshow('Video',frame)
    cv2.imwrite("MY_Phone.jpg",frame)
    if cv2.waitKey(1) == ord('q'):
        break
img.release()
cv2.destroyAllWindows()
```

### iii) Display the video by resizing the window

``` Python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('OSCAR ',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

### iv) Rotate and display the video

``` Python
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2] = smaller_frame 
    image[:height//2, width//2:] = smaller_frame
    image[height//2:, width//2:] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    cv2.imshow('Video', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## Output:


### i) Write the frame as JPG image

![Screenshot 2024-03-08 143749](https://github.com/Hari-Prasath-P-08/Image_Acqusition-_using_Web_Camera/assets/139455593/0ea6860f-50df-4bc2-805d-bdc41c733eeb)

### ii) Display the video

![Screenshot 2024-03-08 143951](https://github.com/Hari-Prasath-P-08/Image_Acqusition-_using_Web_Camera/assets/139455593/445cdcfb-6918-4a22-8af4-7770116e9694)

### iii) Display the video by resizing the window

![Screenshot 2024-03-08 144225](https://github.com/Hari-Prasath-P-08/Image_Acqusition-_using_Web_Camera/assets/139455593/50811b44-487d-44ec-a086-dcca8ebbf9cc)

### iv) Rotate and display the video

![Screenshot 2024-03-08 144408](https://github.com/Hari-Prasath-P-08/Image_Acqusition-_using_Web_Camera/assets/139455593/929541b7-12eb-4c0d-9df0-0a53201b5744)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
