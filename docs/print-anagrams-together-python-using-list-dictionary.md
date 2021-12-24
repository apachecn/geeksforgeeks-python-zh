# 使用列表和字典一起打印 Python 中的字谜

> 原文:[https://www . geesforgeks . org/print-anagrams-together-python-use-list-dictionary/](https://www.geeksforgeeks.org/print-anagrams-together-python-using-list-dictionary/)

给定一组单词，把所有的字谜打印在一起？

示例:

```py
Input : arr = ['cat', 'dog', 'tac', 'god', 'act']
Output : 'cat tac act dog god'

```

此问题已有解决方案请参考[字谜](https://www.geeksforgeeks.org/check-whether-two-strings-are-anagram-of-each-other/)和[给定一个单词序列，将所有字谜打印在一起](https://www.geeksforgeeks.org/given-a-sequence-of-words-print-all-anagrams-together/)链接。我们将使用[列表](https://www.geeksforgeeks.org/python-set-3-strings-lists-tuples-iterations/)和[字典](https://www.youtube.com/watch?v=z7z_e5-l2yE&t=28s)数据结构在 python 中解决这个问题。方法很简单:

*   遍历字符串列表。
*   将每个字符串按升序排序，并将该排序值视为**键**，将原始值视为对应键的**值**。检查关键字在字典中是否不存在，这意味着它是第一次出现，
    因此将一个空列表映射到**关键字**并在其中追加值，如果关键字已经存在，则简单地追加值。
*   现在每一个键都将包含一个字符串列表，这些字符串是一个字谜。

```py
# Function to return all anagrams together 
def allAnagram(input): 

    # empty dictionary which holds subsets 
    # of all anagrams together 
    dict = {} 

    # traverse list of strings 
    for strVal in input: 

        # sorted(iterable) method accepts any 
        # iterable and rerturns list of items 
        # in ascending order 
        key = ''.join(sorted(strVal)) 

        # now check if key exist in dictionary 
        # or not. If yes then simply append the 
        # strVal into the list of it's corresponding 
        # key. If not then map empty list onto 
        # key and then start appending values 
        if key in dict.keys(): 
            dict[key].append(strVal) 
        else: 
            dict[key] = [] 
            dict[key].append(strVal) 

    # traverse dictionary and concatenate values 
    # of keys together 
    output = "" 
    for key,value in dict.items(): 
        output = output + ' '.join(value) + ' '

    return output 

# Driver function 
if __name__ == "__main__": 
    input=['cat', 'dog', 'tac', 'god', 'act'] 
    print (allAnagram(input)) 
```

输出:

```py
'cat tac act dog god'

```

本文由 [**沙莎克·米什拉(古卢)**](https://auth.geeksforgeeks.org/profile.php?user=Shashank Mishra) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。