# 在 Python 中制作自动模块安装程序

> 原文:[https://www . geesforgeks . org/making-automatic-module-installer-in-python/](https://www.geeksforgeeks.org/making-automatic-module-installer-in-python/)

**先决条件:**

*   [urllib](https://www.geeksforgeeks.org/python-urllib-module/)
*   [子流程](https://www.geeksforgeeks.org/python-subprocess-module-to-execute-programs-written-in-different-languages/)

很多时候，安装内置 Python 中尚未提供的模块的任务看起来令人沮丧。本文的重点是删除打开命令行界面的任务，并键入 pip install 模块名称来下载一些 python 模块。在本文中，我们将尝试自动化这个过程。

### **进场:**

*   使用 python 导入子流程模块来模拟命令行
*   正在导入 urllib.request 以实现互联网检查工具。
*   使用 Input()函数输入模块名并初始化 module_name 变量。
*   向主函数发送模块名称。
*   在主功能中，我们首先通过 python 直接更新我们的 pip 版本，以保证我们的应用程序的平稳运行。
*   在下一行 p = subprocess . run(' pip 3 install '+module _ name)中，我们将 pip3 install module_name 虚拟地写入命令行。
*   基于上述语句的返回代码(p)和 connect()函数的返回值的组合，我们可以假设下面提到的事情。

<figure class="table">

| **返回码(P)** | **连接功能** | **结果** |
| one | 错误的 | 互联网关闭 |
| one | 真实的 | 互联网已打开，但出现了一些其他问题 |
| Zero | 真实的 | 模块安装成功 |

</figure>

*   根据上表，我们可以给出所需的输出。

### 使用的功能:

**连接()**功能用于以下目的:

1.  检查互联网是开着还是关着。
2.  使用 urllib.request.urlopen(主机)命令到达特定的网址。
    *   如果成功到达，返回真
    *   否则，如果没有达到，即互联网关闭，返回假。

下面给出了使用上述方法实现我们的功能的实现。

**示例:**

## 蟒蛇 3

```
# importing subprocess module
import subprocess

# importing urllib.requests for internet checking functions
import urllib.request

# initializing host to gfg.
def connect(host='https://www.geeksforgeeks.org/'):

    # trying to open gfg
    try:
        urllib.request.urlopen(host)
        return True

    # trying to catch exception when internet is not ON.
    except:
        return False

def main(module_name):

    # updating pip to latest version
    subprocess.run('python -m pip install --upgrade pip')

    # commanding terminal to pip install
    p = subprocess.run('pip3 install '+module_name)

    # internet off
    if(p.returncode == 1 and connect() == False):
        print("error!! occurred check\nInternet connection")

    # Every thing worked fine
    elif(p.returncode == 0):
        print("It worked", module_name, " is installed")

    # Name of module wrong
    elif(p.returncode == 1 and connect() == True):
        print("error!! occured check\nName of module")

module_name = input("Enter the module name: ")
main(module_name)
```

**输出:**

## 蟒蛇 3

```
# importing subprocess module
import subprocess

# importing urllib.requests for internet checking functions
import urllib.request

# initializing host to gfg.
def connect(host='https://www.geeksforgeeks.org/'):

    # trying to open gfg
    try:
        urllib.request.urlopen(host)
        return True

    # trying to catch exception when internet is not ON.
    except:
        return False

def main(module_name):

    # updating pip to latest version
    subprocess.run('python -m pip install --upgrade pip')

    # commanding terminal to pip install
    p = subprocess.run('pip3 install '+module_name)

    # internet off
    if(p.returncode == 1 and connect() == False):
        print("error!! occurred check\nInternet connection")

    # Every thing worked fine
    elif(p.returncode == 0):
        print("It worked", module_name, " is installed")

    # Name of module wrong
    elif(p.returncode == 1 and connect() == True):
        print("error!! occurred check\nName of module")

module_name = input("Enter the module name: ")
main(module_name)
```