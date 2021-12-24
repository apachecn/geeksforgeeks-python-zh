# 列表中所有回文数字

> 原文:[https://www . geesforgeks . org/all-回文-列表中的数字/](https://www.geeksforgeeks.org/all-palindrome-numbers-in-a-list/)

给定一个列表，统计并打印其中所有的回文数字。

**示例:**

```py
Input: 10 121 133 155 141 252
Output: 121 141 252
Total palindrome nos. are 3

Input: 111 220 784 565 498 787 363
Output: 111 565 787 363
Total palindrome nos. are 4

```

**1。**从列表中访问元素。
T3】2。现在，在一个临时变量中得到它的反向值。
**3。**现在，将列表元素的值与其反向值进行比较，如果两者相同，则打印列表元素并将计数器 c 增加 1。
**4。**继续此程序，直到列表变空。
**5。**现在，打印计数器值，即给定列表中回文数字的总数。

```py
# Python program to count and 
# print all palindrome numbers in a list. 

def palindromeNumbers(list_a): 

    c = 0

    # loop till list is not empty 
    for i in list_a:             

        # Find reverse of current number 
        t = i 
        rev = 0
        while t > 0: 
            rev = rev * 10 + t % 10
            t = t // 10

        # compare rev with the current number 
        if rev == i: 
            print (i) 
            c = c + 1

    print()
    print ("Total palindrome nos. are", c )
    print()

# Driver code 
def main(): 

    list_a = [10, 121, 133, 155, 141, 252] 
    palindromeNumbers(list_a) 

    list_b = [ 111, 220, 784, 565, 498, 787, 363] 
    palindromeNumbers(list_b)                     

if __name__=="__main__": 
    main()             # main function call 
```

**Output:**

```py
121
141
252

Total palindrome nos. are 3

111
565
787
363

Total palindrome nos. are 4

```