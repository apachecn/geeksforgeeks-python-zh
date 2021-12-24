# Python 中的原位模块

> 原文:[https://www.geeksforgeeks.org/in_place-module-in-python/](https://www.geeksforgeeks.org/in_place-module-in-python/)

有时，在使用 Python 文件时，我们可以使用一个实用程序，在这个程序中，我们希望在不使用系统上下文或 sys stdout 的情况下更改文件。这种情况需要就地读/写文件，即不使用进程资源。这可以使用 Python 中的 ein_place 模块来实现。该模块–

*   不使用 sys.stdout，而是返回新的 filehandler 实例。
*   支持所有 filehandler 方法。
*   在异常情况下，原始文件被保留，有助于原子性。
*   创建临时文件不会影响其他打开的文件。

### **安装**

只需运行此命令来安装所需的模块

> pip 就地安装

现在要真正完成工作，请使用本模块的 in_place()方法。

> **语法:**
> 
> 原地。就地(文件名，模式=t，备份=无，备份 _ ext =无，延迟 _ 打开=假，移动 _ 优先=假)
> 
> **参数:**
> 
> **文件名:**要就地打开和编辑的文件的位置。
> **模式:**打开文件的模式。选项有字节(b)和文本(t)。如果它以字节为单位打开，则以字节为单位进行读写。在文本模式下，R & W 以字符串形式出现。默认为文本模式。
> **备份:**进程结束后保存原始文件的路径，以防保留原始文件的备份。
> **backup_ext :** 编辑前已创建原始文件的备份，名称为–filename+backup _ ext。
> **delay_open :** 如果设置为 True，它只会在调用 open()后打开文件，而默认情况下，它会在类启动后立即打开。
> **move_first :** 如果设置为 True，则输入文件被发送到临时位置，输出首先被就地编辑。默认情况下，此过程发生在调用 close()之后或过程结束时。

使用此功能，首先打开正在使用的文件，并对其执行所需的任务。下面给出了最简单的实现。

**例 1 :**

**输入:**

![](img/4cb9ee0a4c97c1bcd9be535164d149dd.png)

原始内容

## 蟒蛇 3

```py
import in_place

# using inplace() to perform same file edit.
with in_place.InPlace('gfg_inplace') as f:
    for line in f:

        # reversing cases while writing in file, inplace
        f.write(''.join(char.upper() if char.islower() else char.lower()
                        for char in line))
```

**输出:**

![](img/2c3990069a0d3049a23699d00d47588e.png)

代码执行后文件的输出。-改变案例。

也可以先将现有文件的数据备份到其他文件中，然后对文件进行所需的更改。为此，您要用来创建备份的文件名作为 backup 参数的值给出。

**例 2 :**

**输入:**

![](img/2c3990069a0d3049a23699d00d47588e.png)

代码执行后文件的输出。-改变案例。

## 蟒蛇 3

```py
import in_place

# using inplace() to perform same file edit.
# backs up original file in given path.
with in_place.InPlace('gfg_inplace', backup='origin_gfg_inplace') as f:
    for line in f:

        # reversing cases while writing in file, inplace
        f.write(''.join(char.upper() if char.islower() else char.lower()
                        for char in line))
```

**输出:**

![](img/2c3990069a0d3049a23699d00d47588e.png)

代码执行后，就地更改。

![](img/66d260a348d823e98f25bd9803312955.png)

原始内容的备份在新文件中创建。

上述方法的替代方法是使用 fo 关键字 **backup_ext。**到这个上只需要传递额外的单词来区分现有的文件。

**例 3:**

**输入:**

![](img/2c3990069a0d3049a23699d00d47588e.png)

## 蟒蛇 3

```py
import in_place

# using inplace() to perform same file edit.
# adds extension to file and creates backup
with in_place.InPlace('gfg_inplace', backup_ext='-original') as f:
    for line in f:

        # reversing cases while writing in file, inplace
        f.write(''.join(char.upper() if char.islower() else char.lower()
                        for char in line))
```

**输出:**

![](img/2c3990069a0d3049a23699d00d47588e.png)

代码执行后，就地更改。

![](img/5272eeaaf3c1d56d82804767c861d2e3.png)

创建了原始文件的备份，添加了给定的扩展名。