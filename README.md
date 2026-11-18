## Record-Image-Transformations
## Geometric Transformations Using OpenCV:

## Aim:

To write a Python program using OpenCV to perform various geometric transformations on an image.

## The program performs the following operations:

* Image Translation
* Image Scaling (Resizing)
* Image Shearing
* Image Reflection (Flipping)
* Image Rotation

## Software Used:

* Anaconda – Python 3.7
* Jupyter Notebook / VS Code
* OpenCV (cv2)
* NumPy
* Matplotlib

## Algorithm:

## Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

## Step 2:
Read the input image in color mode.

## Step 3: Image Translation

* Create a translation matrix to shift the image
* Move the image 50 pixels to the right and 80 pixels down
* Apply transformation using cv2.warpAffine()
* Display original and translated images

## Step 4: Image Scaling

* Resize the image to 0.5× (downscale)
* Resize the image to 2× (upscale)
* Use cv2.resize()
* Display original, downscaled, and upscaled images

## Step 5: Image Shearing

* Create transformation matrices for:
  * Horizontal shearing
  * Vertical shearing
* Apply transformations using cv2.warpAffine()
* Display original and sheared images

## Step 6: Image Reflection

* Perform flipping using cv2.flip():
  * Horizontal reflection
  * Vertical reflection
  * Both axes
* Display all reflected images

## Step 7: Image Rotation

* Create rotation matrices for:
  * 45° rotation
  * 90° rotation
* Use cv2.getRotationMatrix2D() and cv2.warpAffine()
* Display original and rotated images

## Program:

## Developed By: SARAN RAJ M

## Register No: 212225240138

### ORIGINAL IMAGE:

```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

```
image = cv2.imread('sai1.jpeg')
```

```
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB)) 
plt.title("Original Image")  
plt.axis('off') 
```

## TRANSLATED IMAGE:

```
tx, ty = 100, 50  
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])  
translated_image = cv2.warpAffine(image, M_translation, (image.shape[1], image.shape[0]))  
```

```
plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB)) 
plt.title("Translated Image")  
plt.axis('off')
```

## SCALED IMAGE: 

```
fx, fy = 5.0, 2.0  
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)
```

```
plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))  
plt.title("Scaled Image")  
plt.axis('off')
```

## SHEARED IMAGE:

```
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))
```

```
plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB)) 
plt.title("Sheared Image") 
plt.axis('off')
```

## REFLECTED IMAGE:

```
reflected_image = cv2.flip(image, 2)
```

```
plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))  
plt.title("Reflected Image")  
plt.axis('off')
```

## ROTATED IMAGE:

```
(height, width) = image.shape[:2] 
angle = 45 
center = (width // 2, height // 2) 
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)
rotated_image = cv2.warpAffine(image, M_rotation, (width, height)) 
```

```
plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))  
plt.title("Rotated Image") 
plt.axis('off')
```

## CROPPED IMAGE:

```
x, y, w, h = 100, 100, 200, 150 
cropped_image = image[y:y+h, x:x+w]
```

```
plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB))  
plt.title("Cropped Image")
plt.axis('off')
```

## OUTPUT:

## Original Image:

<img width="432" height="312" alt="image" src="https://github.com/user-attachments/assets/4464dc14-018a-4a26-aa25-d36e1550daf6" />



## Image Translation:

<img width="478" height="327" alt="image" src="https://github.com/user-attachments/assets/92d568a5-1a08-4aa4-bc77-da0ebd3d2ded" />


## Image Scaling:

<img width="462" height="140" alt="Screenshot 2026-11-18 085431" src="https://github.com/user-attachments/assets/2628a859-51f1-4e84-b214-06d23521c0aa" />




## Image Shearing:

<img width="422" height="316" alt="image" src="https://github.com/user-attachments/assets/44ab1e01-7647-440f-ad30-e1249da56584" />


## Image Reflection:
<img width="505" height="310" alt="image" src="https://github.com/user-attachments/assets/bd638c8b-1cc7-41ef-99fb-5cef025d4779" />

## Image Rotation:

<img width="472" height="312" alt="image" src="https://github.com/user-attachments/assets/9ed11e4d-74a9-4b71-a77a-870d54ba86be" />


## Image Cropping:

<img width="427" height="348" alt="image" src="https://github.com/user-attachments/assets/1f10dede-aaa3-49d6-86c8-9de0f4d27fc7" />




## RESULT:

Thus, various geometric transformations such as translation, scaling, shearing, reflection, and rotation are successfully performed using OpenCV. These transformations demonstrate how images can be spatially manipulated for different computer vision applications.
