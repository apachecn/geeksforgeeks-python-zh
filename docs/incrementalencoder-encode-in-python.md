# Python 中的增量编码器编码()

> 原文:[https://www . geesforgeks . org/incrementalencoder-encode-in-python/](https://www.geeksforgeeks.org/incrementalencoder-encode-in-python/)

借助`**IncrementalEncoder.encode()**`方法，我们可以使用`IncrementalEncoder.encode()`方法将字符串编码成二进制形式。

> **语法:** `IncrementalEncoder.encode(string)`
> **返回:**返回编码后的字符串。
> 
> **注意:**如果你想用这个方法你应该有 python 3.8.2 版本或者最新版本。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`IncrementalEncoder.encode()`方法，我们能够使用该方法获得可以是二进制形式的编码字符串。

```
# import codecs and IncrementalEncoder
import codecs
from codecs import IncrementalEncoder

s = 'GeeksForGeeks'
obj = IncrementalEncoder()

# Using IncrementalEncoder.encode() method
gfg = obj.encode(s)

print(gfg)
```

**输出:**

> b'GeeksForGeeks

**例 2 :**

```
# import codecs and IncrementalEncoder
import codecs
from codecs import IncrementalEncoder

s = 'This is Python in real world'
obj = IncrementalEncoder()

# Using IncrementalEncoder.encode() method
gfg = obj.encode(s)

print(gfg)
```

**输出:**

> 我喜欢蟒蛇。'