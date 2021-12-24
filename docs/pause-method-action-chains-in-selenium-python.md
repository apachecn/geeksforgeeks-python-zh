# 暂停方法–硒蟒中的动作链

> 原文:[https://www . geesforgeks . org/pause-method-action-chains-in-selenium-python/](https://www.geeksforgeeks.org/pause-method-action-chains-in-selenium-python/)

Selenium 的 Python 模块是为使用 Python 执行自动化测试而构建的。动作链是一种自动化低级交互的方式，例如鼠标移动、鼠标按钮动作、按键和上下文菜单交互。这对于执行更复杂的操作很有用，例如悬停和拖放。高级脚本使用动作链方法，我们需要拖动一个元素，点击一个元素，双击，等等。
本文围绕 Python Selenium 中动作链的`pause`方法展开。pause 方法用于在指定的持续时间内暂停所有输入，以秒为单位。暂停方法非常重要，在执行需要一些 javascript 才能加载的命令时，或者在两个操作之间有时间间隔的类似情况下，暂停方法非常有用。

**语法–**

```
pause(seconds)
```

**Args –**`seconds` – Number of seconds to pause for.**Example –**One can use pause method as an Action chain as below –

```
pause(1024)

```

## 如何在 Selenium Python 中使用暂停动作链方法？

演示一下，硒蟒的`pause`动作链法。让我们参观 https://www.geeksforgeeks.org/，并对一个元素进行操作。

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

# click the item
action.click(on_element = element)

# action.pause(1000)

# click the item
action.click(on_element = element)

# perform the operation
action.perform()
```

**输出–**
![action-chains-selenium-Python](img/c1a36810b15e8c6b0ce195fea1bd05c7.png)