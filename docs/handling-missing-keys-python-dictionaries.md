# 处理 Python 字典中丢失的键

> 原文:[https://www . geesforgeks . org/handling-missing-key-python-dictionary/](https://www.geeksforgeeks.org/handling-missing-keys-python-dictionaries/)

在 python 中，[字典](https://www.geeksforgeeks.org/python-set-4-dictionary-keywords-python/)是将一个键映射到其值的容器，访问时间复杂度为 **O(1)** 。但是在许多应用程序中，用户并不知道字典中存在的所有键。在这种情况下，**如果用户试图访问丢失的钥匙，会弹出一个错误，指示丢失的钥匙**。

## 计算机编程语言

```
# Python code to demonstrate Dictionary and
# missing value error

# initializing Dictionary
d = { 'a' : 1 , 'b' : 2 }

# trying to output value of absent key
print ("The value associated with 'c' is : ")
print (d['c'])
```

**错误:**

```
Traceback (most recent call last):
  File "46a9aac96614587f5b794e451a8f4f5f.py", line 9, in 
    print (d['c'])
KeyError: 'c'
```

在上面的示例中，字典中没有名为“c”的键弹出运行时错误。为了避免这种情况，并让用户知道某个特定的键不存在或在该位置弹出默认消息，有几种方法来处理丢失的键。

### **方法 1:使用 get()**

**get(key，def_val)** 方法在我们必须检查密钥时很有用。如果键存在，则打印与该键关联的值，否则返回参数中传递的 def_value。

**示例:**

## 蟒蛇 3

```
country_code = {'India' : '0091',
                'Australia' : '0025',
                'Nepal' : '00977'}

# search dictionary for country code of India
print(country_code.get('India', 'Not Found'))

# search dictionary for country code of Japan
print(country_code.get('Japan', 'Not Found'))
```

**输出:**

```
0091
Not Found
```

### **方法 2:使用 setdefault()**

**setdefault(key，def_value)** 的工作方式与 get()类似，但不同的是，每次缺少一个**键时，都会创建一个新的键**，def_value 与参数中传递的键相关联。

**示例:**

## 蟒蛇 3

```
country_code = {'India' : '0091',
                'Australia' : '0025',
                'Nepal' : '00977'}

# Set a default value for Japan
country_code.setdefault('Japan', 'Not Present')

# search dictionary for country code of India
print(country_code['India'])

# search dictionary for country code of Japan
print(country_code['Japan'])
```

**输出:**

```
0091
Not Present
```

### **方法三:使用默认**

“ **defaultdict** ”是在名为“**集合**的模块中定义的容器。它以一个**函数(默认工厂)作为参数**。默认情况下，**默认工厂设置为“int”，即 0** 。如果**键不存在**为默认值，则**出厂默认值返回**并显示。它比 get()或 setdefault()有优势。

*   在**声明**处设置默认值。不需要**一次又一次的调用函数并传递相似的值作为参数。于是**节省了时间**。**
*   **defaultdict 的实现比 get()或 setdefault()快**。**** 

******示例:******

## ****计算机编程语言****

```
**# Python code to demonstrate defaultdict

# importing "collections" for defaultdict
import collections

# declaring defaultdict
# sets default value 'Key Not found' to absent keys
defd = collections.defaultdict(lambda : 'Key Not found')

# initializing values
defd['a'] = 1

# initializing values
defd['b'] = 2

# printing value
print ("The value associated with 'a' is : ",end="")
print (defd['a'])

# printing value associated with 'c'
print ("The value associated with 'c' is : ",end="")
print (defd['c'])**
```

******输出:****** 

```
**The value associated with 'a' is : 1
The value associated with 'c' is : Key Not found**
```

****本文由 [**【曼吉特·辛格】**](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。****