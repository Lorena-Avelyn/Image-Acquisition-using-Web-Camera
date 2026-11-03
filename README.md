# EXP-2-Record-Image Acquisition using Web Camera

## Experiment Details

- **Name:** Lorena Avelyn R
- **Register Number:** 212224040174

## Aim

To write a Python program using OpenCV to capture an image from a webcam and perform the following image manipulations:

1. Write the captured frame as a JPG file.
2. Display the video.
3. Display the video by resizing the window.
4. Rotate and display the video.

## Software Requirements

- Anaconda
- Python 3.7
- OpenCV
- Matplotlib

## Algorithm

**Step 1:** Access the webcam using `cv2.VideoCapture(0)`.

**Step 2:** Capture a frame from the webcam using `cap.read()`.

**Step 3:** Save the captured frame as a JPG image using `cv2.imwrite()`.

**Step 4:** Read the captured image using `cv2.imread()`.

**Step 5:** Display the video using `cv2.imshow()` or Matplotlib.

**Step 6:** Resize the video display window using Matplotlib.

**Step 7:** Rotate the video frames using `cv2.rotate()` and display them.

**Step 8:** Release the webcam and close the output window by pressing `q` or terminating the program.

## Program

### i) Write the Frame as a JPG File

```python
import cv2
import matplotlib.pyplot as plt

cap = cv2.VideoCapture(0)

ret, frame = cap.read()

if ret:
    cv2.imwrite("captured_frame.jpg", frame)

cap.release()

captured_image = cv2.imread("captured_frame.jpg")

if captured_image is not None:
    plt.imshow(captured_image[:, :, ::-1])
    plt.title("Captured Frame")
    plt.axis("off")
    plt.show()
```

### ii) Display the Video

```python
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    frame_rgb = cv2.cvtColor(
        frame, cv2.COLOR_BGR2RGB
    )

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()
```

### iii) Display the Video by Resizing the Window

```python
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    frame_rgb = cv2.cvtColor(
        frame, cv2.COLOR_BGR2RGB
    )

    clear_output(wait=True)
    plt.figure(figsize=(5, 3))
    plt.imshow(frame_rgb)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()
```

### iv) Rotate and Display the Video

```python
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    rotated_frame = cv2.rotate(
        frame, cv2.ROTATE_90_CLOCKWISE
    )

    frame_rgb = cv2.cvtColor(
        rotated_frame, cv2.COLOR_BGR2RGB
    )

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()
```

## Output

### i) Write the Frame as a JPG Image

<img width="727" height="431" alt="Screenshot 2026-11-03 215159" src="https://github.com/user-attachments/assets/06b85536-3272-4dee-bf71-b39162aa41d3" />


### ii) Display the Video

<img width="645" height="402" alt="Screenshot 2026-11-03 215257" src="https://github.com/user-attachments/assets/9bc88534-2daf-4557-8271-0500f8d051e0" />


### iii) Display the Video by Resizing the Window

<img width="527" height="397" alt="Screenshot 2026-11-03 215323" src="https://github.com/user-attachments/assets/f04ddc27-3781-47c0-ad84-caa5dced3efd" />


### iv) Rotate and Display the Video

<img width="575" height="427" alt="Screenshot 2026-11-03 215410" src="https://github.com/user-attachments/assets/618d9e74-b2e2-4f97-8313-4932be3412e2" />


## Result

Thus, the image was successfully acquired from the webcam using OpenCV. The captured frame was saved as a JPG image, and the video was displayed, resized, and rotated successfully.

