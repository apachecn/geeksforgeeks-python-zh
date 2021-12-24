# 如何使用硒蟒在历史中来回移动？

> 原文:[https://www . geeksforgeeks . org/如何使用 selenium-python 在历史中前后移动/](https://www.geeksforgeeks.org/how-to-move-back-and-forward-in-history-using-selenium-python/)

Selenium 的 Python 模块是为使用 Python 执行自动化测试而构建的。硒 Python 绑定提供了一个简单的应用编程接口，可以使用硒网络驱动程序编写功能/验收测试。要使用硒 Python 打开网页，请使用 get 方法-硒 Python 签出–[导航链接。仅仅能够去一些地方并没有多大用处。我们真正想做的是与页面交互，或者更具体地说，与页面中的 HTML 元素交互。使用硒元素有多种策略，结账–](https://www.geeksforgeeks.org/navigating-links-using-get-method-selenium-python/)[定位策略](https://www.geeksforgeeks.org/locator-strategies-selenium-python/)。Selenium WebDriver 提供了各种有用的方法来控制会话，或者换句话说，浏览器。例如，添加 cookie、按后退按钮、在选项卡间导航等。

本文围绕在 Selenium 中向前和向后移动的驱动程序方法，以在浏览器历史中向后和向前移动。使用的两种主要方法是–

## 反向驱动方法

`back`方法用于在浏览器历史中倒退一步。

**语法–**

```
driver.back()
```

**示例–**
现在可以使用 back 方法作为驱动方法，如下所示–

```
driver.get("https://www.geeksforgeeks.org/")
driver.back()

```

要检查回溯方法的个别实现，请访问硒 Python 中的–[回溯驱动程序方法。](https://www.geeksforgeeks.org/back-driver-method-selenium-python/)

## 正向驱动方法

`forward`方法用于在浏览器历史中向前迈进一步。

**语法–**

```
driver.forward()
```

**示例–**
现在可以使用正向方法作为驱动方法，如下所示–

```
driver.get("https://www.geeksforgeeks.org/")
driver.forward()

```

检查硒 Python 中正向方法访问–[正向驱动程序方法的单独实现。](https://www.geeksforgeeks.org/forward-driver-method-selenium-python/)

## 如何在 Selenium Python 中使用后退和前进驱动方法？

用硒 Python 演示网络驱动程序的这些方法。让我们访问 https://www.geeksforgeeks.org/，对驱动程序对象进行操作。

**程序–**

```
# import webdriver
from selenium import webdriver

# create webdriver object
driver = webdriver.Firefox()

# get geeksforgeeks.org
driver.get("https://www.geeksforgeeks.org/")

# get geeksforgeeks.org
driver.get("https://www.practice.geeksforgeeks.org/")

# one step backward in browser history
driver.back()

# one step backward in browser history
driver.forward()
```

**输出–**
浏览器在历史中向后追溯，如下所示–
![driver-methods-Selenium-Python](img/54e8e60dfe6948a9078abf9c8e8131f1.png)
然后，浏览器在历史中向前追溯，如下所示–
![action-chains-selenium-Python](img/c1a36810b15e8c6b0ce195fea1bd05c7.png)