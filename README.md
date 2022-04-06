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
Use VideoCapture(0) to access web camera

### Step 2:
Use imread to read the video or image

### Step 3:
use imwrite to save the images

### Step 4:
use imshow to save imaage

### Step 5:
End the program and close the output video windows by pressing 'q'

## Program:
``` Python
### Developed By:U.BHAVYA
### Register No:212220230055

## i) Write the frame as JPG file
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("orange.jpg",frame)
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
![2nd image](https://user-images.githubusercontent.com/75235293/162008660-ca59d1fd-f026-44bd-83c4-7563c599c53f.png)




### ii) Display the video
![reverse image](https://user-images.githubusercontent.com/75235293/162006917-17d82d6c-a567-46f4-bcf9-3e96b97948bb.jpeg)




### iii) Display the video by resizing the window
![4 frame image](https://user-images.githubusercontent.com/75235293/162005666-c8af757d-8e39-4782-b14a-e552fdf7e940.jpeg)




### iv) Rotate and display the video
![reverse image](https://user-images.githubusercontent.com/75235293/162005731-e5a13bdc-7494-41b3-b144-cf777db96005.jpeg)






## Result:
Thus the image is accessed from webcamera and displayed using openCV.
