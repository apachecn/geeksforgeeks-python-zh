# wx 中的 Python–find item()函数。菜单栏

> 原文:[https://www . geesforgeks . org/python-find item-function-in-wx-menu bar/](https://www.geeksforgeeks.org/python-finditem-function-in-wx-menubar/)

在本文中，我们将了解 wx 中的 FindItem 函数。wxPython 的菜单栏类。FindItem()只接受一个参数，即项目标识符。FindItem()查找与给定菜单项标识符相关联的菜单项对象。

> **语法:**
> 
> ```py
> wx.MenuBar.FindItem(self, id)
> 
> ```
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 身份证明（identification） | （同 Internationalorganizations）国际组织 | “项目标识符”菜单。 |

**示例:**

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
        print(menubar.FindItem(20))

def main():

    app = wx.App()
    ex = Example(None)
    ex.Show()
    app.MainLoop()

if __name__ == '__main__':
    main()
```

**输出:**

> (< wx。_ 核心。位于 0x7fd6797401f8 &rt;，< wx 的 MenuItem 对象。_ 核心。0x7fd67973d828 &rt;处的菜单对象)