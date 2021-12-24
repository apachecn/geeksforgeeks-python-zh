# 脸书使用 Python 登录

> 原文:[https://www.geeksforgeeks.org/facebook-login-using-python/](https://www.geeksforgeeks.org/facebook-login-using-python/)

在学习 Python 的同时，Python 脚本是最有趣和迷人的事情之一。自动化和控制浏览器就是其中之一。

在这篇特别的文章中，我们将看到如何使用 Python 和 selenium 的强大功能登录脸书帐户。

[Selenium](https://www.geeksforgeeks.org/browser-automation-using-selenium/) 自动控制浏览器及其活动。在 selenium 的帮助下，我们可以用自己的方式编写代码来控制浏览器任务。首先，它是为了测试目的而自动化 web 应用程序，但当然不仅限于此。枯燥的基于网络的管理任务也可以自动化。随着你了解的越来越多，看到事情自动发生并一次又一次地做无用的事情来节省时间是非常有趣的。

我们在这里使用 selenium 打开我们的需求站点(在这里是脸书)，在那里我们检查电子邮件框、密码框和登录按钮中的元素，以找到它们的 id。

*   使用硒模块提供的 **find_element_by_id()** 功能，可以找到需要的元素(用户名框、密码框、登录按钮)
*   使用硒模块提供的 **send_keys()** 功能，我们将数据发送到盒子中。

1.  **需要安装第三方模块**

    ```
    Selenium 
    getpass
    Additional Requirement : geckodriver for firefox and 
                             chromedriver for chrome

    ```

2.  **导入必要的模块**
    *   硒:自动化浏览器
    *   时间:暂停脚本运行几秒钟，因为浏览器试图检测自动化的东西，如果我们输入太快
3.  **以用户名和密码作为来自用户**
    的输入，使用 **input()** 函数，以传递提示信息作为参数。
4.  **打开浏览器和所需网站**
    **网络驱动。Chrome()** 将开启 Chrome 新窗口。我们将把它的对象保存在名为 driver 的变量中。
    现在使用 get 功能我们将打开脸书网站。
5.  **查找发送数据的元素并发送输入**
    在您想要查找 id 的浏览器元素上使用检查元素工具。在这种情况下，我们将检查用户名框，密码框，登录按钮，以找到他们的 id。然后用这个 id 结合 selenium 函数 **find_element_by_id()** 跨网页查找，保存在变量中备用。然后通过使用 **send_keys()** 我们将跨先前找到的元素发送数据。
6.  **关闭浏览器**
    完成上述所有步骤后，我们必须退出会话，并使用 driver.quit()实现。
    **注意:**这里**驱动**是你为网络驱动选择的变量名称。Chrome()。

**完整代码:**

```
from selenium import webdriver
from time import sleep
from webdriver_manager.chrome import ChromeDriverManager
from selenium.webdriver.chrome.options import Options 

usr=input('Enter Email Id:') 
pwd=input('Enter Password:') 

driver = webdriver.Chrome(ChromeDriverManager().install())
driver.get('https://www.facebook.com/')
print ("Opened facebook")
sleep(1)

username_box = driver.find_element_by_id('email')
username_box.send_keys(usr)
print ("Email Id entered")
sleep(1)

password_box = driver.find_element_by_id('pass')
password_box.send_keys(pwd)
print ("Password entered")

login_box = driver.find_element_by_id('loginbutton')
login_box.click()

print ("Done")
input('Press anything to quit')
driver.quit()
print("Finished")
```

看看这样一段简洁的代码如何为您实现自动化。

**奖励:**
出于安全考虑，我们也可以**输入密码而不在**屏幕上显示。为此，我们必须再包含一个名为 **getpass** 的模块。现在只需对密码的输入语句进行一次更改，我们就可以输入密码，而无需在屏幕上显示。

```
from getpass import getpass
pwd = getpass('Enter Password:') 
```

Getpass 会提示用户输入密码，而不会回显。基本上，它可以让你输入密码而不在屏幕上显示。

同样，你也可以自动完成许多其他的事情，比如推特登录、推特、脸书注销等等。

**如有疑问，请在下方评论区留言。如果你喜欢这篇文章，想看更多类似的东西，请在下面的评论区告诉我。**

本文由**乌蒙阿胡佳**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。