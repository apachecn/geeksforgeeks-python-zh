# 差异隐私和深度学习

> 原文:[https://www . geesforgeks . org/differential-privacy-and-deep-learning/](https://www.geeksforgeeks.org/differential-privacy-and-deep-learning/)

差异隐私是深度学习领域的一个新课题。这是为了确保当我们的神经网络从敏感数据中学习时，它们只学习它们应该从数据中学习的东西。
**辛西娅·德沃克(来自她的《算法基础》一书)提出的隐私的可靠定义:**

> “差异隐私”描述了数据持有人或策展人对数据主体做出的承诺，该承诺是这样的:“无论有什么其他研究、数据集或信息源可用，您都不会因允许您的数据用于任何研究或分析而受到不利或其他影响。”

差异隐私的一般目标是确保不同类型的统计分析不会损害隐私，如果在分析之后，分析者对数据集中的特征一无所知，这意味着在其他地方公开的信息对个人无害，则隐私得到保护。
为了在简单数据库的上下文中定义隐私，我们正在对数据库执行一些查询，如果我们从数据库中删除一个人，并且查询没有改变，那么这个人的隐私将得到充分保护。
**我们举个例子来理解**
给定一个数据库，其中包含一些数字‘1’和‘0’，这是一些敏感的数据，比如一个人是否患有某种疾病(可能患者不想透露这些数据)。

```
  db = [1, 0, 1, 1, 0, 1, 0, 1, 0, 0]
```

现在，您的数据库删除了每个条目中的一个，这称为并行数据库。因此，如果原始数据库的长度为“n”，则有“n”个并行数据库，在我们的例子中为 10 个。
现在我们考虑其中一个平行 DBS，我们来看第一个，其中第一个个体被移除，我们得到了什么？

```
 pdbs[0] = [0, 1, 1, 0, 1, 0, 1, 0, 0]
```

所以你可以看到现在这个数据库的长度是 n-1。因此，为了计算灵敏度，我们需要一个查询函数，因此，我们假设最简单的“和”。所以我们现在关注两个结果:

```
 sum(db) = 5
 sum(pdbs[0]) = 4
```

而上面两者的区别是‘1’，我们知道我们需要找到所有这些差异的最大值，因为这个 DB 只包含‘1’和‘0’，所有这些差异要么是‘1’(当类似于上面时，当 1 被移除时)要么是‘0’(当 0 被移除时)。
因此，我们得到这个例子的敏感度为‘1’，这确实是一个很高的值，因此使用这个‘sum’查询可以很容易地进行差分攻击。
敏感度应该低于，这样就可以定量了解差异攻击可以泄露多少级别的信息/泄露隐私。
**在 Python 中实现差异隐私的代码**

## 蟒蛇 3

```
import torch

# the number of entries in our database
num_entries = 5000

db = torch.rand(num_entries) > 0.5

# generating parallel databases
def get_parallel_db(db, remove_index):

    return torch.cat((db[0:remove_index],
                      db[remove_index+1:]))
get_parallel_db(db, 52352)

def get_parallel_dbs(db):

    parallel_dbs = list()

    for i in range(len(db)):
        pdb = get_parallel_db(db, i)
        parallel_dbs.append(pdb)

    return parallel_dbs

pdbs = get_parallel_dbs(db)

# Creating linear and parallel databases

def create_db_and_parallels(num_entries):

    db = torch.rand(num_entries) > 0.5
    pdbs = get_parallel_dbs(db)

    return db, pdbs

db, pdbs = create_db_and_parallels(2000)

# Creating sensitivity function

def sensitivity(query, n_entries=1000):

    db, pdbs = create_db_and_parallels(n_entries)

    full_db_result = query(db)

    max_distance = 0
    for pdb in pdbs:
        pdb_result = query(pdb)

        db_distance = torch.abs(pdb_result - full_db_result)

        if(db_distance > max_distance):
            max_distance = db_distance

    return max_distance

# query our database and evaluate whether or not the result of the
# query is leaking "private" information

def query(db):
    return db.float().mean()
sensitivity(query)
```

```
Input : A randomly generated database(with the help of torch library) 
```

```
Output : tensor(0.0005)
```

**解释**
首先，我们借助 torch 库创建一个随机数据库，然后我们为线性和并行数据库定义了两个函数 get_parallel_db 和 get_parallel_dbs。现在我们定义了敏感度函数，然后测量每个并行数据库的查询结果和整个数据库的查询结果之间的差异，然后计算最大值(1)。这个值叫做**“灵敏度”**。