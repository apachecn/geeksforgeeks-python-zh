# 覆盖 Python 中的嵌套类成员

> 原文:[https://www . geeksforgeeks . org/overriding-nested-class-members-in-python/](https://www.geeksforgeeks.org/overriding-nested-class-members-in-python/)

覆盖是面向对象编程的概念，通常我们在继承中处理这个概念。方法重写是任何面向对象编程语言的一种能力，它允许子类或子类提供某个方法的特定实现，而该方法已经由其超类或父类之一提供。

让我们考虑一个现实生活中的例子，其中基因嵌入了下一代的特征，每一代都有自己的特征，它们在基因的帮助下传递给其他几代人。这里我们采用一个基因类和一个嵌套类 Trait。特质类有一些特质，比如走路、头发和疾病，以及它们的价值。这些基因会转移到子类，子类可能有自己的一些特征，有些会从父类继承。这个功能可以在重写嵌套类成员的帮助下实现。

**例:**

```
# Genes are like messages in human 
# body which transfers from parent to 
# child. Same thing we have used here
# to show the real implementation of 
# above concept in python.

class Genes:

    # Inner class
    class Trait:
        walk ='Fast'
        hair ='Black'
        disease =('Diabetes', 'Migraine', 'TB')

class child(Genes):

    # Inner class
    class Trait(Genes.Trait):
        walk ='Fast'
        hair ='Black'
        disease =('Typhoid', ) + Genes.Trait.disease

# Driver's code
print(Genes.Trait.disease)
print(child.Trait.disease)
```

**输出:**

```
('Diabetes', 'Migraine', 'TB')
('Typhoid', 'Diabetes', 'Migraine', 'TB')>

```

**注意:**只有在必要的时候才使用嵌套类，否则只会让你的代码变得复杂，难以调试。