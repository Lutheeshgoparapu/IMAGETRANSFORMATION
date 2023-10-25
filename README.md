# IMAGETRANSFORMATION

## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
Step1:

Import the necessary libraries and read the original image and save it as a image variable.

Step2:

Translate the image using M=np.float32([[1,0,20],[0,1,50],[0,0,1]]) translated_img=cv2.warpPerspective(input_img,M,(cols,rows))??

Step3:

Scale the image using M=np.float32([[1.5,0,0],[0,2,0],[0,0,1]]) scaled_img=cv2.warpPerspective(input_img,M,(cols,rows))?

Step4:

Shear the image using M_x=np.float32([[1,0.2,0],[0,1,0],[0,0,1]]) sheared_img_xaxis=cv2.warpPerspective(input_img,M_x,(cols,rows))

Step5:

Reflection of image can be achieved through the code M_x=np.float32([[1,0,0],[0,-1,rows],[0,0,1]]) reflected_img_xaxis=cv2.warpPerspective(input_img,M_x,(cols,rows))

Step6:

Rotate the image using angle=np.radians(45) M=np.float32([[np.cos(angle),-(np.sin(angle)),0],[np.sin(angle),np.cos(angle),0],[0,0,1]]) rotated_img=cv2.warpPerspective(input_img,M,(cols,rows))

Step7:

Crop the image using cropped_img=input_img[20:150,60:230]

Step8:

Display all the Transformed images and end the program.


## Program:
```
python
Developed By: G.Lutheesh
Register Number:212221230029
```
### i)Image Translation
```
import numpy as np
import cv2
import matplotlib.pyplot as plt
inputImage=cv2.imread("33.jpg")
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

```


### ii) Image Scaling
```
rows, cols, dim = inputImage.shape
M = np. float32 ([[1.5, 0 ,0],
                 [0, 1.8, 0],
                  [0, 0, 1]])
scaledImage=cv2.warpPerspective(inputImage, M, (cols * 2, rows * 2))
plt.imshow(scaledImage)
plt.show()
```


### iii)Image shearing
```
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

```



### iv)Image Reflection
```

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

```



### v)Image Rotation
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
angle=np.radians(45)
inputImage=cv2.imread("33.jpg")
rows, cols, dim = inputImage.shape
M=np.float32([[np.cos(angle),-(np.sin(angle)),0],
               [np.sin(angle),np.cos(angle),0],
               [0,0,1]])
rotatedImage = cv2.warpPerspective(inputImage,M,(int(cols),int(rows)))
plt.axis('off')
plt.imshow(rotatedImage)
plt.show()
```



### vi)Image Cropping
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
angle=np.radians(45)
inputImage=cv2.imread("33.jpg")
CroppedImage= inputImage[20:150, 60:230]
plt.axis('off')
plt.imshow(CroppedImage)
plt.show()
```




## Output:
### i)Image Translation


![WhatsApp Image 2023-10-25 at 09 54 17_94db4b4c](https://github.com/Lutheeshgoparapu/IMAGETRANSFORMATION/assets/94154531/fec4557a-dbf2-4f77-af11-30501c98a9ed)



### ii) Image Scaling

![WhatsApp Image 2023-10-25 at 09 54 29_e55d4119](https://github.com/Lutheeshgoparapu/IMAGETRANSFORMATION/assets/94154531/64a4a2b9-9482-424c-b0aa-e1cfea1e2832)




### iii)Image shearing
![WhatsApp Image 2023-10-25 at 09 54 41_47bafc4c](https://github.com/Lutheeshgoparapu/IMAGETRANSFORMATION/assets/94154531/559b80a3-d13b-409c-b8bd-1356bcbe979e)

![WhatsApp Image 2023-10-25 at 09 55 06_ea1578c6](https://github.com/Lutheeshgoparapu/IMAGETRANSFORMATION/assets/94154531/f7b4451f-de02-4614-947e-fe171ec5d7f8)




### iv)Image Reflection


![WhatsApp Image 2023-10-25 at 09 55 21_af5acf0c](https://github.com/Lutheeshgoparapu/IMAGETRANSFORMATION/assets/94154531/1f4f0947-a48e-4df1-963a-5e0576bd79dd)





### v)Image Rotation
![WhatsApp Image 2023-10-25 at 09 55 21_af5acf0c](https://github.com/Lutheeshgoparapu/IMAGETRANSFORMATION/assets/94154531/91b37a30-c46e-444f-bf3b-09f6a61f66f0)




### vi)Image Cropping

![WhatsApp Image 2023-10-25 at 09 55 59_0c1caf8b](https://github.com/Lutheeshgoparapu/IMAGETRANSFORMATION/assets/94154531/b0030608-2043-4d1f-b40a-669a5f3ecbd4)





## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
