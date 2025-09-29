# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
<br>
Import all the necessary modules

### Step2:
<br>
Choose an image and save it as filename.jpg

### Step3:
<br>
Use imread to read the image

### Step4:
<br>
Use cv2.warpPerspective(image,M,(cols,rows)) to translation the image

### Step5:
<br>
Use cv2.warpPerspective(image,M,(cols2,rows2)) to scale the image

### Step6:
Use cv2.warpPerspective(image,M,(int(cols1.5),int(rows1.5))) for x and y axis to shear the image

### Step7:
Use cv2.warpPerspective(image,M,(int(cols),int(rows))) for x and y axis to reflect the image

### Step8:
Use cv2.warpPerspective(image,M,(int(cols),int(rows))) to rotate the image

### Step9:
Crop the image to remove unwanted areas from an image

### Step10:
Use cv2.imshow to show the image

### Step11:
End the program

## Program:
```python
Developed By:NAKUL.R
Register Number:212223240102
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('me.jpg')
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Original Image")  
plt.axis('off')

i)Image Translation

tx, ty = 100, 50  
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])  
# [1, 0, tx] - Horizontal shift by tx
# [0, 1, ty] - Vertical shift by ty
translated_image = cv2.warpAffine(image, M_translation, (image.shape[1], image.shape[0]))  
plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB))  
plt.title("Translated Image")  
plt.axis('off')

ii) Image Scaling

fx, fy = 5.0, 2.0  # Scaling factors (1.5x scaling for both width and height)
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)
plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))  # Display the scaled image
plt.title("Scaled Image")  # Set title
plt.axis('off')


iii)Image shearing

shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  # Shearing matrix
# The matrix shears the image by a factor of 0.5 in both x and y directions
# [1, 0.5, 0] - Shear along the x-axis (horizontal)
# [0.5, 1, 0] - Shear along the y-axis (vertical)
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))
plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB))  # Display the sheared image
plt.title("Sheared Image")  # Set title
plt.axis('off')

iv)Image Reflection

reflected_image = cv2.flip(image, 2)  
plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))  # Display the reflected image
plt.title("Reflected Image")  # Set title
plt.axis('off')

v)Image Rotation

(height, width) = image.shape[:2]  # Get the image height and width
angle = 45  # Rotation angle in degrees (rotate by 45 degrees)
center = (width // 2, height // 2)  # Set the center of rotation to the image center
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)  # Get the rotation matrix
# getRotationMatrix2D: Takes the center of rotation, angle, and scale factor (1 means no scaling)
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))  # Apply rotation
plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))  # Display the rotated image
plt.title("Rotated Image")  # Set title
plt.axis('off')


vi)Image Cropping

x, y, w, h = 100, 100, 200, 150  # Define the top-left corner (x, y) and the width (w) and height (h) of the crop
# Cropping the image from coordinates (x, y) to (x+w, y+h)
cropped_image = image[y:y+h, x:x+w]
plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB))  # Display the cropped image
plt.title("Cropped Image")  # Set title
plt.axis('off')






```
## Output:
### i)Image Translation
<br>
<br>
<br>
<br>
<img width="886" height="490" alt="image" src="https://github.com/user-attachments/assets/172f7e4b-51f6-48b0-81a5-94ab737e3742" />

### ii) Image Scaling
<br>
<br>
<br>
<br>
<img width="927" height="492" alt="image" src="https://github.com/user-attachments/assets/40446e49-2e3e-48c1-8333-39c342cbe569" />


### iii)Image shearing
<br>
<br>
<br>
<br>

<img width="947" height="483" alt="image" src="https://github.com/user-attachments/assets/2ee8d39f-73d2-4485-9c0a-646f96a79422" />

### iv)Image Reflection
<br>
<br>
<br>
<br>

<img width="960" height="526" alt="image" src="https://github.com/user-attachments/assets/2b481bd9-775b-4449-9b5a-53e78c0bed17" />



### v)Image Rotation
<br>
<br>
<br>
<br>
<img width="902" height="497" alt="image" src="https://github.com/user-attachments/assets/fbb69bca-aa5a-413b-bb46-8ed0bcc3c184" />



### vi)Image Cropping
<br>
<br>
<br>
<br>
<img width="882" height="671" alt="image" src="https://github.com/user-attachments/assets/d1e78c8f-21b4-479a-b5eb-025efe8130a7" />




## Result: 
Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
