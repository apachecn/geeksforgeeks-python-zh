# Python | Interlist XOR

> 原文:[https://www.geeksforgeeks.org/python-interlist-xor/](https://www.geeksforgeeks.org/python-interlist-xor/)

可能有许多情况需要对两个不同的列表进行索引异或运算。这在日常编程中可能会有应用。让我们讨论执行这项任务的各种方法。

**方法#1:天真的方法**
在这个方法中，我们简单地运行一个循环，并将两个列表元素在相似索引处的异或追加到新列表中，直到我们到达较小列表的末尾。这是完成这项任务的基本方法。

```
# Python code to demonstrate 
# Interlist XOR
# naive method 

# initializing lists
test_list1 = [1, 3, 4, 6, 8]
test_list2 = [4, 5, 6, 2, 10]

# printing original lists
print ("Original list 1 : " + str(test_list1))
print ("Original list 2 : " + str(test_list2))

# using naive method to 
# Interlist XOR
res_list = []
for i in range(0, len(test_list1)):
    res_list.append(test_list1[i] ^ test_list2[i])

# printing resultant list 
print ("Resultant list is : " + str(res_list))
```

**Output :**

```
Original list 1 : [1, 3, 4, 6, 8]
Original list 2 : [4, 5, 6, 2, 10]
Resultant list is : [5, 6, 2, 4, 2]

```