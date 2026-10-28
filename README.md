# Exp2-Image-Acquisition-Using-Web-Camera

Aim
To write a Python program using OpenCV to capture images from a webcam and perform the following image manipulations:

Write the captured frame as a JPG file.
Display the video.
Display the video by resizing the frame.
Rotate and display the video.

Software Used```
Anaconda
Python 3.7
OpenCV
NumPy
Algorithm

Step 1
Import the cv2 and numpy packages.

Step 2
Read the video frame using cv2.VideoCapture(0).

Step 3
Write the captured image using cv2.imwrite().

Step 4
Display the video frame using cv2.imshow().

Step 5
Divide the frame into four parts, resize the frame, and assign the smaller frame to each part.

Step 6
Rotate the frame using cv2.rotate() and display the output.

Program
Developed By: RITHIKA K

Register Number: 212225040343

i) Write the Frame as a JPG File
```
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("captured_frame.jpg", frame)
cap.release()

captured_image = cv2.imread('captured_frame.jpg')

plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
```
ii) Display the Video
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```

iii) Display the Video by Resizing the Frame
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (100, 150))  # Resize to 320x240
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```
iv) Rotate and Display the Video
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```
Output
i) Write the Frame as a JPG Image
image
ii) Display the Video
image
iii) Display the Video by Resizing the Frame
image
iv) Rotate and Display the Video
image
Result
Thus, images were captured from the webcam, saved as JPG files, and displayed using OpenCV. The video frames were resized and rotated successfully.
