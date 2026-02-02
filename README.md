# Image-Handling-and-Pixel-Transformations-Using-OpenCV 
- **Name:** Vinolia Alaina. R  
- **Register Number:** 212224240184

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

## Program Developed By:
- **Name:** Vinolia Alaina. R  
- **Register Number:** 212224240184

```PYTHON
import cv2
import matplotlib.pyplot as plt
```
## Read the image using OpenCV 
```PYTHON
img = cv2.imread('VIN.jpeg', cv2.IMREAD_COLOR)
```
## Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)#
```PYTHON
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```
## Display the image using Matplotlib #
```PYTHON
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()
```
## Load the image
```PYTHON
image = cv2.imread('VIN.jpeg')
```
## Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
```PYTHON
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
(1536, 941, 3)
```
## Draw a line from top-left to bottom-right
```PYTHON
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2) # cv2.line(image, start_point, end_point, color, thickness)
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()
```
## Load the image
```PYTHON
image = cv2.imread('VIN.jepg') 
```
## Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
```PYTHON
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
(1536, 941, 3)
circle_img = cv2.circle(img_rgb,(400,300),150,(255,0,0),10) # cv2.circle(image, center, radius, color, thickness)
plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()
```
## Load the image
```PYTHON
image = cv2.imread('VIN.jpeg') 
```
## Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
```PYTHON
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img.shape
(1536, 941, 3)
```
## Draw a rectangle around the Whole image
```PYTHON
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()
```
## Load the image
```PYTHON
image = cv2.imread('VIN.jpeg') 
```
## Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
```PYTHON
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```
## Add text to the image
```PYTHON
text_img = cv2.putText(img_rgb, "Opencv Drawing", (10, 35), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 10)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)
plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()
```
## Load the image
```PYTHON
image = cv2.imread('VIN.jpeg') 
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
```
## Original RGB Image
```PYTHON
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
(np.float64(-0.5), np.float64(940.5), np.float64(1535.5), np.float64(-0.5))
```
## Convert RGB to HSV
```PYTHON
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
# HSV Image
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
(np.float64(-0.5), np.float64(940.5), np.float64(1535.5), np.float64(-0.5))
```
## Convert RGB to GRAY
```PYTHON
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)
```
## Grayscale Image
```PYTHON
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
(np.float64(-0.5), np.float64(940.5), np.float64(1535.5), np.float64(-0.5))
```
## Convert RGB to YCrCb
```PYTHON
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)
```
## YCrCb Image
```PYTHON
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
(np.float64(-0.5), np.float64(940.5), np.float64(1535.5), np.float64(-0.5))
```
## Convert HSV back to RGB
```PYTHON
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
(np.float64(-0.5), np.float64(940.5), np.float64(1535.5), np.float64(-0.5))
```
## Modify a block of pixels (300x300) to white, starting from (200, 200)
```PYTHON
image[200:500, 200:500] = [255, 255, 255]  # Rows: 200-499, Columns: 200-499
```
## Convert BGR to RGB for displaying with Matplotlib
```PYTHON
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
```
## Display the modified image
```PYTHON
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()
```
## Load the image
```PYTHON
image = cv2.imread('VIN.jpeg') 
image.shape
(1536, 941, 3)
```
## Resize the image to half its size
```PYTHON
resized_image = cv2.resize(image, (768 // 2, 600 // 2))  # (new_width, new_height)
```
## Convert BGR to RGB for displaying with Matplotlib
```PYTHON
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
resized_image_rgb.shape
(300, 384, 3)
```
## Display the resized image
```PYTHON
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
```
## Load the image
```PYTHON
image = cv2.imread('VIN.jpeg') 
image.shape
(1536, 941, 3)
```
## Crop a 300x300 region starting from (50, 50)
```PYTHON
roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349
```
## Convert BGR to RGB for displaying with Matplotlib
```PYTHON
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
```
## Display the cropped region (ROI)
```PYTHON
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
```
## Load the image
```PYTHON
image = cv2.imread('VIN.jpeg')
```
## Flip the image horizontally (left-right)
```PYTHON
flipped_horizontally = cv2.flip(image, 1)
```
## Convert BGR to RGB for displaying with Matplotlib
```PYTHON
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
```
## Horizontal flip
```PYTHON
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
(np.float64(-0.5), np.float64(940.5), np.float64(1535.5), np.float64(-0.5))
```
## Flip the image vertically (up-down)
```PYTHON
flipped_vertically = cv2.flip(image, 0)
```
## Convert BGR to RGB for displaying with Matplotlib
```PYTHON
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
```
## Vertical flip
```PYTHON
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
(np.float64(-0.5), np.float64(940.5), np.float64(1535.5), np.float64(-0.5))
```
 
# Output:
# Display the image using Matplotlib
<img width="342" height="533" alt="Screenshot 2026-02-02 112957" src="https://github.com/user-attachments/assets/04ccb583-8ca9-4594-824d-368611385d60" />

# Draw a line from top-left to bottom-right
<img width="286" height="523" alt="Screenshot 2026-02-02 113202" src="https://github.com/user-attachments/assets/fbb92f17-a6c5-48ab-bb70-d9305604769f" />
<img width="306" height="524" alt="Screenshot 2026-02-02 113153" src="https://github.com/user-attachments/assets/5811e6d5-6e6a-488f-a5de-ca5f103a7c43" />
<img width="300" height="523" alt="Screenshot 2026-02-02 113306" src="https://github.com/user-attachments/assets/52166a7b-bfc0-45d2-a100-21eb8497a970" />
<img width="288" height="516" alt="Screenshot 2026-02-02 113318" src="https://github.com/user-attachments/assets/34867898-3a85-47aa-b597-8cf446d1b5da" />

# HSV Image
<img width="294" height="507" alt="Screenshot 2026-02-02 113444" src="https://github.com/user-attachments/assets/91d88550-955f-4690-bb32-d1b0dc4edb20" />

# Grayscale Image
<img width="286" height="507" alt="Screenshot 2026-02-02 113528" src="https://github.com/user-attachments/assets/482eeec0-9565-4dd8-aa8c-01066151b329" />


# YCrCb Image
<img width="279" height="503" alt="Screenshot 2026-02-02 113611" src="https://github.com/user-attachments/assets/4597dcf1-001a-4c40-bc67-c4af4fd6208a" />
<img width="349" height="522" alt="Screenshot 2026-02-02 113620" src="https://github.com/user-attachments/assets/46bb2c3c-b3cb-4d42-a5b2-2fc75de827e0" />
<img width="485" height="528" alt="Screenshot 2026-02-02 113637" src="https://github.com/user-attachments/assets/bdad719f-4973-4af2-908d-335d9edeb5f0" />

# Horizontal flip
<img width="291" height="516" alt="Screenshot 2026-02-02 113643" src="https://github.com/user-attachments/assets/51df6ebb-38d4-4d40-96fb-ec24be08abda" />

# Vertical flip
<img width="291" height="512" alt="Screenshot 2026-02-02 113659" src="https://github.com/user-attachments/assets/e1746405-2358-46e4-a6b0-90af22bbbf93" />

## Result:
Thus, the images were read, displayed, adjustments were made, and bitwise operations were performed successfully using the Python program.

