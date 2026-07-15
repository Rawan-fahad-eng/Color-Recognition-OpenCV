# Color Recognition using OpenCV

## About This Project
This is a simple project I made for my Cryptography/Information Security course task using OpenCV. The idea is to build a program that can look at a picture and figure out which colors are in it — like red, yellow, green, blue, and orange — then draw a box around each colored object and label it with its name.

## How It Works
1. The program reads an image file.
2. It converts the image from BGR (the format OpenCV uses by default) to HSV, because HSV makes it much easier to detect colors.
3. For each color (red, yellow, green, blue, orange), I defined a range of HSV values that represent that color.
4. The program checks the image against each color range and creates a "mask" — basically a black and white version of the image where white means "this pixel matches the color" and black means "it doesn't."
5. Using the mask, it finds the contours (the outlines of the colored areas).
6. If a colored area is big enough (more than 500 pixels), the program draws a rectangle around it and writes the color's name on top.
7. At the end, it prints how many areas of each color were found, and shows the final image with all the boxes and labels.

## Tools Used
- Python
- OpenCV (cv2)
- NumPy
- Google Colab (to write and run the code)

## How to Run It
1. Open the notebook in Google Colab (there's an "Open in Colab" button at the top of the file).
2. Upload an image that has a few different colors in it (fruits work great for this).
3. In the code, change the image filename in this line to match your uploaded image:
   ```python
   image = cv2.imread('your_image_name.jpeg')
