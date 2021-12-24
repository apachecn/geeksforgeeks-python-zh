# 使用 Python 创建一个图形用户界面来查找域名的 IP

> 原文:[https://www . geeksforgeeks . org/create-a-GUI-to-find-IP-for-域名-使用-python/](https://www.geeksforgeeks.org/create-a-gui-to-find-the-ip-for-domain-names-using-python/)

**先决条件:**[**Python GUI–tkinter**](https://www.geeksforgeeks.org/python-gui-tkinter/)

在本文中，我们将看到如何从域名中找到 IP，并使用 Python 将其与图形用户界面应用程序绑定。我们将使用 **iplookup** 模块从域名中查找 IP。它是一个小模块，接受单个域作为字符串，或多个域作为列表，并返回相关联的 IP 列表。

将此代码运行到您的终端中进行安装。

```
pip install iplookup
```

**进场:**

*   导入模块
*   创建 iplookup 对象
*   将域传递到 iplookup obj
*   现在遍历 IP

**实施:**

## 蟒蛇 3

```
# import module
from iplookup import iplookup

#create object of iplookup
ip = iplookup.iplookup

# Input by geek
# domain name
domain = "geeksforgeeks.org"

# pass the domain
# into iplookup obj
result = ip(domain)

# traverse the ip
print("Domain name : ",domain)
print("Ip : ",result)
```

**输出:**

```
Domain name :  geeksforgeeks.org
Ip :  ['34.218.62.116']
```

**使用 This 从域图形用户界面应用程序中查找 IP:**该脚本将上述实现实现到图形用户界面中。

## 蟒蛇 3

```
# import modules
from tkinter import *
from tkinter import messagebox
from iplookup import iplookup

def get_ip():
    try:
        ip = iplookup.iplookup
        result = ip(e.get())
        res.set(result)

    except:
        messagebox.showerror("showerror", "Something wrong")

# object of tkinter
# and background set for light grey
master = Tk()
master.configure(bg='light grey')

# Variable Classes in tkinter
res = StringVar()

# Creating label for each information
# name using widget Label
Label(master, text="Enter website name :",
      bg="light grey").grid(row=0, sticky=W)
Label(master, text="Result :", bg="light grey").grid(row=1, sticky=W)

# Creating label for class variable
# name using widget Entry
Label(master, text="", textvariable=res, bg="light grey").grid(
    row=1, column=1, sticky=W)

e = Entry(master)
e.grid(row=0, column=1)

# creating a button using the widget
# Button that will call the submit function
b = Button(master, text="Show", command=get_ip)
b.grid(row=0, column=2, columnspan=2, rowspan=2, padx=5, pady=5)

mainloop()
```

**输出:**

![](img/a66756f9b1c30d6d6fbbd995169b326d.png)