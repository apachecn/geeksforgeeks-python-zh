# 如何用 Python 中的 Selenium 进行截图？

> 原文:[https://www . geesforgeks . org/如何截图-使用 python 中的硒/](https://www.geeksforgeeks.org/how-to-take-screenshot-using-selenium-in-python/)

Selenium 提供了很多功能，其中一个重要且有用的功能就是截图。为了拍摄网页截图，使用了 save _ screenshot()方法。save _ screenshot 方法允许用户将网页保存为 png 文件。

**语法:**

```
driver.save_screenshot("image.png")
```

**参数:**
文件名或您希望保存截图的完整路径。

**执行的动作:**
截图会和程序保存在同一个目录下，如果提供了路径截图只会保存在那个位置。

**代码:**

## 蟒蛇 3

```
# importing webdriver from selenium
from selenium import webdriver

from PIL import Image

# Here Chrome  will be used
driver = webdriver.Chrome()

# URL of website
url = "https://www.geeksforgeeks.org/"

# Opening the website
driver.get(url)

driver.save_screenshot("image.png")

# Loading the image
image = Image.open("image.png")

# Showing the image
image.show()
```

**输出:**

![](img/65cf42745b40132b2666b4d5381e1251.png)