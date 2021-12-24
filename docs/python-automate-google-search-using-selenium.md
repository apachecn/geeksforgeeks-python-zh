# Python |使用 Selenium 实现谷歌搜索自动化

> 原文:[https://www . geesforgeks . org/python-automate-Google-search-use-selenium/](https://www.geeksforgeeks.org/python-automate-google-search-using-selenium/)

只需 2 分钟，使用 Python 脚本即可实现谷歌搜索自动化。这可以使用 **`selenium`** (浏览器自动化工具)来完成。Selenium 是一个用于测试 web 应用程序的可移植框架。它可以自动执行您需要手动执行的相同交互，这是它的一个小例子。掌握 Selenium 将帮助您自动化日常任务，例如控制您的推文、Whatsapp 短信，甚至只是谷歌搜索，而无需实际打开浏览器，只需 15-30 行 python 代码。自动化的极限是无限的硒。

## 装置

1.  **硒**T0】
2.  **Chrome 浏览器**
3.  **Chromedriver**
    从[这里](https://chromedriver.chromium.org/downloads)下载 chrome 浏览器(为你的系统选择版本)
    下载完成后，解压后复制脚本文件夹中的文件。

这可以通过两种方式来实现，一种是从用户那里获取输入，另一种是在命令行中给出输入。

**#方法 1**
询问用户输入。

```
from selenium import webdriver

# Taking input from user
search_string = input("Input the URL or string you want to search for:")

# This is done to structure the string 
# into search url.(This can be ignored)
search_string = search_string.replace(' ', '+') 

# Assigning the browser variable with chromedriver of Chrome.
# Any other browser and its respective webdriver 
# like geckodriver for Mozilla Firefox can be used
browser = webdriver.Chrome('chromedriver')

for i in range(1):
    matched_elements = browser.get("https://www.google.com/search?q=" +
                                     search_string + "&start=" + str(i))
```

在 script.py 中保存上述脚本后，在命令提示符下以如下方式运行:

```
python script.py

```

**#方法二**

在命令行中使用搜索字符串。

```
from selenium import webdriver
import sys

# function to convert a list into string
def convert(s): 
    str1 = "" 
    return(str1.join(s)) 

# Assign the arguments passed to a variable search_string
search_string = sys.argv[1:] 

# The argument passed to the program is accepted
# as list, it is needed to convert that into string
search_string = convert(search_string)

# This is done to structure the string 
# into search url.(This can be ignored)
search_string = search_string.replace(' ', '+') 

# Assigning the browser variable with chromedriver of Chrome.
# Any other browser and its respective webdriver 
# like geckodriver for Mozilla Firefox can be used
browser = webdriver.Chrome('chromedriver')

for i in range(1):
    matched_elements = browser.get("https://www.google.com/search?q=" + 
                                   search_string + "&start=" + str(i))
```

在 script.py 中保存上述脚本后，在命令提示符下以如下方式运行:

```
python script.py "geeksforgeeks"
```