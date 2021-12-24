# 如何使用 Python 从引导选项卡点击 href 链接？

> 原文:[https://www . geesforgeks . org/how-click-a-href-link-from-bootstrap-tab-using-python/](https://www.geeksforgeeks.org/how-to-click-a-href-link-from-bootstrap-tabs-using-python/)

说到对网络内容的操纵，没人比得上 Python。使用 Python 和硒库可以点击一个链接。

**安装**

**1.1 Python 中的 Selenium 绑定**
Selenium Python 绑定提供了一个方便的 API 来访问像 Firefox、Chrome 等 Selenium Web Driver。

```
Pip install Selenium 
```

**1.2 网络驱动程序**
Selenium 需要一个网络驱动程序来与所选的浏览器交互。Web 驱动程序是一个与 web 浏览器交互的包。它通过通用的有线协议与网络浏览器或远程网络服务器进行交互。您可以签出并安装您选择的网络驱动程序。

```
Chrome:    https://sites.google.com/a/chromium.org/chromedriver/downloads
Firefox: https://github.com/mozilla/geckodriver/releases
Safari:    https://webkit.org/blog/6900/webdriver-support-in-safari-10/
```

**注意:**可以在这里查看网站表单的源代码，说明已经使用 bootstrap 制作了网站。网站是 CompCode，你必须点击参考链接

## 蟒蛇 3

```
# Import the webdriver from selenium library
from selenium import webdriver

# Link the driver of the browser
driver = webdriver.Chrome("C://Myspace/chromedriver.exe")

# Open the website  using url
driver.get("https://avanishcodes.github.io/CompCode")

# Target the element using the href value
# In actual, search for an anchor tag and
# among anchor tags, select the one with
# given href value
target = driver.find_element_by_xpath('//a[@href="ref.html"]')

# Click the target to navigate to destination
target.click()

# This Code has been contributed by Avanish Gupta
```

**输出:**

<video class="wp-video-shortcode" id="video-462291-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200728113401/GfG-href.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200728113401/GfG-href.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200728113401/GfG-href.mp4)</video>