# Python 中的嵌套列表理解

> 原文:[https://www . geesforgeks . org/nested-list-explorations-in-python/](https://www.geeksforgeeks.org/nested-list-comprehensions-in-python/)

[列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)是 Python 最惊人的特性之一。这是一种通过迭代可迭代对象来创建列表的聪明而简洁的方法。嵌套列表理解只不过是另一个列表理解中的一个列表理解，与循环的嵌套非常相似。

让我们看一些例子来理解嵌套列表理解的作用:

**例 1:**

```
I want to create a matrix which looks like below:

matrix = [[0, 1, 2, 3, 4],
          [0, 1, 2, 3, 4],
          [0, 1, 2, 3, 4],
          [0, 1, 2, 3, 4],
          [0, 1, 2, 3, 4]]

```

下面的代码对给定的任务使用嵌套 for 循环:

```
matrix = []

for i in range(5):

    # Append an empty sublist inside the list
    matrix.append([])

    for j in range(5):
        matrix[i].append(j)

print(matrix)
```

**Output:**

```
[[0, 1, 2, 3, 4], [0, 1, 2, 3, 4], [0, 1, 2, 3, 4], [0, 1, 2, 3, 4], [0, 1, 2, 3, 4]]

```

使用嵌套列表理解只需一行就可以获得相同的输出:

```
# Nested list comprehension
matrix = [[j for j in range(5)] for i in range(5)]

print(matrix)
```

**Output:**

```
[[0, 1, 2, 3, 4], [0, 1, 2, 3, 4], [0, 1, 2, 3, 4], [0, 1, 2, 3, 4], [0, 1, 2, 3, 4]]

```

**说明:**

> 上述程序的语法如下所示:
> 
> [范围(5)中 I 的表达式]–>这意味着执行该表达式并将其输出附加到列表中，直到变量 I 从 0 迭代到 4。
> 
> 例如:-[范围(5)中 I 的 I]–>在这种情况下，表达式
> 的输出只是变量 I 本身，因此我们将其输出附加到列表中，而 i
> 从 0 迭代到 4。
> 
> 因此，输出将是–>[0，1，2，3，4]
> 
> 但在我们的例子中，表达本身就是一种列表理解。因此，我们需要首先
> 求解表达式，然后将其输出附加到列表中。
> 
> 表达式=[范围(5)中 j 的 j]–>该表达式的输出与上面讨论的
> 示例相同。
> 
> 因此表达式= [0，1，2，3，4]。
> 
> 现在我们只是简单地附加这个输出，直到变量 I 从 0 迭代到 4，总共是 5 次迭代。因此，最终输出将只是重复 5 次以上表达式
> 的输出列表。
> 
> 输出:[[0，1，2，3，4]，[0，1，2，3，4]，[0，1，2，3，4]，[0，1，2，3，4]，[0，1，2，3，4]]

**例 2:**

```
Suppose I want to flatten a given 2-D list:

matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

Expected Output: flatten_matrix = [1, 2, 3, 4, 5, 6, 7, 8, 9]

```

这可以使用嵌套 for 循环来完成，如下所示:

```
# 2-D List
matrix = [[1, 2, 3], [4, 5], [6, 7, 8, 9]]

flatten_matrix = []

for sublist in matrix:
    for val in sublist:
        flatten_matrix.append(val)

print(flatten_matrix)
```

**Output:**

```
[1, 2, 3, 4, 5, 6, 7, 8, 9]

```

这也可以使用嵌套列表理解来完成，如下所示:

```
# 2-D List
matrix = [[1, 2, 3], [4, 5], [6, 7, 8, 9]]

# Nested List Comprehension to flatten a given 2-D matrix
flatten_matrix = [val for sublist in matrix for val in sublist]

print(flatten_matrix)
```

**Output:**

```
[1, 2, 3, 4, 5, 6, 7, 8, 9]

```

**说明:**

> 在这种情况下，我们需要在给定的二维列表中循环每个元素，并将其
> 附加到另一个列表中。为了更好的理解，我们可以将列表理解分为
> 三个部分:
> 
> ```
> flatten_matrix = [val
>                   for sublist in matrix
>                   for val in sublist]
> ```
> 
> 第一行显示了我们想要添加到列表中的内容。第二行是
> 外环，第三行是内环。
> 
> “对于矩阵中的子列表”,逐个返回矩阵中的子列表，如下所示:
> 
> [1, 2, 3], [4, 5], [6, 7, 8, 9]
> 
> “for val in sublist”返回子列表中的所有值。
> 
> 因此，如果子列表= [1，2，3]，'对于子列表中的 val '–>会逐个给出 1，2，3 作为输出。
> 
> 对于每一个这样的 val，我们将输出作为 val，并将其附加到列表中。

**例 3:**

> 假设我想要展平一个给定的二维列表，并且只包括那些长度小于 6 的字符串:
> 
> 行星= [['水星'，'金星'，'地球']，['火星'，'木星'，'土星'，['天王星'，'海王星'，'冥王星']]
> 
> 预期输出:扁平化行星= ['金星'，'地球'，'火星'，'冥王星']

这可以使用嵌套 for 循环中的 if 条件来完成，如下所示:

```
# 2-D List of planets
planets = [['Mercury', 'Venus', 'Earth'], ['Mars', 'Jupiter', 'Saturn'], ['Uranus', 'Neptune', 'Pluto']]

flatten_planets = []

for sublist in planets:
    for planet in sublist:

        if len(planet) < 6:
            flatten_planets.append(planet)

print(flatten_planets)
```

**Output:**

```
['Venus', 'Earth', 'Mars', 'Pluto']

```

这也可以使用嵌套列表理解来完成，如下所示:

```
# 2-D List of planets
planets = [['Mercury', 'Venus', 'Earth'], ['Mars', 'Jupiter', 'Saturn'], ['Uranus', 'Neptune', 'Pluto']]

# Nested List comprehension with an if condition
flatten_planets = [planet for sublist in planets for planet in sublist if len(planet) < 6]

print(flatten_planets)
```

**Output:**

```
['Venus', 'Earth', 'Mars', 'Pluto']

```

**说明:**

> 这个例子与前面的例子非常相似，但是在这个例子中，我们只需要
> 一个额外的 if 条件来检查某个特定行星的长度是否小于
> 6。
> 
> 这可以分为以下 4 个部分:
> 
> ```
> flatten_planets = [planet 
>                    for sublist in planets 
>                    for planet in sublist 
>                    if len(planet) < 6] 
> 
> ```