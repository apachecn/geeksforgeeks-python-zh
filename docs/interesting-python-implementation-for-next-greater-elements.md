# 下一个更大元素的有趣 Python 实现

> 原文:[https://www . geesforgeks . org/interior-python-实现-for-next-greater-elements/](https://www.geeksforgeeks.org/interesting-python-implementation-for-next-greater-elements/)

给定一个数组，为每个元素打印下一个更大的元素(NGE)。元素 x 的下一个较大元素是数组中 x 右侧的第一个较大元素。不存在更大元素的元素，将下一个更大的元素视为-1。

示例:

```
Input : 11, 13, 21, 3, 9, 12
Output :
11 --> 21
13 --> 21
21 --> -1
3 --> 12
9 --> 12
12 --> -1

Input : 10, 9, 8, 7, 6, 5, 4, 3, 2
Output :
10 --> -1
9 --> -1
8 --> -1
7 --> -1
6 --> -1
5 --> -1
4 --> -1
3 --> -1
2 --> -1

```

下面是 Python 中的一个简单实现。

```
# Function for implementation of NGE
def NGE(arr):

    # Iterate through array to check for greatest element
    for i in range(0, len(arr)):

        # Find the maximum from i to end
        lead = max(arr[i:])

        # If max is same as the i'th number then 
        # print -1 else print the maximum
        if (arr[i] == lead):
            print("% d --> % d" % (arr[i], -1))
        else:
            print("% d --> % d" % (arr[i], lead))

# Driver program
def main():
    arr = [11, 13, 21, 3, 9, 12]
    NGE(arr)
    arr = [10, 9, 8, 7, 6, 5, 4, 3, 2]
    NGE(arr)

if __name__ == '__main__':
    main()
```

注意，上述解的时间复杂度为 O(n*n)。我们可以使用堆栈在 [O(n)时间内对其进行优化。](https://www.geeksforgeeks.org/next-greater-element/)