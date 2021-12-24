# 使用 Python 在服务器上找到或找不到测试给定页面的应用程序

> 原文:[https://www . geeksforgeeks . org/一个应用程序使用 python 在服务器上测试给定页面是否被发现/](https://www.geeksforgeeks.org/an-application-to-test-the-given-page-is-found-or-not-on-the-server-using-python/)

**先决条件:**[Python urlib 模块](https://www.geeksforgeeks.org/python-urllib-module/)

在本文中，我们将编写脚本来测试给定的页面是否在服务器上被 GUI 应用程序找到。我们需要安装 Urllib 模块来执行这个操作。在您的终端中键入此命令。

```py
pip install urllib
```

**进场:**

*   导入 urllib 模块。
*   用 urllib.request.urlopen()读取 URL。
*   检查读取网址是否有任何异常。

**实施:**

## 蟒蛇 3

```py
# import module
from urllib.request import urlopen, URLError, HTTPError

# exception handling to
# catch URL error
try:
    html = urlopen("https://www.geeksforgeeks.org/")

except URLError as e:
    print("Server not found!")

except HTTPError as e:
    print("HTTP error")

else:
    print("Server found")
```

**输出:**

```py
Server found
```

**用于测试给定页面的应用程序在服务器上是否找到**[**【Tkinter】**](https://www.geeksforgeeks.org/create-first-gui-application-using-python-tkinter/)**:**该脚本将上述实现与图形用户界面相结合。

## 蟒蛇 3

```py
# import modules
from tkinter import *
from urllib.request import urlopen, URLError

# user defined function
def URL_check():
    try:
        html = urlopen(str(e1.get()))
    except URLError as e:
        res = "Server not found!"
    else:
        res = "Server found"
    result.set(res)

# object of tkinter
# and background set to light grey
master = Tk()
master.configure(bg='light grey')

# Variable Classes in tkinter
result = StringVar()

# Creating label for each information

# name using widget Label
Label(master, text="Enter URL : ", bg="light grey").grid(row=1, sticky=W)
Label(master, text="Status :", bg="light grey").grid(row=3, sticky=W)

# Creating label for class variable

# name using widget Entry
Label(master, text="", textvariable=result,
      bg="light grey").grid(row=3, column=1, sticky=W)

e1 = Entry(master, width=50)
e1.grid(row=1, column=1)

# creating a button using the widget
b = Button(master, text="Check", command=URL_check, bg="white")
b.grid(row=1, column=2, columnspan=2, rowspan=2, padx=5, pady=5,)

mainloop()
```

**输出:**

![](img/17e6111620686e1a602a1c77cc974de3.png)

请检查另一个网址。

![](img/18085d0bd83d0ba20c8f24ddb927e9fa.png)