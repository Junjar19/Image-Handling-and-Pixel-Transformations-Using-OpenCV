## Name: Junjar U
## Register Number: 212224230110

# EXP NO 1 : Image Handling and Pixel Transformations Using OpenCV

## AIM:
Write a Python program using OpenCV that performs the following tasks:

1) Read and Display an Image.  
2) Adjust the brightness of an image.  
3) Modify the image contrast.  
4) Generate a third image using bitwise operations.

## Software Required:
- Anaconda - Python 3.7
- Jupyter Notebook (for interactive development and execution)

## Algorithm:
### Step 1:
Load an image from your local directory and display it.

### Step 2:
Create a matrix of ones (with data type float64) to adjust brightness.

### Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image.  
Display the original, brighter, and darker images.

### Step 4:
Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix).  
Display the original, lower contrast, and higher contrast images.

### Step 5:
Split the image (boy.jpg) into B, G, R components and display the channels

## Program:

### 1. Import Libraries

python
import cv2
import matplotlib.pyplot as plt


*Output:* Libraries are imported successfully.

### 2. Read the Image

python
# Read the image using OpenCV
img = cv2.imread('photo.jpg', cv2.IMREAD_COLOR)


![alt text](Images/image.png)


### 3. Convert BGR to RGB

python
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)


*Output:* The image is converted from BGR to RGB format.

### 4. Display the Original Image

python
# Display the image using Matplotlib
plt.imshow(img_rgb, cmap='viridis')
plt.title("Original Image")
plt.axis('off')
plt.show()


*Output:* The original image is displayed.

### 5. Load the Image for Drawing Operations

python
# Load the image
image = cv2.imread('photo.jpg')


*Output:* The image is loaded for drawing operations.

### 6. Check Image Dimensions

python
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)


python
img_rgb.shape


*Output:*
text
(531, 413, 3)


The image has a height of 531 pixels, width of 413 pixels, and 3 color channels.

### 7. Draw a Line

python
# Draw a line from top-left to bottom-right
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2)


python
plt.imshow(line_img, cmap='viridis')
plt.title("Image with Line")
plt.axis('off')
plt.show()


![alt text](Images/image-1.png)


### 8. Draw a Circle

python
# Load the image
image = cv2.imread('photo.jpg')

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)


python
img_rgb.shape


*Output:*
text
(531, 413, 3)


python
circle_img = cv2.circle(img_rgb, (400, 300), 150, (255, 0, 0), 10)


python
plt.imshow(circle_img, cmap='viridis')
plt.title("Image with Circle")
plt.axis('off')
plt.show()


![alt text](Images/image-2.png)


### 9. Draw a Rectangle

python
# Load the image
image = cv2.imread('photo.jpg')

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)


python
img.shape


*Output:*
text
(531, 413, 3)


python
# Draw a rectangle around the Whole image
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10)


python
plt.imshow(rectangle_img, cmap='viridis')
plt.title("Image with Rectangle")
plt.axis('off')
plt.show()


![alt text](Images/image-3.png)


### 10. Add Text to the Image

python
# Load the image
image = cv2.imread('photo.jpg')

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)


python
# Add text to the image
text_img = cv2.putText(
    img_rgb,
    "OpenCV Drawing",
    (10, 30),
    cv2.FONT_HERSHEY_SIMPLEX,
    1,
    (255, 255, 255),
    10
)


python
plt.imshow(text_img, cmap='viridis')
plt.title("Image with Text")
plt.axis('off')
plt.show()


![alt text](Images/image-4.png)


### 11. Convert the Image into Different Color Spaces

python
# Load the image
image = cv2.imread('photo.jpg')


python
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)


python
# Original RGB Image
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
plt.show()


![alt text](Images/image-5.png)


### 12. Convert RGB to HSV

python
# Convert RGB to HSV
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)


python
# HSV Image
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
plt.show()


![alt text](Images/image-6.png)


### 13. Convert RGB to Grayscale

python
# Convert RGB to GRAY
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)


python
# Grayscale Image
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
plt.show()


![alt text](Images/image-7.png)


### 14. Convert RGB to YCrCb

python
# Convert RGB to YCrCb
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)


python
# YCrCb Image
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
plt.show()


![alt text](Images/image-8.png)


### 15. Convert HSV Back to RGB

python
# Convert HSV back to RGB
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)


python
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
plt.show()


![alt text](Images/image-9.png)


### 16. Modify Image Pixels

python
# Modify a block of pixels (300x300) to white, starting from (200, 200)
image[200:500, 200:500] = [255, 255, 255]


python
# Convert BGR to RGB for displaying with Matplotlib
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)


python
# Display the modified image
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()


![alt text](Images/image-10.png)


### 17. Resize the Image

python
# Load the image
image = cv2.imread('photo.jpg')


python
image.shape


*Output:*
text
(531, 413, 3)


python
# Resize the image to half its size
resized_image = cv2.resize(image, (768 // 2, 600 // 2))


python
# Convert BGR to RGB for displaying with Matplotlib
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)


python
resized_image_rgb.shape


*Output:*
text
(300, 384, 3)


python
# Display the resized image
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()


![alt text](Images/image-11.png)


### 18. Crop a Region of Interest (ROI)

python
# Load the image
image = cv2.imread('photo.jpg')


python
image.shape


*Output:*
text
(531, 413, 3)


python
# Crop a 300x300 region starting from (50, 50)
roi = image[50:350, 50:350]


python
# Convert BGR to RGB for displaying with Matplotlib
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)


python
# Display the cropped region (ROI)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()


![alt text](Images/image-12.png)

### 19. Flip the Image Horizontally

python
# Load the image
image = cv2.imread('photo.jpg')


python
# Flip the image horizontally (left-right)
flipped_horizontally = cv2.flip(image, 1)


python
# Convert BGR to RGB for displaying with Matplotlib
flipped_horizontally_rgb = cv2.cvtColor(
    flipped_horizontally, cv2.COLOR_BGR2RGB
)


python
# Horizontal flip
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
plt.show()


![alt text](Images/image-13.png)


### 20. Flip the Image Vertically

python
# Flip the image vertically (up-down)
flipped_vertically = cv2.flip(image, 0)


python
# Convert BGR to RGB for displaying with Matplotlib
flipped_vertically_rgb = cv2.cvtColor(
    flipped_vertically, cv2.COLOR_BGR2RGB
)


python
# Vertical flip
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
plt.show()


![alt text](Images/image-14.png)




## Result

Thus, image handling and pixel transformation operations, including drawing geometric shapes, adding text, color-space conversion, pixel modification, resizing, cropping, and flipping, were demonstrated using OpenCV and Matplotlib.