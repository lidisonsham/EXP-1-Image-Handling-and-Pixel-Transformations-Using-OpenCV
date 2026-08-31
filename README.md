# Image-Handling-and-Pixel-Transformations-Using-OpenCV 
## NAME: LIDISON SHAM M
## REG.NO: 212224040171
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

  ### Ex. No. 01

### **Step 1: Read and Display Image**
```python
import cv2
import matplotlib.pyplot as plt
img = cv2.imread('Qno. 1.jpg', cv2.IMREAD_COLOR)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
plt.imshow(img_rgb, cmap='viridis')  
plt.title("Original Image")
plt.axis('off')  
plt.show()
```
### **Step 2: Draw a Line**
```python
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2)
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()
```

### **Step 3: Draw a Circle**
```python
circle_img = cv2.circle(img_rgb,(400,300),150,(255,0,0),10)
plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()
```

### **Step 4: Draw a Rectangle**
```python
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10)
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()
```

### **Step 5: Add Text**
```python
text_img = cv2.putText(img_rgb, "OpenCV Drawing", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 10)
plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()
```

### **Step 6: Convert RGB to HSV**
```python
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
```
### **Step 7: Convert RGB to Gray**
```python
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
```
### **Step 8: Convert RGB to YCrCb**
```python
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
```

### **Step 9: Convert HSV back to RGB**
```python
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
```

### **Step 10: Modify Pixel Block**
```python
image[200:500, 200:500] = [255, 255, 255]
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()
```

### **Step 11: Resize Image**
```python
resized_image = cv2.resize(image, (768 // 2, 600 // 2))
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
```

### **Step 12: Crop ROI**
```python
roi = image[50:350, 50:350]
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
```

### **Step 13: Flip Horizontally**
```python
image = cv2.imread('Qno. 1.jpg')
flipped_horizontally = cv2.flip(image, 1)
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
```

### **Step 14: Flip Vertically**
```python
flipped_vertically = cv2.flip(image, 0)
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
```

### **Step 15: Save Final Image**
```python
cv2.imwrite(
"final_output.jpg",
flipped_horizontally
)**
```

## Output:
### Original Image
<img width="388" height="530" alt="image" src="https://github.com/user-attachments/assets/f16f6e2e-cd11-4f36-b33d-c69a9180fd16" />

### Image with Rectangle
<img width="463" height="570" alt="image" src="https://github.com/user-attachments/assets/274108c6-5409-4abd-b63d-b38e147552c4" />



### Gray Image 
<img width="471" height="570" alt="image" src="https://github.com/user-attachments/assets/799baa33-ded1-4b78-8349-f0e9141d259b" />

### HSV, Gray and YCrCb Images
<img width="486" height="597" alt="image" src="https://github.com/user-attachments/assets/70acd438-9a32-4f83-a132-2da017d5b2a0" />


### Cropped Image

<img width="482" height="596" alt="image" src="https://github.com/user-attachments/assets/d9f3c6fb-e072-412c-8b77-2840392db93c" />


### Annotated image 
<img width="482" height="596" alt="image" src="https://github.com/user-attachments/assets/c7844db3-f9e0-4bd1-b9e9-a49f2c0f8235" />


### Blue,Red,Green Image
<img width="1157" height="543" alt="image" src="https://github.com/user-attachments/assets/5ecbcca7-5784-4607-b9aa-a3d563121b9e" />


### Merged RGB Image
<img width="467" height="587" alt="image" src="https://github.com/user-attachments/assets/566bcb27-f5e4-431d-ab48-cbda76150f8b" />


### Hue,Saturation,Value Channel
<img width="1195" height="522" alt="image" src="https://github.com/user-attachments/assets/3973291a-30aa-4dc4-a582-d5408c6aad6a" />

## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.
