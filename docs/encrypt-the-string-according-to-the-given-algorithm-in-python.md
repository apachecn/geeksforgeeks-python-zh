# 根据 Python 中给定的算法加密字符串

> 原文:[https://www . geesforgeks . org/根据 python 中给定的算法加密字符串/](https://www.geeksforgeeks.org/encrypt-the-string-according-to-the-given-algorithm-in-python/)

给定一个字符串 s，任务是以下列方式加密该字符串。让字符串为“苹果”。

*   **Step 1:** Invert the input: "elppa"
*   **Step 2:** Replace all vowels with the following chart:

```py
a => 0
e => 1
i => 2
o => 2
u => 3
Resultant string - "1lpp0"
```

*   **Step 3:** Add "ACA" at the end of the word.

```py
Resultant String: "1lpp0aca"
```

**例:**

```py
Input: banana
Output: 0n0n0baca"

Input: karaca
Output: 0c0r0kaca"

Input: burak
Output: k0r3baca
```

**进场:**

1.  创建一个存储值的字典，以便于访问。
2.  通过索引方法反转字符串。
3.  循环通过单词来替换元音。

下面是实现。

T2T4

```py
# Create an input field
encrypt = "banana"

# Create a dictionary to store keys
# and values
dict = {"a": "0", "e": "1",
        "i": "2", "o": "2",
        "u": "3"}

# Reverse the string
num = encrypt[::-1]

# Replace vowels using loops
for i in dict:
    num = num.replace(i, dict[i])

# f- strings which improves readability
print(f"{num}aca")
```

T5

**输出:**

```py
0n0n0baca
```

**我们来理解一下上面的代码:**

*   For the index, through a string, we have a specified three parameters. Indexing is done with integers (not floating-point values) and should be enclosed in square brackets.
*   The first parameter is the starting point, the second parameter is the substring jump, and the third parameter is the ending point.
*   Therefore, in the reverse string method above, we keep the first parameter blank, so the index will start from the first substring, and the second parameter is blank, so the substring will not be skipped, and the endpoint is -1, which will cause the compiler to manipulate and reverse the given input.