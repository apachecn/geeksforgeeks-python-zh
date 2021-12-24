# 如何用 Python 中的 Selenium 获取网页标题？

> 原文:[https://www . geesforgeks . org/如何获得网页标题-使用 python 中的硒/](https://www.geeksforgeeks.org/how-to-get-title-of-a-webpage-using-selenium-in-python/)

`title`方法用于检索用户当前正在处理的网页标题。它给出了 selenium 中驱动程序加载的当前网页的标题，如果网页没有标题，将返回空字符串。

**网页标题:**页面标题，也称为标题标签，是网页的简短描述，出现在浏览器窗口的顶部和 SERPs 中。这是一个优化的搜索引擎优化页面的重要元素。页面标题应该在标题标签中包含页面的关键字。

**语法:**

```
driver.title

```

**参数:**

不需要争论。

**返回值:**

它以字符串格式返回网页标题。

**Code 1:**

```
# importing webdriver from selenium
from selenium import webdriver

# Here Chrome  will be used
driver = webdriver.Chrome()

# URL of website
url = "https://www.geeksforgeeks.org/"

# Opening the website
driver.get(url)

# Getting current URL source code
get_title = driver.title

# Printing the title of this URL
print(get_title)
```

**输出:**

```
GeeksforGeeks | A computer science portal for geeks
```

**代码 2:**

```
# importing webdriver from selenium
from selenium import webdriver

# Here Chrome  will be used
driver = webdriver.Chrome()

# URL of website
url = "https://www.google.com/"

# Getting current URL source code
get_title = driver.title

# Printing the title of this URL
# Here it is null string
print(get_title, " ", len(get_title))

# Opening the website
driver.get(url)

# Getting current URL source code
get_title = driver.title

# Printing the title of this URL
print(get_title, "  ", len(get_title))
```

**输出:**

```
Google

```