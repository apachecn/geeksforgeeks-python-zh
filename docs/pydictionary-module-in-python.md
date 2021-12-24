# Python 中的 PyDictionary 模块

> 原文:[https://www . geesforgeks . org/py dictionary-python 中的模块/](https://www.geeksforgeeks.org/pydictionary-module-in-python/)

**PyDictionary** 是 Python2 和 Python3 的词典(如英语词典中)模块。PyDictionary 为一个单词提供以下服务:

*   含义
*   翻译

### 装置

要安装 PyDictionary，请在终端/命令提示符下运行以下`pip`代码:

```py
pip install PyDictionary
```

### 入门指南

现在让我们看看如何使用 PyDictionary 模块。首先我们需要导入模块:

```py
from PyDictionary import PyDictionary

```

导入模块后，我们需要创建它的一个实例来使用它:

```py
dict = PyDictionary()

```

要得到一个单词的意思，我们需要在`meaning()`方法中传递这个单词。

**示例:**

```py
from PyDictionary import PyDictionary

dict = PyDictionary()

# meaning of "python"
meaning = dict.meaning("python")
print(meaning)
```

**输出:**

> { '名词':['大的东半球的神灵'，'一种占卜的神灵或被这种神灵附身的人'，'(希腊神话']}

如果一个单词既是名词又是动词，那么该方法将返回一个包含关键字“名词”和“动词”的字典。

**示例:**

```py
from PyDictionary import PyDictionary

dict = PyDictionary()

# meaning of "test"
meaning = dict.meaning("test")
print(meaning)
```

**输出:**

> { '名词':['试图找出某事物'，'测量敏感度、记忆力、智力、天资或个性等的任何标准化程序'，'评估技能或知识的一组问题或练习'，'接受测试的行为'，'测试某事物的行为'，'某些变形虫和海胆的坚硬外壳'，'动词':['进行测试，如测试其质量，或进行实验使用'，'测试或检查疾病或感染的存在'， “检查某人对某事物的了解程度”，“在测试时表现出某种特征”，“在测试中获得某种分数或等级”，“确定(某种物质的)存在或性质”，“接受测试”]}

要获得一个单词的翻译，我们需要将`translate()`方法中的单词作为第一个参数传递，要翻译成的语言作为第二个参数传递。语言的名称应该在其各自的语言代码中。

```py
from PyDictionary import PyDictionary

dict = PyDictionary()

# to translate into German
translation = dict.translate("happy",'de')
print(translation)
```

**输出:**

```py
glücklich
```