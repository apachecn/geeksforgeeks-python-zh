# Python–创建一个以键作为第一个字符，以值作为以该字符开头的单词的字典

> 原文:[https://www . geeksforgeeks . org/python-以键作为第一字符，以值作为单词，以该字符开头创建字典/](https://www.geeksforgeeks.org/python-create-a-dictionary-with-key-as-first-character-and-value-as-words-starting-with-that-character/)

在本文中，我们将编写一个 python 程序来创建一个字典，其中键是第一个字符，值是从该字符开始的单词。

[Python 中的 Dictionary](https://www.geeksforgeeks.org/python-dictionary/) 是一个无序的数据值集合，用于像映射一样存储数据值，与其他只保存单个值作为元素的数据类型不同，Dictionary 保存的是键:值对。字典中提供了键值，以使其更加优化。

**示例:**

```py
Input: Hello World
Output: {'H': ['Hello'], 
         'W': ['World']}

Input: Welcome to GeeksForGeeks
Output: {'W': ['Welcome'], 
         't': ['to'], 
         'G': ['GeeksForGeeks']}

```

### 方法:

*   我们将字符串保存在一个变量中，并声明一个空的 [**字典**](https://www.geeksforgeeks.org/python-dictionary/) 。
*   然后我们将[](https://www.geeksforgeeks.org/python-string-split/)**的字符串拆分成单词，并形成这些单词的列表。**
*   **对于每个单词，我们将检查该单词的键是否存在。**
*   **如果不是，那么我们将把那个关键字和单词添加到字典中，如果它已经存在，那么我们将把那个单词附加到那个关键字的子列表中。**

****以下是上述方法的实现:****

## **蟒蛇 3**

```py
# Python program to Create a Dictionary with Key as First
# Character and Value as Words Starting with that Character

# Driver Code

# Declaring String Data
string_input = '''GeeksforGeeks is a Computer Science  portal for geeks.
       It contains well written, well thought and well explained
       computer science and programming articles, quizzes etc.'''

# Storing words in the input as a list
words = string_input.split()

# Declaring empty dictionary
dictionary = {}

for word in words:

    # If key is not present in the dictionary then we
    # will add the key and word to the dictionary.
    if (word[0] not in dictionary.keys()):

        # Creating a sublist to store words with same
        # key value and adding it to the list.
        dictionary[word[0]] = []
        dictionary[word[0]].append(word)

    # If key is present then checking for the word
    else:

        # If word is not present in the sublist then
        # adding it to the sublist of the proper key
        # value
        if (word not in dictionary[word[0]]):
            dictionary[word[0]].append(word)

# Printing the dictionary
print(dictionary)
```

****输出:****

```py
{'G': ['GeeksforGeeks'], 
 'i': ['is'], 
 'a': ['a', 'and', 'articles,'], 
 'C': ['Computer'],
 'S': ['Science'], 
 'p': ['portal', 'programming'], 
 'f': ['for'], 
 'g': ['geeks.'], 
 'I': ['It'], 
 'c': ['contains', 'computer'], 
 'w': ['well', 'written,'], 
 't': ['thought'],
 'e': ['explained', 'etc.'], 
 's': ['science'], 
 'q': ['quizzes']} 
```

**您可以看到，在上面程序的输出中，以 **G** 开头的单词有两个键“ **G** 和“ **g** ”，因此为了消除这个问题并使代码不区分大小写，我们将使用 python 中的 [**lower()函数**](https://www.geeksforgeeks.org/python-string-lower/) 。我们将用小写字母保存所有键，以便每当我们检查该键时，以“ **G** ”和“ **g** ”开头的单词都将出现在同一个键下。下面是实现:**

## **蟒蛇 3**

```py
# Python program to Create a Dictionary with Key as First
# Character and Value as Words Starting with that Character

# Driver Code

# Declaring String Data
string_input = '''GeeksforGeeks is a Computer Science  portal for geeks.
       It contains well written, well thought and well explained
       computer science and programming articles, quizzes etc.'''

# Storing words in the input as a list
words = string_input.split()

# Declaring empty dictionary
dictionary = {}

for word in words:

    # If key is not present in the dictionary then we
    # will add the key and word to the dictionary.
    if (word[0].lower() not in dictionary.keys()):

        # Creating a sublist to store words with same
        # key value and adding it to the list.
        dictionary[word[0].lower()] = []
        dictionary[word[0].lower()].append(word)

    # If key is present then checking for the word
    else:

        # If word is not present in the sublist then
        # adding it to the sublist of the proper key
        # value
        if (word not in dictionary[word[0].lower()]):
            dictionary[word[0].lower()].append(word)

# Printing the dictionary
print(dictionary)
```

****输出:****

```py
{'g': ['GeeksforGeeks', 'geeks.'],
 'i': ['is', 'It'],
 'a': ['a', 'and', 'articles,'], 
 'c': ['Computer', 'contains', 'computer'], 
 's': ['Science', 'science'], 
 'p': ['portal', 'programming'], 
 'f': ['for'], 
 'w': ['well', 'written,'], 
 't': ['thought'], 
 'e': ['explained', 'etc.'], 
 'q': ['quizzes']} 
```