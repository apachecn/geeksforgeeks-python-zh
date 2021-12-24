# 用 Python 进行道德黑客攻击

> 原文:[https://www.geeksforgeeks.org/ethical-hacking-with-python/](https://www.geeksforgeeks.org/ethical-hacking-with-python/)

作为一名加密世界的计算机科学工程师，应该知道黑客活动是如何进行的。我们必须挺身而出，保护我们的世界免受网络犯罪分子的侵害。

能够进入一个你不应该进入的系统被称为黑客攻击。例如，未经授权登录电子邮件帐户被视为黑客入侵该帐户。未经授权进入远程计算机就是入侵该计算机。所以你可以看到入侵一个系统有很多方法，黑客这个词可以指很多东西，但是主要概念是一样的。获得访问权或能够做你不应该做的事情，被认为是黑客行为。

**道德黑客:**
破解密码还是窃取数据？不，远不止如此。道德黑客是扫描漏洞，发现计算机或网络上的潜在威胁。道德黑客发现计算机、网络应用程序或网络中的弱点或漏洞，并将其报告给组织。所以，让我们一步一步地探索更多关于道德黑客的内容。

这些是各种[类型的黑客](https://www.geeksforgeeks.org/types-of-hackers/):

*   **黑帽黑客:**
    这里，组织不允许用户测试。他们不道德地进入网站，从管理面板窃取数据或操纵数据。他们只关注自己和他们将从个人数据中获得的优势，以获得个人财务收益。它们可以通过改变功能对公司造成重大损害，从而导致公司更大程度的损失。这甚至会给你带来极端的后果。

*   **白帽黑客:**
    在这里，我们寻找 bug，并按照伦理向组织报告。作为用户，我们有权测试网站或网络中的漏洞，并向他们报告。白帽黑客通常从组织本身获得所有需要测试的应用程序或网络的信息。他们利用自己的技能在网站上线或遭到恶意黑客攻击之前进行测试。

*   **3。灰帽黑客:**
    他们有时会获取数据并违反法律。但绝不会和黑帽黑客有同样的意图，他们往往是为了共同利益而行动。主要区别在于，他们公开利用漏洞，而白帽黑客则为公司私下利用漏洞。

**注意:**想了解更多黑客类型[点击这里](https://www.geeksforgeeks.org/types-of-hackers/)。

### 为什么 Python 编程适合黑客

Python 是一种广泛使用的通用高级编程语言。Python 是一种非常简单的语言，但也是一种强大的脚本语言，它是开源的，面向对象的，它有很好的库，既可以用于黑客攻击，也可以用于编写非常有用的普通程序，而不是黑客程序。在未来和现在的时代，python 非常流行，而且很容易学习，学习使用 python 进行黑客攻击将会很有趣，您将会以最好的方式学习 python 编程。市场上对 python 开发者的需求很大。
**注:**了解更多蟒蛇[点击此处](https://www.geeksforgeeks.org/python-programming-language/)。

### 密码是如何被黑的

每个人都知道，密码不是以纯文本形式存储在网站数据库中的。现在，我们将了解当您找到散列(md5)格式的密码时，如何破解纯文本密码。因此，我们获取 input_hash(数据库中的哈希密码)，并尝试将其与密码文件(pass_doc)中的每个纯文本密码的 md5 哈希进行比较，当哈希匹配时，我们只需显示密码文件(pass_doc)中的纯文本密码。如果密码不在输入密码文件中，它会说找不到密码，只有当缓冲区溢出没有发生时才会发生这种情况。这种类型的攻击可以被认为是字典攻击。

下面是实现。假设包含密码列表的文本文件是 password.txt。

## 蟒蛇 3

```
import hashlib
print("**************PASSWORD CRACKER ******************")

# To check if the password
# found or not.
pass_found = 0                                     

input_hash = input("Enter the hashed password:")

pass_doc = input("\nEnter passwords filename including path(root / home/):")

try:
    # trying to open the password file.
    pass_file = open(pass_doc, 'r')             
except:
    print("Error:")
    print(pass_doc, "is not found.\nPlease give the path of file correctly.")
    quit()

# comparing the input_hash with the hashes
# of the words in password file,
# and finding password.

for word in pass_file:
    # encoding the word into utf-8 format
    enc_word = word.encode('utf-8') 

    # Hashing a word into md5 hash
    hash_word = hashlib.md5(enc_word.strip())  

    # digesting that hash into a hexa decimal value    
    digest = hash_word.hexdigest()        

    if digest == input_hash:
        # comparing hashes
        print("Password found.\nThe password is:", word)  
        pass_found = 1
        break

# if password is not found.
if not pass_found:
    print("Password is not found in the", pass_doc, "file")  
    print('\n')
print("*****************  Thank you  **********************")
```

**输入:**

```
Enter the hashed password :  061a01a98f80f415b1431236b62bb10b 
Enter passwords filename including path(root/home/) : password.txt
```

**输出:**

```
Password found.
The password is : vivek 
```

**输入:**

```
Enter the hashed password :  aae039d6aa239cfc121357a825210fa3 
Enter passwords filename including path(root/home/) : password.txt
```

**输出**

```
Password found.
The password is : jessica 
```