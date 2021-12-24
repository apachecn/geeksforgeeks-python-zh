# 移动偏移–硒蟒中的动作链

> 原文:[https://www . geesforgeks . org/move _ by _ offset-action-in-selenium-chains-python/](https://www.geeksforgeeks.org/move_by_offset-action-chains-in-selenium-python/)

Selenium 的 Python 模块是为使用 Python 执行自动化测试而构建的。动作链是一种自动化低级交互的方式，例如鼠标移动、鼠标按钮动作、按键和上下文菜单交互。这对于执行更复杂的操作很有用，例如悬停和拖放。高级脚本使用动作链方法，我们需要拖动一个元素，点击一个元素，双击，等等。
本文围绕 Python Selenium 中动作链的`move_by_offset`方法展开。move_by_offset 方法用于将鼠标从当前鼠标位置移动到偏移位置。
**语法–**

```py
move_by_offset(xoffset, yoffset)
```

**Args –**

*   `xoffset`:移动到的 X 偏移量，为正整数或负整数。
*   `yoffset`:移动到的 Y 偏移量，为正整数或负整数。

**示例–**
可以使用移动鼠标方法作为动作链，如下所示–

```py
move_by_offset(100, 200)

```

## 如何在 Selenium Python 中使用 move_by_offset 动作链方法？

演示一下，硒蟒的`move_by_offset`动作链法。让我们参观 https://www.geeksforgeeks.org/，并对一个元素进行操作。

**程序–**

```py
# import webdriver
from selenium import webdriver

# import Action chains 
from selenium.webdriver.common.action_chains import ActionChains

# create webdriver object
driver = webdriver.Firefox()

# get geeksforgeeks.org
driver.get("https://www.geeksforgeeks.org/")

# create action chain object
action = ActionChains(driver)

# move the cursor
action.move_by_offset(200, 200)

# perform the operation
action.perform()
```

**输出–**
![action-chains-selenium-Python](img/c1a36810b15e8c6b0ce195fea1bd05c7.png)