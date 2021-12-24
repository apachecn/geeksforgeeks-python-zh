# Python 中的 getpass()和 getuser()(无回声的密码)

> 原文:[https://www . geesforgeks . org/getpass-and-getuser-in-python-password-不带回声/](https://www.geeksforgeeks.org/getpass-and-getuser-in-python-password-without-echo/)

getpass()提示用户输入密码，而不进行回显。getpass 模块提供了一种安全的方式来处理密码提示，程序通过终端与用户进行交互。
该模块提供两个功能:

1.  get pass()

```
getpass.getpass(prompt='Password: ', stream=None) 
```

1.  getpass()函数用于使用字符串提示向用户进行提示，并将用户输入的内容读取为密码。输入读数默认为“密码:”并作为字符串返回给调用者。
    让我们通过一些例子来了解它的实现。
    **例 1:主叫方没有提示**

## 计算机编程语言

```
# A simple Python program to demonstrate
# getpass.getpass() to read password
import getpass

try:
    p = getpass.getpass()
except Exception as error:
    print('ERROR', error)
else:
    print('Password entered:', p)
```

1.  这里，呼叫者不提供提示。因此，它被设置为默认提示“密码”。
    **输出:**

```
$ python3 getpass_example1.py

Password: 
('Password entered:', 'aditi')
```

1.  **例 2:安全问题**
    有些程序为了更好的安全性，会询问安全问题，而不是询问密码。在这里，提示可以更改为任何值。

## 计算机编程语言

```
# A simple Python program to demonstrate
# getpass.getpass() to read security question
import getpass

p = getpass.getpass(prompt='Your favorite flower? ')

if p.lower() == 'rose':
    print('Welcome..!!!')
else:
    print('The answer entered by you is incorrect..!!!')
```

1.  **输出:**

```
$ python3 getpass_example2.py

Your favorite flower?
Welcome..!!!

$ python3 getpass_example2.py

Your favorite flower?
The answer entered by you is incorrect..!!!
```

1.  **getuser()**
    getpass。**getuser**()
    getuser()功能显示用户的登录名。该函数依次检查环境变量 LOGNAME、USER、LNAME 和 USERNAME，并返回第一个非空字符串的值。
    **例 3 :**

## 计算机编程语言

```
# Python program to demonstrate working of
# getpass.getuser()
import getpass

user = getpass.getuser()

while True:
    pwd = getpass.getpass("User Name : %s" % user)

    if pwd == 'abcd':
        print "Welcome!!!"
        break
    else:
        print "The password you entered is incorrect."
```

1.  **输出:**

```
$ python3 getpass_example3.py

User Name : bot
Welcome!!!

$ python3 getpass_example3.py

User Name : bot
The password you entered is incorrect.
```

本文由**阿迪提·古普塔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。