# Edge-Detection Using OpenCV
## NAME:  DINESH R
## REG NO: 212224240037
## Aim

To perform edge detection using Sobel, Roberts, Prewitt, Laplacian, and Canny edge detectors.

---

## Software Required

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (cv2)  
- NumPy  
- Matplotlib  

---

## ⚙️ Algorithm

### Step 1:
Import all the necessary modules for the program.

### Step 2:
Load an image using `cv2.imread()`.

### Step 3:
Convert the image to grayscale.

### Step 4:
Apply **Sobel operator** using OpenCV to detect edges.

### Step 5:
Apply **Prewitt operator** using custom kernels.

### Step 6:
Apply **Roberts operator** using custom kernels.

### Step 7:
Apply **Laplacian operator** using OpenCV.

### Step 8:
Apply **Canny edge detector** using OpenCV.

### Step 9:
Display all edge-detected images for comparison.

# Program :
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
```
# Load image
image = cv2.imread("E:\Digital Image\Exp-6.jpg")  # replace with your path
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
```
```
sobel_x = cv2.Sobel(gray, cv2.CV_64F, 1, 0, ksize=5)
sobel_y = cv2.Sobel(gray, cv2.CV_64F, 0, 1, ksize=5)
sobel = cv2.magnitude(sobel_x, sobel_y)
```
```
prewitt_x = np.array([[1, 0, -1],
                      [1, 0, -1],
                      [1, 0, -1]])
```
```
prewitt_y = np.array([[1, 1, 1],
                      [0, 0, 0],
                      [-1, -1, -1]])
```
```
prewitt_x_edge = cv2.filter2D(gray, -1, prewitt_x)
prewitt_y_edge = cv2.filter2D(gray, -1, prewitt_y)
prewitt = cv2.magnitude(prewitt_x_edge.astype(np.float32),
                        prewitt_y_edge.astype(np.float32))
```
```
roberts_x = np.array([[1, 0],
                      [0, -1]])

roberts_y = np.array([[0, 1],
                      [-1, 0]])
```
```
roberts_x_edge = cv2.filter2D(gray, -1, roberts_x)
roberts_y_edge = cv2.filter2D(gray, -1, roberts_y)
roberts = cv2.magnitude(roberts_x_edge.astype(np.float32),
                        roberts_y_edge.astype(np.float32))
```
```

laplacian = cv2.Laplacian(gray, cv2.CV_64F)
```
```

canny = cv2.Canny(gray, 50, 150)
```
```

plt.figure(figsize=(12, 10))

plt.subplot(2, 3, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
print(" DINESH R")
print("212224240037")
plt.title("Original")
plt.axis("off")
```
```
plt.subplot(2, 3, 2)
plt.imshow(sobel, cmap='gray')
print(" DINESH R")
print("212224240037")
plt.title("Sobel")
plt.axis("off")
```
```
plt.subplot(2, 3, 3)
plt.imshow(prewitt, cmap='gray')
print(" DINESH R")
print("212224240037")
plt.title("Prewitt")
plt.axis("off")
```
```
plt.subplot(2, 3, 4)
plt.imshow(roberts, cmap='gray')
print(" DINESH R")
print("212224240037")
plt.title("Roberts")
plt.axis("off")
```
```
plt.subplot(2, 3, 5)
plt.imshow(laplacian, cmap='gray')
print(" DINESH R")
print("212224240037")
plt.title("Laplacian")
plt.axis("off")
```
```
plt.subplot(2, 3, 6)
plt.imshow(canny, cmap='gray')
print(" DINESH R")
print("212224240037")
plt.title("Canny")
plt.axis("off")
```
```
plt.tight_layout()
plt.show()
```



## Output 
### Original Image 
<img width="643" height="337" alt="image" src="https://github.com/user-attachments/assets/6fcad79d-2104-495d-8bb6-9f6a1447550a" />


###  Sobel Edge Detector
- Detects edges in horizontal and vertical directions  
- Produces gradient-based edge map

<img width="640" height="241" alt="image" src="https://github.com/user-attachments/assets/c61b5e88-c473-43f9-9ea8-a8c9cd161015" />


###  Prewitt Edge Detector
- Similar to Sobel but simpler kernel  
- Detects directional edges
  
<img width="677" height="242" alt="image" src="https://github.com/user-attachments/assets/52a9f2c9-b198-4537-88a5-a3c767abeb38" />

###  Roberts Edge Detector
- Detects edges using diagonal gradients  
- Sensitive to noise  


<img width="702" height="232" alt="image" src="https://github.com/user-attachments/assets/88cf4db6-2b02-41d0-86fb-d43398be554f" />

###  Laplacian Edge Detector
- Detects edges using second-order derivatives  
- Highlights rapid intensity changes  

<img width="666" height="227" alt="image" src="https://github.com/user-attachments/assets/ecbe4463-142d-4e56-8e73-633ea5f4ada6" />

###  Canny Edge Detector
- Multi-stage edge detection  
- Produces clean and thin edges  

<img width="668" height="232" alt="image" src="https://github.com/user-attachments/assets/6ca8ce3f-9b23-45af-ae96-2dcd06fcd700" />

### Figure Size
<img width="413" height="67" alt="image" src="https://github.com/user-attachments/assets/47af45f2-c4ff-4f82-9d6c-ca61b6e7e75b" />


## Result

Thus, edges are successfully detected using Sobel, Prewitt, Roberts, Laplacian, and Canny edge detection techniques. Each method highlights edges differently based on gradient and intensity variations, improving feature extraction and analysis.
