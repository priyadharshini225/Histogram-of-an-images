# Histogram-of-an-images
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the gray and color image using imread()

### Step2:
Print the image using imshow().



### Step3:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### step4:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### Step5:
The Histogram of gray scale image and color image is shown.


## Program:
```python
# Developed By: PRIYADHARSHINI S
# Register Number: 212223240129

#import the libraries 
import cv2
from matplotlib import pyplot as plt

# Load the color image
image = cv2.imread(r"C:\Users\admin\Downloads\painting.jpeg")

# Check if the image was loaded successfully
if image is None:
    print("Error: Image not found or path is incorrect.")
else:
    # Convert the image to grayscale
    gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

    # Display the grayscale image
    plt.figure(figsize=(6, 6))
    plt.imshow(gray_image, cmap='gray')
    plt.title('Original Grayscale Image')
    plt.axis('off')
    plt.show()

# Calculate histogram for the original grayscale image
hist_original = cv2.calcHist([gray_image], [0], None, [256], [0, 256])

# Plot the histogram
plt.figure(figsize=(6, 4))
plt.plot(hist_original, color='black')
plt.title('Original Histogram')
plt.xlabel('Pixel Intensity')
plt.ylabel('Frequency')
plt.xlim([0, 256])
plt.grid(True)
plt.show()

# Apply histogram equalization
equalized_image = cv2.equalizeHist(gray_image)

# Display the equalized grayscale image
plt.figure(figsize=(6, 6))
plt.imshow(equalized_image, cmap='gray')  # corrected colormap spelling
plt.title('Equalized Image')
plt.axis('off')
plt.show()

# Calculate histogram for the equalized image
hist_equalized = cv2.calcHist([equalized_image], [0], None, [256], [0, 256])

# Plot the histogram
plt.figure(figsize=(6, 4))
plt.plot(hist_equalized, color='black')
plt.title('Equalized Histogram')
plt.xlabel('Pixel Intensity')
plt.ylabel('Frequency')
plt.xlim([0, 256])
plt.grid(True)
plt.show()

```
## Output:
### Original gray scale image 

![Screenshot 2025-04-23 081101](https://github.com/user-attachments/assets/76d69183-7f3a-401d-9b3b-6b85bbe054de)


### Original Histogram 

![Screenshot 2025-04-23 081108](https://github.com/user-attachments/assets/ab37703b-bc4c-42e7-9734-a186d687ccd2)


### Equalization Image.

![Screenshot 2025-04-23 081114](https://github.com/user-attachments/assets/0757df3a-6431-4501-86a6-2559b27afd2c)


### Equalized Histogram

![Screenshot 2025-04-23 081120](https://github.com/user-attachments/assets/e7c5d1bf-a515-4609-9fbc-d7ab216749d4)


## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
