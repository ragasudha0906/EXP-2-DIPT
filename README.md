# EXP 02 - Record-Image Acquisition using Web Camera
## NAME : RAGASUDHA R
## REG NO :212224230215
## AIM
To acquire and record images using a web camera with the help of OpenCV in Python.
## PROCEDURE
1. Import the required libraries, such as OpenCV and Matplotlib.
2. Initialize the web camera using cv2.VideoCapture(0).
3. Capture an image and save it as a file.
4. Read and display the captured image using Matplotlib.
5. Capture and display video frames from the web camera.
6. Resize the video frames to the required dimensions using cv2.resize().
7. Rotate the video frames by 90° clockwise using cv2.rotate().
8. Release the camera after completing the operations.
## CODE
```python
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
## OUTPUT

### i) Captured image

<img width="987" height="530" alt="image" src="https://github.com/user-attachments/assets/76e09899-d9af-4fdb-81de-b386900825e2" />

### ii) Display the video

<img width="1072" height="507" alt="image" src="https://github.com/user-attachments/assets/5ff4a380-8dfb-46f4-b922-d66cee2184b5" />

### iii) Display the video by resizing the window

<img width="792" height="507" alt="image" src="https://github.com/user-attachments/assets/5a2c671f-4783-4093-b6e9-3ad8c0d47dd0" />

### iv) Rotate and display the video

<img width="947" height="502" alt="image" src="https://github.com/user-attachments/assets/d74ae34c-83f1-491e-a2f7-133e789297de" />

## RESULT
Thus, the image was successfully captured, displayed, and saved using a web camera with the help of OpenCV in Python.



