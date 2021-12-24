# 拖放–硒蟒中的动作链

> 原文:[https://www . geesforgeks . org/拖放-动作-硒链-python/](https://www.geeksforgeeks.org/drag_and_drop-action-chains-in-selenium-python/)

Selenium 的 Python 模块是为使用 Python 执行自动化测试而构建的。动作链是一种自动化低级交互的方式，例如鼠标移动、鼠标按钮动作、按键和上下文菜单交互。这对于执行更复杂的操作很有用，例如悬停和拖放。高级脚本使用动作链方法，我们需要拖动一个元素，点击一个元素，双击，等等。
本文围绕 Python Selenium 中动作链的`drag_and_drop`方法展开。拖放方法在源元素上按住鼠标左键，然后移动到目标元素并释放鼠标按钮。
**语法–**

```
drag_and_drop(source, target)
```

**Args –**

*   `source`:鼠标放下的元素。
*   `target`:鼠标向上的元素。

**示例–**

```
<input type ="text" name ="passwd" id ="passwd-id" />
```

要找到一个元素，需要使用一种定位策略，例如，

```
element = driver.find_element_by_id("passwd-id")
element = driver.find_element_by_name("passwd")
```

现在可以使用拖放方法作为动作链，如下所示–

```
drag_and_drop(source, target)

```

## Selenium Python 中如何使用拖放动作链方法？

演示一下，硒蟒的`drag_and_drop`动作链法。让我们参观 https://www.geeksforgeeks.org/，并对一个元素进行操作。

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

# get source element 
source_element = driver.find_element_by_link_text("Courses")

# get target element 
target_element = driver.find_element_by_link_text("Hard")

# create action chain object
action = ActionChains(driver)

# drag and drop the item
action.drag_and_drop(source_element, target_element)

# perform the operation
action.perform()
```

**输出–**
![action-chains-selenium-Python](img/c1a36810b15e8c6b0ce195fea1bd05c7.png)