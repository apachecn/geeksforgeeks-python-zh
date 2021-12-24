# 使用 Python 生成强密码

> 原文:[https://www . geeksforgeeks . org/generating-strong-password-use-python/](https://www.geeksforgeeks.org/generating-strong-password-using-python/)

对于要求用户凭据高度保密和安全的系统来说，弱密码并不好。事实证明，人们发现很难编造出一个强有力的密码，足以防止未经授权的用户记住它。

本文使用计算机键盘上的数字、字母和其他符号的混合来形成一个 12 个字符的密码，该密码不可预测且不容易记忆。

*   密码的组成部分以数组的形式表示。
*   使用随机方法从每个字符数组中至少选择一个字符。
*   由于需要 12 个字符的密码，所以在剩余的密码长度中填入从最终密码所需的所有字符组合而成的数组中随机选择的字符。每当生成密码时，使用 random.shuffle()对密码进行洗牌，以确保最终密码不遵循特定模式。

## 蟒蛇 3

```
import random
import array

# maximum length of password needed
# this can be changed to suit your password length
MAX_LEN = 12

# declare arrays of the character that we need in out password
# Represented as chars to enable easy string concatenation
DIGITS = ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9']  
LOCASE_CHARACTERS = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 
                     'i', 'j', 'k', 'm', 'n', 'o', 'p', 'q',
                     'r', 's', 't', 'u', 'v', 'w', 'x', 'y',
                     'z']

UPCASE_CHARACTERS = ['A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 
                     'I', 'J', 'K', 'M', 'N', 'O', 'p', 'Q',
                     'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y',
                     'Z']

SYMBOLS = ['@', '#', '{content}apos;, '%', '=', ':', '?', '.', '/', '|', '~', '>', 
           '*', '(', ')', '<']

# combines all the character arrays above to form one array
COMBINED_LIST = DIGITS + UPCASE_CHARACTERS + LOCASE_CHARACTERS + SYMBOLS

# randomly select at least one character from each character set above
rand_digit = random.choice(DIGITS)
rand_upper = random.choice(UPCASE_CHARACTERS)
rand_lower = random.choice(LOCASE_CHARACTERS)
rand_symbol = random.choice(SYMBOLS)

# combine the character randomly selected above
# at this stage, the password contains only 4 characters but 
# we want a 12-character password
temp_pass = rand_digit + rand_upper + rand_lower + rand_symbol

# now that we are sure we have at least one character from each
# set of characters, we fill the rest of
# the password length by selecting randomly from the combined 
# list of character above.
for x in range(MAX_LEN - 4):
    temp_pass = temp_pass + random.choice(COMBINED_LIST)

    # convert temporary password into array and shuffle to 
    # prevent it from having a consistent pattern
    # where the beginning of the password is predictable
    temp_pass_list = array.array('u', temp_pass)
    random.shuffle(temp_pass_list)

# traverse the temporary password array and append the chars
# to form the password
password = ""
for x in temp_pass_list:
        password = password + x

# print out password
print(password)
```

**输出:**

```
yf2byU$@zTg5
```