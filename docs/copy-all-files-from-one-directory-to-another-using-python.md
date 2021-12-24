# 使用 Python 将所有文件从一个目录复制到另一个目录

> 原文:[https://www . geeksforgeeks . org/使用 python 将所有文件从一个目录复制到另一个目录/](https://www.geeksforgeeks.org/copy-all-files-from-one-directory-to-another-using-python/)

在本文中，我们将讨论如何使用 Python 将所有文件从一个目录复制到另一个目录。

这可以使用 **shutil** 模块来完成。这个模块可以在 Python 中使用，对目录中的文件和文件夹执行操作。Shutil 包便于在目录之间访问、移动和删除文件。

### **方法 1:使用 shutil.copytree()**

**[**shutil . copy tree()**](https://www.geeksforgeeks.org/python-shutil-copytree-method/)方法递归地将一整棵以源(src)为根的目录树复制到目标目录。它用于递归地将文件从一个位置复制到另一个位置。目标不应是现有目录。它是在复制操作执行期间创建的。**

> ****语法:** shutil.copytree(src，dst，copy_function = copy2)**
> 
> ****参数:****
> 
> *   **src:源目录**
> *   **dst:目的地控制器**
> *   **copy_function(可选):默认值–copy 2()。也可以使用 copy()方法。**
> 
> ****返回:**新创建的目标目录名**

**Python 中还需要对操作系统包的扩展支持，以便有效地执行与文件操作相关的所有操作。它提供了许多功能来处理目录及其包含的相应文件和文件夹。**

**[**os.listdir(dir)**](https://www.geeksforgeeks.org/python-os-listdir-method/) ，列出指定目录下的所有文件，dir 和 os.path.join(a，b)用于通过分别连接子路径 a 后跟 b 来创建路径。**

****正在使用的目录:****

**![](img/99b4e16e94f7e03c72b4272533ea562e.png)**

## **蟒蛇 3**

```
import shutil
import os

# path to source directory
src_dir = 'fol1'

# path to destination directory
dest_dir = 'fol2'

# getting all the files in the source directory
files = os.listdir(src_dir)

shutil.copytree(src_dir, dest_dir)
```