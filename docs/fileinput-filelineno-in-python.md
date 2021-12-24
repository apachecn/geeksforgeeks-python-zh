# python

中的 fileinput.filelineno()

> 原文:[https://www . geesforgeks . org/file input-filelineno-in-python/](https://www.geeksforgeeks.org/fileinput-filelineno-in-python/)

借助`**fileinput.filelineno()**`方法，我们可以通过使用`fileinput.filelineno()`方法从输入文件中获取每个文件在线读取的每一行的行号。

> **语法:** `fileinput.filelineno()`
> 
> **返回:**返回每个文件的行号。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`fileinput.filelineno()`方法，我们能够通过使用该方法从给定文件中获取每个文件的每行读取的行号。

输入文件–
![](img/e7034e25fe30e200e8ecdfede5b78620.png)

```py
# import fileinput
import fileinput

# Using fileinput.filelineno() method
for line in fileinput.input(files ='gfg.txt'):
    print('{}. '.format(fileinput.filelineno()) + line)
```

**输出:**
![](img/12031b48adb920eccb5c70f89970092a.png)

**例 2 :**

输入文件–
![](img/e7034e25fe30e200e8ecdfede5b78620.png)![](img/d98f03452927aa0a099f5712ecc2f727.png)

```py
# import fileinput
import fileinput

# Using fileinput.filelineno() method
for line in fileinput.input(files =('gfg.txt', 'gfg1.txt')):
    print('{}. '.format(fileinput.filelineno()) + line)
```

**输出:**
![](img/fa536cdcf4cbee0b7b14b07639c724b2.png)