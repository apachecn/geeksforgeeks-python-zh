# 键起方法–硒蟒中的动作链

> 原文:[https://www . geesforgeks . org/key _ up-method-action-in-selenium-chains-python/](https://www.geeksforgeeks.org/key_up-method-action-chains-in-selenium-python/)

Selenium 的 Python 模块是为使用 Python 执行自动化测试而构建的。动作链是一种自动化低级交互的方式，例如鼠标移动、鼠标按钮动作、按键和上下文菜单交互。这对于执行更复杂的操作很有用，例如悬停和拖放。高级脚本使用动作链方法，我们需要拖动一个元素，点击一个元素，双击，等等。
本文围绕 Python Selenium 中动作链上的 key_up 方法展开。key_up 方法用于使用 key_down 方法释放按下的键。

**语法–**

```
key_up(value, element=None)
```

args–

*   值:要发送的修饰键。值在键类中定义。
*   元素:发送密钥的元素。如果为“无”，则向当前聚焦元素发送一个键。

**示例–**
可以使用 key_up 方法作为动作链，如下所示。本示例在打开网页后单击 Ctrl+C，然后向上键方法释放按下的键。

```
ActionChains(driver).key_down(Keys.CONTROL).send_keys('c').key_up(Keys.CONTROL).perform()
```

## 如何在硒 Python 中使用 key_up 动作链方法？

演示一下硒蟒动作链的键方法。让我们访问 https://www.geeksforgeeks.org/，按 ctrl+f 打开搜索栏。
**节目–**

## 蟒蛇 3

```
# import webdriver
from selenium import webdriver

# import Action chains
from selenium.webdriver.common.action_chains import ActionChains

# import KEYS
from selenium.webdriver.common.keys import Keys

# create webdriver object
driver = webdriver.Firefox()

# get geeksforgeeks.org
driver.get("https://www.geeksforgeeks.org/")

# create action chain object
action = ActionChains(driver)

# perform the operation
action.key_down(Keys.CONTROL).send_keys('F').key_up(Keys.CONTROL).perform()
```

**输出–**

![action-chain-method-Selelnium-python](img/783b48d0f978e4f1c9472207ff4ca17f.png)