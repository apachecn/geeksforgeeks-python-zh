# 详细分析动态类型和并发对 Python 的影响？

> 原文:[https://www . geeksforgeeks . org/详细分析动态类型化的影响和 python 的并发性/](https://www.geeksforgeeks.org/detailed-analysis-on-affects-of-dynamic-typing-and-concurrency-on-python/)

python 是不是太慢了？事实是，Python 是一种极其缓慢的编程语言，当我们看到像 Java、C 和 C++这样的东西时，很尴尬他们做事情的速度比 Python 快得多，事实上， 具体的算法和应用程序实际上可以比原生 Python 语言快 100 到 200 倍左右，所以在本文中，我们将讨论为什么会这样，以及作为 Python 程序员，我们可以使用哪些不同的技术来加速和运行更多并发的 Python 应用程序，现在，在我们走得太远之前，值得注意的是，尽管 Python 缺乏速度，但它弥补了这一点，在开发中，用 Python 开发程序要快得多， 更简单，成本更低，因为现在项目涉及的劳动力更少，这是一个巨大的优势，在许多情况下，您实际上可以用 Python 编写相当于 JAVA 的代码，比用那种语言快 4 到 5 倍，所以这是需要考虑的事情？

### **Python 为什么慢？**

这种语言(Python)慢的主要原因不是 [全局解释器锁定](https://www.geeksforgeeks.org/what-is-the-python-global-interpreter-lock-gil/) 虽然这是速度的一个因素，也是我们可以编写更快的 Python 程序的方式，但这并不是这种语言慢的根本原因。Python 之所以慢，是因为它是**动态类型的**现在我们将更详细地讨论这一点，但我们想与像 Java 这样的语言进行比较。现在在 Java 中，所有的东西都是静态类型的，这种语言在运行之前被编译，不像 Python 在运行时通过解释器编译。现在在 Java 中发生的是，当你写代码时，你需要定义你的每一个变量将是什么类型，你的方法和函数将返回什么类型，并且你必须精确地定义在你的代码中所有的东西将是什么类型。虽然这会导致更长的开发时间，并且需要更长的时间来编写代码，但是它确实在编译时提高了效率，这实际上是可行的，而且比 Python 代码快得多，因为如果您知道特定变量或对象的类型， 您可以执行大量不同的优化，并避免在实际运行代码时执行大量不同的检查，因为这些检查是在编译时执行的。在 Java 中，本质上，您不能编译任何没有实际错误的 Java 代码，甚至就像编写代码时键入的错误一样。您将尝试编译它，它会说，这种类型不准确，您不能这样做， 您不能编译它，因为它知道，当运行时，这是行不通的，所以基本上所有这些实际上需要在 Python 中执行的检查都是预先执行的，并且由于这种静态类型的长度，只做了大量的优化。 现在人们可能会问这样一个问题，为什么 Python 不这样做？答案是 Python 是动态类型化的，这意味着任何变量都可以改变它的类型，并且可以在程序运行的任何时候改变它的值，这意味着我们不能事先编译整个程序，因为我们不能一次完成所有这些检查，因为我们不知道这些变量会是什么类型，它们会在运行时改变， 不同的事情将会发生，正因为如此，我们不能得到所有这些优化，我们可能在较低层次的语言，如 Java、C 或 C++中得到这些优化，这是语言缓慢的基本原因，这种动态类型和任何快速语言都将有一个编译器来运行，它将确保一切都是好的， 它将在运行时实际运行代码之前进行所有这些检查，在 Python 中发生的事情是，您的所有代码实际上都是在运行时编译和检查的，因此，与其在运行代码之前编译它并预先花费所有这些时间，不如进行许多检查，以确保说这个对象是正确的，这些类型是正确的，一切都是一样的。

现在接下来要讲的是 Python 中**缺乏并发**。这将是速度的主要因素，如果你用 Java，C 写一个应用程序，你可以把所有的东西分散到多个线程中，这样你就可以利用你的中央处理器的所有核心，所以在现代计算中，为了打破这一点，我们大多数人都有四个核心或更高的中央处理器，这允许我们同时运行四个任务，现在用 Python 这是不可能的。Python 说， 对于每个解释器来说，我们一次最多只能有一个线程在运行，一个 [线程](https://en.wikipedia.org/wiki/Thread_(computing)) 只是发生在 CPU 内核上的某种操作，这意味着即使我们在 Python 程序中创建了许多线程，我们也只能使用一个 CPU 内核，而在 Java 程序或 C 程序中，可能使用全部八个线程，或者使用全部四个线程，这将导致 4X 或者速度提高 8X，现在我们可以在 Python 中通过使用 [**多处理**](https://www.geeksforgeeks.org/multiprocessing-python-set-1/#:~:text=In%20Python%2C%20the%20multiprocessing%20module,dividing%20work%20between%20multiple%20processes.&text=print%20(%20%22Done!%22%20)&text=Square%3A%20100%20Cube%3A%201000%20Done!&text=To%20create%20a%20process%2C%20we%20create%20an%20object%20of%20Process%20class.)**来绕过这一点，但这也有一些问题。**

### ****为什么 Python 中存在全局解释器锁，为什么这是语言的一个特性？**T3】**

**嗯，答案很简单，这要追溯到 Python 的**动态类型**，所以在 Python 中管理内存的方式，现在不是线程安全的，也就是说，如果两个线程同时试图访问内存中的一个特定对象，你会看到一些问题， 本质上，我们不能允许这种情况发生，所以 Python 所做的就是拥有一个全局解释器锁，这意味着一次只能运行一个线程来防止这种情况发生，因为我们知道多处理和多线程应用程序的主要问题是您必须处理锁定和共享内存。**

### **我们如何加快 Python 代码的速度？**

**一种方法是使用 C 代码作为我们 Python 库的扩展。现在 Python 是建立在 C 之上的，这就是为什么 Python 中的排序算法会比用 Python 编写自己的原生排序快得多。因此，如果您需要创建一些在 Python 中运行非常快的东西，并且不能使用不同的语言，我们可以用 C 语言编写该算法，并将其作为扩展导入到您的 Python 代码中，这样您就可以比直接在 Python 中编写该代码更快地运行该代码。**

### ****结论****

*   **Python 之所以慢，主要是因为语言的构建方式，也就是说，由于 Python 中涉及的动态类型，我们无法在编译和解释中引入许多优化，而我们在其他语言(如 Java)中已经做到了这一点。**
*   **为了提高 Python 代码的速度，您可以使用某种线程和并发性，您可以使用多处理模块，这将允许您同时运行多个解释器，并越过全局解释器锁，但是您可能会遇到一些共享和锁定内存的问题。**
*   **加快 Python 代码速度的另一种方法是，您可以为 Python 代码编写一些自己的 C 扩展。**