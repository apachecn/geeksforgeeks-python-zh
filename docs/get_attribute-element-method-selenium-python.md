# get_attribute()元素法–硒蟒

> 原文:[https://www . geesforgeks . org/get _ attribute-element-method-selenium-python/](https://www.geeksforgeeks.org/get_attribute-element-method-selenium-python/)

Selenium 的 Python 模块是为使用 Python 执行自动化测试而构建的。硒 Python 绑定提供了一个简单的应用编程接口，可以使用硒网络驱动程序编写功能/验收测试。要使用硒 Python 打开网页，请使用 get 方法-硒 Python 签出–[导航链接。仅仅能够去一些地方并没有多大用处。我们真正想做的是与页面交互，或者更具体地说，与页面中的 HTML 元素交互。使用 Selenium 查找元素有多种策略，结账–](https://www.geeksforgeeks.org/navigating-links-using-get-method-selenium-python/)[定位策略](https://www.geeksforgeeks.org/locator-strategies-selenium-python/)
本文围绕如何在 Selenium 中使用 get_attribute 方法展开。get_attribute 方法用于获取元素的属性，比如获取锚点标签的 href 属性。此方法将首先尝试返回具有给定名称的属性值。如果同名属性不存在，它将返回同名属性的值。如果没有同名属性，则返回无。
**语法–**

```
element.get_attribute("attribute name")
```

**示例–**

## 超文本标记语言

```
<a href="https://www.geeksforgeeks.org/" id="link" />
```

要找到一个元素，需要使用一种定位策略，例如

```
element = driver.find_element_by_id("link")
element = driver.find_element_by_xpath("//a[@id='link']")
```

同样，要找到多个元素，我们可以使用–

```
elements = driver.find_elements_by_id("link")
```

现在可以通过
获得该字段的属性

```
element.get_attribute('href')
```

## 如何在 Selenium Python 中使用 get_attribute 方法？

让我们用 https://www.geeksforgeeks.org/在 Selenium Python 中说明这个方法。这里我们在 geeksforgeeks 的导航栏中获得课程标签的 href 属性。
**程序–**

## 蟒蛇 3

```
# import webdriver
from selenium import webdriver

# create webdriver object
driver = webdriver.Firefox()

# enter keyword to search
keyword = "geeksforgeeks"

# get geeksforgeeks.org
driver.get("https://www.geeksforgeeks.org/")

# get element
element = driver.find_element_by_link_text("Courses")

# get href attribute
print(element.get_attribute('href'))
```

**输出-**

![click-element-method-Selenium-Python](img/f0907ddfa0efbb461a5e701b81efc05d.png)

**终端输出–**

![get_attribute-element-method-Selenium-Python](img/b29bec92d6dec71c68be7c53b657f8d4.png)