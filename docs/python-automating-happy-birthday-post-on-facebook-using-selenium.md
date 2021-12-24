# Python |使用硒自动化脸书生日快乐帖

> 原文:[https://www . geesforgeks . org/python-自动化-生日快乐-facebook 上的帖子-使用-selenium/](https://www.geeksforgeeks.org/python-automating-happy-birthday-post-on-facebook-using-selenium/)

众所周知，Selenium 是一种通过程序控制网络浏览器的工具。它可以在所有浏览器、操作系统中使用，它的程序是用各种编程语言编写的，即 Java、Python(所有版本)。

Selenium 可以帮助我们自动完成任何经常在笔记本电脑上完成的任务，从使用脸书信使发短信到 WhatsApp，每天在推特上发推文，在脸书祝朋友“生日快乐”，在谷歌上搜索任何我们想学的东西，以及更多的任务。所有这些任务都可以在一个小的实现中使用 selenium 实现自动化。

**安装:**

*   转到命令提示符，并输入:

```py
pip install selenium
```

*   完成后，下载一个用于自动化的 web 驱动程序。这里，我们将使用来自[http://chromedriver.chromium.org/](http://chromedriver.chromium.org/)的 chromedriver

让我们学习如何将在脸书朋友的时间线上许愿的过程自动化。

这种自动化的整个过程可以分为以下几个部分:

*   使用用户名和密码等凭据登录脸书应用程序。
*   在生日是今天的朋友的时间线上发布“生日快乐”消息。

**以下是步骤:**

*   创建一个浏览器对象，并使用 get()函数向我们想要连接/使用的网站发送请求。
*   找到用户名和密码输入框、登录按钮等元素，使用 selenium 函数(如 click()、send_keys()等)分别点击按钮并输入用户名和密码。
*   之后使用 get()函数向/events/生日/页面发送请求。
*   在这个页面的顶部，有一张“今天的生日”卡片，上面显示了一个朋友的名字，他的生日是今天，同时还有一个输入文本框，用于输入他们时间线上的任何提要。
*   使用这些输入文本框的 XPATH，我们将使用 selenium 的 send_keys()函数发送我们的提要，即“生日快乐”。
*   关闭浏览器。

注:在执行以下程序之前，创建一个单独的 test.txt 文件，并在其中输入您的脸书密码。

下面是实现:

## 蟒蛇 3

```py
# importing necessary classes
# from different modules
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.chrome.options import Options
from selenium.common.exceptions import TimeoutException
from selenium.webdriver.common.keys import Keys
import time

chrome_options = webdriver.ChromeOptions()

prefs = {"profile.default_content_setting_values.notifications": 2}
chrome_options.add_experimental_option("prefs", prefs)
browser = webdriver.Chrome("chromedriver.exe")

# open facebook.com using get() method
browser.get('https://www.facebook.com/')

# user_name or e-mail id
username = "agrawal.abhi108@gmail.com"

# getting password from text file
with open('test.txt', 'r') as myfile:
    password = myfile.read().replace('\n', '')

print("Let's Begin")

element = browser.find_elements_by_xpath('//*[@id ="email"]')
element[0].send_keys(username)

print("Username Entered")

element = browser.find_element_by_xpath('//*[@id ="pass"]')
element.send_keys(password)

print("Password Entered")

# logging in
log_in = browser.find_elements_by_id('loginbutton')
log_in[0].click()

print("Login Successful")

browser.get('https://www.facebook.com/events/birthdays/')

feed = 'Happy Birthday !'

element = browser.find_elements_by_xpath("//*[@class ='enter_submit\
       uiTextareaNoResize uiTextareaAutogrow uiStreamInlineTextarea\
                  inlineReplyTextArea mentionsTextarea textInput']")

cnt = 0

for el in element:
    cnt += 1
    element_id = str(el.get_attribute('id'))
    XPATH = '//*[@id ="' + element_id + '"]'
    post_field = browser.find_element_by_xpath(XPATH)
    post_field.send_keys(feed)
    post_field.send_keys(Keys.RETURN)
    print("Birthday Wish posted for friend" + str(cnt))

# Close the browser
browser.close()
```