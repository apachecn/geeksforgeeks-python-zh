# 如何设置 Tkinter 入口小部件的默认文本？

> 原文:[https://www . geeksforgeeks . org/如何设置默认的 tkinter-entry-widget 文本/](https://www.geeksforgeeks.org/how-to-set-the-default-text-of-tkinter-entry-widget/)

Tkinter Entry 小部件没有任何可用于设置默认文本的文本属性。因此，必须使用以下方法将默认文本添加到 Tkinter 中的任何文本字段:

*   插入方法
*   stringvar 方法

**方法 1:使用插入法**

tkinter 模块已导入。根小部件被创建，这必须在创建任何其他小部件之前完成。根小部件的尺寸指定为 200×100。接下来，在根小部件上创建一个条目小部件“文本框”。在入口小部件上调用 insert()方法。insert()方法接受两个参数。第一个参数是字符串的位置，第二个参数是文本本身。由于默认情况下文本必须在条目小部件中，因此文本的位置被设置为 0。最后，在 Entry 小部件上调用 pack()方法，并将其放在根小部件上。root.mainloop()有助于运行应用程序。

**下面是实现:**

## 蟒蛇 3

```py
import tkinter as tk

root = tk.Tk()
root.geometry("200x100")

textBox = tk.Entry(root)
textBox.insert(0, "This is the default text")
textBox.pack()
root.mainloop()
```

**输出**

![](img/066ad81e256acc0a74173cc4aa4cf46d.png)

**方法二:使用 stringvar 方法**

将默认文本添加到 Tkinter 中的 Entry 小部件的第二种方法是 StringVar()方法。tkinter 模块已导入。根小部件被创建，这必须在创建任何其他小部件之前完成。根小部件的尺寸指定为 200×100。文本变量是一个字符串变量，其值被设置为默认文本。接下来，在根小部件上创建一个条目小部件“文本框”。入口小部件的文本变量属性被赋予文本变量的值。最后，在 Entry 小部件上调用 pack()方法，并将其放在根小部件上。root.mainloop()有助于运行应用程序。

**下面是实现:**

## 蟒蛇 3

```py
import tkinter as tk

root = tk.Tk()
root.geometry("200x100")

text = tk.StringVar()
text.set("This is the default text")
textBox = tk.Entry(root,textvariable = text)

textBox.pack()

root.mainloop()
```

**输出**

![](img/066ad81e256acc0a74173cc4aa4cf46d.png)