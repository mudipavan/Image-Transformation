# Image-Transformation
## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the necessary libraries and read the original image and save it as a image variable.

### Step2:
Translate the image using M=np.float32([[1,0,20],[0,1,50],[0,0,1]]) translated_img=cv2.warpPerspective(input_img,M,(cols,rows))

### Step3:
Scale the image using M=np.float32([[1.5,0,0],[0,2,0],[0,0,1]]) scaled_img=cv2.warpPerspective(input_img,M,(cols,rows))

### Step4:
Shear the image using M_x=np.float32([[1,0.2,0],[0,1,0],[0,0,1]]) sheared_img_xaxis=cv2.warpPerspective(input_img,M_x,(cols,rows))

### Step5:
Reflection of image can be achieved through the code M_x=np.float32([[1,0,0],[0,-1,rows],[0,0,1]]) reflected_img_xaxis=cv2.warpPerspective(input_img,M_x,(cols,rows))

### Step6:
Rotate the image using angle=np.radians(45) M=np.float32([[np.cos(angle),-(np.sin(angle)),0],[np.sin(angle),np.cos(angle),0],[0,0,1]]) rotated_img=cv2.warpPerspective(input_img,M,(cols,rows))
### Step7:
Crop the image using cropped_img=input_img[20:150,60:230]
### Step8:
Display all the Transformed images and end the program.

## Program:
```python
Developed By:mudi pavan
Register Number:212221230067
import numpy as np
import cv2
i)Image Translation
import matplotlib.pyplot as plt
inputImage=cv2.imread("jen.jpg")
inputImage=cv2.cvtColor(inputImage, cv2.COLOR_BGR2RGB)
plt.axis("off")
plt.imshow(inputImage)
plt.show()
rows, cols, dim = inputImage.shape
M= np.float32([[1, 0, 100],
                [0, 1, 200],
                 [0, 0, 1]])
translatedImage =cv2.warpPerspective (inputImage, M, (cols, rows))
plt.imshow(translatedImage)
plt.show()

ii) Image Scaling
import numpy as np
import cv2
import matplotlib.pyplot as plt
inputImage=cv2.imread("jenifer.jpg")
inputImage=cv2.cvtColor(inputImage, cv2.COLOR_BGR2RGB)
plt.axis("off")
plt.imshow(inputImage)
plt.show()
rows, cols, dim = inputImage.shape
M = np. float32 ([[1.5, 0 ,0],
                 [0, 1.8, 0],
                  [0, 0, 1]])
scaledImage=cv2.warpPerspective(inputImage, M, (cols * 2, rows * 2))
plt.imshow(scaledImage)
plt.show()



iii)Image shearing
import numpy as np
import cv2
import matplotlib.pyplot as plt
inputImage=cv2.imread("jen2.jpg")
inputImage=cv2.cvtColor(inputImage, cv2.COLOR_BGR2RGB)
plt.axis("off")
plt.imshow(inputImage)
plt.show()
rows, cols, dim = inputImage.shape
matrixX = np.float32([[1, 0.5, 0],
                      [0, 1 ,0],
                      [0, 0, 1]])

matrixY = np.float32([[1, 0, 0],
                      [0.5, 1, 0],
                      [0, 0, 1]])
shearedXaxis = cv2.warpPerspective (inputImage, matrixX, (int(cols * 1.5), int (rows * 1.5)))
shearedYaxis = cv2.warpPerspective (inputImage, matrixY, (int (cols * 1.5), int (rows * 1.5)))
plt.imshow(shearedXaxis)
plt.show()
plt.imshow(shearedYaxis)
plt.show()




iv)Image Reflection
import numpy as np
import cv2
import matplotlib.pyplot as plt
inputImage=cv2.imread("jen3.jpg")
inputImage=cv2.cvtColor(inputImage, cv2.COLOR_BGR2RGB)
plt.axis("off")
plt.imshow(inputImage)
plt.show()
rows, cols, dim = inputImage.shape
matrixx=np.float32([[1, 0, 0],
                    [0,-1,rows],
                    [0,0,1]])
matrixy=np.float32([[-1, 0, cols],
                    [0,1,0],
                    [0,0,1]])
reflectedX=cv2.warpPerspective(inputImage, matrixx, (cols, rows))
reflectedY=cv2.warpPerspective(inputImage, matrixy, (cols, rows))
plt.imshow(reflectedY)
plt.show()



v)Image Rotation

angle=np.radians(45)
inputImage=cv2.imread("rachel.jpg")
M=np.float32([[np.cos(angle),-(np.sin(angle)),0],
               [np.sin(angle),np.cos(angle),0],
               [0,0,1]])
rotatedImage = cv2.warpPerspective(inputImage,M,(int(cols),int(rows)))
plt.axis('off')
plt.imshow(rotatedImage)
plt.show()


vi)Image Cropping
angle=np.radians(45)
inputImage=cv2.imread("friends.jpg")
CroppedImage= inputImage[80:600, 80:430]
plt.axis('off')
plt.imshow(CroppedImage)
plt.show()




```
## Output:
### i)Image Translation
![dip p5-1](https://user-images.githubusercontent.com/94828517/233005627-d0e40802-398b-4db9-82c2-7881c1342820.jpg)


### ii) Image Scaling
![dip p5-2](https://user-images.githubusercontent.com/94828517/233005694-c764bd37-fb50-46f5-adbe-e9c9017ed543.jpg)



### iii)Image shearing
![dip p5-3](https://user-images.githubusercontent.com/94828517/233006037-c9063186-62be-479e-82e2-68e96fece373.jpg)

![dip p5-4](https://user-images.githubusercontent.com/94828517/233006123-df988e76-e7a5-47a6-9c0b-3ad36290fead.jpg)

![dip p5-5](https://user-images.githubusercontent.com/94828517/233006115-d53120d2-392b-4f9a-a0e7-9c6963454baa.jpg)


### iv)Image Reflection
![output]()




### v)Image Rotation
![dip p5-7](https://user-images.githubusercontent.com/94828517/233006793-ba5871e6-284e-4b14-9dc6-8d810a6c4560.jpg)




### vi)Image Cropping

![dip p5-8](https://user-images.githubusercontent.com/94828517/233006870-c08bc9a8-8394-4753-98d2-c33c5667b689.jpg)




## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
