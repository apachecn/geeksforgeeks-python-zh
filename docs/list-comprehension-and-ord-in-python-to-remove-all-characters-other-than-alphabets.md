# 在 Python 中列出理解和顺序()，删除除字母以外的所有字符

> 原文:[https://www . geeksforgeeks . org/list-理解并按 python 顺序删除字母以外的所有字符/](https://www.geeksforgeeks.org/list-comprehension-and-ord-in-python-to-remove-all-characters-other-than-alphabets/)

给定一个由字母和其他字符组成的字符串，删除除字母以外的所有字符，并打印如此形成的字符串。
示例:

```py
Input : str = "$Gee*k;s..fo, r'Ge^eks?"
Output : GeeksforGeeks

```

此问题已有解决方案，请参考[从字符串](https://www.geeksforgeeks.org/remove-characters-alphabets-string/)链接中删除除字母以外的所有字符。
我们将使用[列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)在 python 中快速解决这个问题。
**进场:**为

```py
1\. Traverse string 
2\. Select characters which lie in range of [a-z] or [A-Z]
3\. Print them together
```

**order()和 range()函数在 python 中是如何工作的？**

*   **order()**方法返回一个整数，代表给定 Unicode 字符的 Unicode 代码点。**例如

    ```py
     ord('5') = 53 and ord('A') = 65 and ord('{content}apos;) = 36
    ```** 
*   **范围(a，b，步长)**函数生成一个元素列表，其范围从 a(含)到 b(不含)，给定步长递增/递减。

```py
# Python code to remove all characters 
# other than alphabets from string 

def removeAll(input): 

    # Traverse complete string and separate 
    # all characters which lies between [a-z] or [A-Z] 
    sepChars = [char for char in input if
ord(char) in range(ord('a'),ord('z')+1,1) or ord(char) in
range(ord('A'),ord('Z')+1,1)] 

    # join all separated characters 
    # and print them together 
    return ''.join(sepChars) 

# Driver program 
if __name__ == "__main__": 
    input = "$Gee*k;s..fo, r'Ge^eks?"
    print (removeAll(input)) 
```

输出:

```py
GeeksforGeeks

```