# 如何使用 Python Selenium 创建 GitHub 资源库？

> 原文:[https://www . geesforgeks . org/how-create-github-repository-use-python-selenium/](https://www.geeksforgeeks.org/how-to-create-github-repository-using-python-selenium/)

**先决条件:** [硒](https://www.geeksforgeeks.org/selenium-python-tutorial/)

Selenium 是通过程序控制网络浏览器和执行浏览器自动化的强大工具。它适用于所有浏览器，适用于所有主要操作系统，其脚本是用各种语言编写的，如 Python、Java、C#等，我们将使用 Python。硒教程涵盖了所有主题，如-网络驱动程序，网络元素，单元测试与硒。本 Python 硒教程涵盖了硒从基础到高级和专业用途。

在本文中，我们将编写一个 python 脚本，使用 Python 中的 selenium 创建一个 GitHub 存储库

**创建 GitHub 存储库的步骤:**

*   在创建存储库之前，我们需要首先登录**(需要用户名和密码)。**
*   登录后，我们将创建一个新的存储库，然后我们需要存储库名称。
*   这之后，剩下三件事；描述、模式**(私有或公共)**，以及自述文件。

**分步方法:**

**步骤 1:** 导入模块并创建 Chrome 对象

## 蟒蛇 3

```py
# import Module
from selenium import webdriver

# Create Chrome Object
driver = webdriver.Chrome(
    'Chrome Driver Path')
```

**第二步:**使用以下参数创建 **github_repo()** ，以合适的参数访问用户 github 并执行所需的任务。

## 蟒蛇 3

```py
def github_repo(user_name, pass_word,
                repository_name, descriptions=False,
                private=False, readme=False):

    # Open github login page
    driver.get('https://github.com/login')

    # Username
    username = driver.find_element_by_xpath('//*[@id="login_field"]')
    username.send_keys(user_name)

    # Password
    password = driver.find_element_by_xpath('//*[@id="password"]')
    password.send_keys(pass_word)

    # Click on sign in button
    signin = driver.find_element_by_xpath(
        '//*[@id="login"]/div[4]/form/input[14]')
    signin.click()

    # Create new repo.
    new_repo = driver.find_element_by_xpath('//*[@id="repos-container"]/h2/a')
    new_repo.click()

    # Enter Repo. name
    repositoryname = driver.find_element_by_xpath('//*[@id="repository_name"]')
    repositoryname.send_keys(repository_name)

    # Optional

    # Enter Description
    if descriptions:
        description = driver.find_element_by_xpath(
            '//*[@id="repository_description"]')
        description.send_keys(descriptions)

    # Private Mode
    if private:
        private = driver.find_element_by_xpath(
            '//*[@id="repository_visibility_private"]')
        private.click()

    # Create ReadMe File
    if readme:
        readme = driver.find_element_by_xpath(
            '//*[@id="repository_auto_init"]')
        readme.click()
```

**第三步:**用驱动程序代码中合适的参数调用上述函数，创建 GitHub 存储库。

## 蟒蛇 3

```py
github_repo("Enter Usename", "Enter Password",
            "Repository name")
```

**下面是实现:**

## 蟒蛇 3

```py
# import Module
from selenium import webdriver

# Create Chrome Object
driver = webdriver.Chrome('Chrome Driver Path')

def github_repo(user_name, pass_word,
                repository_name, descriptions=False,
                private=False, readme=False):

    # Open github login page
    driver.get('https://github.com/login')

    # Username
    username = driver.find_element_by_xpath('//*[@id="login_field"]')
    username.send_keys(user_name)

    # Password
    password = driver.find_element_by_xpath('//*[@id="password"]')
    password.send_keys(pass_word)

    # Click on signin button
    signin = driver.find_element_by_xpath(
        '//*[@id="login"]/div[4]/form/input[14]')
    signin.click()

    # Create new repo.
    new_repo = driver.find_element_by_xpath('//*[@id="repos-container"]/h2/a')
    new_repo.click()

    # Enter Repo. name
    repositoryname = driver.find_element_by_xpath('//*[@id="repository_name"]')
    repositoryname.send_keys(repository_name)

    # Optional

    # Enter Description
    if descriptions:
        description = driver.find_element_by_xpath(
            '//*[@id="repository_description"]')
        description.send_keys(descriptions)

    # Private Mode
    if private:
        private = driver.find_element_by_xpath(
            '//*[@id="repository_visibility_private"]')
        private.click()

    # Create ReadMe File
    if readme:
        readme = driver.find_element_by_xpath(
            '//*[@id="repository_auto_init"]')
        readme.click()

github_repo("Enter Usename", "Enter Password",
            "Repository name")

print("Repository created")

create_repo = driver.find_element_by_xpath(
    '//*[@id="new_repository"]/div[4]/button')

create_repo.click()
```

**输出:**

<video class="wp-video-shortcode" id="video-552048-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210202124135/FreeOnlineScreenRecorderProject3.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210202124135/FreeOnlineScreenRecorderProject3.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210202124135/FreeOnlineScreenRecorderProject3.mp4)</video>