# 使用 SimPy 进行离散事件模拟的基础知识

> 原文:[https://www . geesforgeks . org/basic-of-discrete-event-simpy-simpy/](https://www.geeksforgeeks.org/basics-of-discrete-event-simulation-using-simpy/)

SimPy 是用 Python 编写的一个强大的基于流程的离散事件仿真框架。

**安装:**
要安装 SimPy，请使用以下命令–

```py
pip install simpy
```

**基本概念:**

SimPy 背后的核心思想是 Python 中的生成器函数。普通函数和生成器的区别在于普通函数使用“return”语句，而生成器使用“yield”语句。

如果函数有一个 return 语句，那么即使在多次函数调用中，它也会返回相同的值。对于 eg–

```py
def func():
    return 1
    return 2
```

在运行时调用 func()时，它总是在 return 语句的第一个实例返回，也就是说，func()函数总是返回 1，下一个 return 语句永远不会执行。

但是，在离散事件仿真中，我们可能需要找到系统在给定时间 T 的状态，为此，需要记住刚好在 T 之前的区间的状态，然后执行给定的仿真并在时间 T 返回状态。

这就是生成器函数非常有用的地方。例如，考虑以下函数

```py
def func():
    while True:
        yield 1
        yield 2
```

现在，当第一次调用这个函数时，它“产生”1。然而，在下一次调用时，它将产生 2。从某种意义上说，它记得上一次调用时返回了什么，并继续下一个 yield 语句。

SimPy 中的事件称为**进程**，它们由自己的生成器函数定义。这些过程发生在**环境**中。(把环境想象成一个大盒子，里面保存着流程。)

考虑一个简单的例子，包括交通灯的模拟–

```py
# Python 3 code to demonstrate basics of SimPy package 
# Simulation of a Traffic Light 

# import the SimPy package 
import simpy 

# Generator function that defines the working of the traffic light 
# "timeout()" function makes next yield statement wait for a 
# given time passed as the argument 
def Traffic_Light(env): 

    while True: 

        print ("Light turns GRN at " + str(env.now)) 

        # Light is green for 25 seconds 
        yield env.timeout(25)         

        print ("Light turns YEL at " + str(env.now))

        # Light is yellow for 5 seconds 
        yield env.timeout(5) 

        print ("Light turns RED at " + str(env.now)) 

        # Light is red for 60 seconds 
        yield env.timeout(60) 

# env is the environment variable 
env = simpy.Environment()         

# The process defined by the function Traffic_Light(env) 
# is added to the environment 
env.process(Traffic_Light(env)) 

# The process is run for the first 180 seconds (180 is not included) 
env.run(until = 180) 
```

**输出:**

```py
Light turns GRN at 0
Light turns YEL at 25
Light turns RED at 30
Light turns GRN at 90
Light turns YEL at 115
Light turns RED at 120

```

在这段代码中，生成器函数 Traffic_Light(env)将环境变量作为参数，并模拟在 env.run()函数中作为参数传递的时间段内红绿灯的操作。(实际上，SimPy 中的时间是没有单位的。尽管它可以根据方便转换成小时、分钟或秒)。env.now 返回经过时间的当前值。

env.timeout()函数是此模拟的基础，因为它等待作为参数传递的时间在计算机的模拟时钟上过去(它不是实时时钟)，然后启动下一个 yield 语句，直到 env.run()中作为参数传递的时间结束。

env.run()同时启动所有链接到环境的进程= 0。