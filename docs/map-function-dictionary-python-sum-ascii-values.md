# 将 Python 中的函数和字典映射到 ASCII 值的总和

> 原文:[https://www . geesforgeks . org/map-function-dictionary-python-sum-ascii-values/](https://www.geeksforgeeks.org/map-function-dictionary-python-sum-ascii-values/)

给我们一个英语语言的句子(也可以包含数字)，我们需要计算并打印该句子中每个单词的字符的 ASCII 值之和。

示例:

```
Input :  GeeksforGeeks, a computer science portal
         for geeks
Output : Sentence representation as sum of ASCII 
         each character in a word:
         1361 97 879 730 658 327 527 
         Total sum -> 4579
Here, [GeeksforGeeks, ] -> 1361, [a] -> 97, [computer] 
-> 879, [science] -> 730 [portal] -> 658, [for] 
-> 327, [geeks] -> 527 

Input : I am a geek
Output : Sum of ASCII values:
         73 206 97 412 
         Total sum -> 788

```

此问题已有解决方案请参考[句子中每个单词的 ASCII 值总和](https://www.geeksforgeeks.org/sums-of-ascii-values-of-each-word-in-a-sentence/)链接。我们将使用[地图()](https://www.geeksforgeeks.org/sum-2d-array-python-using-map-function/)函数和[字典](https://www.youtube.com/watch?v=z7z_e5-l2yE&t=35s)数据结构在 python 中快速解决这个问题。方法很简单，

1.  首先将句子中的所有单词用空格分开。
2.  创建一个空字典，其中包含单词作为关键字，字符的 ASCII 值之和作为值。
3.  现在遍历拆分单词列表，并为每个单词映射当前单词每个字符的[order(chr)](https://www.geeksforgeeks.org/ord-function-python/)函数，并计算当前单词每个字符的 ascii 值之和。
4.  当遍历每个单词时，将 ascii 值的总和映射到上面创建的结果字典中相应的单词上。
5.  遍历拆分后的单词列表，并通过查找结果字典来打印它们相应的 ascii 值。

    ```
    # Function to find sums of ASCII values of each 
    # word in a sentence in

    def asciiSums(sentence):

        # split words separated by space
        words = sentence.split(' ')

        # create empty dictionary
        result = {}

        # calculate sum of ascii values of each word
        for word in words:
             currentSum = sum(map(ord,word))

             # map sum and word into resultant dictionary
             result[word] = currentSum

        totalSum = 0

        # iterate list of splited words in order to print
        # sum of ascii values of each word sequentially
        sumsOfAscii = [result[word] for word in words]
        print ('Sum of ASCII values:')
        print (' '.join(map(str,sumsOfAscii)))
        print ('Total Sum -> ',sum(sumsOfAscii))

    # Driver program
    if __name__ == "__main__":
        sentence = 'I am a geek'
        asciiSums(sentence)
    ```

    输出:

    ```
    Sum of ASCII values:
    1361 97 879 730 658 327 527 
    Total sum -> 4579

    ```