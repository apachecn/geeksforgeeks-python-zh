# 使用 Python 列表理解对设置位进行计数

> 原文:[https://www . geesforgeks . org/count-set-bits-using-python-list-understance/](https://www.geeksforgeeks.org/count-set-bits-using-python-list-comprehension/)

写一个有效的程序来计算整数的二进制表示中的 1 的个数。

示例:

```
Input : n = 6
Output : 2
Binary representation of 6 is 110 and has 2 set bits

Input : n = 11
Output : 3
Binary representation of 11 is 1101 and has 3 set bits

```

对于这个问题，我们已经有了解决方案，请参考[在整数](https://www.geeksforgeeks.org/count-set-bits-in-an-integer/)链接中计数设置位。我们将使用[列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)在 Python 中解决这个问题。方法很简单，

1.  使用 [bin(number)](https://www.geeksforgeeks.org/bin-in-python/) 函数将给定的数字转换为它的二进制表示。
2.  现在从给定数字的二进制表示中分离出所有 1，并打印 1 的列表长度。

```
# Function to count set bits in an integer 
# in Python 

def countSetBits(num): 

     # convert given number into binary 
     # output will be like bin(11)=0b1101 
     binary = bin(num) 

     # now separate out all 1's from binary string 
     # we need to skip starting two characters 
     # of binary string i.e; 0b 
     setBits = [ones for ones in binary[2:] if ones=='1'] 

     print (len(setBits)) 

# Driver program 
if __name__ == "__main__": 
    num = 11
    countSetBits(num)
```

输出:

```
3

```

下面是单线解决方案。

```
print (bin(num).count("1"))
```