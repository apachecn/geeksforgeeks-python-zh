# 开始使用 Python 进行自动交易

> 原文:[https://www . geeksforgeeks . org/自动交易 python 入门/](https://www.geeksforgeeks.org/getting-started-with-python-for-automated-trading/)

**自动交易**是通过计算机处理和执行的交易入口和出口的术语。自动化交易有一定的优势:

2.  **Minimizes human intervention: Automated trading systems eliminate emotions during trading. Traders usually have an easier time sticking to the strategy by holding emotions in check.**
3.  ****Backtesting on historical data: Backtesting allows a trader to employ their strategies on historical data (previous week/ month/ year data). This helps them understand the implications of their strategy on real-time data and help them determine the probability of winning or losing trade.****
4.  ******Preserving Discipline in a volatile market: When the market is volatile, traders jump the trading rules. This brings about indiscipline in the market. Discipline is lost when a trader gives in to the human emotion of greed or fear. Such parameters can be avoided with Automated trading. Automated trading helps ensure the maintenance of consistency, ensuring that execution of strategy follows rules.******
5.  ******提高订单输入的速度:因为计算机可以立即响应不断变化的市场条件，所以一旦交易要求得到满足，自动化系统就可以生成订单。******

******[Python](https://www.geeksforgeeks.org/python-programming-language/) 因其能够轻松构建复杂的统计模型而在量子金融中广受欢迎。这是因为像熊猫、NumPy、Matplotlib、PyAlgoTrade、Pybacktest 等科学图书馆。******

### ******自动化交易所需的组件******

2.  ******Anaconda: The first step in setting up Python is downloading Anaconda. Anaconda is a reliable distribution of Python, it consists of all tools and libraries, required to execute a Python code.******
3.  ******Spyder IDE: IDE stands for Integrated Development Environment. It provides an interface to write, debug, compile and execute the Python code.******
4.  ******Jupyter 笔记本:Jupyter 笔记本是一个用来理解代码片段的交互平台。Jupyter Notebook 主要使用“标记”单元格解释代码，使用“代码”单元格执行代码。对于试图理解代码片段工作原理的学习者来说，它非常有用。******

********注意:** Spyder IDE 用于运行和执行大项目，而 Jupyter Notebook 用于执行小块代码。******

### ****理解 Python 中关于量子交易的流行包/库****

****Python 有一个庞大的库集合，可以用于不同的功能，如编程、机器学习、可视化等。然而，在真正开始使用 Python 之前，我们将讨论编码交易策略所需的最重要的库。****

****我们将需要导入财务数据，进行数字评估，构建交易策略，绘制图表，并执行数据回溯测试。所需的库如下所示:****

2.  ******NumPy: NumPy shortened for NumericalPy is used for numerical analysis of data.******
3.  ******Pandas: Pandas is widely used when working with data in tabular format (i.e rows and columns) such as spreadsheets. It can be used to import Excel and CSV files in the python code.******
4.  ******Matplotlib: This library comprises functions used for plotting 2D graphs.******
5.  ******TA-Lib: TA-Lib is extensively used to perform technical analysis on data such as Bollinger Bands, RSI (Relative Strength Indicator), VWAP (Volume Weighted Average), MA (Moving Average).******
6.  ******Zipline:一个支持回溯测试和实时交易的事件驱动系统。******

******在开始用 Python 构建自己的策略之前，您需要了解以下几个基本概念。******

********参考文献:********

1.  ****https://num py . org/****
2.  ****[https://matplotlib.org/](https://matplotlib.org/)****
3.  ****[https://pandas . pydata . org/](https://pandas.pydata.org/)****
4.  ****[https://www.zipline.io/](https://www.zipline.io/)****
5.  ****[https://github . com/mrjbq 7/ta-lib](https://github.com/mrjbq7/ta-lib)****