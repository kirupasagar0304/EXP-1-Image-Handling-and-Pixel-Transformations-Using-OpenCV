# NAME : kirupasagar s
# REG.No : 212224230126

# EXP-1: Image-Handling-and-Pixel-Transformations-Using-OpenCV 

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



#### 1. Read the image ('Eagle_in_Flight.jpg') using OpenCV imread() as a grayscale image.
```PYTHON
import cv2
import matplotlib.pyplot as plt
```
## Read the image using OpenCV 
```PYTHON
img = cv2.imread('image.jpg', cv2.IMREAD_COLOR)
```
## Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)#
```PYTHON
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```
## Display the image using Matplotlib #
```PYTHON
plt.imshow(img_rgb, cmap='viridis')
plt.title("Original Image")
plt.axis('off')
plt.show()
```
## Load the image
```PYTHON
image = cv2.imread('image.jpg')
```
## Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
```PYTHON
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
(1536, 941, 3)
```
## Draw a line from top-left to bottom-right
```PYTHON
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2)
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()
```
## Load the image
```PYTHON
image = cv2.imread('image.jpg') 
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
image = cv2.imread('image.jpg') 
```
## Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
```PYTHON
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img.shape
(1536, 941, 3)
```
## Draw a rectangle around the Whole image
```PYTHON
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10) 
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()
```
## Load the image
```PYTHON
image = cv2.imread('image.jpg') 
```
## Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
```PYTHON
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```
## Add text to the image
```PYTHON
text_img = cv2.putText(img_rgb, "Opencv Drawing", (10, 35), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 10) 
plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()
```
## Load the image
```PYTHON
image = cv2.imread('image.jpg') 
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
image[200:500, 200:500] = [255, 255, 255] 
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
resized_image = cv2.resize(image, (768 // 2, 600 // 2))
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
roi = image[50:350, 50:350] 
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
image = cv2.imread('image.jpg')
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

## Output:
<img width="431" height="410" alt="2d4e85fb-6741-4705-be19-57d1e449014a" src="https://github.com/user-attachments/assets/a675024b-1bf6-4597-8b7c-1a198d3828b0" />
<img width="431" height="410" alt="c0a43f6d-fc7f-466f-9a15-dde352e475dd" src="https://github.com/user-attachments/assets/223b2220-5fc5-4a64-b05a-0396a50dd26c" />
<img width="431" height="410" alt="c9f0a209-c4e9-41bd-b2e8-891d1019c118" src="https://github.com/user-attachments/assets/218d33f5-b963-41f9-adf4-b7eb0a1f5c59" />
<img width="431" height="410" alt="467cca45-040c-4e83-8080-9a64a7e5ce87" src="https://github.com/user-attachments/assets/03a07d25-e403-4c93-84f0-b2c702e8fe15" />
<img width="431" height="410" alt="53f89a7f-f8bb-4aaf-b261-54da3bddbd07" src="https://github.com/user-attachments/assets/eea2f300-a161-4a2a-a53c-2ddeb526634d" />
<img width="431" height="410" alt="cf374aa5-22ef-491d-ba42-541ce4ece2a3" src="https://github.com/user-attachments/assets/78427635-4fcc-4ecc-aa06-d19f168528e9" />
<img width="431" height="410" alt="f0e1523f-63ef-4157-b53e-10c02261f042" src="https://github.com/user-attachments/assets/a68ed1cf-8bcb-4069-92e5-15024aaed1d0" />
<img width="431" height="410" alt="71adf061-225c-4e02-a590-c28c7a9fa154" src="https://github.com/user-attachments/assets/7b430a28-54e5-4d0a-bffc-153433dbc3a9" />
<img width="431" height="410" alt="a49ad6d3-ee2d-4249-82af-0c98b8b29886" src="https://github.com/user-attachments/assets/d9bcb25d-a26d-4bff-883d-bde96de6beef" />
<img width="431" height="410" alt="f862a04d-031f-4996-bd96-45a17c03446b" src="https://github.com/user-attachments/assets/af684ad7-1f03-4181-bca2-331e7e29f9f8" />
<img width="431" height="410" alt="65090ca4-c323-4db7-8f51-b060273aaad7" src="https://github.com/user-attachments/assets/24721260-5848-4b3c-8e52-391a7b900de4" />
<img width="493" height="410" alt="abcfe1a1-173d-4591-b3f0-ee01e53d5527" src="https://github.com/user-attachments/assets/2aee76f2-d29a-4736-802c-ee6223f0de48" />
<img width="389" height="410" alt="a707f755-7802-42e0-954f-175c52c7754b" src="https://github.com/user-attachments/assets/03eb4e05-87cd-4dc3-a783-d9801f166a76" />
<img width="431" height="410" alt="88f2e566-17b0-44fa-9f5e-04cb89038fe6" src="https://github.com/user-attachments/assets/c85ae532-e0d1-4fd4-89fe-ad63a275c835" />
<img width="431" height="410" alt="8f5e2436-b540-4691-a1ea-de589741bf4c" src="https://github.com/user-attachments/assets/d36d1215-90ff-47f9-bfdb-72b9f3470172" />

## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.
