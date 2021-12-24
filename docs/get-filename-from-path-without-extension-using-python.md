# 使用 Python 从不带扩展名的路径中获取文件名

> 原文:[https://www . geesforgeks . org/get-filename-from-path-不带扩展名-使用-python/](https://www.geeksforgeeks.org/get-filename-from-path-without-extension-using-python/)

使用路径从 Python 中获取文件名是一个复杂的过程，这不是因为我们需要使用正则表达式来将文件名与路径分开，而是因为在不同的操作系统中，文件路径中使用了不同类型的分隔符。例如，基于 UNIX 的系统，如 Linux 或 Mac Os，使用“/”(正斜杠)作为目录分隔符，而 Windows 使用“\”(反斜杠)分隔路径内的目录。因此，为了避免所有这些问题，我们将在 python ntpath 中使用一个内置包，并使用该包首先提取 basename(包含扩展名为的文件名的名称)。然后我们可以使用简单的 python 切片来找到不带扩展名的文件名。

### 逐步方法:

*   首先，我们将使用 **ntpath** 模块。其次，我们将从路径中提取文件的基本名称，并将其附加到一个单独的数组中。同样的代码是这样的。

## 蟒蛇 3

```
# import module
import ntpath

# used path style of both the UNIX
# and Windows os to show it works on both.
paths = [
    "E:\Programming Source Codes\Python\sample.py",
    "D:\home\Riot Games\VALORANT\live\VALORANT.exe"]

# empty array to store file basenames
filenames = []

for path in paths:
    # used basename method to get the filename
    filenames.append(ntpath.basename(path))
```

*   然后，我们将获取生成的数组，并找到最后一次出现的“.”字符串中的字符。记得只找到“.”的实例如果文件名本身包含“”，而不是最后一次出现，可能会产生问题。我们将使用 **rfind** 找到该索引，然后在索引之前对字符串的一部分进行切片以获得文件名。代码看起来像这样。同样，您可以将这些文件名存储在列表中，并在其他地方使用它们，但在这里，我们决定将它们简单地打印到屏幕上。

## 蟒蛇 3

```
# get names from the list
for name in filenames:

    # finding the index where 
    # the last "." occurs
    k = name.rfind(".")

    # printing the filename
    print(name[:k])
```

**下面是完整的程序:**

## 蟒蛇 3

```
# import module
import ntpath

# used path style of both the UNIX
# and Windows os to show it works on both.
paths = [
    "E:\Programming Source Codes\Python\sample.py",
    "D:\home\Riot Games\VALORANT\live\VALORANT.exe"]

# empty array to store file basenames
filenames = []

for path in paths:

    # used basename method to get the filename
    filenames.append(ntpath.basename(path))

# get names from the list
for name in filenames:

    # finding the index where 
    # the last "." occurs
    k = name.rfind(".")

    # printing the filename
    print(name[:k])
```

**输出:**

![](img/228e40382c6e1978709bdc453e07e4ac.png)