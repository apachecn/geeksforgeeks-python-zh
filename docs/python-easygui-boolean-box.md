# python easy GUI–boolean box

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-easy GUI-boolean box/

**Bollean Box :** 用于在 EasyGUI 中显示一个有多个选项即按钮的窗口，如果第一个选择选项返回 1，索引为 0 的按钮返回 0，则可以在需要获取的地方使用，与索引框略有不同，下面是 Bollean Box 的外观
![](img/9365f6bad5ccebb2b9ced89d8b2a1a01.png)

> 为了做到这一点，我们将使用`boolbox`方法
> 
> **语法:** boolbox(消息、标题、按钮)
> 
> **参数:**需要 3 个参数，第一个字符串即要显示的消息/信息，第二个字符串即窗口标题，第三个是字符串列表即正好有两个按钮的按钮
> 
> **返回:**如果第一个按钮被按下，返回 1，否则用户选择的其他按钮返回 0

**示例:**
在这里我们将创建一个索引框，当任何按钮被按下时它会根据索引在屏幕上显示具体的消息，下面是实现

```py
# importing easygui module
from easygui import *

# message / information to be displayed on the screen
message = "Select any one button"

# title of the window
title = "GfG - EasyGUI"

# creating a index box
output = boolbox(message, title)

# showing new message according to the buttons pressed
# if output is 1
if output == 1:

    # message / information
    message = "First Button is pressed"

# if output is 0
elif output == 0:

    # message / information
    message = "Button rather than first button is pressed"

# title of the window
title = "GfG - EasyGUI"

# creating a message box
msg = msgbox(message, title)

```

**输出:**

<video class="wp-video-shortcode" id="video-479813-1" width="665" height="197" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200903021358/GfG-EasyGUI-2020-09-03-02-13-14.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200903021358/GfG-EasyGUI-2020-09-03-02-13-14.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200903021358/GfG-EasyGUI-2020-09-03-02-13-14.mp4)</video>
<video class="wp-video-shortcode" id="video-479813-2" width="665" height="197" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200903021420/GfG-EasyGUI-2020-09-03-02-13-25.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200903021420/GfG-EasyGUI-2020-09-03-02-13-25.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200903021420/GfG-EasyGUI-2020-09-03-02-13-25.mp4)</video>

**另一个例子:**
在这里我们将创建一个添加了按钮的索引框，当按下任何一个按钮时，它都会根据索引在屏幕上显示具体的消息，下面是实现

```py
# importing easygui module
from easygui import *

# message / information to be displayed on the screen
message = "Select any one button"

# title of the window
title = "GfG - EasyGUI"

# buttons
buttons = ["First", "Second"]

# creating a boolean box
output = boolbox(message, title, buttons)

# showing new message according to the buttons pressed
# if output is 1
if output == 1:

    # message / information
    message = "First Button is pressed"

# if output is 0
elif output == 0:

    # message / information
    message = "Button rather than first button is pressed"

# title of the window
title = "GfG - EasyGUI"

# creating a message box
msg = msgbox(message, title)

```

**输出:**

<video class="wp-video-shortcode" id="video-479813-3" width="665" height="197" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200903021705/GfG-EasyGUI-2020-09-03-02-16-43.mp4?_=3">[https://media.geeksforgeeks.org/wp-content/uploads/20200903021705/GfG-EasyGUI-2020-09-03-02-16-43.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200903021705/GfG-EasyGUI-2020-09-03-02-16-43.mp4)</video><video class="wp-video-shortcode" id="video-479813-4" width="665" height="197" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200903021420/GfG-EasyGUI-2020-09-03-02-13-25.mp4?_=4">[https://media.geeksforgeeks.org/wp-content/uploads/20200903021420/GfG-EasyGUI-2020-09-03-02-13-25.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200903021420/GfG-EasyGUI-2020-09-03-02-13-25.mp4)</video>