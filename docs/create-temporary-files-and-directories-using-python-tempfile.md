# 使用 Python-tempfile 创建临时文件和目录

> 原文:[https://www . geesforgeks . org/create-暂存-文件和目录-使用-python-tempfile/](https://www.geeksforgeeks.org/create-temporary-files-and-directories-using-python-tempfile/)

**Tempfile** 是一个用于处理临时文件的 Python 模块。当我们需要在程序执行过程中临时存储数据或处理大量数据时，可能需要临时文件。这些文件以唯一的名称创建，并存储在依赖于平台的默认位置。使用*临时文件*创建的文件一关闭就会被删除。

让我们看看如何创建和编辑这些文件:

### **创建临时文件**

使用**临时文件()**功能创建文件。默认情况下，文件以 *w+b* 模式打开，也就是说，我们可以对打开的文件进行读写操作。使用二进制模式，以便文件可以处理所有类型的数据。该文件在文件系统中可能没有正确的可见名称。

**示例:**

## 蟒蛇 3

```
import tempfile

temp = tempfile.TemporaryFile()
print(temp)
print(temp.name)
```

**输出:**

```
<_io.BufferedRandom name=7>
7
```

该函数返回一个类似文件的对象，可以用作临时存储区。**名称**属性用于获取文件的随机唯一名称。**注意**这不是一个实际可见的文件名，并且在文件系统中没有对该文件的引用。

### **创建命名临时文件**

**NamedTemporaryFile()** 函数创建文件的方式与 *TemporaryFile()* 相同，但在文件系统中有一个可见的名称。需要一个*删除*参数，我们可以设置为*假*来防止文件在关闭时被删除。

**示例:**

## 蟒蛇 3

```
import tempfile

temp = tempfile.NamedTemporaryFile()
```

## 蟒蛇 3

```
import tempfile

temp = tempfile.NamedTemporaryFile()
print(temp)
print(temp.name)
```

**输出:**

```
<tempfile._TemporaryFileWrapper object at 0x7f77d332f6d8>
/tmp/tmprumbbjz4
```

这也像以前一样返回一个类似对象的文件，唯一的区别是这次文件实际上有一个可见的名称。

### **为临时文件添加后缀和前缀**

通过指定参数“*后缀*和“*前缀*，我们可以选择在命名的临时文件的名称中添加**后缀**或**前缀**。

## 蟒蛇 3

```
import tempfile

temp = tempfile.NamedTemporaryFile(prefix='pre_', suffix='_suf')
print(temp.name)
```

**输出:**

```
/tmp/pre_ddur6hvr_suf
```

### **读写临时文件**

**write()** 方法用于写入临时文件。默认情况下，它将输入作为二进制数据。我们可以传递要作为输入写入的字符串，前面加一个“ *b* ，将其转换为二进制数据。write 函数返回写入的字符数。如果我们在文本模式 *(w+t)* 下打开文件，我们可以使用 **writelines()** 方法，该方法接受一个字符串参数。写入文件后，指针位于文件的末尾。因此，在我们能够读取内容之前，调用 **seek()** 方法将文件指针设置在文件的开始处。 *seek()* 将我们想要放置指针的字符的索引作为参数。然后使用 **read()** 功能读取内容。

**示例:**

## 蟒蛇 3

```
import tempfile

temp = tempfile.TemporaryFile()
temp.write(b'foo bar')
temp.seek(0)
print(temp.read())

temp.close()
```

**输出:**

```
b'foo bar'

```

### **创建临时目录**

像创建文件一样，我们也可以创建一个临时目录来存储我们的临时文件。**临时目录()**功能用于创建目录。处理完临时文件后，需要使用 *os.removedirs()*
手动删除目录

## 蟒蛇 3

```
import tempfile
import os

temp_dir = tempfile.TemporaryDirectory()
print(temp_dir)
```

**输出:**

```
<TemporaryDirectory '/tmp/tmpgjl5ki_5'>
```

### **保护临时文件和目录**

我们可以使用 **mkstemp()** 以安全的方式创建一个临时文件。通过此方法创建的文件只能由创建用户读取和写入。我们可以添加*前缀*和*后缀*参数，就像在*中一样。默认模式为二进制，但我们可以通过将“ *text* 参数设置为 *True* 在文本模式下打开。此文件在关闭时不会被删除。
**示例:***

## 蟒蛇 3

```
import tempfile

secure_temp = tempfile.mkstemp(prefix="pre_",suffix="_suf")
print(secure_temp)
```

**输出:**

```
(71, '/tmp/pre_i5us4u9j_suf')
```

同样，我们可以使用 **mkdtemp()** 方法创建一个安全的临时目录。

**示例:**

## 蟒蛇 3

```
import tempfile

secure_temp_dir = tempfile.mkdtemp(prefix="pre_",suffix="_suf")
print(secure_temp_dir)
```

**输出:**

```
/tmp/pre_9xmtwh4u_suf
```

### **临时文件的位置**

我们可以通过设置 **tempdir** 属性来设置文件的存储位置。可以使用 **gettempdir()** 方法获取位置。当我们创建一个临时文件或目录时，Python 会在一个标准的目录列表中进行搜索，以找到调用用户可以在其中创建文件的目录。

**优先顺序列表为:**

1.  由 *TMPDIR* 环境变量命名的目录。
2.  由 *TEMP* 环境变量命名的目录。
3.  由 *TMP* 环境变量命名的目录。
4.  平台特定的目录:
    *   在 Windows 上，目录 *C:\TEMP* 、 *C:\TMP* 、 *\TEMP* 、 *\TMP* 依次为。
    *   在所有其他平台上，目录 */tmp* 、 */var/tmp* 和 */usr/tmp* 依次为。
5.  当前工作目录。

**示例:**

## 蟒蛇 3

```
import tempfile

tempfile.tempdir = "/temp"
print(tempfile.gettempdir())
```

**输出:**

```
/temp

```