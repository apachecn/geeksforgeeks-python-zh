# str .大写()VS str.title()

的区别

> 原文:[https://www . geesforgeks . org/difference-str-大写-vs-str-title/](https://www.geeksforgeeks.org/difference-between-str-capitalize-vs-str-title/)

[**title()**](https://www.geeksforgeeks.org/title-in-python/) 和 [**大写()**](https://www.geeksforgeeks.org/string-capitalize-python/) 具有相似的首字母大写功能。让我们看看他们两个的区别。

## 标题()

Python 中的 title()函数是 Python 字符串方法，用于将每个单词中的第一个字符转换为大写，并将字符串中的剩余字符转换为小写，并返回一个新字符串。

> **语法:** str.title()
> 
> **参数:**无
> 
> **返回:**这个函数返回一个字符串，其中每个单词的第一个字母是大写的，其余的字母都是小写的。

**示例:**

## 蟒蛇 3

```
# Python Title() Method Example

str1 = 'geeKs foR geEks'
str2 = str1.title()
print('First Output after Title() method is = ', str2)

# observe the original string
print('Converted String is = ', str1.title())
print('Original String is = ', str1)

# Performing title() function directly
str3 = 'ASIPU pawan kuMAr'.title()
print('Second Output after Title() method is = ', str3)

str4 = 'stutya kUMari sHAW'.title()
print('Third Output after Title() method is = ', str4)

str5 = '6041'.title()
print('Fourth Output after Title() method is = ', str5)
```

**输出:**

```
First Output after Title() method is =  Geeks For Geeks
Converted String is =  Geeks For Geeks
Original String is =  geeKs foR geEks
Second Output after Title() method is =  Asipu Pawan Kumar
Third Output after Title() method is =  Stutya Kumari Shaw
Fourth Output after Title() method is =  6041
```

## 大写()

在 Python 中，**大写()**方法将字符串的第一个字符转换为大写**(大写)**字母。如果字符串的第一个字符是大写的，那么它将返回原始字符串。

> **语法:** str .大写()
> 
> **参数:**无
> 
> **返回:**该函数返回一个字符串，该字符串的第一个字母为大写，其余所有字母为小写。

**示例:**

## 蟒蛇 3

```
# Python program to demonstrate the
# use of capitalize() function

# capitalize() first letter of
# string.
name = "geeks for geeks"

print(name.capitalize())

# demonstration of individual words
# capitalization to generate camel case
name1 = "geeks"
name2 = "for"
name3 = "geeks"
print(name1.capitalize() + name2.capitalize()
                         + name3.capitalize())
```

**输出:**

```
Geeks for geeks
GeeksForGeeks
```

### 标题()和大写()之间的区别

它们之间的区别在于 Python string 方法 title()返回一个字符串的副本，其中所有单词的第一个字符都是大写的，而 string 方法大写()返回一个字符串的副本，其中只有整个字符串的第一个单词是大写的。

**示例:**

```
str = "geeks for geeks"
str.title() will return Geeks For Geeks
str.capitalize() will return Geeks for geeks
```

## 蟒蛇 3

```
str1 = "my name is xyz"
str2 = "geeks for geeks"

# using title()
print(str1.title())
print(str2.title())

# using capitalize()
print(str1.capitalize())
print(str2.capitalize())
```

**输出:**

```
My Name Is Xyz
Geeks For Geeks
My name is xyz
Geeks for geeks
```