# Implementation-of-Erosion-and-Dilation
## Aim
To implement Erosion and Dilation using Python and OpenCV.
## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
<br> Initialize a black image of size 300x600 with 3 color channels (for RGB) using np.zeros.

### Step2:
<br> Use cv2.putText to add the text "OpenCV Demo" to the image, specifying the font, size, color, and thickness.

### Step3:
<br> Create a 5x5 rectangular structuring element using cv2.getStructuringElement to be used for erosion and dilation operations.

### Step4:
<br> Use cv2.erode to shrink the white areas (text) of the image, and cv2.dilate to expand them.

### Step5:
<br> Convert the images from BGR to RGB for proper display in Matplotlib, and use plt.subplot to visualize the original, eroded, and dilated images side by side.



## Program:

``` Python
# Import the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Step 1: Create a blank image
image = np.zeros((300, 600, 3), dtype="uint8")


# Step 2: Create the text using cv2.putText
text = "OpenCV Demo"
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, text, (50, 150), font, 2, (255, 255, 255), 3)

# Step 3: Create a structuring element (5x5 rectangular)
kernel = cv2.getStructuringElement(cv2.MORPH_RECT, (5, 5))

# Step 4: Erode the image
eroded_image = cv2.erode(image, kernel, iterations=1)

# Step 5: Dilate the image
dilated_image = cv2.dilate(image, kernel, iterations=1)

# Convert images from BGR to RGB for Matplotlib
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
eroded_image_rgb = cv2.cvtColor(eroded_image, cv2.COLOR_BGR2RGB)
dilated_image_rgb = cv2.cvtColor(dilated_image, cv2.COLOR_BGR2RGB)

# Plot the original, eroded, and dilated images using Matplotlib
plt.figure(figsize=(10, 5))

#Original Image:
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis("off")

#Eroded Image:
plt.imshow(eroded_image_rgb)
plt.title("Eroded Image")
plt.axis("off")

#Dilated Image:
plt.imshow(dilated_image_rgb)
plt.title("Dilated Image")
plt.axis("off")

plt.tight_layout()
plt.show()

```
## Output:

### Display the input Image
<br> <img width="866" alt="Screenshot 2024-10-08 at 12 03 41 PM" src="https://github.com/user-attachments/assets/3d978299-cb73-4184-83a4-fda5f14937f6">

<br>
<br>
<br>
<br>
<br>

### Display the Eroded Image
<br>
<br> <img width="587" alt="Screenshot 2024-10-08 at 12 04 24 PM" src="https://github.com/user-attachments/assets/21376546-3ae8-4864-aca9-4173dc321872">

<br>
<br>
<br>
<br>

### Display the Dilated Image
<br>
<br> <img width="695" alt="Screenshot 2024-10-08 at 12 04 37 PM" src="https://github.com/user-attachments/assets/5c825522-5def-4688-9ad4-ded0996e1386">

<br>
<br>
<br>
<br>

## Result
Thus the generated text image is eroded and dilated using python and OpenCV.
