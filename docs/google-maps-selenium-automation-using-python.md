# 谷歌地图硒自动化使用 Python

> 原文:[https://www . geesforgeks . org/Google-maps-selenium-automation-use-python/](https://www.geeksforgeeks.org/google-maps-selenium-automation-using-python/)

**先决条件:** [使用硒的浏览器自动化](https://www.geeksforgeeks.org/browser-automation-using-selenium/)

Selenium 是通过程序控制网络浏览器的强大工具。它适用于所有浏览器，适用于所有主要操作系统，其脚本是用各种语言编写的，如 Python、Java、C#等，我们将使用 Python。可以使用以下命令进行安装:

```py
pip install selenium

```

在本文中，我们将看到如何通过获取一个地方的位置及其到另一个地方的交通细节，使用 *selenium* 自动执行谷歌地图搜索。

**步骤 1)** 导入模块

## python 3

```py
# import required modules
from selenium import webdriver
from time import sleep
```

**步骤 2)** 在你下载的驱动变量中提到你的 chrome 驱动的路径。然后我们需要一个谷歌地图网站。

## 蟒 3

```py
# assign url in the webdriver object
driver = webdriver.Chrome()
driver.get("https://www.google.co.in/maps/@10.8091781,78.2885026,7z")
sleep(2)
```

**步骤 3)** 下一步声明一个功能在这个功能下你需要检查谷歌地图网站上的搜索栏。并将类名复制到变量位置。您需要向特定的 web 元素发送密钥。给出你的目的地作为输入。在提交变量中提供 *xpath* 值这用于按下搜索按钮

## python 3

```py
# search locations
def searchplace():
    Place = driver.find_element_by_class_name("tactile-searchbox-input")
    Place.send_keys("Tiruchirappalli")
    Submit = driver.find_element_by_xpath(
        "/html/body/jsl/div[3]/div[9]/div[3]/div[1]/div[1]/div[1]/div[2]/div[1]/button")
    Submit.click()

searchplace()
```

**步骤 4)** 声明一个叫做方向的函数。在此功能下，您需要点击方向按钮。从谷歌地图网站复制方向按钮的 X 路径值。并将该值粘贴到变量中。

## 蟒 3

```py
# get directions
def directions():
    sleep(10)
    directions = driver.find_element_by_xpath(
        "/html/body/jsl/div[3]/div[9]/div[7]/div/div[1]/div/div/div[5]/div[1]/div/button")
    directions.click()

directions()
```