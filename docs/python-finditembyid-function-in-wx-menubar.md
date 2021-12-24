# Python–wx 中的 FindItemById()函数。菜单栏

> 原文:[https://www . geesforgeks . org/python-finditembyid-function-in-wx-menu bar/](https://www.geeksforgeeks.org/python-finditembyid-function-in-wx-menubar/)

在本文中，我们将了解 wx 中的 FindItemById()对象。wxPython 的菜单栏类。函数的作用是:返回一个 wx。MenuItem 对象元组。它只接受一个参数，即其中 wx 的 menuitem 的 id。我们需要的菜单项对象。

> **语法:**
> 
> ```py
> wx.MenuBar.FindItemById(self, id)
> 
> ```
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 身份证明（identification） | （同 Internationalorganizations）国际组织 | “项目标识符”菜单。 |
> 
> **返回类型:**
> 
> ```py
> wx.MenuItem
> 
> ```

**代码示例:**

```py
import wx

class Example(wx.Frame):

    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)

        self.InitUI()

    def InitUI(self):
        # create MenuBar using MenuBar() function
        menubar = wx.MenuBar()
        # add menu to MenuBar
        fileMenu = wx.Menu()
        # add submenu item
        fileItem = fileMenu.Append(20, 'SubMenu')
        menubar.Append(fileMenu, '&Menu# 1')
        self.SetMenuBar(menubar)
        self.SetSize((300, 200))
        self.SetTitle('Menu Bar')
        # get wx.MenuItem object
        menuitem = menubar.FindItemById(20)
        # print wx.MenuItem object tuple id = 20
        print(menuitem)
        # print label of menuitem
        print(menuitem.GetLabel())

def main():

    app = wx.App()
    ex = Example(None)
    ex.Show()
    app.MainLoop()

if __name__ == '__main__':
    main()
```

**输出:**

```py
<wx._core.MenuItem object at 0x7fe3009a5288&rt;
SubMenu

```