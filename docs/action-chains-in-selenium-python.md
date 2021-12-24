# 硒蟒中的动作链

> 原文:[https://www . geesforgeks . org/action-in-selenium-chains-python/](https://www.geeksforgeeks.org/action-chains-in-selenium-python/)

Selenium 的 Python 模块是为使用 Python 执行自动化测试而构建的。动作链是一种自动化低级交互的方式，例如鼠标移动、鼠标按钮动作、按键和上下文菜单交互。这对于执行更复杂的操作很有用，例如悬停和拖放。动作链方法被高级脚本使用，在那里我们需要拖动一个元素，点击一个元素。我们已经详细地用例子介绍了所有的方法。

ActionChains 是在 action chain 对象的帮助下实现的，该对象将操作存储在队列中，当调用 perform()时，执行排队的操作。

## 如何创建动作链对象？

要创建 ACtion chain 对象，请从文档中导入 Action Chain 类，并将驱动程序作为关键参数传递。之后，可以使用这个对象来执行动作链的所有操作。

```
# import webdriver
from selenium import webdriver

# import Action chains 
from selenium.webdriver.common.action_chains import ActionChains

# create webdriver object
driver = webdriver.Firefox()

# create action chain object
action = ActionChains(driver)

```

## 如何使用硒元素中的动作链？

创建动作链对象后，打开网页，使用以下语法和示例执行各种其他方法。动作链可用于如下的链模式–

```
menu = driver.find_element_by_css_selector(".nav")
hidden_submenu = driver.find_element_by_css_selector(".nav # submenu1")

ActionChains(driver).move_to_element(menu).click(hidden_submenu).perform()
```

或者动作可以一个接一个地排队，然后执行。：

```
menu = driver.find_element_by_css_selector(".nav")
hidden_submenu = driver.find_element_by_css_selector(".nav # submenu1")

actions = ActionChains(driver)
actions.move_to_element(menu)
actions.click(hidden_submenu)
actions.perform()
```

## 项目示例–

让我们尝试使用 https://www.geeksforgeeks.org/实现动作链，并使用 Selenium Python 的各种方法来玩。

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

# perform the operation
action.perform()
```

上面的代码，首先打开 https://www.geeksforgeeks.org/，然后点击标题中的课程按钮，然后自动将浏览器重定向到 https://practice.geeksforgeeks.org/。
**输出–**
第一个驾驶员打开 https://www.geeksforgeeks.org/,

![action-chain-Selenium-Python](img/54e8e60dfe6948a9078abf9c8e8131f1.png)

然后重定向到 https://practice.geeksforgeeks.org/

![click-element-method-Selenium-Python](img/f0907ddfa0efbb461a5e701b81efc05d.png)

## 硒蟒的动作链方法

人们可以使用动作链执行大量的操作，如点击、右键点击等。以下是动作链中使用的重要方法列表。

| 方法 | 描述 |
| --- | --- |
| [点击](https://geeksforgeeks.org/click-method-action-chains-in-selenium-python/) | 单击一个元素。 |
| [点击并按住](https://www.geeksforgeeks.org/click_and_hold-action-chains-in-selenium-python/?ref=rp) | 在元素上按住鼠标左键。 |
| [上下文 _ 点击](https://www.geeksforgeeks.org/context_click-action-chains-in-selenium-python/?ref=rp) | 对元素执行上下文单击(右键单击)。 |
| [双击](https://www.geeksforgeeks.org/double_click-method-action-chains-in-selenium-python/?ref=rp) | 双击一个元素。 |
| [拖放](https://www.geeksforgeeks.org/drag_and_drop-action-chains-in-selenium-python/?ref=rp) | 按住源元素上的鼠标左键，然后移动到目标元素并释放鼠标按钮。 |
| 拖放偏移 | 按住源元素上的鼠标左键，然后移动到目标偏移量并释放鼠标按钮。 |
| [向下键](https://www.geeksforgeeks.org/key_down-method-action-chains-in-selenium-python/?ref=rp) | 只发送按键，不释放。 |
| [向上键](https://www.geeksforgeeks.org/key_up-method-action-chains-in-selenium-python/?ref=rp) | 释放修饰键。 |
| [移动偏移](https://www.geeksforgeeks.org/move_by_offset-action-chains-in-selenium-python/?ref=rp) | 将鼠标从当前鼠标位置移动一个偏移量。 |
| [移动到元素](https://www.geeksforgeeks.org/move_to_element-method-action-chains-in-selenium-python/?ref=rp) | 将鼠标移动到元素的中间。 |
| [移动 _ 到 _ 元素 _ 带 _ 偏移](https://www.geeksforgeeks.org/move_to_element_with_offset-method-action-chains-in-selenium-python/?ref=rp) | 将鼠标移动指定元素的偏移量，偏移量相对于元素的左上角。 |
| [执行](https://www.geeksforgeeks.org/perform-method-action-chains-in-selenium-python/?ref=rp) | 执行所有存储的操作。 |
| 休息 | 以秒为单位暂停指定持续时间内的所有输入 |
| [释放](https://www.geeksforgeeks.org/release-method-action-chains-in-selenium-python/?ref=rp) | 在元素上释放鼠标左键。 |
| [复位 _ 动作](https://www.geeksforgeeks.org/reset_actions-method-action-chains-in-selenium-python/?ref=rp) | 清除已经存储在本地和远程端的操作 |
| [发送 _ 键](https://www.geeksforgeeks.org/send_keys-method-action-chains-in-selenium-python/?ref=rp) | 向当前聚焦元素发送键。 |