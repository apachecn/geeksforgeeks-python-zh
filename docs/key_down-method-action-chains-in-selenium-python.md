# 键下方法–硒蟒中的动作链

> 原文:[https://www . geesforgeks . org/key _ down-方法-动作-硒链-python/](https://www.geeksforgeeks.org/key_down-method-action-chains-in-selenium-python/)

Selenium 的 Python 模块是为使用 Python 执行自动化测试而构建的。动作链是一种自动化低级交互的方式，例如鼠标移动、鼠标按钮动作、按键和上下文菜单交互。这对于执行更复杂的操作很有用，例如悬停和拖放。高级脚本使用动作链方法，我们需要拖动一个元素，点击一个元素，双击，等等。
本文围绕 Python Selenium 中动作链的 key_down 方法展开。key_down 方法用于发送按键，而不释放它。这种方法用于想要按下 ctrl+c 或 ctrl+v 的情况。为此，需要先按住 ctrl 键，然后按下 c。这种方法使这项工作自动化。它只能与修饰键(控制、Alt 和 Shift)一起使用。
**语法–**

```py
key_down(value, element=None)
```

**args–**T2]

*   值:要发送的修饰键。值在键类中定义。
*   元素:发送密钥的元素。如果为“无”，则向当前聚焦元素发送一个键。

**示例–**
可以使用 key_down 方法作为动作链，如下所示。本示例打开网页
后点击 Ctrl+C

```py
ActionChains(driver).key_down(Keys.CONTROL).send_keys('c').key_up(Keys.CONTROL).perform()
```

## Selenium Python 中如何使用 key_down 动作链方法？

为了演示，在硒 Python 中键下动作链的方法。让我们访问 https://www.geeksforgeeks.org/，按 ctrl+f 打开搜索栏。
**程序–**

## 蟒蛇 3

```py
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