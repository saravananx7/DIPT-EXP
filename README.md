# DIPT-EXP-3
## Image-Handling-and-Pixel-Transformations-Using-OpenCV
## AIM:
Write a Python program using OpenCV that performs the following tasks:

1.Read and Display an Image.
2.Adjust the brightness of an image.
3.Modify the image contrast.
4.Generate a third image using bitwise operations.

## Software Required:
Anaconda - Python 3.7
Jupyter Notebook (for interactive development and execution)

## Algorithm:
## Step 1:
Load an image from your local directory and display it.

## Step 2:
Create a matrix of ones (with data type float64) to adjust brightness.

## Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image.
Display the original, brighter, and darker images.

## Step 4:
Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix).
Display the original, lower contrast, and higher contrast images.

## Step 5:
Split the image (boy.jpg) into B, G, R components and display the channels
Program Developed By:
## Name: SARAVANAN K
## Register Number: 212225040387

Ex. No. 01
## 1. Read the image ('Eagle_in_Flight.jpg') using OpenCV imread() as a grayscale image.
~~~
import cv2
import matplotlib.pyplot as plt
~~~
## 2. Print the image width, height & Channel.
~~~
 img = cv2.imread('MS_Dhoni.jpg', cv2.IMREAD_COLOR)
 img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
~~~
## 3. Display the image using matplotlib imshow().
~~~
 plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()
~~~
## 4. Save the image as a PNG file using OpenCV imwrite().
~~~
 image = cv2.imread('MS_Dhoni.jpg')
~~~
## 5. Read the saved image above as a color image using cv2.cvtColor().
~~~
 img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
~~~
## 6. Display the Colour image using matplotlib imshow() & Print the image width, height & channel.
~~~
 img_rgb.shape
~~~
## 7. Crop the image to extract any specific (Eagle alone) object from the image.
~~~
 line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2) # cv2.line(image, start_point, end_point, color, thickness)
~~~
## 8. Resize the image up by a factor of 2x.
~~~
 plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()
~~~
## 9. Flip the cropped/resized image horizontally.
~~~
 image = cv2.imread('MS_Dhoni.jpg') 
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
~~~
## 10. Read in the image ('Apollo-11-launch.jpg').
~~~
 img_rgb.shape
~~~
## 11. Add the following text to the dark area at the bottom of the image (centered on the image):
~~~
text = 'Apollo 11 Saturn V Launch, July 16, 1969'
font_face = cv2.FONT_HERSHEY_PLAIN
 square_img = img_rgb.copy()

cv2.rectangle(square_img,
              (250, 150),
              (550, 450),
              (255, 0, 0),
              10)
~~~
## 12. Draw a magenta rectangle that encompasses the launch tower and the rocket.
~~~
rect_color = magenta
 plt.imshow(square_img)
plt.title("Image with Square")
plt.axis("off")
plt.show()
~~~
## 13. Display the final annotated image.
~~~
 image = cv2.imread('MS_Dhoni.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
~~~
## 14. Read the image ('Boy.jpg').
~~~
img.shape
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)

~~~
## 15. Adjust the brightness of the image.
# Create a matrix of ones (with data type float64)
# matrix_ones = 
~~~
 plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()
~~~
## 16. Create brighter and darker images.
~~~
img_brighter = cv2.add(img, matrix)
img_darker = cv2.subtract(img, matrix)
image = cv2.imread('MS_Dhoni.jpg') 

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
 
~~~
## 17. Display the images (Original Image, Darker Image, Brighter Image).
~~~
text_img = cv2.putText(img_rgb, "OpenCV Drawing", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 10)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)
~~~
## 18. Modify the image contrast.
~~~
plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()
 
~~~
## 19. Display the images (Original, Lower Contrast, Higher Contrast).
~~~
image = cv2.imread('MS_Dhoni.jpg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
~~~
## 20. Split the image (boy.jpg) into the B,G,R components & Display the channels.
~~~
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
~~~
## 21. Merged the R, G, B , displays along with the original image
~~~
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")


~~~
## 22. Split the image into the H, S, V components & Display the channels.
~~~
insert_img = cv2.imread("photo.jpeg")
insert_img = cv2.resize(insert_img, (300, 300))
image[200:500, 200:500] = insert_img
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
plt.imshow(image_rgb)
plt.title("Image with Inserted Image")
plt.axis("off")
plt.show()
image = cv2.imread('MS_Dhoni.jpg')
image.shape
resized_image = cv2.resize(image, (768 // 2, 600 // 2))  # (new_width, new_height)
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
resized_image_rgb.shape
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
image = cv2.imread('MS_Dhoni.jpg')
image.shape
roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
image = cv2.imread('MS_Dhoni.jpg')
flipped_horizontally = cv2.flip(image, 1)
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
~~~
## 23. Merged the H, S, V, displays along with original image.
~~~
flipped_vertically = cv2.flip(image, 0)
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")

~~~
## Output:
<img width="711" height="515" alt="image" src="https://github.com/user-attachments/assets/8441c344-0871-45b5-80d7-9f098e93c3ed" />
<img width="736" height="530" alt="image" src="https://github.com/user-attachments/assets/63c193f3-cbf4-454e-a0f1-e3b05ac5626f" />
<img width="767" height="527" alt="image" src="https://github.com/user-attachments/assets/854e13bf-08d8-4147-90b9-3bf53b8c8a44" />
<img width="715" height="532" alt="image" src="https://github.com/user-attachments/assets/24b6eddd-8412-43fd-bff6-5c89e23c7772" />
<img width="617" height="551" alt="image" src="https://github.com/user-attachments/assets/70fb5977-5033-4995-923a-172dd9ec7121" />
<img width="687" height="518" alt="image" src="https://github.com/user-attachments/assets/cb0d9f81-1799-4f85-9dee-c66c4e138367" />
<img width="691" height="518" alt="image" src="https://github.com/user-attachments/assets/354e4ad3-ad24-4cb7-ba11-f037047ba615" />
<img width="692" height="517" alt="image" src="https://github.com/user-attachments/assets/d50943cb-dbd6-4d81-8d2e-9d1068836f69" />
<img width="712" height="536" alt="image" src="https://github.com/user-attachments/assets/44496f93-93b2-46b9-9ed8-558b904a4b13" />
<img width="693" height="521" alt="image" src="https://github.com/user-attachments/assets/87a80a62-05bd-44af-b301-b879f827bb4f" />
<img width="757" height="541" alt="image" src="https://github.com/user-attachments/assets/39e077ba-d5a8-4bb7-a61f-5cb988596a03" />
<img width="770" height="545" alt="image" src="https://github.com/user-attachments/assets/dc773a23-4f8b-43f4-8d4f-82bc92af2008" />
<img width="670" height="522" alt="image" src="https://github.com/user-attachments/assets/4e96c819-f752-4a6e-9ac8-1119d6cfcb17" />
<img width="683" height="510" alt="image" src="https://github.com/user-attachments/assets/dedbb625-6e23-4a30-8098-3240d2f5483e" />
<img width="741" height="543" alt="image" src="https://github.com/user-attachments/assets/32259ce5-f586-4d7b-b71a-1e10e869151c" />




## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.
