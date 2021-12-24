# 硒蟒的隐性等待

> 原文:[https://www . geesforgeks . org/implicit-in-waities-in-selenium-python/](https://www.geeksforgeeks.org/implicit-waits-in-selenium-python/)

硒 Python 是测试自动化的伟大工具之一。如今，大多数网络应用程序都在使用 AJAX 技术。当浏览器加载一个页面时，该页面中的元素可能会以不同的时间间隔加载。这使得定位元素变得困难:如果一个元素还没有出现在 DOM 中，定位函数将会引发 ElementNotVisibleException 异常。使用等待，我们可以解决这个问题。等待在执行的操作之间提供了一定的间隔，主要是定位元素或元素的任何其他操作。Selenium 网络驱动程序提供两种类型的等待——隐式和显式。本文围绕硒 Python 中的隐式等待展开。

**隐式等待**
隐式等待告诉网络驱动程序在一定时间内轮询 DOM，试图找到任何不立即可用的元素。默认设置为 0。一旦设置，隐式等待将在 WebDriver 对象的生命周期内设置。让我们考虑一个例子–

```py
# import webdriver
from selenium import webdriver

driver = webdriver.Firefox()

# set implicit wait time
driver.implicitly_wait(10) # seconds

# get url
driver.get("http://somedomain / url_that_delays_loading")

# get element after 10 seconds
myDynamicElement = driver.find_element_by_id("myDynamicElement")
```

这将在引发超时异常之前等待 10 秒钟，除非它发现元素在 10 秒钟内返回。

## 如何在 Selenium Python 中创建隐式等待？

定义的隐式等待将是使用驱动程序的隐式等待方法设置的。让我们在 https://www.geeksforgeeks.org/上实现它，并等待 10 秒钟再定位一个元素。

```py
# import webdriver 
from selenium import webdriver 

# create webdriver object 
driver = webdriver.Firefox() 

# set implicit wait time
driver.implicitly_wait(10) # seconds

# get geeksforgeeks.org 
driver.get("https://www.geeksforgeeks.org/") 

# get element after 10 seconds
element = driver.find_element_by_link_text("Courses")

# click element
element.click()

```

**输出–**
首先打开 https://www.geeksforgeeks.org/，然后找到课程链接
![driver-methods-Selenium-Python](img/54e8e60dfe6948a9078abf9c8e8131f1.png)

它点击课程链接并被重定向到 https://practice.geeksforgeeks.org/

![action-chains-selenium-Python](img/c1a36810b15e8c6b0ce195fea1bd05c7.png)