# 硒蟒中的显式等待

> 原文:[https://www . geesforgeks . org/explicit-硒中等待-python/](https://www.geeksforgeeks.org/explicit-waits-in-selenium-python/)

硒 Python 是测试自动化的伟大工具之一。如今，大多数网络应用程序都在使用 AJAX 技术。当浏览器加载一个页面时，该页面中的元素可能会以不同的时间间隔加载。这使得定位元素变得困难:如果一个元素还没有出现在 DOM 中，定位函数将会引发 ElementNotVisibleException 异常。使用等待，我们可以解决这个问题。等待在执行的操作之间提供了一定的间隔，主要是定位元素或元素的任何其他操作。Selenium 网络驱动程序提供两种类型的等待——隐式和显式。本文围绕硒 Python 中的显式等待展开。

**显式等待**
显式等待是您定义的代码，用于等待某个条件发生，然后再继续执行代码。这种情况的极端情况是 time.sleep()，它将条件设置为等待的确切时间段。提供了一些方便的方法来帮助您编写只等待所需时间的代码。显式等待是通过结合使用 webdriverWait 类和 expected_conditions 实现的。让我们考虑一个例子–

```py
# import necessary classes
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC

# create driver object 
driver = webdriver.Firefox()

# A URL that delays loading
driver.get("http://somedomain / url_that_delays_loading")

try:
    # wait 10 seconds before looking for element
    element = WebDriverWait(driver, 10).until(
        EC.presence_of_element_located((By.ID, "myDynamicElement"))
    )
finally:
    # else quit
    driver.quit()
```

这将在引发超时异常之前等待 10 秒钟，除非它发现元素在 10 秒钟内返回。默认情况下，WebDriverWait 每 500 毫秒调用一次 ExpectedCondition，直到它成功返回。
**预期条件–**
在自动化网络浏览器时，有一些常用的条件。例如，presence_of_element_located、title_is、ad 等等。您可以从这里查看整个方法–[便利方法](https://selenium-python.readthedocs.io/api.html#module-selenium.webdriver.support.expected_conditions)。其中一些是–

*   标题列表
*   标题 _ 包含
*   已定位元素的存在
*   定位元素的可见性
*   的可见性
*   存在所有已定位的元素
*   元素 _ 定位 _ 待选
*   元素选择状态目标
*   元素定位选择状态目标
*   alert_is_present

## 如何在 Selenium Python 中创建显式等待？

定义的显式等待是网络驱动和预期条件的组合。让我们在 https://www.geeksforgeeks.org/上实现它，并等待 10 秒钟再定位一个元素。

```py
# import webdriver 
from selenium import webdriver 
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC

# create webdriver object 
driver = webdriver.Firefox() 

# get geeksforgeeks.org 
driver.get("https://www.geeksforgeeks.org/") 

# get element  after explicitly waiting for 10 seconds
element = WebDriverWait(driver, 10).until(
        EC.presence_of_element_located((By.link_text, "Courses"))
    )
# click the element 
element.click() 
```

**输出–**
首先打开 https://www.geeksforgeeks.org/，然后找到课程链接
![driver-methods-Selenium-Python](img/54e8e60dfe6948a9078abf9c8e8131f1.png)

它点击课程链接并被重定向到 https://practice.geeksforgeeks.org/

![action-chains-selenium-Python](img/c1a36810b15e8c6b0ce195fea1bd05c7.png)