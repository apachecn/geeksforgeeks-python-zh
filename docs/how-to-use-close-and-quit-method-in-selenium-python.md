# 如何在硒蟒中使用 close()和 quit()方法？

> 原文:[https://www . geesforgeks . org/使用方法-关闭并退出方法-硒-python/](https://www.geeksforgeeks.org/how-to-use-close-and-quit-method-in-selenium-python/)

在用硒做事情的时候，通常会打开多个带有多个标签的浏览器来关闭这些标签`close()`和`quit()`方法。`close()`方法用于关闭当前设置了焦点的浏览器窗口，另一方面`quit()`方法本质上是调用 driver.dispose 方法，依次关闭所有浏览器窗口，优雅地结束 WebDriver 会话。

**语法:**

```
driver.close()
driver.quit()

```

**参数:**

两种方法都不需要参数

**执行的动作:**
`close()`方法关闭当前窗口。
`quit()`方法退出驱动程序实例，关闭所有打开的相关窗口。

**Code for close method() :**

```
# importing webdriver from selenium
from selenium import webdriver

# Here Chrome  will be used
driver = webdriver.Chrome()

# URL of website
url = "https://www.geeksforgeeks.org/"

# Opening the website
driver.get(url)

# Closes the current window
driver.close()
```

**输出:**网页将被加载，然后由于 close()方法而关闭。

**退出()方法代码:**

```
# importing webdriver from selenium
from selenium import webdriver

# Here Chrome  will be used
driver = webdriver.Chrome()

# URL of website
url = "https://www.geeksforgeeks.org/"

# Opening the website
driver.get(url)

# All windows related to driver instance will quit
driver.quit()
```

**输出:**由于 quit()方法，网页将被加载，然后窗口退出。