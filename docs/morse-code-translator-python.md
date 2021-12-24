# Python 中的莫尔斯电码翻译器

> 原文:[https://www.geeksforgeeks.org/morse-code-translator-python/](https://www.geeksforgeeks.org/morse-code-translator-python/)

[莫尔斯电码](https://www.geeksforgeeks.org/morse-code-implementation/)是一种通过一系列开关音、灯光或点击来传递文本信息的方法，熟练的听者或观察者无需特殊设备即可直接理解。它是以电报发明者塞缪尔·莫尔斯的名字命名的。

### **算法**

算法非常简单。英语中的每个字符都被一系列的“点”和“破折号”替代，或者有时只是单个的“点”或“破折号”，反之亦然。
详情请参考本维基百科[图片](https://en.wikipedia.org/wiki/Morse_code#/media/File:International_Morse_Code.svg)。

### **加密**

1.  在加密的情况下，我们一次从一个单词中提取每个字符(如果不是空格的话)，并将其与存储在我们选择的任何数据结构中的相应莫尔斯电码进行匹配(如果您使用 python 编码，字典在这种情况下会非常有用)
2.  将莫尔斯电码存储在一个包含编码字符串的变量中，然后在包含结果的字符串中添加一个空格。
3.  在用莫尔斯电码编码时，我们需要在每个字符之间加上 1 个空格，在每个单词之间加上 2 个连续的空格。
4.  如果字符是一个空格，那么在包含结果的变量中添加另一个空格。我们重复这个过程，直到遍历整个字符串

### **解密**

1.  在解密的情况下，我们从在要解码的字符串末尾添加一个空格开始(这将在后面解释)。
2.  现在我们继续从字符串中提取字符，直到没有任何空格。
3.  一旦我们得到一个空格，我们就在提取的字符序列(或我们的莫尔斯电码)中查找相应的英语字符，并将其添加到存储结果的变量中。
4.  请记住，跟踪空间是解密过程中最重要的部分。一旦我们得到 2 个连续的空格，我们将在包含解码字符串的变量中添加另一个空格。
5.  字符串末尾的最后一个空格将帮助我们识别莫尔斯电码字符的最后一个序列(因为空格用作提取字符并开始解码的检查)。

### **实施:**

Python 提供了一种称为[字典](https://www.geeksforgeeks.org/python-set-4-dictionary-keywords-python/)的数据结构，它以键值对的形式存储信息，这对于实现诸如莫尔斯码之类的密码非常方便。我们可以将莫尔斯电码图表保存在字典中，其中**(键值对)= >(英文字符-莫尔斯电码)**。明文(英文字符)代替密钥，密文(莫尔斯码)形成相应密钥的值。键的值可以从字典中访问，就像我们通过索引访问数组的值一样，反之亦然。

## 计算机编程语言

```
# Python program to implement Morse Code Translator

'''
VARIABLE KEY
'cipher' -> 'stores the morse translated form of the english string'
'decipher' -> 'stores the english translated form of the morse string'
'citext' -> 'stores morse code of a single character'
'i' -> 'keeps count of the spaces between morse characters'
'message' -> 'stores the string to be encoded or decoded'
'''

# Dictionary representing the morse code chart
MORSE_CODE_DICT = { 'A':'.-', 'B':'-...',
                    'C':'-.-.', 'D':'-..', 'E':'.',
                    'F':'..-.', 'G':'--.', 'H':'....',
                    'I':'..', 'J':'.---', 'K':'-.-',
                    'L':'.-..', 'M':'--', 'N':'-.',
                    'O':'---', 'P':'.--.', 'Q':'--.-',
                    'R':'.-.', 'S':'...', 'T':'-',
                    'U':'..-', 'V':'...-', 'W':'.--',
                    'X':'-..-', 'Y':'-.--', 'Z':'--..',
                    '1':'.----', '2':'..---', '3':'...--',
                    '4':'....-', '5':'.....', '6':'-....',
                    '7':'--...', '8':'---..', '9':'----.',
                    '0':'-----', ', ':'--..--', '.':'.-.-.-',
                    '?':'..--..', '/':'-..-.', '-':'-....-',
                    '(':'-.--.', ')':'-.--.-'}

# Function to encrypt the string
# according to the morse code chart
def encrypt(message):
    cipher = ''
    for letter in message:
        if letter != ' ':

            # Looks up the dictionary and adds the
            # correspponding morse code
            # along with a space to separate
            # morse codes for different characters
            cipher += MORSE_CODE_DICT[letter] + ' '
        else:
            # 1 space indicates different characters
            # and 2 indicates different words
            cipher += ' '

    return cipher

# Function to decrypt the string
# from morse to english
def decrypt(message):

    # extra space added at the end to access the
    # last morse code
    message += ' '

    decipher = ''
    citext = ''
    for letter in message:

        # checks for space
        if (letter != ' '):

            # counter to keep track of space
            i = 0

            # storing morse code of a single character
            citext += letter

        # in case of space
        else:
            # if i = 1 that indicates a new character
            i += 1

            # if i = 2 that indicates a new word
            if i == 2 :

                 # adding space to separate words
                decipher += ' '
            else:

                # accessing the keys using their values (reverse of encryption)
                decipher += list(MORSE_CODE_DICT.keys())[list(MORSE_CODE_DICT
                .values()).index(citext)]
                citext = ''

    return decipher

# Hard-coded driver function to run the program
def main():
    message = "GEEKS-FOR-GEEKS"
    result = encrypt(message.upper())
    print (result)

    message = "--. . . -.- ... -....- ..-. --- .-. -....- --. . . -.- ... "
    result = decrypt(message)
    print (result)

# Executes the main function
if __name__ == '__main__':
    main()
```

**输出:**

```
--. . . -.- ... -....- ..-. --- .-. -....- --. . . -.- ... 
GEEKS-FOR-GEEKS
```

本文由 [Palash Nigam](https://www.linkedin.com/in/palash25) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。