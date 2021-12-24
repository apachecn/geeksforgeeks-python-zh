# 用 _offset 方法移动 _ 到 _ 元素 _ 硒 Python 中的动作链

> 原文:[https://www . geeksforgeeks . org/move _ to _ element _ with _ offset-method-action-in-selenium-chains-python/](https://www.geeksforgeeks.org/move_to_element_with_offset-method-action-chains-in-selenium-python/)

Selenium 的 Python 模块是为使用 Python 执行自动化测试而构建的。动作链是一种自动化低级交互的方式，例如鼠标移动、鼠标按钮动作、按键和上下文菜单交互。这对于执行更复杂的操作很有用，例如悬停和拖放。高级脚本使用动作链方法，我们需要拖动一个元素，点击一个元素，双击，等等。
本文围绕 Python Selenium 中动作链的`move_to_element_with_offset`方法展开。move_to_element_with_offset 方法用于将鼠标移动指定元素的偏移量。偏移相对于元素的左上角。
**语法–**

```
move_to_element_with_offset(to_element, xoffset, yoffset)
```

**Args –**

*   `to_element`:要移动到的 WebElement。
*   `xoffset`:要移动到的 X 偏移量。
*   `yoffset`:要移动到的 Y 偏移。

**示例–**

```
<input type ="text" name ="passwd" id ="passwd-id" />
```

要找到一个元素，需要使用一种定位策略，例如，

```
element = driver.find_element_by_id("passwd-id")
element = driver.find_element_by_name("passwd")
```

现在，您可以使用 move_to_element_with_offset 方法作为动作链，如下所示

```
move_to_element_with_offset(to_element=element, 100, 200)

```

## 如何在 Selenium Python 中使用 move_to_element_with_offset 动作链方法？

演示一下，硒蟒的`move_to_element_with_offset`动作链法。让我们参观 https://www.geeksforgeeks.org/，并对一个元素进行操作。

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

# get  element 
element = driver.find_element_by_link_text("Courses")

# create action chain object
action = ActionChains(driver)

# perform the operation
action.move_to_element_with_offset(element, 100, 200).click().perform()
```

**输出–**
![action-chains-selenium-Python](img/c1a36810b15e8c6b0ce195fea1bd05c7.png)