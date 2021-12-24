# Python 中的 bin()

> 原文:[https://www.geeksforgeeks.org/bin-in-python/](https://www.geeksforgeeks.org/bin-in-python/)

**Python bin()函数**返回给定整数的二进制字符串。

> **语法:** bin(a)
> 
> **参数:a :** 要转换的整数
> 
> **返回值:**整数或 int 对象的二进制字符串。
> 
> **异常:**在参数中发送浮点值时引发类型错误。

## **Python bin()示例**

### 示例 1:使用 bin()方法将整数转换为二进制

## 蟒蛇 3

```
# Python code to demonstrate working of
# bin()

# declare variable
num = 100

# print binary number
print(bin(num))
```

**输出:**

```
0b1100100
```

### **示例 2:使用用户定义功能**将整数转换为二进制

## **蟒蛇 3**

```
# Python code to demonstrate working of
# bin()

# function returning binary string
def Binary(n):
    s = bin(n)

    # removing "0b" prefix
    s1 = s[2:]
    return s1

print("The binary representation of 100 (using bin()) is : ", end="")
print(Binary(100))
```

****输出:****

```
The binary representation of 100 (using bin()) is : 1100100
```

### **示例 3:使用 bin()和 __index()__**

**这里我们把类的对象发送到 bin 方法，使用的是 python 特殊方法 __index()__ 方法，总是返回正整数，如果值不是整数，就不能是上升误差。**

## **蟒蛇 3**

```
# Python code to demonstrate working of
# bin()
class number:
    num = 100

    def __index__(self):
        return(self.num)

print(bin(number()))
```

****输出:****

```
0b1100100
```

**本文由 [**【曼吉特·辛格】**](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。**

**如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**