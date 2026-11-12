# Image-Handling-and-Pixel-Transformations-Using-OpenCV 

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
- **Name:** Sanjai R 
- **Register Number:** 212223040180

  ### Ex. No. 01

```
import cv2
import matplotlib.pyplot as plt
# Read the image using OpenCV
img = cv2.imread('me.jpg', cv2.IMREAD_COLOR)
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
# Display the image using Matplotlib
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()
```

<img width="306" height="410" alt="7093a69e-f8fb-4795-80fa-41cad50db725" src="https://github.com/user-attachments/assets/d9f19e5a-f73f-4a32-9d1c-1313e92232c6" />


```
# Load the image
image = cv2.imread('me.jpg')
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
# Draw a line from top-left to bottom-right
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (0, 255, 0), 2) # cv2.line(image, start_point, end_point, color, thickness)
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()
```

<img width="306" height="410" alt="f9cd14bf-eede-4719-b374-5bd8dbe6a4a8" src="https://github.com/user-attachments/assets/19a8b79f-0261-4657-96e0-f752d9924919" />


```
# Load the image
image = cv2.imread('me.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
circle_img = cv2.circle(img_rgb,(400,300),150,(0,255,0),10) # cv2.circle(image, center, radius, color, thickness)
plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()
```

<img width="306" height="410" alt="80d06338-8724-4920-b3f5-614b3ce1b3b5" src="https://github.com/user-attachments/assets/e9cc85bc-3ebf-469b-b88e-05ccf4ddc685" />


```
# Load the image
image = cv2.imread('me.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img.shape
# Draw a rectangle around the Whole image
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()
```

<img width="306" height="410" alt="7682f683-ec7e-4f91-97ee-988a8f5b797e" src="https://github.com/user-attachments/assets/ded57e3f-952c-4265-9229-ae1fe69078f9" />


```
# Load the image
image = cv2.imread('me.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
# Add text to the image
text_img = cv2.putText(img_rgb, "KANAGAVEL R", (30, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (0, 0, 255), 800)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)
plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()
```

<img width="306" height="410" alt="8852f3a8-871a-4861-92d4-13087a88dd4b" src="https://github.com/user-attachments/assets/e20d1185-9eb1-4b65-9206-64789a283ada" />


```
# Load the image
image = cv2.imread('me.jpg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
# Original RGB Image
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
```

<img width="306" height="410" alt="53fd8cb8-e1f0-4fb6-8f8b-94173f3265a5" src="https://github.com/user-attachments/assets/46be684f-fc2b-4ebc-8414-54f29c2b282d" />


```
# Convert RGB to HSV
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
# HSV Image
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
```

<img width="306" height="410" alt="95d1c60d-9809-435a-8a6c-002d04ca283d" src="https://github.com/user-attachments/assets/9ee89440-0023-426b-a2c9-1566d41cee3a" />


```
# Convert RGB to GRAY
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)
# Grayscale Image
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
```

<img width="306" height="410" alt="cb341a0d-260c-4355-ac3c-ef4d0eeee6f8" src="https://github.com/user-attachments/assets/219a86fe-e7f8-403c-a1ac-9cd3096bfe39" />


```
# Convert RGB to YCrCb
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)
# YCrCb Image
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
```

<img width="306" height="410" alt="b788fcf4-f80d-46b4-a25f-6e59f41e896d" src="https://github.com/user-attachments/assets/afcf5d90-c24a-4aee-9155-e1b36fcbcba7" />


```
# Convert HSV back to RGB
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
```

<img width="306" height="410" alt="d61465f2-912f-46b2-b3d6-b03144f493ab" src="https://github.com/user-attachments/assets/58ada818-ceb0-40ef-b3db-7310be39d0a5" />


```
# Modify a block of pixels (300x300) to white, starting from (200, 200)
image[200:500, 200:500] = [255, 255, 255]  # Rows: 200-499, Columns: 200-499
# Convert BGR to RGB for displaying with Matplotlib
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
# Display the modified image
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()
```
<img width="306" height="410" alt="a1f25437-4e38-44b9-8955-4949ead1d35a" src="https://github.com/user-attachments/assets/de6d6c5d-97fc-4700-be29-d3103cbbfe06" />


```
# Load the image
image = cv2.imread('me.jpg')
image.shape
# Resize the image to half its size
resized_image = cv2.resize(image, (768 // 2, 600 // 2))  # (new_width, new_height)
# Convert BGR to RGB for displaying with Matplotlib
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
resized_image_rgb.shape
# Display the resized image
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
```

<img width="493" height="410" alt="90b07ba1-a78b-437d-8f9f-5890f16e7c55" src="https://github.com/user-attachments/assets/0d758232-d51e-412f-99b5-612ee3bd66d2" />


```
# Load the image
image = cv2.imread('me.jpg')
image.shape
# Crop a 300x300 region starting from (50, 50)
roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349
# Convert BGR to RGB for displaying with Matplotlib
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
# Display the cropped region (ROI)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
```

<img width="389" height="410" alt="9e0f1eb1-024b-4ad3-ae92-686b5c152126" src="https://github.com/user-attachments/assets/0fd98d3f-037f-4215-9947-5c6f188987b0" />


```
# Load the image
image = cv2.imread('me.jpg') 
# Flip the image horizontally (left-right)
flipped_horizontally = cv2.flip(image, 1)
# Convert BGR to RGB for displaying with Matplotlib
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
# Horizontal flip
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
```

<img width="306" height="410" alt="8555cfd8-4327-422c-b207-b1940aad9c69" src="https://github.com/user-attachments/assets/262ad275-ebd8-4f3b-a544-e4ac3fbda492" />


```
# Flip the image vertically (up-down)
flipped_vertically = cv2.flip(image, 0)
# Convert BGR to RGB for displaying with Matplotlib
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
# Vertical flip
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
```

<img width="306" height="410" alt="5e9c872a-e671-4563-a8bd-d0356f5daf58" src="https://github.com/user-attachments/assets/8b95a9fd-0f86-4497-9e97-d3aeccd81a98" />



## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.
