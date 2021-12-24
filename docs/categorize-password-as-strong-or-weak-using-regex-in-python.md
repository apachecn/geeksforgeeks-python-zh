# 使用 Python 中的正则表达式将密码分类为强或弱

> 原文:[https://www . geeksforgeeks . org/category-password-as-strong-or-weak-using-regex-in-python/](https://www.geeksforgeeks.org/categorize-password-as-strong-or-weak-using-regex-in-python/)

给定一个密码，我们必须将其分为强密码或弱密码。要成为强密码，需要满足一些检查。对于弱密码，我们需要返回它弱的原因。

**需要满足的条件是:**

*   最少 9 个字符，最多 20 个字符。
*   不能是换行符或空格
*   一行中不应有三个或更多重复字符。
*   同一字符串模式(最少两个字符长度)不应重复。

**注意:**要检查密码的基本验证，[请单击此处。](https://www.geeksforgeeks.org/password-validation-in-python/)

**示例:**

```
Input1 : Qggf!@ghf3
Output1 : Strong Password!

Input2 : aaabnil1gu
Output2 : Weak Password: Same character repeats three 
or more times in a row

Input3 : Geeksforgeeks
Output3 : Weak Password: Same character repeats three 
or more times in a row

Input4 : Aasd!feasnm
Output4 : Weak password: Same string pattern repetition

Input5 : 772*hdf77
Output5 : Weak password: Same string pattern repetition

Input6 : " "
Output6 : Password cannot be a newline or space!

```

下面是实现。

```
# Categorizing password as Strong or 
# Weak in Python using Regex 

import re

# Function to categorize password
def password(v):

    # the password should not be a
    # newline or space
    if v == "\n" or v == " ":
        return "Password cannot be a newline or space!"

    # the password length should be in
    # between 9 and 20
    if 9 <= len(v) <= 20:

        # checks for occurrence of a character 
        # three or more times in a row
        if re.search(r'(.)\1\1', v):
            return "Weak Password: Same character repeats three or more times in a row"

        # checks for occurrence of same string 
        # pattern( minimum of two character length)
        # repeating
        if re.search(r'(..)(.*?)\1', v):
            return "Weak password: Same string pattern repetition"

        else:
            return "Strong Password!"

    else:
        return "Password length must be 9-20 characters!"

# Main method
def main():

    # Driver code
    print(password("Qggf!@ghf3"))
    print(password("Gggksforgeeks"))
    print(password("aaabnil1gu"))
    print(password("Aasd!feasn"))
    print(password("772*hd897"))
    print(password(" "))

# Driver Code
if __name__ == '__main__':
    main()
```

**输出:**

> 强密码！
> 弱密码:相同字符串模式重复
> 弱密码:同一字符连续重复三次以上
> 强密码！
> 强密码！
> 密码不能是换行符或空格！