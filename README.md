# Image-Acquisition-from-Web-Camera
## Aim
 
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
<br>
Use VideoCapture(0) to access web camera
<br>
### Step 2:
<br>
Use imread to read the video or image
<br>
### Step 3:
<br>
Use imwrite to save the images
<br>
### Step 4:
<br>
Use imshow to save image
<br>
### Step 5:
<br>
End the program and close the output video windows by pressing 'q'
<br>

## Program:
``` Python
### Developed By: A.Divya Meenakshi
### Register No: 212220230014

## i) Write the frame as JPG file
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("dicon.jpg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()



## ii) Display the video
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret,frame = cap.read()
    cv2.imshow('frame', frame)q
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()



## iii) Display the video by resizing the window
import cv2
import numpy as np
cap=cv2.VideoCapture(0)

while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    
    image=np.zeros(frame.shape, np.uint8)
    smaller_frame=cv2.resize(frame, (0,0), fx=0.5, fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    
    cv2.imshow('frame', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()




## iv) Rotate and display the video
import cv2
import numpy as np
cap=cv2.VideoCapture(0)

while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    
    image=np.zeros(frame.shape, np.uint8)
    smaller_frame=cv2.resize(frame, (0,0), fx=0.5, fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=image[height//2:, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=image[height//2:, width//2:] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    
    cv2.imshow('frame', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()










```
## Output

### i) Write the frame as JPG image
![nip2](https://user-images.githubusercontent.com/75235402/162274833-b32fac08-dcd3-4a47-b8ad-8b35033c6f11.JPG)



### ii) Display the video
![nip 3](https://user-images.githubusercontent.com/75235402/162274863-945f8386-76c9-48e5-85a5-b6208b02fa79.JPG)



### iii) Display the video by resizing the window

![nip 5](https://user-images.githubusercontent.com/75235402/162274885-6daaf126-ec09-4b11-99be-86b37d1b7f77.JPG)



### iv) Rotate and display the video

![nip 4](https://user-images.githubusercontent.com/75235402/162274913-552b31f1-2aa0-40bf-a526-b58ce15d200d.JPG)





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
