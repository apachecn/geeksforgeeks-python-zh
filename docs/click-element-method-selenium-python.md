# 点击()元素法–硒蟒

> 原文:[https://www . geesforgeks . org/click-element-method-selenium-python/](https://www.geeksforgeeks.org/click-element-method-selenium-python/)

Selenium 的 Python 模块是为使用 Python 执行自动化测试而构建的。硒 Python 绑定提供了一个简单的应用编程接口，可以使用硒网络驱动程序编写功能/验收测试。要使用硒 Python 打开网页，请使用 get 方法-硒 Python 签出–[导航链接。仅仅能够去一些地方并没有多大用处。我们真正想做的是与页面交互，或者更具体地说，与页面中的 HTML 元素交互。使用硒元素有多种策略，结账–](https://www.geeksforgeeks.org/navigating-links-using-get-method-selenium-python/)[定位策略](https://www.geeksforgeeks.org/locator-strategies-selenium-python/)

本文围绕如何在硒中使用`click`方法展开。`click`方法用于点击任何元素，如一个锚点标签、一个链接等。

**Syntax –**

```
element.click()
```

**示例–**

```
<a href="https://www.geeksforgeeks.org/" id="link" />
```

要找到一个元素，需要使用一种定位策略，例如，

```
element = driver.find_element_by_id("link")
element = driver.find_element_by_xpath("//a[@id='link']")
```

此外，要找到多个元素，我们可以使用–

```
elements = driver.find_elements_by_id("link")
```

现在你可以点击这个元素

```
element.click()
```

## 如何在 Selenium Python 中使用点击元素法？

让我们用 https://www.geeksforgeeks.org/在 Selenium Python 中说明这个方法。在这里，我们点击 geeksforgeeks
**程序–**导航栏中的课程选项卡

```
# import webdriver
from selenium import webdriver

# create webdriver object
driver = webdriver.Firefox()

# get geeksforgeeks.org
driver.get("https://www.geeksforgeeks.org/")

# get element 
element = driver.find_element_by_link_text("Courses")

# click the element
element.click()
```

**输出-**

![click-element-method-Selenium-Python](img/f0907ddfa0efbb461a5e701b81efc05d.png)