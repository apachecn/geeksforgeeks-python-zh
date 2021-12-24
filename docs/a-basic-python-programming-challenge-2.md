# 一个基本的 Python 编程挑战

> 原文:[https://www . geesforgeks . org/a-basic-python-编程-挑战赛-2/](https://www.geeksforgeeks.org/a-basic-python-programming-challenge-2/)

嘿伙计们！我带着另一篇文章回来了，那是我之前关于安全编码的文章。这次我们不打算讨论任何理论问题。几个月前，我用 Python 为我的学生编写了一个程序，这样他们就可以练习基本的 BODMAS 问题。目的是让程序生成随机的问题集(用户输入的问题数量)，然后检查输入的答案是否正确。很明显，对我来说编码很容易，但是，问题是我必须确保 5/2 = 2.5 和 2.500 一样正确。所以，我就是不能去配两根弦。我必须想出一个不同的解决办法。只是为了玩得开心，看看我的学生或志愿者中有没有人能想出程序中的漏洞，我专门写了一个弱程序。现在，我已经修改了程序，使你们更容易识别其中的错误和漏洞。

现在，我要你做的是:

1.  **Don't look at the code. Compile it, run it, and see if you can find out the loopholes in the code.**
2.  **If you can't find the vulnerability in the first step, or even if you do, look at the program code and try to find out what you missed!**

完成后，请评论您认为代码中的漏洞是什么，以及您将如何纠正它们！

开始了。！

给定输入:

```
3
6
-1

```

**小基础 python 挑战程序**

```
## Note: This program has been modified a bit for
## GeeksForGeeks article
import random,operator
print ('===========================================')

def randomCalc(i,j):
    ops = {'+':operator.add,
          '-':operator.sub,
          '*':operator.mul,
          '/':operator.truediv }
    num = [1,2,3,4]
    num1,num2 = num[i],num[j]
    op = (list(ops.keys()))[i]
    answer = round(ops.get(op)(num1,num2),3)
    print('What is {} {} {}?\n'.format(num1, op, num2))
    return answer

def askQuestion(i):
    answer = randomCalc(i,i+1)
    guess = float(input())
    return guess == answer,answer

def quiz(numOfQues):
    print('\nWelcome. This is a '+str(numOfQues)+' question math quiz.')
    print('Your answer should be correct to three decimal places.\n')
    score = 0
    for i in range(numOfQues):
        correct,ans = askQuestion(i)
        if correct:
            score += 1
            print('Correct!\n')
        else:
            print('Incorrect! The correct answer is ' + str(ans)+'\n')
    return ('Your score was {}/'+str(numOfQues)).format(score)

# Driver Code
print (quiz(3))
```

### 输出:

```
===========================================

Welcome. This is a 3 question math quiz
 Your answer should be correct to three decimal places.

What is 1 + 2?

Correct!

What is 2 * 3?

Correct!

What is 3 - 4?

Correct!

Your score was 3/3

```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论！！

**关于作者:**

**维斯韦什·施里马里**是 BITS Pilani 的机械工程本科生。他满足了所有没有在他的分支机构教过的要求——白帽黑客、网络安全操作员和前竞争性程序员。作为 Python 力量的坚定信仰者，他的大部分作品都是同一种语言。每当他除了编程、上课、看 CSI Cyber 之外有时间的时候，他都会去散步，默默地弹吉他。他的人生格言是——“享受你的生活，因为它值得享受！”

**如果你也想在这里展示你的博客，请查看[博客](http://geeksquiz.com/gblog/)在极客博客上的客座博文。**