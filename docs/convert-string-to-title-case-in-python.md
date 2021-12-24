# 在 Python 中将字符串转换为标题大小写

> 原文:[https://www . geesforgeks . org/convert-string-to-title-in-python/](https://www.geeksforgeeks.org/convert-string-to-title-case-in-python/)

**标题格**是一种用于文章、书籍、电影等作品标题的文风。标题案例的写作规则是:

1)始终将第一个单词大写。
2)大写除以下词类以外的所有单词:

*   文章——一篇，一篇，一篇
*   协调连词——而且，但是，for，nor，or，所以，还没有
*   短介词–to、in、up、from 等

**示例:**

```
Input : The quick brown fox jumps over the lazy dog.
Output : The Quick Brown Fox Jumps over the Lazy Dog.

Input : A tale of two cities
Output : A Tale of Two Cities

```

**算法:**

1.  列出所有必须小写的单词。
2.  对于输入的每个单词，检查它是否在上面的列表中。
3.  如果是，则忽略该单词，如果否，则大写其第一个字符。

上述算法的实现是:

```
# Function to convert into title case
def generateTitleCase(input_string):

    # list of articles
    articles = ["a", "an", "the"]

    # list of coordinating conjunctins
    conjunctions = ["and", "but",
                    "for", "nor",
                    "or", "so",
                    "yet"]

    # list of some short articles
    prepositions = ["in", "to", "for", 
                    "with", "on", "at",
                    "from", "by", "about",
                    "as", "into", "like",
                    "through", "after", "over",
                    "between", "out", "against", 
                    "during", "without", "before",
                    "under", "around", "among",
                    "of"]

    # merging the 3 lists
    lower_case = articles + conjunctions + prepositions

    # variable declaration for the output text 
    output_string = ""

    # separating each word in the string
    input_list = input_string.split(" ")

    # checking each word
    for word in input_list:

        # if the word exists in the list
        # then no need to capitalize it
        if word in lower_case:
            output_string += word + " "

        # if the word does not exists in
        # the list, then capitalize it
        else:
            temp = word.title()
            output_string += temp + " "

    return output_string

# Driver code  
if __name__=='__main__':  
    input_text1 = "The quick brown fox jumps over the lazy dog."
    input_text2 = "A tale of two cities"

    print(generateTitleCase(input_text1)) 
    print(generateTitleCase(input_text2)) 
```

**输出:**

```
The Quick Brown Fox Jumps over the Lazy Dog. 
A Tale of Two Cities 
```