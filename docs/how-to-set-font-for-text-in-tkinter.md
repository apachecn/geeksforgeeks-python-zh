# 如何设置 Tkinter 中文本的字体？

> 原文:[https://www . geesforgeks . org/如何在 tkinter 中为文本设置字体/](https://www.geeksforgeeks.org/how-to-set-font-for-text-in-tkinter/)

**先决条件:** [Python 图形用户界面–tkinter](https://www.geeksforgeeks.org/python-gui-tkinter/)

Python 为 GUI(图形用户界面)提供了一个 Tkinter 模块。在这篇文章中，我们将看到如何在 Tkinter 中设置文本字体。

[文本小部件](https://www.geeksforgeeks.org/python-tkinter-text-widget/)用于用户想要插入多行文本字段的地方。在本文中，我们将学习设置插入文本小部件的文本字段中的字体的方法。可以用不同的方法来完成。

**方法 1:** 使用元组和。configure()方法。

**进场:**

*   导入 tkinter 模块。
*   创建图形用户界面窗口。
*   创建我们的文本小部件。
*   创建一个包含字体规格的元组。但是在创建这个元组时，顺序应该像这样保持(font_family，font_size_in_pixel，font_weight)。Font_family 和 font_weight 应该作为字符串传递，字体大小应该作为整数传递。
*   使用解析文本小部件的规范。configure()方法。

**以下是上述方法的实施**

## 蟒蛇 3

```
# Import the tkinter module
import tkinter

# Creating the GUI window.
root = tkinter.Tk()
root.title("Welcome to GeekForGeeks") 
root.geometry("400x240")

# Creating our text widget.
sample_text = tkinter.Text( root, height = 10)
sample_text.pack()

# Creating a tuple containing 
# the specifications of the font.
Font_tuple = ("Comic Sans MS", 20, "bold")

# Parsed the specifications to the
# Text widget using .configure( ) method.
sample_text.configure(font = Font_tuple)
root.mainloop()
```

**输出:**

![](img/99e2e0c0929409c69038a05cdaf0df47.png)

**方法 2:** 使用 tkinter.font 的 font 对象设置字体

**进场:**

*   导入 Tkit 模块。
*   导入 Tkinter font。
*   创建图形用户界面窗口
*   创建我们的文本小部件。
*   从 tkinter.font 模块创建一个 Font 类型的对象。它采用所需的字体规格(字体系列、字体大小像素、字体粗细)作为该对象的构造函数。这是文本小部件在确定其字体时需要的指定对象。
*   使用将字体对象解析为文本小部件。configure()方法。

**以下是上述方法的实现:**

## 蟒蛇 3

```
# Import module
import tkinter
import tkinter.font

# Creating the GUI window.
root = tkinter.Tk()
root.title("Welcome to GeekForGeeks") 
root.geometry("918x450")

# Creating our text widget.
sample_text=tkinter.Text( root, height = 10)
sample_text.pack()

# Create an object of type Font from tkinter.
Desired_font = tkinter.font.Font( family = "Comic Sans MS", 
                                 size = 20, 
                                 weight = "bold")

# Parsed the Font object 
# to the Text widget using .configure( ) method.
sample_text.configure(font = Desired_font)
root.mainloop()
```

**输出:**

![](img/85390dc35a9c646d04093f48810a3b64.png)