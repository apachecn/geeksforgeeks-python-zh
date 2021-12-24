# 点击并按住–硒蟒动作链

> 原文:[https://www . geesforgeks . org/click _ and _ hold-action-in-selenium-chains-python/](https://www.geeksforgeeks.org/click_and_hold-action-chains-in-selenium-python/)

Selenium 的 Python 模块是为使用 Python 执行自动化测试而构建的。动作链是一种自动化低级交互的方式，例如鼠标移动、鼠标按钮动作、按键和上下文菜单交互。这对于执行更复杂的操作很有用，例如悬停和拖放。高级脚本使用动作链方法，我们需要拖动一个元素，点击一个元素，双击，等等。
本文围绕 Python Selenium 中动作链的`click_and_hold`方法展开。`click_and_hold`方法用于在一个元素上按住鼠标左键。
**语法–**

```
click_and_hold(on_element=None)
```

**Args –**`on_element`: The element to mouse down. If None, clicks on current mouse position.

**示例–**

```
<input type ="text" name ="passwd" id ="passwd-id" />
```

要找到一个元素，需要使用一种定位策略，例如，

```
element = driver.find_element_by_id("passwd-id")
element = driver.find_element_by_name("passwd")
```

现在可以使用点击并保持方法作为动作链，如下所示–

```
click_and_hold(on_element=element)

```

## 如何在 Selenium Python 中使用 click_and_hold 动作链方法？

演示一下，硒蟒的`click_and_hold`动作链法。让我们参观 https://www.geeksforgeeks.org/，并对一个元素进行操作。

**程序–**

```
# import webdriver
from selenium import webdriver

# import Action chains 
from selenium.webdriver.common.action_chains import ActionChains

# create webdriver object
driver = webdriver.Firefox()

# get geeksforgeeks.org
driver.get("https://www.geeksforgeeks.org/")

# get element 
element = driver.find_element_by_link_text("Courses")

# create action chain object
action = ActionChains(driver)

# click and hold  the item
action.click_and_hold(on_element = element)

# perform the operation
action.perform()
```

**输出–**
![action-chains-selenium-Python](img/c1a36810b15e8c6b0ce195fea1bd05c7.png)