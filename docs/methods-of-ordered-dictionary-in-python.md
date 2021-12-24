# Python 中有序字典的方法

> 原文:[https://www . geesforgeks . org/methods-of-ordered-in-dictionary-python/](https://www.geeksforgeeks.org/methods-of-ordered-dictionary-in-python/)

一个[**ordereddct**](https://www.geeksforgeeks.org/ordereddict-in-python/)**是一个记住按键第一次插入顺序的格言。如果新条目覆盖现有条目，则原始插入位置保持不变。删除一个条目并重新插入它会将它移动到最后。有序字典可以在使用哈希映射和队列的地方使用。它具有集两者于一体的特点。像队列一样，它**记住顺序**并且它还允许在两端插入和删除。而像字典也是表现为**哈希映射。****

****注意:**从 Python 3.6 开始，传递给 OrderedDict 构造函数的关键字参数保留顺序，参见 PEP-468。**

### **有序词典的方法**

**让我们看看有序字典提供的各种方法。**

*   ****popup():t1****

**此方法用于从头删除密钥。**

****语法:****

```
popitem(last = True) 
```

**如果最后一个为假，那么这个方法将从字典的开头删除一个键。这用作队列中的先进先出，否则它将从字典的末尾删除关键字。**

****时间复杂度:** O(1)。**

**为了更好地理解，请看一下代码。**

## **蟒蛇 3**

```
from collections import OrderedDict

ord_dict = OrderedDict().fromkeys('GeeksForGeeks')
print("Original Dictionary")
print(ord_dict)

# Pop the key from last
ord_dict.popitem()
print("\nAfter Deleting Last item :")
print(ord_dict)

# Pop the key from beginning
ord_dict.popitem(last = False)
print("\nAfter Deleting Key from Beginning :")
print(ord_dict)
```

****输出:****

> **原词典
> ordereddct([(' G '，None)、(' e '，None)、(' k '，None)、(' s '，None)、(' F '，None)、(' o '，None)、(' r '，None)】
> 删除最后一项后:
> ordereddct([(' G '，None)、(' e '，None)、(' k '，None)、(' s '，None)、(' F '，None)、(' o '，None)】
> 删除开头的关键字后:
> ordereddct([(' e**

*   ****move_to_end():****

**此方法用于将字典的现有键移动到末尾或开头。该功能有两个版本–**

****语法:****

```
move_to_end(key, last = True)
```

**如果 last 为 True，则此方法将在最后移动字典的现有键，否则它将在开始移动字典的现有键。如果密钥在开始时被移动，那么它将作为队列中的先进先出。**

****时间复杂度:** O(1)**

## **蟒蛇 3**

```
from collections import OrderedDict

ord_dict = OrderedDict().fromkeys('GeeksForGeeks')
print("Original Dictionary")
print(ord_dict)

# Move the key to  end
ord_dict.move_to_end('G')
print("\nAfter moving key 'G' to end of dictionary :")
print(ord_dict)

# Move the key to beginning
ord_dict.move_to_end('k', last = False)
print("\nAfter moving Key in the Beginning :")
print(ord_dict)
```

****输出:****

> **原词典
> 在将键“G”移动到词典末尾后排序的 CT([(‘G’，None)、(‘e’，None)、(‘k’，None)、(‘F’，None)、(‘o’，None)、(‘r’，None)】
> :
> 在将键移入词典后排序的 CT([(‘e’，None)、(‘k’，None)、(‘s’，None)、(‘F’，None)、(‘o’，None)、(‘r’，None)、(‘G’，None)】**

****移动到结束()功能的工作****

**基本上，这个方法在字典中的链表中查找一个链接。_ _ 映射并更新链接及其邻居的上一个和下一个指针。它从其位置删除该元素，并根据参数值将其添加到结尾或开头。由于下面所有的操作都需要恒定的时间，*ordereddct . move _ to _ end()*的复杂度也是恒定的。**