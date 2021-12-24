# python 中的 fileinput.lineno()文件

> 原文:[https://www.geeksforgeeks.org/fileinput-lineno-in-python/](https://www.geeksforgeeks.org/fileinput-lineno-in-python/)

借助`**fileinput.lineno()**`方法，我们可以使用`fileinput.lineno()`方法获得从输入文件中读取的每一行的行号。

> **语法:** `fileinput.lineno()`
> 
> **返回:**返回行号。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`fileinput.lineno()`方法，我们能够通过使用该方法获得从给定文件中读取的每一行的行号。

输入文件–
![](img/e7034e25fe30e200e8ecdfede5b78620.png)

```
# import fileinput
import fileinput

# Using fileinput.lineno() method
for line in fileinput.input(files ='gfg.txt'):
    print('{}. '.format(fileinput.lineno()) + line)
```

**输出:**
![](img/12031b48adb920eccb5c70f89970092a.png)

**例 2 :**

输入文件–
![](img/e7034e25fe30e200e8ecdfede5b78620.png)
![](img/d98f03452927aa0a099f5712ecc2f727.png)

```
# import fileinput
import fileinput

# Using fileinput.lineno() method
for line in fileinput.input(files =('gfg.txt', 'gfg1.txt')):
    print('{}. '.format(fileinput.lineno()) + line)
```

**输出:**
![](img/8c11d72d5381bb7596cc77b78d0f2bbf.png)