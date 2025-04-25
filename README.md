# EDGE-DETECTION
## Aim:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the necessary modules for the program.

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale

### Step4:
Using Sobel operator from cv2,detect the edges of the image.

### Step5:

Using Laplacian operator from cv2,detect the edges of the image and Using Canny operator from cv2,detect the edges of the image.

## Output:
```
import cv2
import numpy as np

# Load the image
image = cv2.imread('parrot.jpg')  # Replace with your image path
if image is None:
    raise ValueError("Image not found. Check the file path.")

# Convert to grayscale
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
```

![exp6op1](https://github.com/user-attachments/assets/75b9b65f-dd3f-46ab-b709-845dc0fd6834)

### SOBEL EDGE DETECTOR
```
# Detect edges in X and Y directions
sobelx = cv2.Sobel(gray, cv2.CV_64F, 1, 0, ksize=3)
sobely = cv2.Sobel(gray, cv2.CV_64F, 0, 1, ksize=3)
sobel_combined = cv2.magnitude(sobelx, sobely)
sobel_combined = cv2.convertScaleAbs(sobel_combined)
```
![dipep6op2](https://github.com/user-attachments/assets/30a8baec-3b11-4d00-8206-eb8a13283e31)

![dipexp6op3](https://github.com/user-attachments/assets/a8979d64-db66-4b2b-8835-02d91ca715dd)

![dipexp6op4](https://github.com/user-attachments/assets/423a9445-d245-4280-b20b-893679926f2b)



### LAPLACIAN EDGE DETECTOR
```
laplacian = cv2.Laplacian(gray, cv2.CV_64F)
laplacian = cv2.convertScaleAbs(laplacian)
```
![dipexp6op5](https://github.com/user-attachments/assets/611e4f1a-9422-4a8b-85c6-cb6760fb5017)




### CANNY EDGE DETECTOR
```
canny = cv2.Canny(gray, 100, 200)  # Adjust thresholds as needed

```
```
cv2.imshow('Original', image)
cv2.imshow('Sobel X', cv2.convertScaleAbs(sobelx))
cv2.imshow('Sobel Y', cv2.convertScaleAbs(sobely))
cv2.imshow('Sobel Combined', sobel_combined)
cv2.imshow('Laplacian', laplacian)
cv2.imshow('Canny', canny)

cv2.waitKey(0)
cv2.destroyAllWindows()
```

![dipexp6op6](https://github.com/user-attachments/assets/e2664ab4-e9c5-432f-a8d9-94fd26b3920d)

## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
