# Python–GTK+3 中的网格容器

> 原文:[https://www . geesforgeks . org/python-grid-container-in-GTK-3/](https://www.geeksforgeeks.org/python-grid-container-in-gtk-3/)

`Gtk.Grid`是一个容器，它以行和列的形式排列它的子小部件，而没有在构造函数中指定维度。使用`Gtk.Grid.attac` h()添加孩子。它们可以跨越多行或多列。

> **`Gtk.Grid.attach()`方法取五个参数:**
> 
> `child`:要添加的`Gtk.Widget`。
> 
> `left`:要附加到`child`左侧的列号。
> 
> `top`:表示`child`顶面要贴的行号。
> 
> `width`:表示`child`将要跨越的列数。
> 
> `height`:表示`child`将要跨越的行数。

使用`Gtk.Grid.attach_next_to()`也可以在现有孩子旁边添加一个孩子。

> **`Gtk.Grid.attach_next_to`方法取五个参数:**
> 
> `child` :Gtk。要添加的小部件。
> 
> `sibling`:一个`Gtk.Grid`或【无】的现有`child`小部件。子部件将放置在`sibling`旁边。
> 
> `side` : `Gtk.PositionType`表示兄弟姐妹的一方。
> 
> `width`:表示`child`小部件将要跨越的列数。
> 
> `height`:表示`child` 小部件将要跨越的行数

**遵循以下步骤:**

1.  导入 GTK+ 3 模块。
2.  创建主窗口。
3.  创建按钮。
4.  创建网格。

**注意:**在像 Pycharm 这样的 IDE 中，为了使用 GTK+ 3，我们可以安装一个名为 PyGObject 的包。

**Example :**

```py
import gi
# Since a system can have multiple versions
# of GTK + installed, we want to make 
# sure that we are importing GTK + 3.
gi.require_version("Gtk", "3.0")
from gi.repository import Gtk

class GridWin(Gtk.Window):
    def __init__(self):
        Gtk.Window.__init__(self, title ="GfG")

        grid = Gtk.Grid()
        self.add(grid)

        button1 = Gtk.Button(label ="Button 1")
        button2 = Gtk.Button(label ="Button 2")
        button3 = Gtk.Button(label ="Button 3")
        button4 = Gtk.Button(label ="Button 4")
        button5 = Gtk.Button(label ="Button 5")
        button6 = Gtk.Button(label ="Button 6")

        grid.add(button1)

        # With in parentheses child, left, top, width,
        # height respectively
        grid.attach(button2, 1, 0, 2, 1)

        # With in parentheses child, sibling, left, top, width,
        # height respectively 
        grid.attach_next_to(button3, button1, Gtk.PositionType.BOTTOM, 1, 2)
        grid.attach_next_to(button4, button3, Gtk.PositionType.RIGHT, 1, 1)
        grid.attach(button5, 1, 2, 1, 1)
        grid.attach_next_to(button6, button4, Gtk.PositionType.RIGHT, 1, 2)

win = GridWin()
win.connect("destroy", Gtk.main_quit)
win.show_all()
Gtk.main()
```

**输出:**
![](img/69270aadf7763d46373fa1a019411bd2.png)