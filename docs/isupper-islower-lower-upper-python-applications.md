# Python 中的 isupper()，islower()，lower()，upper()及其应用

> 原文:[https://www . geeksforgeeks . org/I upper-is lower-lower-upper-python-applications/](https://www.geeksforgeeks.org/isupper-islower-lower-upper-python-applications/)

在本文中，我们将讨论 Python 中的 **isupper()、islower()、upper()和 lower()** 函数。这些方法是用于处理字符串的内置方法。在详细研究它们之前，让我们先了解一下这些函数的基本功能。

*   如果字符串的所有字符分别为大写或小写，函数 **isupper()** 和 **islower()将返回布尔值** True 值。
*   函数 **upper()** 和 **lower()通过将字符串的所有字符分别转换为大写或小写来返回字符串**

现在让我们详细讨论这些函数。

## isupper()

在 Python 中，isupper()是一种用于字符串处理的内置方法。如果字符串中的所有字符都是大写的，该方法返回 **True** ，否则返回“False”。
此函数用于检查参数是否包含任何大写字符，例如:

```py
ABCDEFGHIJKLMNOPQRSTUVWXYZ 
```

**语法:**

```py
string.isupper()

Parameters: 
isupper() does not take any parameters

Returns :

```

*   True-如果字符串中的所有字符都是大写的。
*   False-如果字符串包含 1 个或多个非大写字符。

示例:

```py
Input : string = 'GEEKSFORGEEKS'
Output : True

Input : string = 'GeeksforGeeks'
Output : False

```

**错误和异常**

1.  对于空白，它返回“真”，但是如果字符串中只有空白，则返回“假”。
2.  它不接受任何参数，因此，如果传递参数，它将返回一个错误。
3.  数字和符号返回“真”，但如果字符串只包含数字和数字，则返回“假”

```py
# Python code for implementation of isupper()

# checking for uppercase characters
string = 'GEEKSFORGEEKS'
print(string.isupper())

string = 'GeeksforGeeks'
print(string.isupper())
```

**输出:**

```py
True
False

```

## **岛电()**

在 Python 中，islower()是一种用于字符串处理的内置方法。如果字符串中的所有字符都是小写的，islower()方法返回 **True** ，否则返回“False”。
此函数用于检查参数是否包含任何小写字符，例如:

```py
abcdefghijklmnopqrstuvwxyz 
```

**语法:**

```py
string.islower()

Parameters:
islower() does not take any parameters
Returns :

```

*   如果字符串中的所有字符都较低，则为 True。
*   False-如果字符串包含 1 个或多个非小写字符。

示例:

```py
Input : string = 'geeksforgeeks'
Output : True

Input : string = 'GeeksforGeeks'
Output : False

```

**错误和异常**

1.  对于空白，它返回“真”，但是如果字符串中只有空白，则返回“假”。
2.  它不接受任何参数，因此，如果传递参数，它将返回一个错误。
3.  数字和符号返回“真”，但如果字符串只包含数字和数字，则返回“假”。

```py
# Python code for implementation of isupper()

# checking for lowercase characters
string = 'geeksforgeeks'
print(string.islower())

string = 'GeeksforGeeks'
print(string.islower())
```

**输出:**

```py
True
False

```

## **下降()**

在 Python 中，lower()是用于字符串处理的内置方法。lower()方法从给定的字符串中返回 lower 化的字符串。它将所有大写字符转换为小写字符。如果不存在大写字符，它将返回原始字符串。

**语法:**

```py
string.lower()

Parameters:
lower() does not take any parameters

Returns :
It converts the given string in into lowercase and returns the string.

```

示例:

```py
Input : string = 'GEEKSFORGEEKS'
Output : geeksforgeeks

Input : string = 'GeeksforGeeks'
Output : geeksforgeeks

```

**错误和异常**

1.  它不接受任何参数，因此，如果传递参数，它将返回一个错误。
2.  返回的数字和符号按原样返回，转换为小写后只返回大写字母。

```py
# Python code for implementation of lower()

# Checking for lowercase characters
string = 'GEEKSFORGEEKS'
print(string.lower())

string = 'GeeksforGeeks'
print(string.lower())
```

**输出:**

```py
geeksforgeeks
geeksforgeeks

```

## **上()**

在 Python 中，upper()是用于字符串处理的内置方法。upper()方法从给定的字符串中返回 uppercased 字符串。它将所有小写字符转换为大写字符。如果不存在小写字符，它将返回原始字符串。

**语法:**

```py
string.upper()

Parameters:
upper() does not take any parameters

Returns :
It converts the given string in into uppercase and returns the string.

```

示例:

```py
Input : string = 'geeksforgeeks'
Output : GEEKSFORGEEKS

Input : string = 'My name is ayush'
Output : MY NAME IS AYUSH

```

**错误和异常**

1.  它不接受任何参数，因此，如果传递参数，它将返回一个错误。
2.  返回的数字和符号按原样返回，转换为大写后只返回小写字母。

```py
# Python code for implementation of upper()

# checking for uppercase characters
string = 'geeksforgeeks'
print(string.upper())

string = 'My name is ayush'
print(string.upper())
```

**输出:**

```py
GEEKSFORGEEKS
MY NAME IS AYUSH

```

**应用:**给定一个字符串，任务是编写一个 Python 程序来统计字符串中大写字母、小写字母和空格的个数，并切换给定字符串的大小写(将小写转换为大写，反之亦然)。

**示例:**

```py
Input : string = 'GeeksforGeeks is a computer Science portal for Geeks'
Output : Uppercase - 4
         Lowercase - 41
         spaces - 7
         gEEKSFORGEEKS IS A COMPUTER sCIENCE PORTAL FOR gEEKS

Input : string = 'My name is Ayush'
Output : Uppercase - 2
         Lowercase - 11
         spaces - 3
         mY NAME IS aYUSH

```

**算法**

1.  逐个字符遍历给定的字符串直到其长度，使用内置方法检查字符是小写还是大写。
2.  如果小写，递增其各自的计数器，使用 upper()函数将其转换为大写并将其添加到新字符串中，如果大写，递增其各自的计数器，使用 lower()函数将其转换为小写并将其添加到新字符串中。
3.  如果是空格，则递增其相应的计数器，并将其添加到新字符串中
4.  打印新字符串。

下面是实现。

```py
# Python code for implementation of upper() 
# Given string and new string 

string ='GeeksforGeeks is a computer Science portal for Geeks'
newstring ='' 
count1 = 0
count2 = 0
count3 = 0

for a in string: 

    # Checking for lowercase letter and 
    # converting to uppercase. 
    if (a.isupper()) == True: 
        count1+= 1
        newstring+=(a.lower()) 

    # Checking for uppercase letter and
    # converting to lowercase. 
    elif (a.islower()) == True: 
        count2+= 1
        newstring+=(a.upper()) 

    # Checking for whitespace letter and
    # adding it to the new string as it is. 
    elif (a.isspace()) == True: 
        count3+= 1
        newstring+= a 

print("In original String : ") 
print("Uppercase -", count1) 
print("Lowercase -", count2) 
print("Spaces -", count3) 

print("After changing cases:") 
print(newstring) 
```

**输出:**

```py
In original String : 
Uppercase - 4
Lowercase - 41
Spaces - 7
After changing cases:
gEEKSFORgEEKS IS A COMPUTER sCIENCE PORTAL FOR gEEKS

```