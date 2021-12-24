# 在 Python 中找到一个字符串中每个单词的出现频率

> 原文:[https://www . geesforgeks . org/find-python 字符串中每个单词的出现频率/](https://www.geeksforgeeks.org/find-frequency-of-each-word-in-a-string-in-python/)

写一段 python 代码，找出给定字符串中每个单词的出现频率。

示例:

```
Input :  str[] = "Apple Mango Orange Mango Guava Guava Mango" 
Output : frequency of Apple is : 1
         frequency of Mango is : 3
         frequency of Orange is : 1
         frequency of Guava is : 2

Input :  str = "Train Bus Bus Train Taxi Aeroplane Taxi Bus"
Output : frequency of Train is : 2
         frequency of Bus is : 3
         frequency of Taxi is : 2
         frequency of Aeroplane is : 1

```

**使用 list()方法 1:**
**1。**使用 python 中带有分隔符空格的 Split 函数(即 string.split())将字符串拆分成包含单词的列表。

```
Note:
string_name.split(separator) method is used to split the string 
by specified separator(delimiter) into the list.
If delimiter is not provided then white space is a separator. 

For example:
CODE   : str='This is my book'
         str.split()
OUTPUT : ['This', 'is', 'my', 'book']

```

**2。**初始化一个新的空列表。
T3】3。如果新列表中没有该单词，现在将该单词追加到先前字符串的新列表中。
**4。**迭代新列表，使用 count 函数(即 string . count(newstring[iteration]))求出每次迭代的词频。

```
Note:
string_name.count(substring) is used to find no. of occurrence of 
substring in a given string.

For example:
CODE   : str='Apple Mango Apple'
         str.count('Apple')
         str2='Apple'
         str.count(str2)
OUTPUT : 2
         2

```

## 蟒蛇 3

```
# Python code to find frequency of each word
def freq(str):

    # break the string into list of words 
    str = str.split()         
    str2 = []

    # loop till string values present in list str
    for i in str:             

        # checking for the duplicacy
        if i not in str2:

            # insert value in str2
            str2.append(i) 

    for i in range(0, len(str2)):

        # count the frequency of each word(present 
        # in str2) in str and print
        print('Frequency of', str2[i], 'is :', str.count(str2[i]))    

def main():
    str ='apple mango apple orange orange apple guava mango mango'
    freq(str)                    

if __name__=="__main__":
    main()             # call main function
```

**输出:**

```
Frequency of  apple  is :  3
Frequency of  mango  is :  3
Frequency of  orange  is :  2
Frequency of  guava  is :  1

```

**进场 2 使用套():**
**1。**使用 python 中带有分隔符空格的 Split 函数(即 string.split())将字符串拆分成包含单词的列表。
**2。**使用 **set()** 方法删除一个重复项，并给出一组唯一的单词
**3。**迭代集合，使用 count 函数(即 string . count(newstring[iteration]))求出每次迭代的词频。

## 蟒蛇 3

```
# Python3 code to find frequency of each word
# function for calculating the frequency
def freq(str):

    # break the string into list of words
    str_list = str.split()

    # gives set of unique words
    unique_words = set(str_list)

    for words in unique_words :
        print('Frequency of ', words , 'is :', str_list.count(words))

# driver code
if __name__ == "__main__":

    str ='apple mango apple orange orange apple guava mango mango'

    # calling the freq function
    freq(str)
```

**输出:**

```
Frequency of  apple  is :  3
Frequency of  mango  is :  3
Frequency of  orange  is :  2
Frequency of  guava  is :  1

```

 **接近 3(使用字典)**

```
# Find frequency of each word in a string in Python
# using dictionary.

def count(elements):
    # check if each word has '.' at its last. If so then ignore '.'
    if elements[-1] == '.':
        elements = elements[0:len(elements) - 1]

    # if there exists a key as "elements" then simply
    # increase its value.
    if elements in dictionary:
        dictionary[elements] += 1

    # if the dictionary does not have the key as "elements" 
    # then create a key "elements" and assign its value to 1.
    else:
        dictionary.update({elements: 1})

# driver input to check the program.

Sentence = "Apple Mango Orange Mango Guava Guava Mango"

# Declare a dictionary
dictionary = {}

# split all the word of the string.
lst = Sentence.split()

# take each word from lst and pass it to the method count.
for elements in lst:
    count(elements)

# print the keys and its corresponding values.
for allKeys in dictionary:
    print ("Frequency of ", allKeys, end = " ")
    print (":", end = " ")
    print (dictionary[allKeys], end = " ")
    print() 

# This code is contributed by Ronit Shrivastava.
```