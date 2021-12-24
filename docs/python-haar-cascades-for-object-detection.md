# Python |用于对象检测的哈尔级联

> 原文:[https://www . geesforgeks . org/python-Haar-cascades-for-object-detection/](https://www.geeksforgeeks.org/python-haar-cascades-for-object-detection/)

目标检测是一种与计算机视觉、图像处理和深度学习相关的计算机技术，用于检测图像和视频中的目标实例。在本文中，我们将使用哈尔级联来进行物体检测。

### **什么是哈尔喀斯喀特？**

哈尔级联分类器是一种有效的目标检测方法。这种方法是由保罗·维奥拉和迈克尔·琼斯在他们的论文[中提出的，利用简单特征的增强级联](https://www.researchgate.net/publication/3940582_Rapid_Object_Detection_using_a_Boosted_Cascade_of_Simple_Features)快速检测目标。哈尔级联是一种基于机器学习的方法，其中使用大量的正图像和负图像来训练分类器。

*   **正面图像–**这些图像包含我们希望分类器识别的图像。
*   **负像–**其他一切的像，不包含我们想要检测的物体。

**要求:**

*   确保你的电脑上安装了 python、Matplotlib 和 OpenCV(所有最新版本)。
*   哈尔级联文件可以从 [OpenCV Github 资源库](https://github.com/opencv/opencv/tree/master/data/haarcascades)下载。

**实施**T2】

## 蟒蛇 3

```
# Importing all required packages
import cv2
import numpy as np
import matplotlib.pyplot as plt % matplotlib inline

# Read in the cascade classifiers for face and eyes
face_cascade = cv2.CascadeClassifier('../DATA / haarcascades / haarcascade_frontalface_default.xml')
eye_cascade = cv2.CascadeClassifier('../DATA / haarcascades / haarcascade_eye.xml')

# create a function to detect face
def adjusted_detect_face(img):

    face_img = img.copy()

    face_rect = face_cascade.detectMultiScale(face_img,
                                              scaleFactor = 1.2,
                                              minNeighbors = 5)

    for (x, y, w, h) in face_rect:
        cv2.rectangle(face_img, (x, y),
                      (x + w, y + h), (255, 255, 255), 10)\

    return face_img

# create a function to detect eyes
def detect_eyes(img):

    eye_img = img.copy()   
    eye_rect = eye_cascade.detectMultiScale(eye_img,
                                            scaleFactor = 1.2,
                                            minNeighbors = 5)   
    for (x, y, w, h) in eye_rect:
        cv2.rectangle(eye_img, (x, y),
                      (x + w, y + h), (255, 255, 255), 10)       
    return eye_img

# Reading in the image and creating copies
img = cv2.imread('../sachin.jpg')
img_copy1 = img.copy()
img_copy2 = img.copy()
img_copy3 = img.copy()

# Detecting the face
face = adjusted_detect_face(img_copy)
plt.imshow(face)
# Saving the image
cv2.imwrite('face.jpg', face)
```

![](img/591f53587a37764c05f4cde3c9241681.png)

**代码:探测眼睛**

## 蟒蛇 3

```
eyes = detect_eyes(img_copy2)
plt.imshow(eyes)
cv2.imwrite('face_eyes.jpg', eyes)
```

![](img/ecb10af798b3850fb2b1045c642bfa06.png)

**代码:检测脸部和眼睛**

## 蟒蛇 3

```
eyes_face = adjusted_detect_face(img_copy3)
eyes_face = detect_eyes(eyes_face)
plt.imshow(eyes_face)
cv2.imwrite('face+eyes.jpg', eyes_face)
```

![](img/137afd46f0eeba56cfbe4dd6056f49b6.png)

哈尔级联可以用来检测任何类型的对象，只要你有合适的 XML 文件。您甚至可以从头开始创建自己的 XML 文件来检测您想要的任何类型的对象。