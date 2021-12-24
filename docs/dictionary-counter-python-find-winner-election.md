# Python 中的字典和计数器查找选举获胜者

> 原文:[https://www . geesforgeks . org/dictionary-counter-python-find-winner-election/](https://www.geeksforgeeks.org/dictionary-counter-python-find-winner-election/)

在选举中给定一系列候选人的名字。数组中的候选人姓名代表对候选人的投票。打印获得最高票数的候选人姓名。如果有领带，打印一个字典上较小的名字。
示例:

```
Input :  votes[] = {"john", "johnny", "jackie", 
                    "johnny", "john", "jackie", 
                    "jamie", "jamie", "john",
                    "johnny", "jamie", "johnny", 
                    "john"};
Output : John
We have four Candidates with name as 'John', 
'Johnny', 'jamie', 'jackie'. The candidates
John and Johny get maximum votes. Since John
is alphabetically smaller, we print it.
```

对于这个问题，我们已经有了解决方案，请参考[查找选举获胜者，其中选票被表示为候选人姓名](https://www.geeksforgeeks.org/find-winner-election-votes-represented-candidate-names/)链接。我们可以使用[字典数据结构](https://www.youtube.com/watch?v=z7z_e5-l2yE&t=31s)在 python 中快速解决这个问题。
**方法一:**
方法很简单，

1.  使用计数器(迭代器)方法将给定的投票列表转换为字典。我们将有一个字典，候选名称为**键**，它们的频率(计数)为**值**。
2.  由于可能有 1 个以上的候选人获得相同的票数，在这种情况下，我们需要打印字典上较小的名字，因此现在我们将通过遍历以前创建的字典来创建另一个字典，票数将是**键**，候选人姓名将是**值**。
3.  现在找到候选人的最大投票值，并获得映射到该计数值的候选人列表。
4.  对具有相同最大票数的候选人列表进行排序，并打印排序列表的第一个元素，以便打印按字典顺序排列的较小名称。

## 蟒蛇 3

```
# Function to find winner of an election where votes
# are represented as candidate names
from collections import Counter

def winner(input):

    # convert list of candidates into dictionary
    # output will be likes candidates = {'A':2, 'B':4}
    votes = Counter(input)

    # create another dictionary and it's key will
    # be count of votes values will be name of
    # candidates
    dict = {}

    for value in votes.values():

        # initialize empty list to each key to
        # insert candidate names having same
        # number of votes
        dict[value] = []

    for (key,value) in votes.items():
        dict[value].append(key)

    # sort keys in descending order to get maximum
    # value of votes
    maxVote = sorted(dict.keys(),reverse=True)[0]

    # check if more than 1 candidates have same
    # number of votes. If yes, then sort the list
    # first and print first element
    if len(dict[maxVote])>1:
        print (sorted(dict[maxVote])[0])
    else:
        print (dict[maxVote][0])

# Driver program
if __name__ == "__main__":
    input =['john','johnny','jackie','johnny',
            'john','jackie','jamie','jamie',
            'john','johnny','jamie','johnny',
            'john']
    winner(input)
```

**输出:**

```
john
```

**方法二:**
这是一个比较短的方法。
1。统计每个人的投票数，并存入字典。
2。求最大票数。
3。查找投票数等于最大投票数的相应人员。
4。因为我们希望按照字典顺序输出，所以排序列表并打印第一个元素。

## 蟒蛇 3

```
from collections import Counter

votes =['john','johnny','jackie','johnny','john','jackie',
    'jamie','jamie','john','johnny','jamie','johnny','john']

#Count the votes for persons and stores in the dictionary
vote_count=Counter(votes)

#Find the maximum number of votes
max_votes=max(vote_count.values())

#Search for people having maximum votes and store in a list
lst=[i for i in vote_count.keys() if vote_count[i]==max_votes]

#Sort the list and print lexicographical smallest name
print(sorted(lst)[0])
```

输出:

```
john
```