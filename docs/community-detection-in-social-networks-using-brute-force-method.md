# 使用蛮力方法在社交网络中进行社区检测

> 原文:[https://www . geesforgeks . org/community-在社交网络中检测-使用暴力方法/](https://www.geeksforgeeks.org/community-detection-in-social-networks-using-brute-force-method/)

**先决条件-** [**Python 基础知识**](https://www.geeksforgeeks.org/python-programming-language/)**[**NetworkX 基础知识**](https://www.geeksforgeeks.org/introduction-to-social-networks-using-networkx-in-python/)**

**我们将使用蛮力方法将图的节点分成两个或多个社区。蛮力方法意味着我们将尝试将每个节点划分为社区，并检查社区是否正确划分。我们将使用蛮力方法来完成这项任务。**

****算法:****

1.  **创建一个由 N 个节点及其边组成的图，或者像杠铃图那样的内置图。**
2.  **现在拿两个列表作为第一个社区和第二个社区。**
3.  **现在开始将节点放入社区，如将第一个节点放入第一个社区，将其余 N-1 个节点放入第二个社区，并检查其内部和外部边缘。**
4.  **现在我们将使用 [itertools](https://www.geeksforgeeks.org/python-itertools/) 进行组合。**
5.  **对每个组合重复步骤 3 和 4。**
6.  **现在，通过计算社区内/社区间边数的比率来检查哪种划分最好。**
7.  **现在找到第一个社区和第二个社区的最大比率值，并打印该值。**

****下面是实现。****

## **蟒蛇 3**

```
import networkx as nx
import itertools

def communities_using_brute(gfg):
  nodes = gfg.nodes()
  n = gfg.number_of_nodes()
  first_community = []

  for i in range(1, n//2 + 1):
    c = [list(a) for a in itertools.combinations(nodes, i)]
    first_community.extend(c)

  second_community = []

  for i in range(len(first_community)):
    b = list(set(nodes)-set(first_community[i]))
    second_community.append(b)

  # Which division is best...
  intra_edges1 = []
  intra_edges2 = []
  inter_edges = []

  # ratio of number of intra/number of inter
  # community edges
  ratio = []  

  for i in range(len(first_community)):
    intra_edges1.append(gfg.subgraph(first_community[i]).number_of_edges())

  for i in range(len(second_community)):
    intra_edges2.append(gfg.subgraph(second_community[i]).number_of_edges())

  e = gfg.number_of_edges()

  for i in range(len(first_community)):
    inter_edges.append(e-intra_edges1[i]-intra_edges2[i])

  # Calculate the Ratio

  for i in range(len(first_community)):
    ratio.append((float(intra_edges1[i]+intra_edges2[i]))/inter_edges[i])

  maxV=max(ratio)
  mindex=ratio.index(maxV)

  print('[ ', first_community[mindex], ' ] , [ ', second_community[mindex], ' ]')

# Example graph
gfg=nx.barbell_graph(5, 0)
communities_using_brute(gfg)
```

****输出:****

```
[ [0,1,2,3,4] ] , [ [8,9,5,6,7] ] 
```