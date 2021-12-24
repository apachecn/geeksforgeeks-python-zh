# Python EasyGUI–按钮盒

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-easy GUI 按钮盒/

**EasyGUI** 是一个用 Python 进行非常简单、非常容易的 GUI 编程的模块。EasyGUI 与其他 GUI 生成器的不同之处在于 EasyGUI 不是事件驱动的。相反，所有的图形用户界面交互都是通过简单的函数调用来调用的。与其他复杂的图形用户界面不同，易趣是迄今为止最简单的图形用户界面。

**按钮框:**用于在 EasyGUI 中显示一个有多个按钮的窗口，在有条件的情况下可以在很多按钮中选择一个，例如电梯中的按钮一次用户只能选择一个选项，下图是普通按钮框的样子
![](img/f465fb74c39fb7b1bd607f10ea4234ab.png)

> 为了做到这一点，我们将使用`buttonbox`方法
> 
> **语法:**按钮框(文本、标题、按钮列表)
> 
> **参数:**需要 3 个参数，第一个字符串即要显示的文本，第二个字符串即窗口标题和第三个按钮列表(字符串)
> 
> **返回:**返回用户选择的按钮文本

**示例:**
在这里我们将创建一个有三个按钮的按钮框窗口，用户可以选择并打印所选的按钮文本，下面是实现

```py
# importing easygui module
from easygui import *

# message to be displayed 
text = "Message to be displayed on the window GfG"

# window title
title = "Window Title GfG"

# button list
button_list = []

# button 1
button1 = "First"

# second button
button2 = "Second"

# third button
button3 = "Third"

# appending button to the button list
button_list.append(button1)
button_list.append(button2)
button_list.append(button3)

# creating a button box
output = buttonbox(text, title, button_list)

# printing the button pressed by the user
print("User selected option : ", end = " ")
print(output)
```

**输出:**

<video class="wp-video-shortcode" id="video-479803-1" width="665" height="197" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200902184307/Window-Title-GfG-2020-09-02-18-42-20.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200902184307/Window-Title-GfG-2020-09-02-18-42-20.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200902184307/Window-Title-GfG-2020-09-02-18-42-20.mp4)</video>

```py
User selected option :  Second

```

**另一个例子:**

```py
# importing easygui module
from easygui import *

# message to be displayed 
text = "Message to be displayed on the window GfG"

# window title
title = "Window Title GfG"

# creating a button box
output = buttonbox(text, title)

# printing the button pressed by the user
print("User selected option : ", end = " ")
print(output)
```

**输出:**

<video class="wp-video-shortcode" id="video-479803-2" width="665" height="197" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200902184554/Window-Title-GfG-2020-09-02-18-45-02.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200902184554/Window-Title-GfG-2020-09-02-18-45-02.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200902184554/Window-Title-GfG-2020-09-02-18-45-02.mp4)</video>

```py
User selected option :  Button[3]

```