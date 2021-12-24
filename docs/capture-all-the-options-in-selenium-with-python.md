# 用 Python 捕获 Selenium 中的所有选项

> 原文:[https://www . geesforgeks . org/capture-all-options-in-selenium-with-python/](https://www.geeksforgeeks.org/capture-all-the-options-in-selenium-with-python/)

**先决条件:** [使用硒的浏览器自动化](https://www.geeksforgeeks.org/browser-automation-using-selenium/)

硒是通过程序控制互联网浏览器的有效设备。它对所有浏览器都是有目的的，适用于所有基本操作系统，其脚本是用许多语言编写的，即 Python、Java、C#等，我们将使用 Python。

**要求:**

需要从这里[下载安装 chrome 驱动点击这里](https://sites.google.com/a/chromium.org/chromedriver/downloads)设置路径。

**使用下拉列表:**

首先你要导入*选择*类，然后你要做*选择*类的案例。完成*选择*类的案例后，您可以在该场合执行选择策略，从下拉列表中选择选项。

导入*选择*类:

```
from selenium.webdriver.support.ui import Select
```

查找选项长度:

```
drop=Select(driver.find_element_by_id(' ')

print(len(drop.options))
```

**循序渐进法:**

*   从*硒*模块导入*网络驱动程序*。

## 蟒蛇 3

```
# Import required module
from selenium import webdriver
```

*   导入*选择*类模块。

## 蟒蛇 3

```
# Importing Select class
from selenium.webdriver.support.ui import Select
```

*   使用网页进行下拉列表(例如:[网址](https://fs2.formsite.com/meherpavan/form2/index.html?1537702596407) <u>)</u> 。
*   导航选项栏的 id。

![](img/2c060435ee20a546aa1972d1a04ab2d5.png)

*   开始捕捉所有选项的循环。

**以下是上述方法的完整程序:**

## 蟒蛇 3

```
# Import required module
import time
from selenium import webdriver

# Import Select class
from selenium.webdriver.support.ui import Select

# Using chrome driver
driver = webdriver.Chrome()

# Web page url
driver.get("https://fs2.formsite.com/meherpavan/form2/index.html?1537702596407")

# Find id of option
x = driver.find_element_by_id('RESULT_RadioButton-9')
drop = Select(x)

# Count number of options
print(len(drop.options))

# Capture all the options
for i in drop.options:
    print(i.text)

driver.close()
```

**输出:**

![](img/a750a41a2c057b8958743adc4381966c.png)

**注意:**一个空格是，所以只打印三个选项。