# 如何获取 selenium-Python 中标签的文本？

> 原文:[https://www . geesforgeks . org/如何获取硒元素标签文本-python/](https://www.geeksforgeeks.org/how-to-get-text-of-a-tag-in-selenium-python/)

[Selenium](https://www.geeksforgeeks.org/selenium-python-tutorial/) 是通过程序控制网页浏览器，执行浏览器自动化的强大工具。它适用于所有浏览器，适用于所有主要操作系统，其脚本是用各种语言编写的，如 Python、Java、C#等，我们将使用 Python。

在本文中，我们将编写一个 Python 脚本，用于使用 *selenium* 模块从标签名称中获取文本。我们将从这个[网址](https://phptravels.com/demo/)获取标签文本。

### 逐步方法

**步骤#1:** 导入所需的库

## 蟒蛇 3

```
# Import Library
from selenium import webdriver
```

**第 2 步:**创建一个 *Chrome* 对象，或者指定网页驱动程序路径(如果它不在默认路径中)，并分配 [URL](https://phptravels.com/demo/) 。

## 蟒蛇 3

```
# Chrome Path
driver = webdriver.Chrome('Enter Chrome Path')

# Web URL
driver.get('Enter Web URL')
```

**步骤#3:** 指定标签名称，您要从中提取文本。

**语法:**

```
Object Name.find_element_by_tag_name(Tag Name)
```

## 蟒蛇 3

```
# Get Text
print (element.text)

# Close the window
driver.close()
```

下面是实现。

## 蟒蛇 3

```
# Import Library
from selenium import webdriver

# Chrome Path
driver = webdriver.Chrome()

# Web URL
driver.get('https://phptravels.com/demo/')

element = driver.find_element_by_tag_name('a')

# Get Text
print(element.text)

# Close the window
driver.close()
```

**输出:**

<video class="wp-video-shortcode" id="video-540504-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210109110451/FreeOnlineScreenRecorderProject16.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210109110451/FreeOnlineScreenRecorderProject16.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210109110451/FreeOnlineScreenRecorderProject16.mp4)</video>