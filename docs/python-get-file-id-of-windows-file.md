# Python–获取 windows 文件的文件 id

> 原文:[https://www . geesforgeks . org/python-get-file-id-of-windows-file/](https://www.geeksforgeeks.org/python-get-file-id-of-windows-file/)

**文件标识**是在窗口上使用的唯一文件标识符，用于标识卷上的唯一文件。*文件标识*的工作原理类似于*nix 发行版中的索引节点号。使得文件标识可用于唯一地标识卷中的文件。
我们将使用在**窗口命令处理器**cmd.exe 中找到的命令来查找文件的文件 id。为了从 python 中访问/调用 cmd.exe，我们将使用*os 库中的 popen()函数。
os 库预装在大多数 python 发行版中。如果没有，可以通过在其操作系统的命令处理器中运行以下命令来安装库:

```py
pip install os
```

*不需要为了调用命令行而仅使用*OS 库。也可以使用替代方法来调用命令行(例如。subprocess.popen()也可以用于此目的)。
在本文中，我们将使用文件的路径来查询驱动器上文件的文件标识。然后稍后将使用这个文件标识来获取文件的绝对路径。* 

## *蟒蛇 3*

```py
*# importing popen from the os library
from os import popen

# Path to the file whose id we would
# be obtaining (relative / absolute)
file = r"C:\Users\Grandmaster\Desktop\testing.py"

# Running the command for obtaining the fileid,
# and saving the output of the command
output = popen(fr"fsutil file queryfileid {file}").read()

# printing the output of the previous command
print(output)*
```