# Python 中映射函数和 Lambda 表达式替换字符

> 原文:[https://www . geesforgeks . org/map-function-lambda-expression-python-replace-characters/](https://www.geeksforgeeks.org/map-function-lambda-expression-python-replace-characters/)

给定字符串 S、c1 和 c2。用 c2 替换字符 c1，用 c1 替换 c2。
示例:

```
Input : str = 'grrksfoegrrks'
        c1 = e, c2 = r 
Output : geeksforgeeks 

Input : str = 'ratul'
        c1 = t, c2 = h 
Output : rahul

```

这个问题我们在 C++中已经有了解决方案，请参考[将字符串 S](https://www.geeksforgeeks.org/replace-character-c1-c2-c2-c1-string-s/) 链接中的字符 c1 替换为 c2，c2 替换为 c1。我们将在 Python 中使用 [Lambda 表达式](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)和 [map()](https://www.geeksforgeeks.org/sum-2d-array-python-using-map-function/) 函数快速解决这个问题。我们将创建一个**λ表达式**，其中字符串中的字符 c1 将被 c2 替换，c2 将被 c1 替换，其他将保持不变，然后我们将**将这个表达式映射到字符串的每个字符上，并将获得更新的字符串。**

```
# Function to replace a character c1 with c2 
# and c2 with c1 in a string S 

def replaceChars(input,c1,c2):

     # create lambda to replace c1 with c2, c2 
     # with c1 and other will remain same 
     # expression will be like "lambda x:
     # x if (x!=c1 and x!=c2) else c1 if (x==c2) else c2"
     # and map it onto each character of string
     newChars = map(lambda x: x if (x!=c1 and x!=c2) else \
                c1 if (x==c2) else c2,input)

     # now join each character without space
     # to print resultant string
     print (''.join(newChars))

# Driver program
if __name__ == "__main__":
    input = 'grrksfoegrrks'
    c1 = 'e'
    c2 = 'r'
    replaceChars(input,c1,c2)
```

输出:

```
geeksforgeeks

```