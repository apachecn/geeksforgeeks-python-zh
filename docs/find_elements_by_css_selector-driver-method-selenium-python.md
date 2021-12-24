# find _ elements _ by _ CSS _ selector()驱动方法–Selenium Python

> 原文:[https://www . geesforgeks . org/find _ elements _ by _ CSS _ selector-driver-method-selenium-python/](https://www.geeksforgeeks.org/find_elements_by_css_selector-driver-method-selenium-python/)

Selenium 的 Python 模块是为使用 Python 执行自动化测试而构建的。硒 Python 绑定提供了一个简单的应用编程接口，可以使用硒网络驱动程序编写功能/验收测试。安装完 selenium 并签出–[使用 get 方法导航链接](https://www.geeksforgeeks.org/navigating-links-using-get-method-selenium-python)后，您可能希望使用 Selenium Python 玩得更多。在使用 geeksforgeeks 等 selenium 打开页面后，您可能希望自动单击某些按钮或自动填写表单或任何此类自动任务。

本文围绕如何使用 Selenium Web Driver 的定位策略抓取或定位网页中的元素展开。更具体地说，本文将讨论`find_elements_by_css_selector()`。此方法返回指定元素类型的列表。
要获取单个第一个元素，请签出–[find _ element _ by _ CSS _ selector()驱动程序方法–Selenium Python](https://www.geeksforgeeks.org/find_element_by_css_selector-driver-method-selenium-python/)

**Syntax –**

```py
driver.find_elements_by_css_selector("css selector")

```

**示例–**
例如，考虑一下这个页面来源:

```py
<html>
 <body>
  <form id="loginForm">
   <input name="1" type="text" />
   <input name="1" type="password" />
   <input name="1" type="submit" value="Login" />
  </form>
 </body>
<html>
```

现在，在您创建了驱动程序之后，您可以使用–

```py
login_form = driver.find_elements_by_css_selector('#loginForm')

```

## 如何在 Selenium 中使用 driver . find _ elements _ by _ CSS _ selector()方法？

让我们尝试实际实现这个方法，并为**获取一个元素实例。让我们尝试使用它的类名“gsc-input”来抓取搜索表单输入。
创建一个名为 run.py 的文件来演示 find_elements_by_css_selector 方法–**

```py
# Python program to demonstrate
# selenium

# import webdriver
from selenium import webdriver

# create webdriver object
driver = webdriver.Firefox()

# enter keyword to search
keyword = "geeksforgeeks"

# get geeksforgeeks.org
driver.get("https://www.geeksforgeeks.org/")

# get elements
elements = driver.find_elements_by_css_selector(".gsc-input")

# print complete elements list
print(element)
```

现在使用运行–

```py
Python run.py
```

首先，它会用 geeksforgeeks 打开 firefox 窗口，然后选择元素并将其打印在终端上，如下所示。
**浏览器输出–**
![find_element-driver-method-Selenium-Python](img/e4c693a41389c0afdcf6559992cf6c6a.png)
**终端输出–**
![elements-list-driver-methods-Selenium-Python](img/aa1cd449266c387fb20f322c867be458.png)