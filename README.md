
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm

**Step 1:** Import the required libraries (`cv2`).

**Step 2:** Initialize the webcam using `cv2.VideoCapture(0)`.

**Step 3:** Start a loop to continuously capture frames from the webcam.

**Step 4:**
- **i)** Save the captured frame as a JPG image using `cv2.imwrite()`.  
- **ii)** Display the video frames using `cv2.imshow()`.  
- **iii)** Resize the frame using `cv2.resize()` and display it in a window.  
- **iv)** Rotate the frame using transformation functions like `cv2.rotate()` and display it.  

**Step 5:** Wait for a key press (`cv2.waitKey(1)`).  
If the user presses **'q'**, then break the loop.  

**Step 6:** Release the camera using `cap.release()` and close all windows with `cv2.destroyAllWindows()`.  

## Program:
``` Python
### Developed By:Karuniya M
### Register No:21222324..68

## i) Write the frame as JPG file
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



## ii) Display the video
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




## iii) Display the video by resizing the window

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


## iv) Rotate and display the video


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

### i) Write the frame as JPG image
</br>
</br>
<img width="667" height="531" alt="image" src="https://github.com/user-attachments/assets/bc576003-854c-4c04-acf7-0d6e2babf0f4" />


### ii) Display the video
</br>
</br>
<img width="632" height="475" alt="image" src="https://github.com/user-attachments/assets/242845f4-81a0-499d-890c-3df516cee72f" />


### iii) Display the video by resizing the window
</br>
</br>
<img width="325" height="464" alt="image" src="https://github.com/user-attachments/assets/428af05c-4514-413a-a97c-78fb24ea27ff" />




### iv) Rotate and display the video
</br>
</br>
<img width="351" height="468" alt="image" src="https://github.com/user-attachments/assets/56c54d97-416f-42ab-8327-a9b7dd00513f" />






## Result:
Thus the image is accessed from webcamera and displayed using openCV.
