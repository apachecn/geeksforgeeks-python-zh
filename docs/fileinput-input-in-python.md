# Python 中的 fileinput.input()

> 原文:[https://www.geeksforgeeks.org/fileinput-input-in-python/](https://www.geeksforgeeks.org/fileinput-input-in-python/)

借助`**fileinput.input()**`方法，我们可以获得文件作为输入，并且可以使用`fileinput.input()`方法来更新和追加文件中的数据。

> **语法:** `fileinput.input(files)`
> 
> **返回:**返回文件的数据。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`fileinput.input()`方法，我们能够使用该方法逐行获取文件的数据。

输入文件–
![](img/e7034e25fe30e200e8ecdfede5b78620.png)

```py
# import fileinput
import fileinput

# Using fileinput.input() method
for line in fileinput.input(files ='gfg.txt'):
    print(line)
```

**输出:**
![](img/f2ee36ef199340b0a55ab76f2d1fad44.png)

**例 2 :**

输入文件–
![](img/e7034e25fe30e200e8ecdfede5b78620.png)![](img/d98f03452927aa0a099f5712ecc2f727.png)

```py
# import fileinput
import fileinput

# Using fileinput.input() method
for line in fileinput.input(files =('gfg.txt', 'gfg1.txt')):
    print(line)
```

**输出:**
![](img/e815122962f9b3af6085eba0257a5875.png)