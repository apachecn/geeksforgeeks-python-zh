# Python | cmp()函数

> 原文:[https://www.geeksforgeeks.org/python-cmp-function/](https://www.geeksforgeeks.org/python-cmp-function/)

Python 2.x 中的 cmp()方法比较两个整数，根据比较结果返回-1、0、1。
cmp() **在 python 3.x** 中不起作用。你可能想看 Python 中的[列表比较](https://www.geeksforgeeks.org/python-2-number-cmplist-method/)。

```py
Syntax:
cmp(a, b)
Parameters:
a and b are the two numbers in which the comparison is being done. 
Returns:
-1 if a<b

0 if a=b

1 if a>b

```

```py
# Python program to demonstrate the 
# use of cmp() method

# when a<b
a = 1 
b = 2 
print(cmp(a, b))  

# when a = b 
a = 2
b = 2 
print(cmp(a, b))  

# when a>b 
a = 3
b = 2 
print(cmp(a, b))
```

**输出:**

```py
-1
0 
1

```

**实际应用:**使用 cmp 功能检查数字是偶数还是奇数的程序。

方法:比较 0 和 n%2，如果它返回 0，那么它是偶数，否则它是奇数。

下面是上述程序的 Python 实现:

```py
# Python program to check if a number is  
# odd or even using cmp function  

# check 12  
n = 12 
if cmp(0, n % 2):  
    print"odd"
else: 
    print"even" 

# check 13     
n = 13 
if cmp(0, n % 2):  
    print"odd"
else: 
    print"even" 
```

**输出:**

```py
even
odd

```