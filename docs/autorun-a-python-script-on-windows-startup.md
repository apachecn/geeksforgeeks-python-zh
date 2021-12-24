# 在 windows 启动时自动运行 Python 脚本

> 原文:[https://www . geesforgeks . org/autorun-a-python-script-on-windows-startup/](https://www.geeksforgeeks.org/autorun-a-python-script-on-windows-startup/)

向 windows 启动中添加 python 脚本基本上意味着 Python 脚本将在 windows 启动时运行。这可以通过两步过程来完成–

**步骤#1:将脚本添加到 windows 启动文件夹**
在 windows 启动后，它会运行(相当于双击)其启动目录中的所有应用程序。

**地址:**

> c:\ user \ current _ user \ AppData \漫游\ Microsoft \ Windows \开始菜单\程序\启动\

默认情况下 *current_user* 下的 AppData 文件夹是隐藏的，所以启用隐藏文件来获取它，并将脚本的快捷方式粘贴到给定的地址或脚本本身。也该**了。PY** 文件默认必须设置为 python IDE，否则脚本可能会以文本形式打开而不是执行。

**第二步:向 windows 注册表添加脚本**
这个过程如果做得不好可能会有风险，它涉及到从 python 脚本本身编辑 windows 注册表项 *HKEY_CURRENT_USER* 。该注册表包含用户登录后必须运行的程序列表。就像很少有应用程序会在 windows 启动时弹出一样，因为它会导致注册表发生变化，并将应用程序路径添加到注册表中。

**注册表路径:**

> HKEY _ 当前 _ 用户\软件\微软\视窗\当前版本\运行

下面是 Python 代码:

## 蟒蛇 3

```py
# Python code to add current script to the registry

# module to edit the windows registry
import winreg as reg
import os            

def AddToRegistry():

    # in python __file__ is the instant of
    # file path where it was executed
    # so if it was executed from desktop,
    # then __file__ will be
    # c:\users\current_user\desktop
    pth = os.path.dirname(os.path.realpath(__file__))

    # name of the python file with extension
    s_name="mYscript.py"    

    # joins the file name to end of path address
    address=os.join(pth,s_name)

    # key we want to change is HKEY_CURRENT_USER
    # key value is Software\Microsoft\Windows\CurrentVersion\Run
    key = HKEY_CURRENT_USER
    key_value = "Software\Microsoft\Windows\CurrentVersion\Run"

    # open the key to make changes to
    open = reg.OpenKey(key,key_value,0,reg.KEY_ALL_ACCESS)

    # modify the opened key
    reg.SetValueEx(open,"any_name",0,reg.REG_SZ,address)

    # now close the opened key
    reg.CloseKey(open)

# Driver Code
if __name__=="__main__":
    AddToRegistry()
```

**注意:**对于每次启动时要执行的任务，可以在该脚本中添加更多代码，并且该脚本必须是**首次以管理员身份运行**。