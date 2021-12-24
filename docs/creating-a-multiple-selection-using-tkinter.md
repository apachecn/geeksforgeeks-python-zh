# 使用 Tkinter 创建多重选择

> 原文:[https://www . geesforgeks . org/creating-a-multi-selection-use-tkinter/](https://www.geeksforgeeks.org/creating-a-multiple-selection-using-tkinter/)

**前提条件:**[python tkinter──列表框构件](https://www.geeksforgeeks.org/python-tkinter-listbox-widget/)、[python-tkinter 中的滚动列表框](https://www.geeksforgeeks.org/scrollable-listbox-in-python-tkinter/)

Tkinter 是 python 中的 GUI 库，易于阅读和理解。在 Tkinter 中，可以使用列表框小部件进行多重选择。通常，列表框以列表的形式显示不同的项目。列表框小部件从列表中提供一个或多个项目选择。Listbox 小部件中有许多选项可供用户选择多个选项。通过将选择模式选项指定为多个，用户可以选择多个选项。如果选择模式选项是单一的，则用户只能选择一个选项。
列表框小部件的 selectmode 选项可以是单个、浏览、多个或扩展。

*   **单个**–选择一行文本。
*   **浏览**–这是一个默认选项，用户可以选择一行文本。
*   **多行**–选择多行文本，无需从选项的第一行拖到最后一行。
*   **扩展**–用户可以选择并拖动相邻的多行文本。

**语法:**

```py
list_box = Listbox(root, options, ....)

```

**示例 1:** 在列表框中显示有限项目的 Python 程序。

```py
# Python program demonstrating
# Multiple selection in Listbox widget

from tkinter import * 

window = Tk()
window.geometry('100x150')

# Choosing selectmode as multiple 
# for selecting multiple options
list = Listbox(window, selectmode = "multiple")

# Widget expands horizontally and
# vertically by assigning both to 
# fill option
list.pack(expand = YES, fill = "both")

# Taking a list 'x' with the items 
# as languages
x = ["C", "C++", "Java", "Python", "R",
     "Go", "Ruby", "JavaScript", "Swift"]

for each_item in range(len(x)):

    list.insert(END, x[each_item])

    # coloring alternative lines of listbox
    list.itemconfig(each_item,
             bg = "yellow" if each_item % 2 == 0 else "cyan")

window.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-399678-1" width="665" height="374" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/uploads/20200420183159/multiple-slection-tkinter.webm?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200420183159/multiple-slection-tkinter.webm](https://media.geeksforgeeks.org/wp-content/uploads/20200420183159/multiple-slection-tkinter.webm)</video>

从上面的多选列表框中，用户可以选择多个选项。由于列表框中符合规定大小的项目有限，用户可以看到所有项目。但是如果有更多的项目要显示给用户，那么列表框中的所有项目都不会同时可见。因此，如果列表中有更多的项目要显示，就需要在列表框上附加滚动条。这可以通过列表框中的`yscrollcommand`选项(垂直滚动)来完成。

**示例 2:** Python 程序显示带有滚动条的列表框。

```py
# Python program demonstrating Multiple selection
# in Listbox widget with a scrollbar

from tkinter import *

window = Tk()
window.title('Multiple selection')

# for scrolling vertically
yscrollbar = Scrollbar(window)
yscrollbar.pack(side = RIGHT, fill = Y)

label = Label(window,
              text = "Select the languages below :  ",
              font = ("Times New Roman", 10), 
              padx = 10, pady = 10)
label.pack()
list = Listbox(window, selectmode = "multiple", 
               yscrollcommand = yscrollbar.set)

# Widget expands horizontally and 
# vertically by assigning both to
# fill option
list.pack(padx = 10, pady = 10,
          expand = YES, fill = "both")

x =["C", "C++", "C#", "Java", "Python",
    "R", "Go", "Ruby", "JavaScript", "Swift",
    "SQL", "Perl", "XML"]

for each_item in range(len(x)):

    list.insert(END, x[each_item])
    list.itemconfig(each_item, bg = "lime")

# Attach listbox to vertical scrollbar
yscrollbar.config(command = list.yview)
window.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-399678-2" width="665" height="374" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/uploads/20200420183240/multiple-slection-python-tkinter-scrollable.webm?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200420183240/multiple-slection-python-tkinter-scrollable.webm](https://media.geeksforgeeks.org/wp-content/uploads/20200420183240/multiple-slection-python-tkinter-scrollable.webm)</video>