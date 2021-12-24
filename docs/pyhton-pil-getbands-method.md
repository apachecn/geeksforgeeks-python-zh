# Python PIL | getbands()方法

> 原文:[https://www.geeksforgeeks.org/pyhton-pil-getbands-method/](https://www.geeksforgeeks.org/pyhton-pil-getbands-method/)

PIL is the Python Imaging Library which provides the python interpreter with image editingcapabilities. **PIL.Image.getbands()** method returns a tuple containing the name of each band in the image.For example, getbands on an RGB image returns (“R”, “G”, “B”).

```py
Syntax: PIL.Image.getbands()
Parameters: no arguments
Returns: A tuple containing band names.

```

```py
# Importing Image module from PIL package 
from PIL import Image

# creating a image object
im1 = Image.open(r"C:\Users\sadow984\Desktop\i3.PNG")

# get bands of image
im2 = im1.getbands()

# print band names.
print(im2)
```

**输出:**
('R '，' G '，' B '，' A ')

上面使用的图像是:
![](img/c8d4a0e91e024d3d7c73c60e72b6a907.png)

```py
# Importing Image module from PIL package 
from PIL import Image

# creating a image object
im1 = Image.open(r"C:\Users\sadow984\Desktop\r1.PNG")

# get bands of image
im2 = im1.getbands()

# print band names.
print(im2)
```

**输出:**
('P '，)

上面使用的图像是:
![](img/bddb5fa589c97ddbd14f0b222cc69ffe.png)