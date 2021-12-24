# 在 Tkinter 文本小部件中创建查找和替换功能

> 原文:[https://www . geesforgeks . org/create-find-and-replace-features-in-tkinter-text-widget/](https://www.geeksforgeeks.org/create-find-and-replace-features-in-tkinter-text-widget/)

**先决条件:**[Python GUI–tkinter](https://www.geeksforgeeks.org/python-gui-tkinter/)
首先，我们需要在下面的文本中找到我们想要替换的所有单词或字母，为此，我们将使用 find 函数，在该函数中，我们将从同一个单词的编辑器中确定所有的开始和结束索引，然后我们将应用 replace 功能，在该功能中，我们将删除文本的该部分，然后，我们将应用 insert 函数在该确切位置添加文本。
**使用的重要内置功能**

*   **Tk()** 它创建一个基础窗口/tkinter 基础小部件
*   **Frame()** 它在 Tk()实例的特定位置创建一个单独的 Frame
*   **标签()**它添加任何事物的陈述或名称或标签
*   **输入()**增加对话框输入文本
*   **“入口姿态”。pack()** 它在指定的位置包装入口箱
*   **按钮()**将带有命令和标签的按钮放置在指定位置
*   **Text()** 它放置一个文本框来编写和添加内容
*   **“文本实例”。insert()** 它在指定的索引处添加文本(这里的索引是字符串类型的)
*   **“文本实例”。tag_add()** 标签用于同时引用所有内容，例如，如果一个段落包含文本“this”五次，为了同时对它们进行更改，我们使用标签。tag_Add 将所有这些文本添加到由我们提供名称的特定标签下
*   **“文本实例”。tag_config()** 用于配置高亮、字体、背景色、前景色
*   **“文本实例”。tag_remove()** 用于删除从起始索引到结束索引使用的所有文本
*   **“入口姿态”。get()** 用于访问在输入对话框中输入的文本
*   **“文本实例”。search()** 用于在整个编辑器中搜索特定文本，从开始索引到结束，参数为“nocase ”,如果设置为 1，则表示搜索时不考虑大小写
*   **“按钮实例”。config()** 用于配置按钮，即我们可以单独添加命令或按钮被按下时发生的变化
*   **“TkInstance”。mainloop()** 用于确保文本小部件保持打开状态

下面是实现。

## 蟒蛇 3

```py
from tkinter import *

# to create a window
root = Tk()

# root window is the parent window
fram = Frame(root)

# Creating Label, Entry Box, Button
# and packing them adding label to
# search box
Label(fram, text ='Find').pack(side = LEFT)

# adding of single line text box
edit = Entry(fram)

# positioning of text box
edit.pack(side = LEFT, fill = BOTH, expand = 1)

# setting focus
edit.focus_set()

# adding of search button
Find = Button(fram, text ='Find')
Find.pack(side = LEFT)

Label(fram, text = "Replace With ").pack(side = LEFT)

edit2 = Entry(fram)
edit2.pack(side = LEFT, fill = BOTH, expand = 1)
edit2.focus_set()

replace = Button(fram, text = 'FindNReplace')
replace.pack(side = LEFT)

fram.pack(side = TOP)

# text box in root window
text = Text(root)

# text input area at index 1 in text window
text.insert('1.0', '''Type your text here''')
text.pack(side = BOTTOM)

# function to search string in text
def find():

    # remove tag 'found' from index 1 to END
    text.tag_remove('found', '1.0', END)

    # returns to widget currently in focus
    s = edit.get()

    if (s):
        idx = '1.0'
        while 1:
            # searches for desired string from index 1
            idx = text.search(s, idx, nocase = 1,
                            stopindex = END)

            if not idx: break

            # last index sum of current index and
            # length of text
            lastidx = '% s+% dc' % (idx, len(s))

            # overwrite 'Found' at idx
            text.tag_add('found', idx, lastidx)
            idx = lastidx

        # mark located string as red

        text.tag_config('found', foreground ='red')
    edit.focus_set()

def findNreplace():

    # remove tag 'found' from index 1 to END
    text.tag_remove('found', '1.0', END)

    # returns to widget currently in focus
    s = edit.get()
    r = edit2.get()

    if (s and r):
        idx = '1.0'
        while 1:
            # searches for desired string from index 1
            idx = text.search(s, idx, nocase = 1,
                            stopindex = END)
            print(idx)
            if not idx: break

            # last index sum of current index and
            # length of text
            lastidx = '% s+% dc' % (idx, len(s))

            text.delete(idx, lastidx)
            text.insert(idx, r)

            lastidx = '% s+% dc' % (idx, len(r))

            # overwrite 'Found' at idx
            text.tag_add('found', idx, lastidx)
            idx = lastidx

        # mark located string as red
        text.tag_config('found', foreground ='green', background = 'yellow')
    edit.focus_set()

Find.config(command = find)
replace.config(command = findNreplace)

# mainloop function calls the endless
# loop of the window, so the window will
# wait for any user interaction till we
# close it
root.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-418937-1" width="640" height="360" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/uploads/20200527182326/tkinter-find-and-replace.webm?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200527182326/tkinter-find-and-replace.webm](https://media.geeksforgeeks.org/wp-content/uploads/20200527182326/tkinter-find-and-replace.webm)</video>