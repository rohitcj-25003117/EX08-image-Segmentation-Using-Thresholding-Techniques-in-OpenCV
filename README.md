# EX08-image-Segmentation-Using-Thresholding-Techniques-in-OpenCV


# Image Segmentation Using Thresholding Techniques in OpenCV

## Aim

To segment an image using **Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding** techniques using Python and OpenCV.

The program performs the following operations:

* Global Thresholding
* Adaptive Thresholding
* Otsu's Thresholding

---

## Software Used

* Anaconda – Python 3.7
* Jupyter Notebook / VS Code
* OpenCV (`cv2`)
* NumPy
* Matplotlib

---

## Algorithm

### Step 1: Import Libraries

Import the required libraries:

* OpenCV
* NumPy
* Matplotlib

### Step 2: Load the Image

Load the input image using OpenCV.

### Step 3: Convert to Grayscale

Convert the input image into grayscale format.

### Step 4: Global Thresholding

* Select a fixed threshold value.
* Apply thresholding to separate foreground and background pixels.
* Display the thresholded image.

### Step 5: Adaptive Thresholding

* Compute threshold values for small regions of the image.
* Apply Adaptive Mean Thresholding.
* Apply Adaptive Gaussian Thresholding.
* Display the segmented images.

### Step 6: Otsu's Thresholding

* Automatically determine the optimal threshold value.
* Apply Otsu's thresholding technique.
* Display the segmented image.

### Step 7: Compare Results

Compare the results obtained from Global, Adaptive, and Otsu's thresholding methods.

---

## Program

### 1. Original Image

```python
import cv2
import matplotlib.pyplot as plt

img = cv2.imread("baseball.jpg")

if img is None:
    print("Error: Image not found. Check the file path.")
else:
    img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
    plt.imshow(img_rgb)
    plt.title("Original Image")
    plt.axis("off")
    plt.show()
```

### Output

<img width="484" height="350" alt="download" src="https://github.com/user-attachments/assets/76d9974a-26c5-471c-97e7-8b178e400d8f" />

---

### 2. Original Grayscale Image

```python
import cv2
import matplotlib.pyplot as plt

img = cv2.imread("baseball.jpg", cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap="gray")
plt.title("Original Grayscale Image")
plt.axis("off")
plt.show()
```

### Output
<img width="484" height="350" alt="download" src="https://github.com/user-attachments/assets/361f9b0c-8c96-4589-b1ba-50cfb33c4af5" />



---

### 3. Global Thresholding

```python
import cv2
import matplotlib.pyplot as plt

img = cv2.imread("baseball.jpg", cv2.IMREAD_GRAYSCALE)

_, result = cv2.threshold(
    img,
    127,
    255,
    cv2.THRESH_BINARY
)

plt.imshow(result, cmap="gray")
plt.title("Global Thresholding")
plt.axis("off")
plt.show()
```

### Output
<img width="484" height="350" alt="download" src="https://github.com/user-attachments/assets/b5cfcf4e-c4c8-44a9-b2f7-47f1ea3a0e4f" />


---

### 4. Adaptive Thresholding

```python
import cv2
import matplotlib.pyplot as plt

img = cv2.imread("baseball.jpg", cv2.IMREAD_GRAYSCALE)

result = cv2.adaptiveThreshold(
    img,
    255,
    cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
    cv2.THRESH_BINARY,
    11,
    2
)

plt.imshow(result, cmap="gray")
plt.title("Adaptive Thresholding")
plt.axis("off")
plt.show()
```

### Output

<img width="484" height="350" alt="download" src="https://github.com/user-attachments/assets/dd006164-f5d9-4ce0-892c-6d77ad404e65" />

---

### 5. Otsu's Thresholding

```python
import cv2
import matplotlib.pyplot as plt

img = cv2.imread("baseball.jpg", cv2.IMREAD_GRAYSCALE)

_, result = cv2.threshold(
    img,
    0,
    255,
    cv2.THRESH_BINARY + cv2.THRESH_OTSU
)

plt.imshow(result, cmap="gray")
plt.title("Otsu's Thresholding")
plt.axis("off")
plt.show()
```

### Output
<img width="484" height="350" alt="download" src="https://github.com/user-attachments/assets/cacdd6c2-3623-453f-987d-d218caf66292" />

<img width="1189" height="661" alt="download" src="https://github.com/user-attachments/assets/24062c5f-73a1-49f8-a9bc-50ca683994d7" />

---

## Comparison

| Technique             | Threshold Selection      | Advantage                              |
| --------------------- | ------------------------ | -------------------------------------- |
| Global Thresholding   | Fixed manually           | Simple and fast                        |
| Adaptive Thresholding | Local regions            | Works well with uneven illumination    |
| Otsu's Thresholding   | Automatically calculated | No manual threshold selection required |

---

## Result

Thus, image segmentation is successfully performed using **Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding** techniques in OpenCV.

---

## Developed By

**Name:** CJ ROHIT


**Register No:** 212224243005
