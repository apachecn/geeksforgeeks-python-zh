# Python |统计给定字符串中重叠的子字符串

> 原文:[https://www . geesforgeks . org/python-计数-重叠-给定字符串中的子字符串/](https://www.geeksforgeeks.org/python-count-overlapping-substring-in-a-given-string/)

给定一个字符串和一个子字符串，任务是从给定的字符串中获取重叠子字符串的计数。

请注意，在 Python 中，`count()`函数返回给定字符串中的子字符串数量，但是当子字符串的两次出现重叠时，它不会给出正确的结果。考虑这个例子–

```
string = "GeeksforGeeksforGeeksforGeeks"

print(string.count("GeeksforGeeks"))
```

**输出:**

```
2
```

我们在这里得到的输出是 2，但是预期的输出是 3，因为我们还想计算重叠子串的出现。

为了解决这个问题，我们可以使用 Python 中的`find()`函数。它返回给定字符串中第一个出现的子字符串的开始位置，然后我们将该位置增加 1，并从该位置继续搜索，直到字符串结束。

以下是实施–

```
def CountOccurrences(string, substring):

    # Initialize count and start to 0
    count = 0
    start = 0

    # Search through the string till
    # we reach the end of it
    while start < len(string):

        # Check if a substring is present from
        # 'start' position till the end
        pos = string.find(substring, start)

        if pos != -1:
            # If a substring is present, move 'start' to
            # the next position from start of the substring
            start = pos + 1

            # Increment the count
            count += 1
        else:
            # If no further substring is present
            break
    # return the value of count
    return count

# Driver Code
string = "GeeksforGeeksforGeeksforGeeks"
print(CountOccurrences(string, "GeeksforGeeks"))
```

**Output:**

```
3

```