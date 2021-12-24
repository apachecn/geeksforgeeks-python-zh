# 如何用按钮设置 Tkinter 文本小部件的文本？

> 原文:[https://www . geeksforgeeks . org/如何设置带按钮的文本窗口小部件/](https://www.geeksforgeeks.org/how-to-set-text-of-tkinter-text-widget-with-a-button/)

**先决条件:** [Python 图形用户界面–tkinter](https://www.geeksforgeeks.org/python-gui-tkinter/)

[文本小部件](https://www.geeksforgeeks.org/python-tkinter-text-widget/)用于用户想要插入多行文本字段的地方。在本文中，我们将学习在按钮的帮助下在文本小部件的文本字段中设置文本的方法。

#### 方法:**使用插入和删除方法**

*   导入 Tkit 模块。
*   创建图形用户界面窗口。
*   创建我们的文本小部件
*   创建借助按钮设置文本的功能。该函数包含一个插入方法和一个删除方法。首先调用 delete 方法来删除文本小部件中的剩余文本。它将删除从 0 到结束的给定范围内的任何内容。
*   然后调用 insert 方法将我们想要推送的文本插入文本小部件。它接受两个参数，一个是我们想要插入的位置，第二个是我们想要以字符串形式设置的想要的文本。
*   按钮被创建，函数被解析为其中的一个命令。

下面是上述方法的实现

## 蟒蛇 3

```
# Import the tkinter module
import tkinter

# Creating the GUI window.
window = tkinter.Tk()
window.title("Welcome to geeksforgeeks")
window.geometry("800x100")

# Creating our text widget.
sample_text = tkinter.Entry(window)
sample_text.pack()

# Creating the function to set the text 
# with the help of button
def set_text_by_button():

    # Delete is going to erase anything
    # in the range of 0 and end of file,
    # The respective range given here
    sample_text.delete(0,"end")

    # Insert method inserts the text at
    # specified position, Here it is the
    # begining
    sample_text.insert(0, "Text set by button")

# Setting up the button, set_text_by_button() 
# is passed as a command
set_up_button = tkinter.Button(window, height=1, width=10, text="Set", 
                    command=set_text_by_button)

set_up_button.pack()

window.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-525935-1" width="665" height="374" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/20201211212505/tinkter-text-by-button.webm?_=1">[https://media.geeksforgeeks.org/wp-content/cdn-uploads/20201211212505/tinkter-text-by-button.webm](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20201211212505/tinkter-text-by-button.webm)</video>