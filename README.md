# Image Capture and Video Processing Using OpenCV

---

## Aim

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Write the frame as a JPG file  
2. Display the video  
3. Display the video by resizing the window  
4. Rotate and display the video  

---

## 🛠️ Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  

---

## ⚙️ Algorithm

### Step 1:
Import the required libraries and initialize the webcam using `cv2.VideoCapture()`.

### Step 2:
Capture frames continuously from the webcam.

### Step 3:
Save a frame as a JPG image using `cv2.imwrite()`.

### Step 4:
Display the live video stream using `cv2.imshow()`.

### Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.

---

## 💻 Program

### Developed By:
**Name:** ASWINI D

### Register No: 212225240015
---
---

### 1. Import the required libraries.

```python
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
```

---

### 2. Capture a frame from the webcam and save it as a JPG image.

```python
cap = cv2.VideoCapture(0)

ret, frame = cap.read()

if ret:
    cv2.imwrite("captured_frame.jpg", frame)

cap.release()
```

---

### 3. Read the captured image.

```python
captured_image = cv2.imread("captured_frame.jpg")
```

---

### 4. Display the captured image.

```python
plt.imshow(captured_image[:, :, ::-1])
plt.title("Captured Frame")
plt.axis("off")
plt.show()
```

---

### 5. Display the live webcam video.

```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()
```

---

### 6. Display the video after resizing.

```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    resized_frame = cv2.resize(frame, (100, 150))

    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()
```

---

### 7. Rotate the video by 90° clockwise and display it.

```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)

    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()
```

---
## Output

### i) Write the frame as JPG image
The captured frame is saved as **captured_frame.jpg**

<img width="658" height="516" alt="image" src="https://github.com/user-attachments/assets/e45ff5d8-e63c-4a5a-8ddc-1934f0589032" />



### ii) Display the video
The live webcam video is displayed.

<img width="676" height="499" alt="image" src="https://github.com/user-attachments/assets/c492eb82-7a54-44a5-aa9d-31cd6a3f585a" />



### iii) Display the video by resizing the window
The webcam video is displayed after resizing the frame.

<img width="486" height="496" alt="image" src="https://github.com/user-attachments/assets/3ebe70f9-ea69-4276-9489-6e92b5ea2b95" />



### iv) Rotate and display the video
The webcam video is displayed after rotating it by **90° clockwise**.

<img width="406" height="497" alt="image" src="https://github.com/user-attachments/assets/a3b5f389-0554-4a2c-9c81-4faf9ff7c281" />

## Result

Thus, the image was successfully captured from the webcam and various video processing operations such as image capture, live video display, resizing, and rotation were performed successfully using OpenCV.
