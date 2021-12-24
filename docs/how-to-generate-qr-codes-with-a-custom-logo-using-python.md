# 如何使用 Python 生成带有自定义标志的二维码？

> 原文:[https://www . geesforgeks . org/如何使用 python 生成带有自定义徽标的二维码/](https://www.geeksforgeeks.org/how-to-generate-qr-codes-with-a-custom-logo-using-python/)

在本文中，我们将讨论如何生成一个以图像为中心的二维码。我们将生成任何文本、链接等的二维码。，并将图像放在该二维码的中心，使其代表品牌二维码

### 所需模块:

*   [**【枕头】**](https://www.geeksforgeeks.org/python-pillow-a-fork-of-pil/) **:** 它是一个轻量级的图像处理工具，可以帮助编辑、创建和保存图像。枕头支持许多图像文件格式，包括 BMP、PNG、JPEG 和 TIFF。可以使用以下命令安装:

```py
pip install Pillow
```

*   **二维码:**是用于生成二维码的外部 python 库。可以使用以下命令安装:

```py
pip install qrcode
```

### **使用的图像:**

![](img/d3794a7c2e68a1be8e4507615cf58d4a.png)

## 蟒蛇 3

```py
# import modules
import qrcode
from PIL import Image

# taking image which user wants 
# in the QR code center
Logo_link = 'g4g.jpg'

logo = Image.open(Logo_link)

# taking base width
basewidth = 100

# adjust image size
wpercent = (basewidth/float(logo.size[0]))
hsize = int((float(logo.size[1])*float(wpercent)))
logo = logo.resize((basewidth, hsize), Image.ANTIALIAS)
QRcode = qrcode.QRCode(
    error_correction=qrcode.constants.ERROR_CORRECT_H
)

# taking url or text
url = 'https://www.geeksforgeeks.org/'

# addingg URL or text to QRcode
QRcode.add_data(url)

# generating QR code
QRcode.make()

# taking color name from user
QRcolor = 'Green'

# adding color to QR code
QRimg = QRcode.make_image(
    fill_color=QRcolor, back_color="white").convert('RGB')

# set size of QR code
pos = ((QRimg.size[0] - logo.size[0]) // 2,
       (QRimg.size[1] - logo.size[1]) // 2)
QRimg.paste(logo, pos)

# save the QR code generated
QRimg.save('gfg_QR.png')

print('QR code generated!')
```