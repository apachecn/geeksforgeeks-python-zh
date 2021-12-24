# 使用 Python 中的 Selenium 打印所有链接名称

> 原文:[https://www . geesforgeks . org/print-all-link-name-use-selenium in-python/](https://www.geeksforgeeks.org/print-all-link-name-using-selenium-in-python/)

Selenium 是通过程序控制网络浏览器和执行浏览器自动化的强大工具。它适用于所有浏览器，适用于所有主要操作系统，其脚本是用各种语言编写的，如 Python、Java、C#等，我们将使用 Python。

**要求:**

您需要安装 chromedriver 并设置路径。 [**点击此处**](https://sites.google.com/a/chromium.org/chromedriver/downloads) 下载。

**注:**更多信息跟随 [**本链接**](https://www.geeksforgeeks.org/browser-automation-using-selenium/) 。

**分步方法:**

*   导入所需模块
*   取任意[**网址**](https://www.youtube.com/) 。
*   通过使用。在网页上查找网页链接。
*   然后使用循环打印链接名称。

**实施:**

## 蟒蛇 3

```
#import module
from selenium import webdriver
from selenium.webdriver.common.by import By

driver = webdriver.Chrome()

# url
driver.get('https://www.youtube.com/')

# find web links
link = driver.find_elements(By.TAG_NAME, 'a')

# print name of all links
for i in link:
    print(i.text)
```

<video class="wp-video-shortcode" id="video-507909-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201101183511/weblinkss.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201101183511/weblinkss.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201101183511/weblinkss.mp4)</video>

**输出:**