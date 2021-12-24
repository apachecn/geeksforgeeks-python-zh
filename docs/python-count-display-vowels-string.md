# Python |统计并显示字符串中的元音

> 原文:[https://www . geesforgeks . org/python-count-display-元音-string/](https://www.geeksforgeeks.org/python-count-display-vowels-string/)

在这个程序中，我们需要计算一个字符串中存在的元音数量，并显示这些元音。这可以使用各种方法来完成。在本文中，我们将通过一些流行的方法来有效地做到这一点。
示例:

```
In a simple way
Input : Geeks for Geeks
Output :
5
['e', 'e', 'o', 'e', 'e']

This is in a different way
Input : Geeks for Geeks
Output : {'u': 0, 'o': 1, 'e': 4, 'a': 0, 'i': 0}
```

**统计元音:串音方式**

在这种方法中，我们将所有的元音存储在一个字符串中，然后从查询的字符串中挑选每个字符，并检查它是否在元音字符串中。元音串由两种情况下的所有元音组成，因为我们没有忽略这些情况。如果遇到元音，则计数递增并存储在列表中，最后打印出来。

## 蟒蛇 3

```
# Python code to count and display number of vowels
# Simply using for and comparing it with a
# string containing all vowels
def Check_Vow(string, vowels):
    final = [each for each in string if each in vowels]
    print(len(final))
    print(final)

# Driver Code
string = "Geeks for Geeks"
vowels = "AaEeIiOoUu"
Check_Vow(string, vowels);
```

输出:

```
5
['e', 'e', 'o', 'e', 'e']
```

**统计元音:词典方式**

这也执行相同的任务，但方式不同。在这种方法中，我们用元音组成一个字典，当遇到元音时增加它们。在这种方法中，我们使用格折叠方法来忽略格，然后我们形成一个以键为元音的元音字典。这是一种更好、更有效的方法来检查和查找字符串中每个元音的数量。

## 蟒蛇 3

```
# Count vowels in a different way
# Using dictionary
def Check_Vow(string, vowels):

    # casefold has been used to ignore cases
    string = string.casefold()

    # Forms a dictionary with key as a vowel
    # and the value as 0
    count = {}.fromkeys(vowels, 0)

    # To count the vowels
    for character in string:
        if character in count:
            count[character] += 1   
    return count

# Driver Code
vowels = 'aeiou'
string = "Geeks for Geeks"
print (Check_Vow(string, vowels))
```

输出:

```
{'u': 0, 'o': 1, 'e': 4, 'a': 0, 'i': 0}
```