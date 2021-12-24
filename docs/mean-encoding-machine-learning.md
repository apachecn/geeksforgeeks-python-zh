# 均值编码-机器学习

> 原文:[https://www . geesforgeks . org/mean-encoding-machine-learning/](https://www.geeksforgeeks.org/mean-encoding-machine-learning/)

在特征工程中，将分类特征转换为数字特征的任务称为编码。
有各种方法来处理分类特征，如 **OneHotEncoding** 和**label lencoding**、 **FrequencyEncoding** 或通过分类特征的计数来替换分类特征。类似地，我们可以使用**表示编码**。

创建了一个具有两个特征的数据框，这两个特征名为*主题*和*目标*，我们可以看到其中一个特征(主题名)是分类的，因此我们通过应用均值编码将其转换为数字特征。
代码:

```
# importing libraries
import pandas as pd

# creating dataset
data={'SubjectName':['s1','s2','s3','s1','s4','s3','s2','s1','s2','s4','s1'],
      'Target':[1,0,1,1,1,0,0,1,1,1,0]}

df = pd.DataFrame(data)

print(df)
```

****输出:****

```
 SubjectName  Target
0    s1    1
1    s2    0
2    s3    1
3    s1    1
4    s4    1
5    s3    0
6    s2    0
7    s1    1
8    s2    1
9    s4    1
10    s1    0 
```

****代码:统计主题名称**中的每个数据点**

```
df.groupby(['SubjectName'])['Target'].count()
```

****输出:****

```
subjectName
 s1         4
 s2         3
 s3         2
 s4         2
Name: Target, dtype: int64 
```

****编码:根据正目标值将主题名为平均值的数据分组****

```
df.groupby(['SubjectName'])['Target'].mean()
```

****输出:****

```
subjectName
s1         0.750000
s2         0.333333
s3         0.500000
s4         1.000000
Name: Target, dtype: float64 
```

**输出显示了主题名称中数据点映射的平均值及其正目标值(1-正和 0-负)。**

****代码:最后赋值平均值，用 *df['SubjectName']*** 映射**

```
Mean_encoded_subject = df.groupby(['SubjectName'])['Target'].mean().to_dict()

df['SubjectName'] =  df['SubjectName'].map(Mean_encoded_subject)

print(df)
```

****输出:平均编码数据****

```
 SubjectName    Target
0    0.750000    1
1    0.333333    0
2    0.500000    1
3    0.750000    1
4    1.000000    1
5    0.500000    0
6    0.333333    0
7    0.750000    1
8    0.333333    1
9    1.000000    1
10    0.750000    0 
```

****含义编码的优点:****

*   **捕获标签中的信息，从而呈现更多的预测特征**
*   **在变量和目标之间创建单调关系**

****意义的缺点挖掘:****

*   **它可能会导致模型中的过度拟合。**