# Image_Acqusition-_using_Web_Camera

## Aim:
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.<br>

i) Write the frame as JPG<br>
ii) Display the video<br>
iii) Display the video by resizing the window<br>
iv) Rotate and display the video<br>

## Software Used
Anaconda - Python 3.7

## Algorithm

### Step 1:
Use cv2.VideoCapture(0) to access web camera

### Step 2:
Use cv2.imread to read the video or image

### Step 3:
Use cv2.imwrite to save the image

### Step 4:
Use cv2.imshow to show the video

### Step 5:
End the program and close the output video window by pressing 'q'.

## Program:
#### Developed By: Krithick Vivekananda 
#### Register No: 212223240075
##### i) Write the frame as JPG file
``` Python
import cv2
videoCaptureObject = cv2.VideoCapture(0)
frame_count = 0
while(True):
    ret, frame = videoCaptureObject.read()
    cv2.imwrite(f"frame_{frame_count}.jpg", frame)
    frame_count += 1
    
    if frame_count >= 100:
        break
videoCaptureObject.release()
cv2.destroyAllWindows()
```
##### ii) Display the video
```Python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('OUTPUT',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
##### iii) Display the video by resizing the window
```python
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
    cv2.imshow('Krithick',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
##### iv) Rotate and display the video
```python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('Krithick',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## Output

### i) Write the frame as JPG image
![Screenshot 2025-05-20 084601](https://github.com/user-attachments/assets/bca96edd-aa68-41fb-8dcb-d19c293d84c8)

### ii) Display the video
![Screenshot 2025-05-20 084601](https://github.com/user-attachments/assets/341e9c65-a691-4be9-bf56-11d80adb61cd)

### iii) Display the video by resizing the window
![Screenshot 2025-05-20 084650](https://github.com/user-attachments/assets/31276d62-4372-410e-a975-f1a0c71a8e2b)

### iv) Rotate and display the video
![Screenshot 2025-05-20 084737](https://github.com/user-attachments/assets/14ea8bd7-d84c-4c08-9e18-24ae1e56f131)


## Result:
Thus the image is accessed from webcamera and displayed using openCV.
