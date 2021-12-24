# 多语言编程——Java 进程类、JNI 和 IO

> 原文:[https://www . geesforgeks . org/多语言-编程-Java-进程-类-jni-and-io/](https://www.geeksforgeeks.org/multi-language-programming-java-process-class-jni-and-io/)

顾名思义，多语言编程涉及在一个程序中使用多种编程语言。有大量的编程语言，这是一种常见的体验，我们希望我们也可以使用其他语言的组件。嗯，开始的时候，使用多种语言，用多种语言编译代码似乎很奇怪，但最终，它非常有用。

在深入探讨细节和基于代码的东西之前，让我们回顾一下编程语言的历史 Java 的历史和操作系统的历史。汇编级编程语言诞生于 20 世纪 40 年代。1951 年的今天，区域汇编语言出现。1958 年——ALGOL；1959 年——COBOL(面向公共业务的语言)，最后是 BASIC(初学者通用符号指令代码)，1964 年。最后，我们在 1972 年拿到了 C。Python 出现于 1990 年，但由于数据科学和机器学习技术的出现，它只是在现在才流行起来。Java 诞生于 1995 年。其他语言如 Go、Rust、Dark、Kotlin、Swift、Scala、Scratch 等。都是最近的发展。我为什么要说这些？这看似与讨论的主题无关，但实际上并非如此。

不同的编程语言有不同的能力，这是可以接受的。比如 C 和 C++支持指针；Python 对数据科学和基于 AI 的领域有好处；r 适合数据分析和数学运算。从我的个人经历来看，BASIC 是我在 2011 年使用的第一种语言。(我主要用的是 QBASIC)。虽然 QBASIC 是一种解释语言，但我后来转向了 QB64，这是 BASIC 的现代化版本，它主要编译并生成一个 EXE 文件。除此之外，有时我们也使用机器可执行脚本来实现某些目标。例如，切换电脑蓝牙的 bash 脚本、与连接的外设通信的 bat 文件等等。

现在，可能有些时候你会说，“天哪！我希望语言 X 的这个特性也存在于语言 Y 中。”很多时候我们都面对过。但是现在，借助 Java 中的 Process 类、JNI 和 IO，我们可以访问 Java 中任何编程语言的特性，前提是机器上已经安装了相同的特性以及依赖项。例如，我们可以使用 Python OpenCV 或 java 中的 Python 文本到语音(PyTTSx3)库。

**实施:**

一个从 Java 运行文本到语音引擎的短程序。它由两个文件组成，即 python 的 tt.py 和 java 的 GFG.java。

**文件 1:**TTS . py

T5】python 3

```py
# Python Demo Program

# System for reading command line arguments
import sys 
# Our Text to speech module
import pyttsx3 

if __name__ == "__main__":
    engine = pyttsx3.init()

    # Command line inputs saved in arg
    for arg in sys.argv[1:]: 

        # Speaking the input
        engine.say(arg) 
        engine.runAndWait()
```

**文件二:**GFG.java

T4

## 爪哇

T7

```py
// Java Program to Run a Text to Speech Engine

// Importing I/O classes
import java.io.*;

// Main class
class GFG
{
    // Main driver method
    public static void main(String args[])
    {
        // Custom input string consisting of text to speak
        String str= "Hello world";

        // Try block to handle the exceptions 
        try
        {
             Process ec=Runtime.getRuntime().exec("python tts.py "+str); //Using str as command line argument for the python script
             ec.waitFor(); //Waiting for the python script to finish executing
        }
        catch(Exception excep)
        {
             excep.printStackTrace();
        }
    }
}
```

T8T10】

**输出:**

```py
Hello world (spoken)
```

好了，现在来看定义，

> “processbuilder . start()和 Runtime.exec 方法创建一个本机进程，并返回一个 process 子类的实例，该实例可用于控制该进程并获取有关它的信息。”
> 
> –文档

**实施:**

可以看到，我们可以将控制流从 java 应用程序转移到 python 脚本，在脚本执行完成后，控制流被返回。现在，问题是除了控制流之外，如何传输数据。在这里，输入输出类开始发挥作用。

从 python 程序中，我们可以将我们想要的数据打印到 STDOUT 中。(使用 python 中的简单 print()函数。)现在，Process 类的实例 ec 有一个名为 [*getInputStream()*](https://www.geeksforgeeks.org/java-lang-processbuilder-class-java/) 的函数。这将为 Java 程序返回一个 InputStream 对象。现在，来自输入流的输入可以很容易地用 BufferedReader 或 Scanner 类来处理。Python 类的标准输出连接到流程类实例的输入流。

**示例 1:** 文件:TTS . py

T5】python 3

```py
# Importing required python classes
import sys
import pyttsx3

if __name__ == "__main__":
    engine = pyttsx3.init()

    # Iterating over using for loop
    for arg in sys.argv[1:]
    engine.say(arg)
    engine.runAndWait()

    # Print to STDOUT of python script
    print("Execution from Python completed")
```

**示例 2:** 文件 GFG.java

T3

## Java

T6T8】

```py
// Importing java I/O classes
import java.io.*;

// Main class
class GFG {

    // MAin driver method
    public static void main(String args[])
    {
        // Custom input string
        String str = "Hello world";

        // Try block to check for exceptions
        try {
            // Creating object of Processor class for python
            // script
            Process ec = Runtime.getRuntime().exec(
                "python tts.py " + str);

            // Taking input from user by
            // creating object of BufferedReader class
            // as for less salalbilty it is fast

            // Connect STDOUT of Python script to
            // BufferedReader of Java
            BufferedReader br = new BufferedReader(
                new InputStreamReader(ec.getInputStream()));

            // Initially declaring and initializing empty
            // string
            String st = " ";

            // Read all outputs from python script
            while ((st = br.readLine()) != null) {
                // Printing them
                System.out.println(st);
            }

            ec.waitFor();
        }

        // Catch block to handle the exceptions
        catch (Exception excep) {

            // Print the exception/s along twith line number
            // using pprintStacktrace() method
            excep.printStackTrace();
        }
    }
}
```