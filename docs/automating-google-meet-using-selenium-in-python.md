# 使用 Python 中的硒实现谷歌会议自动化

> 原文:[https://www . geesforgeks . org/automation-Google-meet-use-selenium in-python/](https://www.geeksforgeeks.org/automating-google-meet-using-selenium-in-python/)

**先决条件** : [硒 Python 基础知识](https://www.geeksforgeeks.org/selenium-python-basics/)，[使用硒的浏览器自动化](https://www.geeksforgeeks.org/browser-automation-using-selenium/)

Selenium 是通过程序控制网络浏览器和执行浏览器自动化的强大工具。它适用于所有浏览器，适用于所有主要操作系统，其脚本是用各种语言编写的，如 Python、Java、C#等，我们将使用 Python。

硒可以用来自动化网络浏览器。在这篇文章中，我们将学习如何登录谷歌帐户，并通过谷歌会议在使用硒关闭摄像头和麦克风的情况下加入会议。

### 安装:

使用以下命令可以安装*硒*模块:

```
pip install selenium
```

### 逐步方法:

**步骤 1:** 导入模块

## 蟒蛇 3

```
# import required modules
from selenium import webdriver
from selenium.webdriver.chrome.options import Options
import time
```

**步骤 2:** 创建一个 Chrome 浏览器实例，其中包含一些必需的先决条件 Chrome *选项()。*

## 蟒蛇 3

```
# creating chrome instance
opt = Options()
opt.add_argument('--disable-blink-features=AutomationControlled')
opt.add_argument('--start-maximized')
opt.add_experimental_option("prefs", {

    "profile.default_content_setting_values.media_stream_mic": 1,
    "profile.default_content_setting_values.media_stream_camera": 1,
    "profile.default_content_setting_values.geolocation": 0,
    "profile.default_content_setting_values.notifications": 1
})
driver = webdriver.Chrome(options=opt)
```

**步骤 3:** 使用此命令前往 Google meet

## 蟒蛇 3

```
# go to google meet
driver.get('https://meet.google.com/xby-zehb-ncf')
```

**第四步:**调用下面的功能会关闭摄像头和麦克风。在此功能中，*关闭麦克风()*，我们使用硒元素中名为*的函数 find_element_by_xpath()通过其[XPath](https://www.geeksforgeeks.org/introduction-to-xpath/)找到麦克风&摄像头按钮。*

## 蟒蛇 3

```
# explicit function to turn off mic and cam
def turnOffMicCam():

    # turn off Microphone
    time.sleep(2)
    driver.find_element_by_xpath(
        '//*[@id="yDmH0d"]/c-wiz/div/div/div[8]/div[3]/div/div/div[2]/div/div[1]/div[1]/div[1]/div/div[4]/div[1]/div/div/div').click()
    driver.implicitly_wait(3000)

    # turn off camera
    time.sleep(1)
    driver.find_element_by_xpath(
        '//*[@id="yDmH0d"]/c-wiz/div/div/div[8]/div[3]/div/div/div[2]/div/div[1]/div[1]/div[1]/div/div[4]/div[2]/div/div').click()
    driver.implicitly_wait(3000)
```

**第五步:**下面的功能将帮助我们加入谷歌会议。在这个函数 *joinNow()* 中，我们通过其 css 选择器找到 joinNow 按钮，使用 selenium 中一个名为*的函数 find _ element _ by _ CSS _ selector()*并点击它加入会议！(我们在 *AskToJoin()* 功能中也是这样做的)。

## 蟒蛇 3

```
def AskToJoin():
    # Ask to Join meet
    time.sleep(5)
    driver.implicitly_wait(2000)
    driver.find_element_by_css_selector(
        'div.uArJ5e.UQuaGc.Y5sE8d.uyXBBb.xKiqt').click()
    # Ask to join and join now buttons have same xpaths
```

**步骤 6:** 下面是使用提供的凭据登录谷歌账户的功能。在此功能中， *Glogin(mail，pw)* ，我们使用名为*的 selenium 中的函数 find_element_by_id()* 通过其 id 找到电子邮件文本框，并使用 *send_keys()* &键入电子邮件，使用其 *id* 再次单击*下一步*按钮，并使用其 [xpath](https://www.geeksforgeeks.org/introduction-to-xpath/) 找到密码文本框，使用 *send_keys* &键入密码

## 蟒蛇 3

```
def Glogin(mail_address, password):
    # Login Page
    driver.get(
        'https://accounts.google.com/ServiceLogin?hl=en&passive=true&continue=https://www.google.com/&ec=GAZAAQ')

    # input Gmail
    driver.find_element_by_id("identifierId").send_keys(mail_address)
    driver.find_element_by_id("identifierNext").click()
    driver.implicitly_wait(10)

    # input Password
    driver.find_element_by_xpath(
        '//*[@id="password"]/div[1]/div/div[1]/input').send_keys(password)
    driver.implicitly_wait(10)
    driver.find_element_by_id("passwordNext").click()
    driver.implicitly_wait(10)

    # go to google home page
    driver.get('https://google.com/')
    driver.implicitly_wait(100)
```

**以下是基于上述分步方法的完整程序:**

## 蟒蛇 3

```
# import required modules
from selenium import webdriver
from selenium.webdriver.chrome.options import Options
import time

def Glogin(mail_address, password):
    # Login Page
    driver.get(
        'https://accounts.google.com/ServiceLogin?hl=en&passive=true&continue=https://www.google.com/&ec=GAZAAQ')

    # input Gmail
    driver.find_element_by_id("identifierId").send_keys(mail_address)
    driver.find_element_by_id("identifierNext").click()
    driver.implicitly_wait(10)

    # input Password
    driver.find_element_by_xpath(
        '//*[@id="password"]/div[1]/div/div[1]/input').send_keys(password)
    driver.implicitly_wait(10)
    driver.find_element_by_id("passwordNext").click()
    driver.implicitly_wait(10)

    # go to google home page
    driver.get('https://google.com/')
    driver.implicitly_wait(100)

def turnOffMicCam():
    # turn off Microphone
    time.sleep(2)
    driver.find_element_by_xpath(
        '//*[@id="yDmH0d"]/c-wiz/div/div/div[8]/div[3]/div/div/div[2]/div/div[1]/div[1]/div[1]/div/div[4]/div[1]/div/div/div').click()
    driver.implicitly_wait(3000)

    # turn off camera
    time.sleep(1)
    driver.find_element_by_xpath(
        '//*[@id="yDmH0d"]/c-wiz/div/div/div[8]/div[3]/div/div/div[2]/div/div[1]/div[1]/div[1]/div/div[4]/div[2]/div/div').click()
    driver.implicitly_wait(3000)

def joinNow():
    # Join meet
    print(1)
    time.sleep(5)
    driver.implicitly_wait(2000)
    driver.find_element_by_css_selector(
        'div.uArJ5e.UQuaGc.Y5sE8d.uyXBBb.xKiqt').click()
    print(1)

def AskToJoin():
    # Ask to Join meet
    time.sleep(5)
    driver.implicitly_wait(2000)
    driver.find_element_by_css_selector(
        'div.uArJ5e.UQuaGc.Y5sE8d.uyXBBb.xKiqt').click()
    # Ask to join and join now buttons have same xpaths

# assign email id and password
mail_address = 'emaild@gmail.com'
password = 'geeksforgeeks'

# create chrome instamce
opt = Options()
opt.add_argument('--disable-blink-features=AutomationControlled')
opt.add_argument('--start-maximized')
opt.add_experimental_option("prefs", {
    "profile.default_content_setting_values.media_stream_mic": 1,
    "profile.default_content_setting_values.media_stream_camera": 1,
    "profile.default_content_setting_values.geolocation": 0,
    "profile.default_content_setting_values.notifications": 1
})
driver = webdriver.Chrome(options=opt)

# login to Google account
Glogin(mail_address, password)

# go to google meet
driver.get('https://meet.google.com/xby-zehb-ncf')
turnOffMicCam()
# AskToJoin()
joinNow()
```

**输出:**

<video class="wp-video-shortcode" id="video-536259-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210101235447/Google-Meet-using-Selenium.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210101235447/Google-Meet-using-Selenium.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210101235447/Google-Meet-using-Selenium.mp4)</video>