# 如何创建 COVID19 数据表示图形用户界面？

> 原文:[https://www . geeksforgeeks . org/如何创建-a-co vid 19-数据表示-gui/](https://www.geeksforgeeks.org/how-to-create-a-covid19-data-representation-gui/)

**先决条件:**[Python Requests](https://www.geeksforgeeks.org/python-requests-tutorial/)[Python GUI–tkinter](https://www.geeksforgeeks.org/python-gui-tkinter/)
有时候我们只是想要一个快速的工具来真正告诉当前更新是什么，我们只需要最少的数据。网络废弃是指从网络上获取一些数据，然后对其进行处理，并以简洁明了的方式显示相关内容。
**代码在做什么？**

*   首先，我们使用 Tkinter 库使我们的脚本需要图形用户界面
*   我们使用请求库从非官方 api 获取数据
*   然后，我们显示我们需要的数据，在这种情况下，它的总活跃病例:和确诊病例

下面是实现。

## 蟒蛇 3

```py
import requests
import json
from tkinter import *

window = Tk()

# creating the Box
window.title("Covid-19")

# Determining the size of the Box
window.geometry('220x70')

# Including labels
lbl = Label(window,
            text ="Total active cases:-......")
lbl1 = Label(window,
             text ="Total confirmed cases:-...")

lbl.grid(column = 1, row = 0)
lbl1.grid(column = 1, row = 1)
lbl2 = Label(window, text ="")
lbl2.grid(column = 1, row = 3)

def clicked():
    # Opening the url and loading the
    # json data using json Library
    url = "https://api.covid19india.org / data.json"
    page = requests.get(url)
    data = json.loads(page.text)

    lbl.configure(text ="Total active cases:-"
                  + data["statewise"][0]["active"])

    lbl1.configure(text ="Total Confirmed cases:-"
                   + data["statewise"][0]["confirmed"])

    lbl2.configure(text ="Data refreshed")

btn = Button(window, text ="Refresh", command = clicked)
btn.grid(column = 2, row = 0)

window.mainloop()
```