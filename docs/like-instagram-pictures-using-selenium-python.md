# 喜欢使用硒元素的 instagram 图片| Python

> 原文:[https://www . geesforgeks . org/like-insta gram-pictures-use-selenium-python/](https://www.geeksforgeeks.org/like-instagram-pictures-using-selenium-python/)

在本文中，我们将学习如何在 Instagram 上喜欢一个个人资料的所有图片，而无需滚动和手动单击按钮。我们将使用硒来完成这项任务。

**所需包/软件:**

> 1.Python 3
> 2。Chromedriver 兼容现有 chrome 版本[(下载 chromedriver)](https://chromedriver.chromium.org/downloads)
> 3。谷歌浏览器
> 4。硒包(pip 安装硒)，bs4 包(pip 安装 bs4)

**步骤#1:** 导入模块，输入登录信息以及页面的网址。

## 蟒蛇 3

```py
from bs4 import BeautifulSoup as bs
import selenium.common.exceptions
from selenium import webdriver
import time
from selenium.webdriver.common.keys import Keys

print("enter username")
username = input()

print("enter password")
password = input()

print("enter the url")
url = input()
```

**步骤#2:** 功能输入 chromedriver.exe 文件在您的系统中存在的路径

## 蟒蛇 3

```py
def path(): 
    global chrome
    print("enter the driver path")
    exe_path = input()

    # starts a new chrome session
    chrome = webdriver.Chrome(executable_path = exe_path)
```

**第三步:**功能输入页面的网址

## 蟒蛇 3

```py
def url_name(url): 
    # the web page opens up
    chrome.get(url)

    # webdriver will wait for 4 sec before throwing a 
    # NoSuchElement exception so that the element
    # is detected and not skipped.
    time.sleep(4)
```

**第 4 步:**功能输入您的登录信息

## 蟒蛇 3

```py
def login(username, your_password):

    # finds the login button
    log_but = chrome.find_element_by_class_name("L3NKy")
    time.sleep(2)

    # clicks the login button
    log_but.click()   
    time.sleep(4)

    # finds the username box
    usern = chrome.find_element_by_name("username")   

    # sends the entered username
    usern.send_keys(username)  

    # finds the password box
    passw = chrome.find_element_by_name("password")   

    # sends the entered password
    passw.send_keys(your_password)     
    passw.send_keys(Keys.RETURN)
    time.sleep(6)
    notn = chrome.find_element_by_class_name("yWX7d")# dont save info button
    notn.click()# click don't save button
    time.sleep(3)
```