# 双向联想记忆(BAM)从头实现

> 原文:[https://www . geesforgeks . org/双向-关联-内存-bam-从头实现/](https://www.geeksforgeeks.org/bidirectional-associative-memory-bam-implementation-from-scratch/)

**先决条件:** [ANN |双向联想记忆(BAM)学习算法](https://www.geeksforgeeks.org/ann-bidirectional-associative-memory-bam-learning-algorithm/)
要实现 BAM 模型，这里有一些基本的考虑和方法-

1.  考虑 M 的值，因为 BAM 将由 M 对模式构成。这里 M 的值是 4。
2.  集合 A:输入模式
3.  集合 B:对应的目标模式
4.  分配输入和输出层的神经元。这里，输入层的神经元是 6，输出层是 3
5.  使用 BAM 算法计算权重矩阵
6.  测试输入模式的 BAM 模型，它将返回相应的目标模式作为输出。对于每个目标模式，BAM 模型都将返回相应的输入模式。

**BAM 的 Python 实现:**

## 蟒蛇 3

```py
# Import Python Libraries
import numpy as np

# Take two sets of patterns:
# Set A: Input Pattern
x1 = np.array([1, 1, 1, 1, 1, 1]).reshape(6, 1)
x2 = np.array([-1, -1, -1, -1, -1, -1]).reshape(6, 1)
x3 = np.array([1, 1, -1, -1, 1, 1]).reshape(6, 1)
x4 = np.array([-1, -1, 1, 1, -1, -1]).reshape(6, 1)

# Set B: Target Pattern
y1 = np.array([1, 1, 1]).reshape(3, 1)
y2 = np.array([-1, -1, -1]).reshape(3, 1)
y3 = np.array([1, -1, 1]).reshape(3, 1)
y4 = np.array([-1, 1, -1]).reshape(3, 1)

'''
print("Set A: Input Pattern, Set B: Target Pattern")
print("\nThe input for pattern 1 is")
print(x1)
print("\nThe target for pattern 1 is")
print(y1)
print("\nThe input for pattern 2 is")
print(x2)
print("\nThe target for pattern 2 is")
print(y2)
print("\nThe input for pattern 3 is")
print(x3)
print("\nThe target for pattern 3 is")
print(y3)
print("\nThe input for pattern 4 is")
print(x4)
print("\nThe target for pattern 4 is")
print(y4)

print("\n------------------------------")
'''
# Calculate weight Matrix: W
inputSet = np.concatenate((x1, x2, x3, x4), axis = 1)
targetSet = np.concatenate((y1.T, y2.T, y3.T, y4.T), axis = 0)
print("\nWeight matrix:")
weight = np.dot(inputSet, targetSet)
print(weight)

print("\n------------------------------")

# Testing Phase
# Test for Input Patterns: Set A
print("\nTesting for input patterns: Set A")
def testInputs(x, weight):
  # Multiply the input pattern with the weight matrix
  # (weight.T X x)
  y = np.dot(weight.T, x)
  y[y < 0] = -1
  y[y >= 0] = 1
  return np.array(y)

print("\nOutput of input pattern 1")
print(testInputs(x1, weight))
print("\nOutput of input pattern 2")
print(testInputs(x2, weight))
print("\nOutput of input pattern 3")
print(testInputs(x3, weight))
print("\nOutput of input pattern 4")
print(testInputs(x4, weight))

# Test for Target Patterns: Set B
print("\nTesting for target patterns: Set B")
def testTargets(y, weight):
  # Multiply the target pattern with the weight matrix
  # (weight X y)
  x = np.dot(weight, y)
  x[x <= 0] = -1
  x[x > 0] = 1
  return np.array(x)

print("\nOutput of target pattern 1")
print(testTargets(y1, weight))
print("\nOutput of target pattern 2")
print(testTargets(y2, weight))
print("\nOutput of target pattern 3")
print(testTargets(y3, weight))
print("\nOutput of target pattern 4")
print(testTargets(y4, weight))
```

**Output:** 

```py
Weight matrix:
[[4 0 4]
 [4 0 4]
 [0 4 0]
 [0 4 0]
 [4 0 4]
 [4 0 4]]

------------------------------

Testing for input patterns: Set A

Output of input pattern 1
[[1]
 [1]
 [1]]

Output of input pattern 2
[[-1]
 [-1]
 [-1]]

Output of input pattern 3
[[ 1]
 [-1]
 [ 1]]

Output of input pattern 4
[[-1]
 [ 1]
 [-1]]

Testing for target patterns: Set B

Output of target pattern 1
[[1]
 [1]
 [1]
 [1]
 [1]
 [1]]

Output of target pattern 2
[[-1]
 [-1]
 [-1]
 [-1]
 [-1]
 [-1]]

Output of target pattern 3
[[ 1]
 [ 1]
 [-1]
 [-1]
 [ 1]
 [ 1]]

Output of target pattern 4
[[-1]
 [-1]
 [ 1]
 [ 1]
 [-1]
 [-1]]
```

这里，对于每个输入模式，BAM 模型给出正确的目标模式，对于目标模式，模型也给出相应的输入模式。
因此，它表示 BAM 模型被正确实现。