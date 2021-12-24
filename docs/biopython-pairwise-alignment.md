# 生物节律–成对排列

> 原文:[https://www.geeksforgeeks.org/biopython-pairwise-alignment/](https://www.geeksforgeeks.org/biopython-pairwise-alignment/)

成对序列比对是一次比较两个序列并提供最佳可能序列比对的过程。成对序列比对使用动态编程算法。Biopython 有一个特殊的模块 *Bio.pairwise2* ，它使用成对方法识别比对序列。与其他软件相比，Biopython 提供了寻找比对序列的最佳算法。

让我们以两个简单且假设的序列为例，使用成对模块。

## 蟒 3

```py
# Import libraries
from Bio import pairwise2
from Bio.Seq import Seq

# Creating sample sequences
seq1 = Seq("TGTGACTA")
seq2 = Seq("CATGGTCA")

# Finding similarities
alignments = pairwise2.align.globalxx(seq1, seq2)

# Showing results
for match in alignments:
    print(match)
```