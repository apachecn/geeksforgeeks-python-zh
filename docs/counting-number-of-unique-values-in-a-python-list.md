# 计算 Python 列表中唯一值的数量

> 原文:[https://www . geesforgeks . org/counting-python 列表中唯一值的数量/](https://www.geeksforgeeks.org/counting-number-of-unique-values-in-a-python-list/)

让我们看看如何计算 Python 列表中唯一值的数量。
**例:**

```
Input : 10 20 10 30 40 40
Output : 2
Explanation : Only 2 elements, 20 and 30 are unique in the list.

Input : 'geeks' 'for' 'geeks'
Output : 1

```

**方法 1 :** 遍历列表，使用字典统计每个元素的频率，最后统计频率为 1 的元素。

```
# function to count the unique elements
def count_unique(my_list):

    # variable to store the unique count
    count = 0

    # creating dictionary to count frequency
    freq = {}

    # traversing the list
    for x in my_list:
        if (x in freq):
            freq[x] += 1
        else:
            freq[x] = 1

    # traversing the dictionary
    for key, value in freq.items():
        if value == 1:
            count += 1

    # displaying the count of unique elements
    print(count)

# driver function
if __name__ == "__main__":

    my_list = [10, 20, 10, 30, 40, 40]
    count_unique(my_list)

    my_list = ['geeks', 'for', 'geeks']
    count_unique(my_list)
```

**输出:**

```
2
1

```

**时间复杂度:**O(N)
T3】空间复杂度: O(N)

**方法 2 :** 这里我们将使用字典类的`get()`方法来统计频率。这使得程序变得更短，并演示了`get()`方法如何代替 if…else 有用。

```
# function to count the unique elements
def count_unique(my_list):

    # variable to store the unique count
    count = 0

    # creating dictionary to count frequency
    freq = {}

    # traversing the list
    for x in my_list:
        freq[x] = freq.get(x, 0) + 1

    # traversing the dictionary
    for key, value in freq.items():
        if value == 1:
            count += 1

    # displaying the count of unique elements
    print(count)

# driver function
if __name__ == "__main__":

    my_list = [10, 20, 10, 30, 40, 40]
    count_unique(my_list)

    my_list = ['geeks', 'for', 'geeks']
    count_unique(my_list)
```

**输出:**

```
2
1

```

**时间复杂度:**O(N)
T3】空间复杂度: O(N)

**方法 3 :** 这里我们将使用列表类的`count()`方法来统计频率。

```
# function to count the unique elements
def count_unique(my_list):

    # variable to store the unique count
    count = 0

    # creating dictionary to count frequency
    freq = {}

    # traversing the list
    for x in my_list:
        freq[x] = my_list.count(x)

    # traversing the dictionary
    for key, value in freq.items():
        if value == 1:
            count += 1

    # displaying the count of unique elements
    print(count)

# driver function
if __name__ == "__main__":

    my_list = [10, 20, 10, 30, 40, 40]
    count_unique(my_list)

    my_list = ['geeks', 'for', 'geeks']
    count_unique(my_list)
```

**输出:**

```
2
1

```

**时间复杂度:**O(N)
T3】空间复杂度: O(N)

**方法 4 :** 这里我们将使用集合模块的`Counter()`方法来统计频率。

```
# importing the module
import collections

# function to count the unique elements
def count_unique(my_list):

    # variable to store the unique count
    count = 0

    # creating dictionary to count frequency
    freq = collections.Counter(my_list)

    # traversing the dictionary
    for key, value in freq.items():
        if value == 1:
            count += 1

    # displaying the count of unique elements
    print(count)

# driver function
if __name__ == "__main__":

    my_list = [10, 20, 10, 30, 40, 40]
    count_unique(my_list)

    my_list = ['geeks', 'for', 'geeks']
    count_unique(my_list)
```

**输出:**

```
2
1

```