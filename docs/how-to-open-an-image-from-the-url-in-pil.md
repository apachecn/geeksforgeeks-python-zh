# 如何从 PIL 的 URL 打开图片？

> 原文:[https://www . geeksforgeeks . org/如何从 pil 中的 url 打开图像/](https://www.geeksforgeeks.org/how-to-open-an-image-from-the-url-in-pil/)

在本文中，我们将学习如何使用 python 中的 PIL 模块从 URL 打开图像。为了从 Python 中的一个网址打开图像，我们需要两个包[](https://www.geeksforgeeks.org/python-urllib-module/)**和 [**枕头(PIL)。**](https://www.geeksforgeeks.org/python-pillow-a-fork-of-pil/)**

#### **方法:**

*   **安装所需的库，然后导入它们。要安装，请使用以下命令:**

```
pip install pillow
```

*   **复制任何图像的网址。**
*   **在 urllib.request.urlretrieve()方法中写入文件名为的 URL。**
*   **使用 Image.open()方法打开图像。**
*   **最后用 obj.show()方法显示图像。**

****样本代码:****

> **导入 urllib.request**
> 
>  **来自 PIL 进口图像
> 
> URL lib . request . URL retrieve(' Image URL '，" file_name ")
> 
> 打开(“文件名”)
> 
> img.show()**

****示例:****

## **蟒蛇 3**

```
# importing modules
import urllib.request
from PIL import Image

urllib.request.urlretrieve(
  'https://media.geeksforgeeks.org/wp-content/uploads/20210318103632/gfg-300x300.png',
   "gfg.png")

img = Image.open("gfg.png")
img.show()
```

#### **输出:**

**![](img/7b7bd75f63720acb95fb357c87949991.png)**