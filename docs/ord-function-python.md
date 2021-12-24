# Python 中的 order()函数

> 原文:[https://www.geeksforgeeks.org/ord-function-python/](https://www.geeksforgeeks.org/ord-function-python/)

**Python order()函数**返回给定字符的 Unicode 代码。这个函数接受一串 单位长度作为参数，并返回传递参数的 Unicode 等价值。换句话说，给定长度为 1 的字符串，当参数是 Unicode 对象时，order()函数返回一个表示字符的 Unicode 代码点的整数，或者当参数是 8 位字符串时，返回字节的值。

### Python 顺序()语法:

> **语法:**阶(ch)

### python order()参数:

> ch–unicode 字符

### Python 顺序()示例

例如，order(' a ')返回整数 97，order('€')(欧元符号)返回 8364。这是 8 位字符串的 [chr()](https://www.geeksforgeeks.org/chr-in-python/) 和 Unicode 对象的 Unicode()的倒数。如果给定了一个 Unicode 参数，并且 Python 是用 UCS2 Unicode 构建的，那么字符的代码点必须在[0..65535]含。

**注意:**如果字符串长度超过一个，将引发类型错误。语法可以是 order(“a”)或 order(“a”)，两者将给出相同结果。

### **例 1:**Python order()函数的演示

## **计算机编程语言**

```py
# inbuilt function return an
# integer representing the Unicode code
value = ord("A")

# writing in ' ' gives the same result
value1 = ord('A')

# prints the unicode value
print (value, value1)
```

****输出:****

```py
65 65
```

### **示例 2: Python 顺序()错误条件**

**当字符串长度不等于 1 时，出现**类型错误**，如下所示:**

## **蟒蛇 3**

```py
# inbuilt function return an
# integer representing the Unicode code
# demonstrating exception

# Raises Exception
value1 = ord('AB')

# prints the unicode value
print(value1)
```

****输出:****

> **追溯(最近一次通话持续时间):**
> 
> **文件"/home/f 988 dfe 667 CDC 9 A8 e 5658464 c 87 CCD 18 . py "，第 6 行，in**
> 
> **值 1 =订单(' AB ')**
> 
> **类型错误:order()需要一个字符，但找到了长度为 2 的字符串**

## **python order()和 chr()函数**

**chr()方法返回一个字符串，该字符串表示 Unicode 代码点为整数的字符。**

> ****语法** : chr(num)**
> 
> **数字:整数值**

**其中 order()方法对 chr()函数起相反作用:**

### **order()和 chr()函数示例**

## **蟒蛇 3**

```py
# inbuilt function return an
# integer representing the Unicode code
value = ord("A")

# prints the unicode value
print (value)

# print the character
print(chr(value))
```

****输出:****

```py
65
A
```