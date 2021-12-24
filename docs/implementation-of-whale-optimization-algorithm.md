# 鲸鱼优化算法的实现

> 原文:[https://www . geeksforgeeks . org/实现鲸鱼优化算法/](https://www.geeksforgeeks.org/implementation-of-whale-optimization-algorithm/)

前一篇[鲸鱼优化算法(WOA)](https://www.geeksforgeeks.org/whale-optimization-algorithm-woa/) 讲了鲸鱼优化的启发，它的数学建模和算法。在本文中，我们将为两个适应度函数实现一个鲸鱼优化算法(WOA)1)[拉斯特里金函数](https://en.wikipedia.org/wiki/Rastrigin_function#:~:text=In%20mathematical%20optimization%2C%20the%20Rastrigin,has%20been%20generalized%20by%20Rudolph.) 2)球体函数该算法将运行预定次数的最大迭代，并将尝试找到这些适应度函数的最小值。

## 健身功能

### 1) [Rastrigin 功能](https://en.wikipedia.org/wiki/Rastrigin_function#:~:text=In%20mathematical%20optimization%2C%20the%20Rastrigin,has%20been%20generalized%20by%20Rudolph.)

Rastrigin 函数是一个非凸函数，经常被用作优化算法的性能测试问题。

#### 函数方程:

![f(x_1 \cdots x_n) = 10n + \sum_{i=1}^n (x_i^2 -10cos(2\pi x_i))](img/d29dc02ad7673069510c1ece10768965.png "Rendered by QuickLaTeX.com")

![\text{minimum at }f(0, \cdots, 0) = 0](img/d49f8c2a15d0d6b2b58ac3a6ed8ba615.png "Rendered by QuickLaTeX.com")

![](img/96c4510681384c451b01fe8b2c6f4e51.png)

图 1:两个变量的 Rastrigin 函数

对于优化算法来说，rastrigin 函数是一个非常具有挑战性的函数。它的复杂行为导致优化算法经常陷入局部极小值。平面上有很多余弦振荡会给这个函数带来复杂的行为。

### 2)球面函数

球面函数是评估优化算法性能的标准函数。

#### 函数方程:

![f(x_1 \cdots x_n) = \sum_{i=1}^n x_i^2](img/ebe8eed46597f2fd6ae5a1e85aca2c27.png "Rendered by QuickLaTeX.com")

![\text{minimum at }f(0, \cdots, 0) = 0](img/d49f8c2a15d0d6b2b58ac3a6ed8ba615.png "Rendered by QuickLaTeX.com")

![](img/ab7340fc032364aef85fdf53e650c655.png)

图 2:两个变量的球函数

## 超参数的选择

### 问题参数:

*   尺寸数量( **d** ) = 3
*   下限( **minx** ) = -10.0
*   上限( **maxx** ) = 10.0

### 算法的超参数:

*   粒子数( **N** ) = 50
*   最大迭代次数( **max_iter** ) = 100
*   螺旋系数( **b** ) = 1

### 输入

*   健身功能
*   问题参数(如上所述)
*   群体大小( **N** )和最大迭代次数( **max_iter** )
*   算法特定超参数 **b**

## 算法

鲸鱼优化的算法和数学方程已经在[之前的文章](https://www.geeksforgeeks.org/whale-optimization-algorithm-woa/)中描述过了。

## 履行

## 蟒蛇 3

```py
# python implementation of whale optimization algorithm (WOA)
# minimizing rastrigin and sphere function

import random
import math  # cos() for Rastrigin
import copy  # array-copying convenience
import sys  # max float

# -------fitness functions---------

# rastrigin function
def fitness_rastrigin(position):
    fitness_value = 0.0
    for i in range(len(position)):
        xi = position[i]
        fitness_value += (xi * xi) - (10 * math.cos(2 * math.pi * xi)) + 10
    return fitness_value

# sphere function
def fitness_sphere(position):
    fitness_value = 0.0
    for i in range(len(position)):
        xi = position[i]
        fitness_value += (xi * xi);
    return fitness_value;

# -------------------------

# whale class
class whale:
    def __init__(self, fitness, dim, minx, maxx, seed):
        self.rnd = random.Random(seed)
        self.position = [0.0 for i in range(dim)]

        for i in range(dim):
            self.position[i] = ((maxx - minx) * self.rnd.random() + minx)

        self.fitness = fitness(self.position)  # curr fitness

# whale optimization algorithm(WOA)
def woa(fitness, max_iter, n, dim, minx, maxx):
    rnd = random.Random(0)

    # create n random whales
    whalePopulation = [whale(fitness, dim, minx, maxx, i) for i in range(n)]

    # compute the value of best_position and best_fitness in the whale Population
    Xbest = [0.0 for i in range(dim)]
    Fbest = sys.float_info.max

    for i in range(n):  # check each whale
        if whalePopulation[i].fitness < Fbest:
            Fbest = whalePopulation[i].fitness
            Xbest = copy.copy(whalePopulation[i].position)

    # main loop of woa
    Iter = 0
    while Iter < max_iter:

        # after every 10 iterations
        # print iteration number and best fitness value so far
        if Iter % 10 == 0 and Iter > 1:
            print("Iter = " + str(Iter) + " best fitness = %.3f" % Fbest)

        # linearly decreased from 2 to 0
        a = 2 * (1 - Iter / max_iter)
        a2=-1+Iter*((-1)/max_iter)

        for i in range(n):
            A = 2 * a * rnd.random() - a
            C = 2 * rnd.random()
            b = 1
            l = (a2-1)*rnd.random()+1;
            p = rnd.random()

            D = [0.0 for i in range(dim)]
            D1 = [0.0 for i in range(dim)]
            Xnew = [0.0 for i in range(dim)]
            Xrand = [0.0 for i in range(dim)]
            if p < 0.5:
                if abs(A) > 1:
                    for j in range(dim):
                        D[j] = abs(C * Xbest[j] - whalePopulation[i].position[j])
                        Xnew[j] = Xbest[j] - A * D[j]
                else:
                    p = random.randint(0, n - 1)
                    while (p == i):
                        p = random.randint(0, n - 1)

                    Xrand = whalePopulation[p].position

                    for j in range(dim):
                        D[j] = abs(C * Xrand[j] - whalePopulation[i].position[j])
                        Xnew[j] = Xrand[j] - A * D[j]
            else:
                for j in range(dim):
                    D1[j] = abs(Xbest[j] - whalePopulation[i].position[j])
                    Xnew[j] = D1[j] * math.exp(b * l) * math.cos(2 * math.pi * l) + Xbest[j]

            for j in range(dim):
                whalePopulation[i].position[j] = Xnew[j]

        for i in range(n):
            # if Xnew < minx OR Xnew > maxx
            # then clip it
            for j in range(dim):
                whalePopulation[i].position[j] = max(whalePopulation[i].position[j], minx)
                whalePopulation[i].position[j] = min(whalePopulation[i].position[j], maxx)

            whalePopulation[i].fitness = fitness(whalePopulation[i].position)

            if (whalePopulation[i].fitness < Fbest):
                Xbest = copy.copy(whalePopulation[i].position)
                Fbest = whalePopulation[i].fitness

        Iter += 1
    # end-while

    # returning the best solution
    return Xbest

# ----------------------------

# Driver code for rastrigin function

print("\nBegin whale optimization algorithm on rastrigin function\n")
dim = 3
fitness = fitness_rastrigin

print("Goal is to minimize Rastrigin's function in " + str(dim) + " variables")
print("Function has known min = 0.0 at (", end="")
for i in range(dim - 1):
    print("0, ", end="")
print("0)")

num_whales = 50
max_iter = 100

print("Setting num_whales = " + str(num_whales))
print("Setting max_iter    = " + str(max_iter))
print("\nStarting WOA algorithm\n")

best_position = woa(fitness, max_iter, num_whales, dim, -10.0, 10.0)

print("\nWOA completed\n")
print("\nBest solution found:")
print(["%.6f" % best_position[k] for k in range(dim)])
err = fitness(best_position)
print("fitness of best solution = %.6f" % err)

print("\nEnd WOA for rastrigin\n")

print()
print()

# Driver code for Sphere function
print("\nBegin whale optimization algorithm on sphere function\n")
dim = 3
fitness = fitness_sphere

print("Goal is to minimize sphere function in " + str(dim) + " variables")
print("Function has known min = 0.0 at (", end="")
for i in range(dim - 1):
    print("0, ", end="")
print("0)")

num_whales = 50
max_iter = 100

print("Setting num_whales = " + str(num_whales))
print("Setting max_iter    = " + str(max_iter))
print("\nStarting WOA algorithm\n")

best_position = woa(fitness, max_iter, num_whales, dim, -10.0, 10.0)

print("\nWOA completed\n")
print("\nBest solution found:")
print(["%.6f" % best_position[k] for k in range(dim)])
err = fitness(best_position)
print("fitness of best solution = %.6f" % err)

print("\nEnd WOA for sphere\n")
```

## 输出

```py
Begin whale optimization algorithm on rastrigin function

Goal is to minimize Rastrigin's function in 3 variables
Function has known min = 0.0 at (0, 0, 0)
Setting num_whales = 50
Setting max_iter    = 100

Starting WOA algorithm

Iter = 10 best fitness = 0.018
Iter = 20 best fitness = 0.000
Iter = 30 best fitness = 0.000
Iter = 40 best fitness = 0.000
Iter = 50 best fitness = 0.000
Iter = 60 best fitness = 0.000
Iter = 70 best fitness = 0.000
Iter = 80 best fitness = 0.000
Iter = 90 best fitness = 0.000

WOA completed

Best solution found:
['0.000000', '-0.000000', '-0.000000']
fitness of best solution = 0.000000

End WOA for rastrigin

Begin whale optimization algorithm on sphere function

Goal is to minimize sphere function in 3 variables
Function has known min = 0.0 at (0, 0, 0)
Setting num_whales = 50
Setting max_iter    = 100

Starting WOA algorithm

Iter = 10 best fitness = 0.130
Iter = 20 best fitness = 0.000
Iter = 30 best fitness = 0.000
Iter = 40 best fitness = 0.000
Iter = 50 best fitness = 0.000
Iter = 60 best fitness = 0.000
Iter = 70 best fitness = 0.000
Iter = 80 best fitness = 0.000
Iter = 90 best fitness = 0.000

WOA completed

Best solution found:
['0.000000', '0.000000', '-0.000000']
fitness of best solution = 0.000000

End WOA for sphere
```

### 参考文献:

**研究论文:**https://www . science direct . com/science/article/pii/S0965997816300163

**作者原创实现(在 MATLAB 中):**https://www . mathworks . com/matlabcentral/file exchange/55667-the-whale-optimization-algorithm