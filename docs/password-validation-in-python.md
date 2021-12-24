# Python 中的密码验证

> 原文:[https://www . geesforgeks . org/密码验证-python/](https://www.geeksforgeeks.org/password-validation-in-python/)

让我们将密码视为字母数字字符和特殊字符的组合，并借助几个条件来检查密码是否有效。

**有效密码的条件是:**

1.  应该至少有一个数字。
2.  应该至少有一个大写和一个小写字符。
3.  应该至少有一个特殊符号。
4.  长度应该在 6 到 20 个字符之间。

```
Input :  Geek12#
Output : Password is valid.

Input :  asd123
Output : Invalid Password !!
```

我们可以使用多种方法来检查给定的字符串是否适合作为密码。

**方法#1:** 朴素方法(不使用正则表达式)。

```
# Password validation in Python
# using naive method

# Function to validate the password
def password_check(passwd):

    SpecialSym =['{content}apos;, '@', '#', '%']
    val = True

    if len(passwd) < 6:
        print('length should be at least 6')
        val = False

    if len(passwd) > 20:
        print('length should be not be greater than 8')
        val = False

    if not any(char.isdigit() for char in passwd):
        print('Password should have at least one numeral')
        val = False

    if not any(char.isupper() for char in passwd):
        print('Password should have at least one uppercase letter')
        val = False

    if not any(char.islower() for char in passwd):
        print('Password should have at least one lowercase letter')
        val = False

    if not any(char in SpecialSym for char in passwd):
        print('Password should have at least one of the symbols $@#')
        val = False
    if val:
        return val

# Main method
def main():
    passwd = 'Geek12@'

    if (password_check(passwd)):
        print("Password is valid")
    else:
        print("Invalid Password !!")

# Driver Code        
if __name__ == '__main__':
    main()
```

**Output:**

```
Password is valid

```

这段代码使用布尔函数来检查是否满足所有条件。我们看到，虽然代码的复杂性是基本的，但长度是相当可观的。

**方法 2:** 使用[正则表达式](https://www.geeksforgeeks.org/pattern-matching-python-regex/)

regex 模块的`compile()`方法制作了一个 Regex 对象，使得在 *pat* 变量上执行 Regex 函数成为可能。然后我们检查由 *pat* 定义的模式后面是否跟有输入字符串 *passwd* 。如果是，搜索方法返回*真*，这将允许密码有效。

```
# importing re library
import re

def main():
    passwd = 'Geek12@'
    reg = "^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)(?=.*[@$!%*#?&])[A-Za-z\d@$!#%*?&]{6,20}{content}quot;

    # compiling regex
    pat = re.compile(reg)

    # searching regex                 
    mat = re.search(pat, passwd)

    # validating conditions
    if mat:
        print("Password is valid.")
    else:
        print("Password invalid !!")

# Driver Code     
if __name__ == '__main__':
    main()
```

**Output:**

```
Password is valid.

```