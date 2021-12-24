# 使用 Tkinter | Python 获取屏幕的高度和宽度

> 原文:[https://www . geesforgeks . org/get-screens-height-and-width-use-tkinter-python/](https://www.geeksforgeeks.org/getting-screens-height-and-width-using-tkinter-python/)

Tkinter 提供了一些方法，借助这些方法我们可以得到当前屏幕的高度和宽度。
可采用以下方法确定高度和宽度:

```
winfo_screenheight() // Returns screen height in pixels

winfo_screenmmheight() // Returns screen height in mm

winfo_screenwidth() // Returns screen width in pixels

winfo_screenmmwidth() // Returns screen width in mm
```

**代码#1:** 以像素为单位获取高度和宽度。

## 蟒蛇 3

```
# importing tkinter module
from tkinter import * from tkinter.ttk import *

# creating tkinter window
root = Tk()

# getting screen's height in pixels
height = root.winfo_screenheight()

# getting screen's width in pixels
width = root.winfo_screenwidth()

print("\n width x height = %d x %d (in pixels)\n" %(width, height))
# infinite loop
mainloop()
```