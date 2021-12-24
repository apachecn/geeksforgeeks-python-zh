# Python 中如何将字符串转换为整数？

> 原文:[https://www . geesforgeks . org/如何在 python 中将字符串转换为整数/](https://www.geeksforgeeks.org/how-to-convert-string-to-integer-in-python/)

在 Python 中，可以使用以下方法将字符串转换为整数:

**方法 1:** **使用内置 int()函数:**

如果您的字符串包含一个十进制整数，并且您希望将其转换为 int，在这种情况下，将您的字符串传递给 int()函数，它会将您的字符串转换为等效的十进制整数。

> **语法:** int(字符串，基数)
> 
> **参数:**该函数取以下参数:
> 
> *   **字符串:**由 1、0 或十六进制、八进制数字等组成。
>     
> *   **基数:**(整数值)数字的基数。
> 
> **返回:**返回一个整数值，相当于给定基数的字符串的
> 。

**代码:**

## 蟒蛇 3

```py
# Initialising a string 
# with decimal value
string = "100"

# Show the Data type
print(type(string))

# Converting string into int
string_to_int = int(string)

# Show the Data type
print(type(string_to_int))
```

**输出:**

```py
<class 'str'>
<class 'int'>

```

默认情况下，int()期望字符串参数表示十进制整数。假设在任何情况下，您将一个十六进制字符串传递给 int()，那么它将显示 ValueError。在这种情况下，您可以指定字符串中数字的基数。

**代码:**

## 蟒蛇 3

```py
# Initialising a string
# with hexadecimal value
string = "0x12F"

# Show the Data type
print(type(string))

# Converting hexadecimal 
# string into int
string_to_int = int(string, 
                    base=16)
# Show the Data type
print(type(string_to_int))
```

**输出:**

```py
<class 'str'>
<class 'int'>

```

**方法二:使用自定义函数:**

我们还可以通过创建自己的用户定义函数将字符串转换为 int。

**进场:**

*   我们将检查这个数字是否有“-”符号，因为如果它是负数，它将包含“-”符号。如果它包含“-”符号，那么我们将从包含数字的第二个位置开始转换。
*   任何数字，假设 321，都可以写成这样的结构:10**2 * 3 + 10**1*2 + 10**0*1
*   类似地，我们使用**order(自变量)**order(' 0 ')将返回 48，order(' 1 ')返回 49，以此类推。
*   这里逻辑是顺序(' 1 ')–顺序(' 0) = 1，顺序(' 2 ')–顺序(' 0 ' = 2，依此类推，它给出了要从给定输入数字中提取的有效数字。
*   最后，我们从函数中得到的结果是一个整数，它是由给定的字符串转换而来的。

**代码:**

## 蟒蛇 3

```py
# User-defined function to 
# convert a string into integer
def string_to_int(input_string):

  output_int = 0

  # Check if the number contains
  # any minus sign or not, 
  # i.e. is it a negative number or not. 
  # If it contains in the first
  # position in a minus sign,
  # we start our conversion 
  # from the second position which
  # contains numbers.
  if input_string[0] == '-' :
    starting_idx = 1
    check_negative = True

  else:
    starting_idx = 0
    check_negative = False

  for i in range(starting_idx, len(input_string)):

    # calculate the place value for 
    # the respective digit
    place_value = 10**(len(input_string) - (i+1))

    # calculate digit value
    # ord() function gives Ascii value
    digit_value = ord(input_string[i]) - ord('0')

    # calculating the final integer value
    output_int += place_value * digit_value

  # if check_negative is true 
  # then final integer value 
  # is multiplied by -1
  if check_negative :
    return -1 * output_int
  else:
    return output_int

# Driver code
if __name__ == "__main__" : 

  string = "554"

  # function call
  x = string_to_int(string)

  # Show the Data type
  print(type(x))

  string = "123"

  # Show the Data type
  print(type(string_to_int(string))) 

  string = "-123"

  # Show the Data type
  print(type(string_to_int(string)))
```

**输出:**

```py
<class 'int'>
<class 'int'>
<class 'int'>

```