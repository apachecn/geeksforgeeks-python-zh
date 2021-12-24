# 使用 Python 中的格文纽曼算法检测社交网络中的社区

> 原文:[https://www . geesforgeks . org/detecting-communities-in-social-networks-use-gir van-Newman-algorithm-in-python/](https://www.geeksforgeeks.org/detecting-communities-in-social-networks-using-girvan-newman-algorithm-in-python/)

**先决条件**–[Python 基础知识](https://www.geeksforgeeks.org/python-programming-language/)、[网络基础知识](https://www.geeksforgeeks.org/introduction-to-social-networks-using-networkx-in-python/)

我们将使用格文纽曼算法把图的节点分成两个或更多的社区。格文纽曼算法删除中间值最高的边，直到没有剩余的边。**介数**是穿过它的节点对之间的最短路径数。

我们将使用格文纽曼算法来完成这项任务。

**算法:**

1.  创建一个由 N 个节点及其边组成的图，或者像杠铃图那样的内置图。
2.  计算图中所有现有边的介数。
3.  现在移除所有介数最高的边。
4.  现在重新计算所有受移除边影响的边的介数。
5.  现在重复第 3 步和第 4 步，直到没有剩余的边。

**Python 代码:**

## 蟒蛇 3

```py
import networkx as nx

def edge_to_remove(g):

    d1 = nx.edge_betweenness_centrality(g)
    list_of_tuples = list(d1.items())

    sorted(list_of_tuples, key = lambda x:x[1], reverse = True)

    # Will return in the form (a,b)
    return list_of_tuples[0][0]

def girvan(g):
    a = nx.connected_components(g)
    lena = len(list(a))
    print (' The number of connected components are ', lena)
    while (lena == 1):

        # We need (a,b) instead of ((a,b))
        u, v = edge_to_remove(g)
        g.remove_edge(u, v) 

        a = nx.connected_components(g)
        lena=len(list(a))
        print (' The number of connected components are ', lena)

    return a

# Driver Code
g = nx.barbell_graph(5,0)
a = girvan(g)
print ('Barbell Graph')

for i in a:
    print (i.nodes())
    print ('.............')

g1 = nx.karate_club_graph()
a1 = girvan(g1)

print ('Karate Club Graph')
for i in a1:
    print (i.nodes())
    print ('.............')
```

**输出:**

> 杠铃图
> 
> 连接组件的数量为 1
> 
> 连接的组件数量为 2
> 
> [0, 1, 2, 3, 4]
> 
> ………….
> 
> [8, 9, 5, 6, 7]
> 
> ………….
> 
> 空手道俱乐部图表
> 
> 连接组件的数量为 1
> 
> 连接组件的数量为 1
> 
> 连接组件的数量为 1
> 
> 连接组件的数量为 1
> 
> 连接组件的数量为 1
> 
> 连接组件的数量为 1
> 
> 连接组件的数量为 1
> 
> 连接组件的数量为 1
> 
> 连接组件的数量为 1
> 
> 连接组件的数量为 1
> 
> 连接组件的数量为 1
> 
> 连接的组件数量为 2
> 
> [32, 33, 2, 8, 9, 14, 15, 18, 20, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31]
> 
> ………….
> 
> [0, 1, 3, 4, 5, 6, 7, 10, 11, 12, 13, 16, 17, 19, 21]
> 
> ………….