# Python |查找发微博最多的人

> 原文:[https://www . geesforgeks . org/python-find-who-tweet-most/](https://www.geeksforgeeks.org/python-find-who-tweeted-the-most/)

给定一个推文列表，任务是找到推文最多的用户。

**注意:**
如果多个用户的推文数量相同，则按照用户名的字母顺序打印所有用户。

**输入格式:**

```py
Read the input from the console.
The first line of input should be the number of test cases
Remaining lines of input should contain each test case input. 

```

**对于每个测试用例输入:**

```py
First-line should contain the number of tweets.
Followed by N lines, each containing the user name
and tweet id separated by a space.

```

**输出格式:**

```py
Find the user with max number of tweets. 
Print user name and the total number of tweets.

```

**示例:**

```py
Input : 
1
4
sachin tweet_id_1
sehwag tweet_id_2
sachin tweet_id_3
sachin tweet_id_4

Output :
sachin 3

Input :
1
6
sachin tweet_id_1
sehwag tweet_id_2
sachin tweet_id_3
sehwag tweet_id_4
kohli tweet_id_5
kohli tweet_id_6

Output : 
kohli 2
sachin 2
sehwag 2

```

**代码:Python 实现查找发微博最多的人**

```py
# Write Python3 code here
# collection module used counting in dic for value and keys 
from collections import Counter

tweet_names = ["sachin tweet_id_1", 
               "sehwag tweet_id_2",
               "sachin tweet_id_3",
               "sachin tweet_id_4"] 

uniq_names = [pref_names.split()[0] for
              pref_names in tweet_names]

times = Counter(uniq_names)
repeat = times.values()

for element in set(repeat):
    dupl = ([(key, value) for
             key, value in sorted(times.items()) if
             value == element])

    if len(dupl) > 1:
        for (key, value) in dupl:
            print (key,'',value)
    max_value = max(times.values())
    temp_max_result = [(key, value) for 
                       key, value in sorted(times.items()) if
                       value == max_value]

    if temp_max_result != dupl:
        for (key,value) in temp_max_result:
            print (key,'',value)

```

**输出:**

```py
sachin  3
```