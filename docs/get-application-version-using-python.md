# 使用 Python 获取应用程序版本

> 原文:[https://www . geesforgeks . org/get-application-version-use-python/](https://www.geeksforgeeks.org/get-application-version-using-python/)

软件版本化可能得益于推理 pc 软件包的独特状态，因为它是开发和卸载的。版本符号通常是一个单词、一个数字或两者兼有。例如，1.0 版本通常用来表示程序最初的不安全性。在本文中，我们将看到如何使用 Python 获取应用程序版本号。

**方法 1:** 这里将使用 **win32api** 模块。

微软视窗的 Python 扩展提供了对许多 Win32 应用编程接口的访问，制作和使用 COM 对象的灵活性，以及 Pythonwin 氛围。

在开始之前，我们需要安装模块

```py
pip install pywin32
```

**这里我们将使用这些方法:**

*   **GetFileVersionInfo:** 此方法用于检索给定文件的版本信息

```py
GetFileVersionInfo(File Path, SubBlock, **attr)
```

*   **LOWORD:**win 32 API LOWORD 宏的接口。值是整数数据类型

```py
LOWORD(val)
```

*   **HIWORD:**win 32 API HIWORD 宏的接口。值是整数数据类型

```py
HIWORD(val)
```

**进场:**

*   首先，我们将使用 GetFileVersionInfo()方法解析文件信息。
*   文件信息是字典的形式，我们将获取两个信息，一个是 msfileversion，另一个是 lsfileversion

**下面是实现:**

## 蟒蛇 3

```py
# Import Module
from win32api import *

def get_version_number(file_path):

    File_information = GetFileVersionInfo(file_path, "\\")

    ms_file_version = File_information['FileVersionMS']
    ls_file_version = File_information['FileVersionLS']

    return [str(HIWORD(ms_file_version)), str(LOWORD(ms_file_version)),
            str(HIWORD(ls_file_version)), str(LOWORD(ls_file_version))]

file_path = r'C:\Program Files (x86)\Google\Chrome\Application\chrome.exe'

version = ".".join(get_version_number(file_path))

print(version)
```

**输出:**

```py
88.0.4324.104
```

**方法二:**使用 [win32com](https://www.geeksforgeeks.org/convert-text-speech-python-using-win32com-client/)

这里将使用 win32com 模块。在开始之前，我们需要安装模块

```py
pip install pypiwin32
```

**进场:**

*   我们将创建一个信息解析器，它将使用 Dispatch()方法解析所需的信息。
*   然后我们将使用 GetFileVersion()方法获取文件版本。

**下面是实现:**

## 蟒蛇 3

```py
# Import Module
from win32com.client import *

def get_version_number(file_path):

    information_parser = Dispatch("Scripting.FileSystemObject")
    version = information_parser.GetFileVersion(file_path)
    return version

file_path = r'C:\Program Files (x86)\Google\Chrome\Application\chrome.exe'
version = get_version_number(file_path)

print(version)
```

**输出:**

```py
88.0.4324.104
```