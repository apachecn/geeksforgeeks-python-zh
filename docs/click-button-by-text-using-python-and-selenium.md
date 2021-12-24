# 使用 Python 和 Selenium 通过文本点击按钮

> 原文:[https://www . geesforgeks . org/点击-使用 python 和 selenium 逐文本按钮/](https://www.geeksforgeeks.org/click-button-by-text-using-python-and-selenium/)

Selenium 是一个工具，它提供 API 来自动化 web 应用程序，以帮助其测试。在本文中，我们讨论了使用硒 Python API 绑定来访问硒网络驱动程序，通过按钮中的文本点击按钮。在下面的例子中，我们利用了 Chrome 的帮助。使用的方法是**find _ element _ by _ link _ text()**，它使用当前的文本来抓取元素。如果给定的文本属性中没有这样的元素，则返回 **NoSuchElementException** 。

### 安装:

确保您使用安装了 Selenium

```
pip3 install Selenium
```

并为您的网络浏览器下载网络驱动程序:

```
Chrome : https://chromedriver.chromium.org/downloads
Firefox : https://github.com/mozilla/geckodriver/releases
Safari : https://webkit.org/blog/6900/webdriver-support-in-safari-10/
```

一旦 Selenium 与所需的网络驱动程序一起安装，我们就创建一个文件脚本。py 并使用我们的代码编辑器编写下面的 python 脚本，该脚本使用 Selenium 网络驱动程序打开 geeksforgeeks 网站，并使用链接文本单击登录按钮。

**语法:**

```
driver.find_element_by_link_text("sample text")
```

**逐步逼近:**

*   导入所需模块。
*   创建 webdriver 对象。
*   分配网址。
*   使用 **maximize_window()** 方法将浏览器窗口最大化。然后使用**睡眠()**方法等待 10 秒。
*   使用**find _ element _ by _ link _ text()**方法按文本点击按钮。

下面是实现。

## 蟒蛇 3

```
# import module
from selenium import webdriver
import time

# Create the webdriver object. Here the 
# chromedriver is present in the driver 
# folder of the root directory.
driver = webdriver.Chrome(r"./driver/chromedriver")

# get https://www.geeksforgeeks.org/
driver.get("https://www.geeksforgeeks.org/")

# Maximize the window and let code stall 
# for 10s to properly maximise the window.
driver.maximize_window()
time.sleep(10)

# Obtain button by link text and click.
button = driver.find_element_by_link_text("Sign In")
button.click()
```

**输出:**

<video class="wp-video-shortcode" id="video-563654-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210222231422/output_FTOFsx0Z_Tx7e.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210222231422/output_FTOFsx0Z_Tx7e.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210222231422/output_FTOFsx0Z_Tx7e.mp4)</video>

首先，网络驱动程序用 geeksforgeeks 打开窗口，最大化它，并等待 10 秒钟。然后点击登录按钮，打开注册面板。