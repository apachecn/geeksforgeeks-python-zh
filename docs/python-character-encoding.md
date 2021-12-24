# Python |字符编码

> 原文:[https://www.geeksforgeeks.org/python-character-encoding/](https://www.geeksforgeeks.org/python-character-encoding/)

查找具有非标准字符编码的文本是文本处理中非常常见的步骤。
理想情况下，所有文本都应该来自 utf-8 或 ASCII 编码，但情况可能并非总是如此。因此，在编码未知的情况下，必须检测这种未编码的文本，并将其转换为标准编码。因此，在进一步处理文本之前，这一步很重要。
**字谜安装:**
为了执行编码的检测和转换，**字谜**–需要 Python 库。这个模块可以简单地使用 sudo easy_install 哑谜或 pip install 哑谜安装。
我们来看看哑谜模块周围的**包装函数。**
**代码:encoding.detect(字符串)，检测编码**

## 蟒蛇 3

```
# -*- coding: utf-8 -*-

import charade
def detect(s):

    try:
        # check it in the charade list
        if isinstance(s, str):
            return charade.detect(s.encode())
        # detecting the string
          else:
            return charade.detect(s)

    # in case of error
    # encode with 'utf -8' encoding
    except UnicodeDecodeError:
        return charade.detect(s.encode('utf-8'))
```

检测功能将返回 2 个属性:

```
Confidence : the probability of charade being correct.
Encoding   : which encoding it is. 
```

**代码:encoding.convert(字符串)转换编码。**

## 蟒蛇 3

```
# -*- coding: utf-8 -*-
import charade

def convert(s):

    # if in the charade instance
    if isinstance(s, str):
        s = s.encode()

    # retrieving the encoding information
    # from the detect() output
    encode = detect(s)['encoding']

    if encode == 'utf-8':
        return s.decode()
    else:
        return s.decode(encoding)
```

**代码:示例**

## 蟒蛇 3

```
# importing library
import encoding

d1  = encoding.detect('geek')
print ("d1 is encoded as  : ", d1)

d2  = encoding.detect('ascii')
print ("d2 is encoded as  : ", d2)
```

**输出:**

```
d1 is encoded as : (confidence': 0.505, 'encoding': 'utf-8')
d2 is encoded as : ('confidence': 1.0, 'encoding': 'ascii')
```

**detect() :** 这是一个哑谜. detect()包装器。它对字符串进行编码，并处理 UnicodeDecodeError 异常。它需要一个 bytes 对象，因此在尝试检测编码之前对字符串进行编码。
**convert() :** 这是个哑谜。它首先调用 detect()来获取编码。然后，它返回一个解码的字符串。