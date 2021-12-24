# Python 如何在 Selenium 中切换到新窗口？

> 原文:[https://www . geeksforgeeks . org/如何切换到 python 硒新窗口/](https://www.geeksforgeeks.org/how-to-switch-to-new-window-in-selenium-for-python/)

Selenium 是用于网络测试和自动化的最常用的 Python 工具。但是当用户需要在 chrome 中的窗口之间切换时，问题就出现了。因此，硒也得到了保护。Selenium 将这些方法用于此任务-

*   **Window _ handles** is used to handle different windows. It stores the window id for switching.
*   **Switch _ to.window** The method is to switch between windows by means of window_handles ids.

**步骤覆盖:**

*   Set the URL and import selenium

## python 3

```
# import modules
from selenium import webdriver  
import time  

# provide the path for chromedriver
PATH = "C:/chromedriver.exe"  

# pass on the path to driver for working
driver = webdriver.Chrome(PATH)  
```