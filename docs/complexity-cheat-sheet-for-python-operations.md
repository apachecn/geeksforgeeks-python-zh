# Python 操作的复杂性备忘单

> 原文:[https://www . geesforgeks . org/complexity-python 操作备忘单/](https://www.geeksforgeeks.org/complexity-cheat-sheet-for-python-operations/)

**先决条件:** [列表](https://www.geeksforgeeks.org/python-list/)[词典](https://www.geeksforgeeks.org/python-dictionary/)[集合](https://www.geeksforgeeks.org/python-sets/)

像 [list](https://www.geeksforgeeks.org/python-list/) 、[set](https://www.geeksforgeeks.org/python-sets/)、[dictionary](https://www.geeksforgeeks.org/python-dictionary/)这样的 Python 内置数据结构提供了大量的操作，使得编写简洁的代码变得更加容易，但是没有意识到它们的复杂性可能会导致您的 python 代码出现意想不到的缓慢行为。

**例如:**

简单的字典查找操作可以通过以下方式完成:

```
if key in d:
```

或者

```
if dict.get(key)
```

前者有`O(N)`的时间复杂度，后者有`O(1)`，可以在嵌套语句中产生很大的差异。

**要点:**

1.  Lists are similar to arrays with bidirectional addition and deletion functions.
2.  And dictionaries and collections use hash tables for insertion/deletion and lookup operations.

该备忘单可用于选择对时间有效的操作。

## 列表操作

| 操作 | 例子 | 复杂性类别 |
| --- | --- | --- |
|  | 平均案例 | 摊销最坏情况 |
| --- | --- | --- |
| 附加 | l .追加(项目) | O(1) | O(1) |
| 清楚的 | l.clear() | O(1) | O(1) |
| 包含 | 项目在/不在 l 中 | O(N) | O(N) |
| 复制 | l.copy() | O(N) | O(N) |
| 删除 | 的 l[i] | O(N) | O(N) |
| 扩展 | l.extend(…) | O(N) | O(N) |
| 平等 | l1==l2，l1！=l2 | O(N) | O(N) |
| 索引 | l[i] | O(1) | O(1) |
| 循环 | 对于 l 中的项目: | O(N) | O(N) |
| 长度 | 透镜(l) | O(1) | O(1) |
| 乘；成倍增加；（使）繁殖 | k*l | O(k*N) | O(k*N) |
| 最小值、最大值 | 最小(升)，最大(升) | O(N) | O(N) |
| 从头到尾弹出 | l.pop(-1) | O(1) | O(1) |
| Pop 中间体 | l.pop（项目） | O(N) | O(N) | 去除 | l.remove(…) | O(N) | O(N) |
| 反面的 | l .反向() | O(N) | O(N) |
| 薄片 | l[x:y] | O(y-x) | O(y-x) |
| 分类 | l.sort() | O(N*log(N)) | O(N*log(N)) |
| 商店 | l[I]=项目 | O(1) | O(1) |

更多信息请参考 Python 中列表的[内部工作](https://www.geeksforgeeks.org/internal-working-of-list-in-python/)。

**注意:**元组具有相同的运算(不可变)和复杂度。

## 字典操作

| 操作 | 例子 | 复杂性类别 |
| --- | --- | --- |
|  | 平均案例 | 摊销最坏情况 |
| --- | --- | --- |
| 清楚的 | d.clear() | O(1) | O(1) |
| 建筑 | dict(…) | O(len(d)) | O(len(d)) |
| 删除 | 从 d[k] | O(1) | O(N) |
| 得到 | d.get() | O(1) | O(N) |
| 迭代(键、值、项目) | 对于 d 中的项目: | O(N) | O(N) |
| 长度 | len(d) | O(1) | O(1) |
| 流行音乐 | d.pop(项目) | O(1) | O(N) |
| Pop 项目 | d.popitem（） | O(1) | O(1) |
| 返回视图 | d.keys() | O(1) | O(1) |
| Fromkeys | d . from key(seq) | O（len（seq）） | O（len（seq）） |

**注意:** Defaultdict 的运算与 dict 相同，时间复杂度与继承 dict 相同。

## 设置操作

| 操作 | 例子 | 复杂性类别 |
| --- | --- | --- |
|  | 平均案例 | 摊销最坏情况 |
| --- | --- | --- |
| 增加 | s.add(项目) | O(1) | O(N) |
| 清楚的 | s.clear() | O(1) | O(1) |
| 复制 | s.copy() | O(N) | O(N) |
| 包含 | 项目在/不在 | O(1) | O(N) |
| 创造 | set(…) | o(透镜) | o(透镜) |
| 抛弃 | s .丢弃(项目) | O(1) | O(N) |
| 差异 | s1-s2 | o(透镜(s1)) | o(透镜(s1)) |
| 差异更新 | s1.difference_update(s2) | o(透镜(s2)) | – |
| 平等 | s1==s2，s1！=s2 | o(最小值(透镜(s1)，透镜(s2)) | o(最小值(透镜(s1)，透镜(s2)) |
| 交集 | s1 和 s2 | o(最小值(透镜(s1)，透镜(s2)) | o(最小值(透镜(s1)，透镜(s2)) |
| 循环 | 对于中的项目: | O(N) | O(N) |
| 是子集 | s1<=s2 | o(透镜(s1)) | o(透镜(s1)) |
| 是超集 | s1>=s2 | o(透镜(s2)) | o(透镜(s1)) |
| 流行音乐 | s.pop() | O(1) | O(N) |
| 联盟 | s1&#124;s2 | O(len(s1)+len(s2)) | – |
| 对称差 | s1^s2 | 透镜(s1) | o(镜头(S1)*镜头(s2)) |

更多信息请参考 Python 中[Set 的内部工作](https://www.geeksforgeeks.org/internal-working-of-set-in-python/)

**注意:**冻结集具有相同的操作(不可变)和复杂性。