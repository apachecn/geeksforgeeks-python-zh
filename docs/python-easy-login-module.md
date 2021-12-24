# Python 简易登录模块

> 原文:[https://www.geeksforgeeks.org/python-easy-login-module/](https://www.geeksforgeeks.org/python-easy-login-module/)

**轻松登录**模块是 Python 库，可以帮助你通过 Python 登录脸书、Instagram、Twitter、Linkedin、Reddit 等社交账号，无需手动打开网站。

**安装**

这个模块没有内置 Python。你需要从外部安装它。要安装此模块，请在终端中键入以下命令。

```py
pip install easy-login
```

它将使用 chrome webdriver 在一个单独的窗口中自动登录您的帐户，并将带您进入该网站的主页

**网络驱动程序**
Selenium 需要一个网络驱动程序来与所选的浏览器交互。Web 驱动程序是一个与 web 浏览器交互的包。它通过通用的有线协议与网络浏览器或远程网络服务器进行交互。您可以签出并安装您选择的网络驱动程序。

```py
Chrome:    https://sites.google.com/a/chromium.org/chromedriver/downloads
Firefox: https://github.com/mozilla/geckodriver/releases
Safari:    https://webkit.org/blog/6900/webdriver-support-in-safari-10/
```

用户名和密码必须与您必须登录的帐户相同，并且必须是字符串格式。地址必须是带正斜杠(/)的字符串格式，如 C://Users/user 1/chrome driver _ win32/chrome driver。

以下是本模块的演示:

## 蟒蛇 3

```py
# importing the module
from easy_login import login

# initializing the username and password
username = ""
password = ""

# initializing the address of chrome web driver
address = ""

# creating an object of login
obj = login(username, password, addresses)

# calling the account in which we want to login
obj.Facebook()
obj.Instagram()
obj.Twitter()
obj.Linkedin()
obj.Reddit()
```