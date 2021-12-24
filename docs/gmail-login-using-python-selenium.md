# 使用 Python Selenium 登录 Gmail】

> 原文:[https://www . geesforgeks . org/Gmail-登录-使用-python-selenium/](https://www.geeksforgeeks.org/gmail-login-using-python-selenium/)

在学习 Python 的同时，Python 脚本是最有趣和迷人的事情之一。自动化和控制浏览器就是其中之一。

在这篇特别的文章中，我们将看到如何使用 Python 和硒的力量登录 Gmail 帐户。

Selenium 自动化并控制浏览器及其活动。在 selenium 的帮助下，我们可以用自己的方式编写代码来控制浏览器任务。首先，它是为了测试目的而自动化 web 应用程序，但当然不仅限于此。枯燥的基于网络的管理任务也可以自动化。随着你了解的越来越多，看到事情自动发生并一次又一次地做无用的事情来节省时间是非常有趣的。

我们在这里使用 selenium 打开我们需求的站点(在这个例子中是 Gmail)，在那里我们检查电子邮件框、密码框和下一步按钮中的元素，以找到它们的 Xpath。

*   Using the find _ element _ by _ XPath () function provided by **selenium module, we can find the required elements (user name box, password box, next button).**

 **send_keys()** 

*   Using the **click ()** function, a selenium module is provided, and we click on the current element.
*   **。 The get ()** property allows us to open a web page.
*   **。 Implicit wait ()** allows us to wait for the page to load.

#### **需要安装第三方模块**

*   硒
*   get pass(get pass)
*   附加要求:火狐的 geckodriver 和 chrome 的 chromedriver

#### **导入必要的模块**

硒:自动化浏览器

#### **以用户名和密码作为用户输入**

使用**输入()**函数并传递提示信息作为参数。

#### **打开浏览器和所需网站**

**webdriver。Chrome()** 将打开 Chrome 的新窗口。我们将把它的对象保存在名为 driver 的变量中。

现在使用 get 功能，我们将打开 Gmail 网站。

#### **查找发送数据和发送输入的元素**

在要查找 id 的浏览器元素上使用检查元素工具。在这种情况下，我们将检查用户名框，密码框，下一步按钮，以找到他们的 Xpath。然后用这个 Xpath 结合 selenium 函数 **find_element_by_xpath()** 跨网页查找，保存在变量中备用。然后通过使用 **send_keys()** 我们将跨先前找到的元素发送数据，然后通过使用 **click()** 我们将单击找到的元素。

**注意:**这里**驱动**是你为**网络驱动选择的变量名称。Chrome()** 。

### 算法:

这是一个简单的程序，可以登录到你的 gmail 帐户。最好的情况是帐户不安全或组织邮件 id。

最坏的情况是，如果你有一个 gmail 帐户，启用了两步或双因素身份验证。

算法:

第一步:获取邮件 id 和密码

第二步:打开 gmail 登录页面

第三步:输入 gmail-id 并点击下一步按钮

第四步:输入密码，点击下一步按钮

第五步:打印成功或失败并结束

### 完整代码:

```
from selenium import webdriver
from webdriver_manager.chrome import ChromeDriverManager

print('Enter the gmailid and password')
gmailId, passWord = map(str, input().split())
try:
    driver = webdriver.Chrome(ChromeDriverManager().install())
    driver.get(r'https://accounts.google.com/signin/v2/identifier?continue='+\
    'https%3A%2F%2Fmail.google.com%2Fmail%2F&service=mail&sacu=1&rip=1'+\
    '&flowName=GlifWebSignIn&flowEntry = ServiceLogin')
    driver.implicitly_wait(15)

    loginBox = driver.find_element_by_xpath('//*[@id ="identifierId"]')
    loginBox.send_keys(gmailId)

    nextButton = driver.find_elements_by_xpath('//*[@id ="identifierNext"]')
    nextButton[0].click()

    passWordBox = driver.find_element_by_xpath(
        '//*[@id ="password"]/div[1]/div / div[1]/input')
    passWordBox.send_keys(passWord)

    nextButton = driver.find_elements_by_xpath('//*[@id ="passwordNext"]')
    nextButton[0].click()

    print('Login Successful...!!')
except:
    print('Login Failed')
```

看看这样一段简洁的代码如何为您实现自动化。

### 奖金:

出于安全考虑，我们也可以**输入密码而不在**屏幕上显示。为此，我们必须增加一个名为 **getpass** 的模块。现在只需对密码的输入语句进行一次更改，我们就可以输入密码，而无需在屏幕上显示。

```
from getpass import getpass

pwd = getpass('Enter Password:')
```

Getpass 会提示用户输入密码，而不会回显。基本上，它可以让你输入密码而不在屏幕上显示。

同样，你也可以自动完成许多其他事情，比如 twitter 登录、推文、Gmail 注销等等。