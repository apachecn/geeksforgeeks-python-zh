# 使用 dfflib 模块比较 Python 中的序列

> 原文:[https://www . geesforgeks . org/compare-sequence-in-python-using-dfflib-module/](https://www.geeksforgeeks.org/compare-sequences-in-python-using-dfflib-module/)

*dfflib* Python 模块包含各种评估序列比较的特性，可以用来比较文件，可以创建不同格式的文件变体信息，包括 HTML 和上下文以及统一的 diffs。

它包含各种类来执行序列之间的各种比较:

### **级序列匹配器**

这是一个非常灵活的类，用于匹配任何种类的序列对。这个类包含下面讨论的各种函数:

*   这个类的 ***ratio()*** 方法返回传递的两个参数之间的相似比。相似比使用下面的公式确定。

> **2*X/Y**
> 
> 其中 X 是相似匹配的数量
> 
> y 是两个序列中存在的元素总数。

**例 1:**

## 蟒蛇 3

```py
# import required module
import difflib

# assign parameters
par1 = ['g', 'f', 'g']
par2 = 'gfg'

# compare
print(difflib.SequenceMatcher(None, par1, par2).ratio())
```

**输出:**

```py
1.0
```

**例 2:**

## 蟒蛇 3

```py
# import required module
import difflib

# assign parameters
par1 = 'Geeks for geeks!'
par2 = 'geeks'

# compare
print(difflib.SequenceMatcher(None, par1, par2).ratio())
```

**输出:**

```py
0.47619047619047616
```

**例 3:**

## 蟒蛇 3

```py
# import required module
import difflib

# assign parameters
par1 = 'gfg'
par2 = 'GFG'

# compare
print(difflib.SequenceMatcher(None, par1, par2).ratio())
```

**输出:**

```py
0.0
```

*   这个类的***get _ matching _ blocks()***方法返回描述匹配子序列的三元组列表。每个三元组都是(I，j，n)的形式，意味着 *a[i:i+n] == b[j:j+n]* 。

**例 1:**

## 蟒蛇 3

```py
# import required module
import difflib

# assign parameters
par1 = 'Geeks for geeks!'
par2 = 'geeks'

# compare
matches = difflib.SequenceMatcher(
    None, par1, par2).get_matching_blocks()

for ele in matches:
    print(par1[ele.a:ele.a + ele.size])
```

**输出:**

```py
geeks
```

**例 2:**

## 蟒蛇 3

```py
# import required module
import difflib

# assign parameters
par1 = 'GFG'
par2 = 'gfg'

# compare
matches = difflib.SequenceMatcher(
    None, par1, par2).get_matching_blocks()

for ele in matches:
    print(par1[ele.a:ele.a + ele.size])
```

**输出:**

由于 *GFG* 和 *gfg 之间没有匹配的子序列。*所以不显示输出。

*   ***get_close_matches()方法:*** 此方法返回最佳字符或字符组匹配列。术语是一个序列，其中需要紧密的相似性(通常是一个字符串)，可能性是一组匹配术语的序列(大部分是字符串列表)。

**示例:**

## 蟒蛇 3

```py
# import required module
import difflib

# assign parameters
string = "Geeks4geeks"
listOfStrings = ["for", "Gks", "G4g", "geeks"]

# find common strings
print(difflib.get_close_matches(string, listOfStrings))
```

**输出:**

```py
['geeks']
```

### **等级不同**

此类用于匹配文本行形式的序列，并创建人类可读的变体或增量。*差异*增量的每一行都以两个字母的代码开始:

<figure class="table">

| 密码 | 意义 |
| '- ' | 序列 1 的唯一行 |
| '+ ' | 序列 2 的唯一行 |
| ' ' | 两个序列共有的行 |
| '? ' | 在任一输入序列中都不存在行 |

</figure>

以下是该类中包含的函数:

*   这个类中的 ***比较()*** 方法，比较两个序列的线，并生成 delta(一个序列的线)。

**例 1:**

## 蟒蛇 3

```py
# import required module
from difflib import Differ

# assign parameters
par1 = 'Geeks'
par2 = 'geeks!'

# compare parameters
for ele in Differ().compare(par1, par2):
    print(ele)
```

**输出:**

```py
- G
+ g
  e
  e
  k
  s
+ !
```

**例 2:**

## 蟒蛇 3

```py
# import required module
from difflib import Differ

# assign parameters
par1 = ['Geeks','for','geeks!']
par2 = 'geeks!'

# compare parameters
for ele in Differ().compare(par1, par2):
    print(ele)
```

**输出:**

```py
- G
+ g
  e
  e
  k
  s
+ !
```

*   ***【ndiff()】方法:*** 上述类型的比较也可以使用该方法进行。然而、如果列表被通过，那么列表的元素首先被比较。

**例 1:**

## 蟒蛇 3

```py
# import required module
import difflib

# assign parameters
par1 = 'Geeks'
par2 = 'geeks!'

# compare parameters
for ele in difflib.ndiff(par1, par2):
    print(ele)
```

**输出:**

```py
- G
+ g
  e
  e
  k
  s
+ !
```

**例 2:**

## 蟒蛇 3

```py
# import required module
import difflib

# assign parameters
par1 = ['Geeks','for','geeks!']
par2 = 'geeks!'

# compare parameters
for ele in difflib.ndiff(par1, par2):
    print(ele)
```

**输出:**

```py
- Geeks
- for
- geeks!
+ g
+ e
+ e
+ k
+ s
+ !
```

*   ***context_diff()方法:*****Context diff 是一种方便的方法，只显示已经移动的行，带有几行上下文。从之前/之后的风格可以看出改进。背景行数设置为 n，默认设置为 3。**

****例 1:****

## **蟒蛇 3**

```py
# import required module
import difflib

# assign parameters
par1 = 'Geeks'
par2 = 'geeks!'

# compare parameters
for ele in difflib.context_diff(par1, par2):
    print(ele)
```

****输出:****

> *******
> 
> **—**
> 
> *******************
> 
> ***** 1,5 ******
> 
> **！G**
> 
> **e**
> 
> **e**
> 
> **k**
> 
> **s**
> 
> **— 1,6 —-**
> 
> **！g**
> 
> **e**
> 
> **e**
> 
> **k**
> 
> **s**
> 
> **+ !**

****例 2:****

## **蟒蛇 3**

```py
# import required module
import difflib

# assign parameters
par1 = ['Geeks', 'for', 'geeks!']
par2 = 'geeks!'

# compare parameters
for ele in difflib.context_diff(par1, par2):
    print(ele)
```

****输出:****

> *******
> 
> **—**
> 
>  *****************
> 
> *** 1,3 ****
> 
> ！奇葩
> 
> ！为
> 
> ！极客！
> 
> — 1,6 —-
> 
> ！g
> 
> ！e
> 
> ！e
> 
> ！k
> 
> ！s
> 
> ！！**