# 被动攻击性量词

> 原文:[https://www . geesforgeks . org/被动-攻击-分类器/](https://www.geeksforgeeks.org/passive-aggressive-classifiers/)

被动-主动算法是机器学习算法的一个家族，初学者甚至是中级机器学习爱好者都不太了解它。然而，它们对于某些应用非常有用和有效。

**注意:**这是算法的高级概述，解释了它如何工作以及何时使用。它没有深入研究它是如何工作的。
被动-主动算法通常用于大规模学习。这是为数不多的在线学习算法之一。在在线机器学习算法中，输入数据按顺序出现，机器学习模型逐步更新，这与批处理学习相反，批处理学习一次性使用整个训练数据集。这在有大量数据的情况下非常有用，并且由于数据的巨大规模，训练整个数据集在计算上是不可行的。我们可以简单地说，一个在线学习算法会得到一个训练例子，更新分类器，然后扔掉这个例子。

这方面的一个很好的例子是在推特这样的社交媒体网站上检测假新闻，那里每秒钟都在添加新数据。要从推特上连续动态读取数据，数据将是巨大的，使用在线学习算法将是理想的。

被动-主动算法有点类似于感知器模型，因为它们不需要学习速率。然而，它们确实包括正则化参数。

**被动-主动算法是如何工作的:**
被动-主动算法之所以这么叫，是因为:

*   **被动:**如果预测正确，保留模型，不做任何改动。即示例中的数据不足以引起模型的任何变化。
*   **攻击性:**如果预测不正确，请更改模型。即模型的一些改变可以纠正它。

理解这个算法背后的数学不是很简单，超出了一篇文章的范围。本文只提供了算法的概述和简单的实现。要了解更多关于这个算法背后的数学知识，我推荐观看维克多·拉夫连科博士的这个关于算法工作的优秀视频。

**重要参数:**

*   这是正则化参数，表示模型对错误预测的惩罚
*   max_iter:模型对训练数据进行迭代的最大次数。
*   停止标准。如果设置为无，当(*丢失>先前 _ 丢失–tol*)时，模型将停止。默认情况下，它设置为 1e-3。

**在 Python3 中的简单实现**
虽然对于该算法的实际使用，需要巨大的数据流，但是为了这个例子，我们将使用流行的虹膜数据集。要了解更多关于此数据集的信息，您可以使用 go this [链接](https://archive.ics.uci.edu/ml/datasets/iris)。

**代码:Python 的 scikit-learn 库实现被动-主动分类器。**

```py
# Importing modules
from sklearn.datasets import load_iris
from sklearn.linear_model import PassiveAggressiveClassifier
from sklearn.metrics import classification_report, accuracy_score
from sklearn.model_selection import train_test_split

# Loading dataset
dataset = load_iris()
X = dataset.data
y = dataset.target

# Splitting iris dataset into train and test sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size = 0.1, random_state = 13)

# Creating model
model = PassiveAggressiveClassifier(C = 0.5, random_state = 5)

# Fitting model 
model.fit(X_train, y_train)

# Making prediction on test set
test_pred = model.predict(X_test)

# Model evaluation
print(f"Test Set Accuracy : {accuracy_score(y_test, test_pred) * 100} %\n\n")  

print(f"Classification Report : \n\n{classification_report(y_test, test_pred)}")
```

我们已经使用将正则化参数“C”设置为 0.5。现在让我们看看输出。
**输出:**

```py
Test Set Accuracy : 93.33333333333333 %

Classification Report : 

              precision    recall  f1-score   support

           0       1.00      1.00      1.00         4
           1       1.00      0.75      0.86         4
           2       0.88      1.00      0.93         7

    accuracy                           0.93        15
   macro avg       0.96      0.92      0.93        15
weighted avg       0.94      0.93      0.93        15
```

我们实现了 93.33%的测试集准确率。
**结论:**
如果你想研究大数据，这是一个非常重要的分类器，我鼓励你继续尝试使用这个分类器构建一个项目，并使用来自 Twitter 等社交媒体网站的实时数据作为输入。每秒钟都会有大量的数据进来，这个分类器将能够处理这种大小的数据。