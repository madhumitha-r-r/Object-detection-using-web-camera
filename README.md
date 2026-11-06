# Ex. No: 02 – Image Acquisition Using Web Camera

## Aim

To write a Python program using OpenCV to capture images from a webcam, save the captured frame as a JPG file, display video, resize the video, and rotate the video.

## Software Requirements

- Anaconda Navigator
- Jupyter Notebook
- Python
- OpenCV (`cv2`)
- Matplotlib

## Algorithm

1. Import the required libraries.
2. Initialize the webcam using `cv2.VideoCapture(0)`.
3. Capture a frame from the webcam.
4. Save the captured frame as a JPG image.
5. Read and display the captured image.
6. Capture and display video frames using a loop.
7. Resize the video frames using `cv2.resize()`.
8. Rotate the video frames using `cv2.rotate()`.
9. Release the webcam after completing the operations.

## Program
### Developed by
#### NAME: MADHUMITHA R R
#### REG NO: 212224240083

### 1. Write the Frame as JPG File

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
```

### 2. Display the Video

```python
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

### 3. Display the Video by Resizing the Window

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
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```

### 4. Rotate and Display the Video

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
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```

## Output

- Captured webcam image saved as `captured_frame.jpg`.

<img width="632" height="507" alt="image" src="https://github.com/user-attachments/assets/dce9a0cf-1e8a-4847-b944-8beec4e77983" />


- Original video displayed using Matplotlib.

<img width="626" height="465" alt="image" src="https://github.com/user-attachments/assets/e4c7bcb1-b5fd-4016-bed5-1d8b309a7252" />


- Resized video displayed.

<img width="315" height="446" alt="image" src="https://github.com/user-attachments/assets/e8c153b9-e2d1-4e3e-b193-7f7a917001a9" />


- Rotated video displayed at 90 degrees clockwise.

  <img width="355" height="480" alt="image" src="https://github.com/user-attachments/assets/8bd3eeb2-3ec0-4e67-af93-d644042db090" />


## Result

Thus, image acquisition using a webcam was performed successfully using OpenCV. The captured image was saved as a JPG file, and video display, resizing, and rotation operations were implemented successfully.
