# 使用卡路里妈妈 API 的食物识别硒

> 原文:[https://www . geesforgeks . org/food-recognition-selenium-use-caloriemama-API/](https://www.geeksforgeeks.org/food-recognition-selenium-using-caloriemama-api/)

[硒](https://www.geeksforgeeks.org/browser-automation-using-selenium/)是通过程序控制网页浏览器的强大工具。它适用于所有浏览器，适用于所有主要操作系统，其脚本是用各种语言编写的，如 Python、Java、C#等，我们将使用 Python。

在本文中，我们将看到如何使用 selenium 自动运行 Caloriemama 网站。我们只是要在`caloriemama` API 网站上发布一张美食图片，并返回它在那个网站上显示的结果。

在进入代码之前，我们需要为 Python 安装 selenium。

```
pip install selenium
```

**网络驱动程序**
Selenium 需要一个网络驱动程序来与所选的浏览器交互。Web 驱动程序是一个与 web 浏览器交互的包。它通过通用的有线协议与网络浏览器或远程网络服务器进行交互。您可以签出并安装您选择的网络驱动程序。

```
Chrome: https://sites.google.com/a/chromium.org/chromedriver/downloads
Firefox: https://github.com/mozilla/geckodriver/releases
Safari: https://webkit.org/blog/6900/webdriver-support-in-safari-10/
```

#### 需要的模块

*   **硒:**用于自动化网络浏览器
*   **time:** For using sleep function because selenium works only when the all the elements of the page is loaded.

    我们将发送食物的图片，并将识别的食物结果作为文本发送。让我们考虑一下食物的形象是这样的–

    ![food](img/b1a057bdeb82315d328c17371b4f8c7e.png)

    ```
    # food recognition using caloriemama API
    # selenium example
    from selenium import webdriver
    import time

    # create the variable for webdriver 
    browser = webdriver.Firefox(executable_path='/path/to/geckodriver') 

    # it will open browser and
    # search for the below URL
    browser.get('https://www.caloriemama.ai/api')

    # find class name 'file-upload' 
    upload = browser.find_element_by_class_name('file-upload')

    # enter your image file
    # location here & send image
    upload.send_keys("/path/to/food.jpeg") 

    time.sleep(5) 

    # return the value by class name
    get = browser.find_element_by_class_name('group-name')

    print(get.text) 
    # on the website, it will show many
    # results depend on the accuracy
    # first result is  high accuracy one

    # if need all the result put it in 
    # loop like below and change
    # 'find_element_by_class_name' 
    # to 'find_elements_by_class_name'
    # for got in get:
    # print(got.text, "\n") 
    # break 
    ```

    **输出:**

    ```
    Pizza
    ```