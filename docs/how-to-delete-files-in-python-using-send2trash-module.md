# 如何使用 send2trash 模块删除 Python 中的文件？

> 原文:[https://www . geesforgeks . org/如何删除文件-在 python 中-使用-send 2 trach-module/](https://www.geeksforgeeks.org/how-to-delete-files-in-python-using-send2trash-module/)

在本文中，我们将看到如何使用 Python 中的 **send2trash** 模块安全删除文件和文件夹。使用*发送 2 个请求*，我们可以将文件发送到垃圾桶或回收站，而不是永久删除它们。[操作系统模块的](https://www.geeksforgeeks.org/os-module-python-examples/) [取消链接()](https://www.geeksforgeeks.org/python-os-unlink-method/)、[删除()](https://www.geeksforgeeks.org/python-os-remove-method/)和 [rmdir()](https://www.geeksforgeeks.org/python-os-rmdir-method/) 功能可用于删除文件或文件夹。但是，这些功能会永久删除文件。如果执行了任何意外删除，这些操作将无法撤消。这可以通过使用 **send2trash** 来防止。

#### **所需模块**

*   **OS:**Python 中的 OS 模块提供了与操作系统交互的功能。操作系统模块附带 Python 的标准库。
*   **send2trash :** Send2Trash 是一个小的包，它在所有平台上以本机方式将文件发送到废纸篓(或回收站)。要安装它，请在终端中键入以下命令。

```
pip install send2trash

```

## **删除文件或文件夹**

**send2trash()** 函数接受要删除的文件或文件夹的位置。

## 蟒 3

```
import send2trash

send2trash.send2trash("/location/to/file")
```