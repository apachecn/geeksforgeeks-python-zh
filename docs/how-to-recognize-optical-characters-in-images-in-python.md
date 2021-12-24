# 如何在 Python 中识别图像中的光学字符？

> 原文:[https://www . geesforgeks . org/如何识别 python 图像中的光学字符/](https://www.geeksforgeeks.org/how-to-recognize-optical-characters-in-images-in-python/)

**先决条件:**[](https://www.geeksforgeeks.org/text-localization-detection-and-recognition-using-pytesseract/)****[**OpenCV**](https://www.geeksforgeeks.org/opencv-python-tutorial/)****

****在本文中，我们将从图像中识别字符，并从图像中获取文本数据。让我们快速介绍一下所需模块。****

*   ******OpenCV:** 它是一个 Python 模块，我们可以在其中进行图像处理、视频捕捉，以及一些分析工具，比如人脸检测或者物体检测。它有 C++、Python、Java 和 MATLAB 接口，支持 Windows、Linux、Android 和 Mac OS。****
*   ******小魔方:**Python-小魔方是一款针对 Python 的光学字符识别(OCR)工具。也就是说，它将识别并“读取”嵌入图像中的文本。python-宇宙魔方是谷歌[宇宙魔方-光学字符识别](https://tesseract-ocr.github.io/tessdoc/4.0-with-LSTM.html#400-alpha-for-windows)引擎的包装器。作为一个独立的调用脚本，它也很有用，因为它可以读取枕头和细尼卡图像库支持的所有图像类型，包括 jpeg、png、gif、BMP、tiff 等。此外，如果用作脚本，Python-tesserrate 将打印识别出的文本，而不是将其写入文件。****

******进场:******

*   ****导入所需模块****
*   ****设置 pytesseract 的路径。****
*   ****用 cv2.imread()读取图像****
*   ****将图像转换为 RGB 格式。****
*   ****使用 pytesserract . image _ to _ string(img)从图像中提取文本。****

******我们将使用这张图片进行** **演示:******

****![](img/e6f0fcb44d11bb93b365231db8d34f96.png)****

******以下是完整实现:******

## ****蟒蛇 3****

```py
**# importing the libraries
import cv2
import pytesseract

# seting the path of pytesseract exe
# you have to write the location of
# on which your tesseract was installed
pytesseract.pytesseract.tesseract_cmd = 'C:\\Program Files\\Tesseract-OCR\\tesseract.exe'

# Now we will read the image in our program
# you have to put your image path in place of photo.jpg
img = cv2.imread('photo.jpg')

# Our image will read as BGR format,
# So we will convert in RGB format because 
# tesseract can only read in RGB format
img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

# For getting the text and number from image
print(pytesseract.image_to_string(img))

# For displaying the orignal image
cv2.imshow("result", img)
cv2.waitKey(0)**
```

******输出:******

```py
****GeeksforGeeks****
```