# 生物节律–顺序操作

> 原文:[https://www . geesforgeks . org/bio Tyson-sequence-operations/](https://www.geeksforgeeks.org/biopython-sequence-operations/)

[**【bio ython】**](https://www.geeksforgeeks.org/introduction-to-biopython/)**模块提供了各种内置方法，通过这些方法我们可以对序列执行各种基本和高级操作。基本操作与*切片、拼接、查找、计数、剥离、拆分、*等字符串方法非常相似。下面列出了一些高级操作**

****补体和反向补体:**bio ython 提供了**补体()**和**反向 _ 补体()**功能，可以用来寻找给定核苷酸序列的补体，得到新的序列，而被补足的序列也可以被反向补足，得到原始序列。下面是所描述函数的一个简单示例:**

> ****句法**:补语(自)**
> 
>  ****返回类型** : <类‘生物’。序列'>**

## **蟒蛇 3**

```py
# Import Libraries
from Bio.Seq import Seq
from Bio.Alphabet import IUPAC

# Creating sequence
seq = Seq('CTGACTGAAGCT', IUPAC.ambiguous_dna)

# Creating complement of the sequence and print
comp = seq.complement()
comp

# Creating reverse complement and print
rev_comp = comp.reverse_complement()
rev_comp
```

****输出:****

```py
Seq('GACTGACTTCGA', IUPACAmbiguousDNA()) 
Seq('TCGAAGTCAGTC', IUPACAmbiguousDNA())
```

**在上例中，complex()方法创建了 DNA 或 RNA 序列的补码，而**reverse _ complex()**函数创建了序列的补码，并将结果从左向右反转。**

****生物。biopython 的**模块提供了**二义性 _ dna _ 补体**变量，用于执行补体操作。**

## **蟒蛇 3**

```py
# Import libraries
from Bio.Data import IUPACData
import pprint

# Printing the dataset
pprint.pprint(IUPACData.ambiguous_dna_complement)
```

****输出:****

```py
{
   'A': 'T',
   'B': 'V',
   'C': 'G',
   'D': 'H',
   'G': 'C',
   'H': 'D',
   'K': 'M',
   'M': 'K',
   'N': 'N',
   'R': 'Y',
   'S': 'S',
   'T': 'A',
   'V': 'B',
   'W': 'W',
   'X': 'X',
   'Y': 'R'} 
```

****GC 含量(鸟嘌呤-胞嘧啶含量):** GC 含量基本上是 DNA 或 RNA 分子中含氮碱基的百分比，这种分子或者是鸟嘌呤，或者是胞嘧啶。可以通过计算 GC 核苷酸数除以核苷酸总数来预测。以下是计算气相色谱含量的基本示例:**

> ****语法** : Bio。顺序气相色谱**
> 
> ****返回类型** : <类【浮动】>**

## **蟒蛇 3**

```py
# Import Libraries
from Bio.Seq import Seq
from Bio.SeqUtils import GC
from Bio.Alphabet import IUPAC

# Creating sequence
seq = Seq("CTGACTGAAGCT", IUPAC.unambiguous_dna)

# Getting GC count
print(GC(seq))
```

****输出:****

```py
50.00
```

****转录:**基本上是将一个 DNA 转化为一个 RNA 序列的过程。实际的生物转录是一个进行反向互补(GACT - > AGUC)以获得以脱氧核糖核酸为模板链的基因的过程。在**生物节律**中，通过简单地将字母 *T* 改为 *U* ，碱基 DNA 链直接转化为 mRNA。下面给出了一个简单的例子:**

> ****语法**:转录(自)**
> 
> ****返回类型:** <类‘生物’。>T2**

## **蟒蛇 3**

```py
# Import Libraries
from Bio.Seq import Seq
from Bio.Seq import transcribe
from Bio.Alphabet import IUPAC

# Creating sequence
dna_seq = Seq("CTGACTGAAGCT", IUPAC.unambiguous_dna)

# Transcription to RNA
print(transcribe(dna_seq))

# Reverse Transcription to DNA
rna_seq = transcribe(dna_seq)
print(rna_seq.back_transcribe())
```

****输出:-****

```py
Seq('CUGACUGAAGCU', IUPACUnambiguousRNA())
Seq('CTGACTGAAGCT', IUPACUnambiguousDNA())
```

****翻译:**是将 RNA 序列翻译成蛋白质序列的过程。序列模块内置了用于此目的的 **translate()** 方法。如果我们必须在第一个密码子停止翻译，可以通过将 **to_stop = True** 参数传递给 translation()方法。**

**Biopython 使用 **NCBI 遗传密码页面提供的翻译表。**翻译表完整列表如下:**

> ****语法** : translate(self，table='Standard '，stop_symbol='* '，to_stop=False，cds=False，gap = '-')
> **Return Type**:<class ' Bio。序列序列'>**

## **蟒蛇 3**

```py
# import libraries
from Bio.Data import CodonTable

# Creating table
table = CodonTable.unambiguous_dna_by_name["Standard"]

# Print table
print(table)
```

****输出:****

```py
Table 1 Standard, SGC0

  |  T      |  C      |  A      |  G      |
--+---------+---------+---------+---------+--
T | TTT F   | TCT S   | TAT Y   | TGT C   | T
T | TTC F   | TCC S   | TAC Y   | TGC C   | C
T | TTA L   | TCA S   | TAA Stop| TGA Stop| A
T | TTG L(s)| TCG S   | TAG Stop| TGG W   | G
--+---------+---------+---------+---------+--
C | CTT L   | CCT P   | CAT H   | CGT R   | T
C | CTC L   | CCC P   | CAC H   | CGC R   | C
C | CTA L   | CCA P   | CAA Q   | CGA R   | A
C | CTG L(s)| CCG P   | CAG Q   | CGG R   | G
--+---------+---------+---------+---------+--
A | ATT I   | ACT T   | AAT N   | AGT S   | T
A | ATC I   | ACC T   | AAC N   | AGC S   | C
A | ATA I   | ACA T   | AAA K   | AGA R   | A
A | ATG M(s)| ACG T   | AAG K   | AGG R   | G
--+---------+---------+---------+---------+--
G | GTT V   | GCT A   | GAT D   | GGT G   | T
G | GTC V   | GCC A   | GAC D   | GGC G   | C
G | GTA V   | GCA A   | GAA E   | GGA G   | A
G | GTG V   | GCG A   | GAG E   | GGG G   | G
--+---------+---------+---------+---------+--
```

**下面给出了一个简单的**翻译示例:****

## **蟒蛇 3**

```py
# Import Libraries
from Bio.Seq import Seq
from Bio.Alphabet import IUPAC

# Creating sequence
rna = Seq('UACCGGAUUGUUUUCCCGGGCUGAUCCUGUGCCCGA', IUPAC.unambiguous_rna)
print(rna)

# Translating RNA
print(rna.translate())

# Stop translation to first stop codon ( asterisk '*' is stop codon)
print(rna.translate(to_stop = True))
```

****输出:****

```py
Seq('UACCGGAUUGUUUUCCCGGGCUGAUCCUGUGCCCGA', IUPACUnambiguousRNA())
Seq('YRIVFPG*SCAR', HasStopCodon(IUPACProtein(), '*'))
Seq('YRIVFPG', IUPACProtein())
```