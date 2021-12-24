# 如何用 Python 中的 Selenium 获取 current_url？

> 原文:[https://www . geesforgeks . org/how-to-current _ URL-使用 python 中的硒/](https://www.geeksforgeeks.org/how-to-get-current_url-using-selenium-in-python/)

在使用 selenium 进行工作时，会打开并重定向许多 URL，以便跟踪 URL【使用 T0】方法。`current_url`方法用于检索用户当前正在访问的网页的网址。它给出了驱动程序在 selenium 中加载的当前网页的 URL。

**URL :** URL 是统一资源定位符的缩写，被定义为万维网上文档和其他资源的全球地址，例如，要访问 GeeksforGeeks 网站，您将进入 URL https://www.geeksforgeeks.org/。

**语法:**

```
driver.current_url

```

**参数:**

不需要争论。

**返回值:**
返回字符串格式的网址。

**Code 1:**

```
# Importing webdriver from selenium
from selenium import webdriver

# Here chrome webdriver is used
driver = webdriver.Chrome()

# URL of the website 
url = "https://www.geeksforgeeks.org/"

# Opening the URL
driver.get(url)

# Getting current URL
get_url = driver.current_url

# Printing the URL
print(get_url)
```

**输出:**

```
https://www.geeksforgeeks.org/
```

**代码 2:**

```
# Importing webdriver from selenium
from selenium import webdriver

# Here chrome webdriver is used
driver = webdriver.Chrome()

# URL of the website 
url = "https://www.geeksforgeeks.org/"

# Getting current URL
get_url = driver.current_url

# Printing the URL
print(get_url)

# Opening the URL
driver.get(url)

# Getting current URL
get_url = driver.current_url

# Printing the URL
print(get_url)
```

**输出:**

```
data:,
https://www.geeksforgeeks.org/

```

**注意:这里打印“数据:”，是因为当时没有打开网页。**