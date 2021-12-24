# Python–创建一个由给定字符串的前两个和后两个字符组成的字符串

> 原文:[https://www . geeksforgeeks . org/python-从给定字符串中创建由第一个和最后两个字符组成的字符串/](https://www.geeksforgeeks.org/python-create-a-string-made-of-the-first-and-last-two-characters-from-a-given-string/)

这里我们将看到由给定字符串的前 2 个和后 2 个字符组成字符串的方法。

```
Input: Geeksforgeeks
Output: Geks

Input: Hi, There
Output: Hire

```

**方法#1:** 使用[列表切片](https://www.geeksforgeeks.org/python-list-slicing/)

在本例中，我们将遍历字符串，并将字符串的长度存储在 count 变量中，然后在 count 变量的帮助下，通过获取前两个字符和后两个字符来创建新的子字符串。

## 计算机编程语言

```
# Taking input from the user
inputString = "Geeksforgeeks"

count = 0

# Loop through the string
for i in inputString:
      count = count + 1
newString = inputString[ 0:2 ] + inputString [count - 2: count ] 

# Printing the new String
print("Input string = " + inputString)
print("New String = "+ newString)
```

**输出:**

```
Input string = Geeksforgeeks
New String = Geks

```

**方法#2:** 使用循环

在这个例子中，我们将把字符串的长度存储在一个变量中，如果它的长度小于 4 个字符，就中断这个循环，否则，如果这个变量符合定义的条件，我们将存储这些字符，并从中生成一个新的字符串。

## 计算机编程语言

```
# Taking input from user
inputString = "Geeksforgeeks"

l = len(inputString)
newString = ""

# looping through the string
for i in range(0, len(inputString)):
    if l < 3:
        break
    else:
        if i in (0, 1, l-2, l-1):
            newString = newString + inputString[i]
        else:
            continue

# Printing New String
print("Input string : " + inputString)
print("New String : " + newString)
```

**输出:**

```
Input string : Geeksforgeeks
New String : Geks

```