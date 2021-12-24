# 使用 Python 自动生成 Java 的 getter-setter 生成器

> 原文:[https://www . geesforgeks . org/automate-getter-setter-generator-for-Java-use-python/](https://www.geeksforgeeks.org/automate-getter-setter-generator-for-java-using-python/)

[封装](https://www.geeksforgeeks.org/encapsulation-in-python/)定义为将数据封装在一个单元下。封装可以通过将类中的所有变量声明为私有，并在类中编写公共方法来设置和获取变量值来实现。这些公共方法被称为**吸气剂**和**设置剂**。实际上，为 Java 中的所有变量编写 getter-setter 是一个相当耗时且重复的过程。
这里给我们提供了一个变量名及其数据类型的列表，我们必须为它们打印所有的 getter-setter 方法，同时遵循基本的 Java 编程约定。
**算法:**

1.  将每个变量的第一个字符改为大写。
2.  在每个改变的变量的开头加上“get”，并把它们存储在一个列表中。
3.  在每个改变的变量的开头加上“set”，并把它们存储在一个列表中。
4.  对于每个变量及其对应的数据类型，使用字符串连接打印 getter 和 setter 方法。

下面是实现。

## 蟒蛇 3

```
# Function to print getter and setter methods
# for variables according to Java
def print_getter_setter(variables, datatypes):

    # List to store getVariable
    getters = []

    # List to store setVariable
    setters = []

    # Iterate for every variable
    for var in variables:

        # Prepend "get" in every variable and change
        # the first character to uppercase
        getter = "get" + var[0].capitalize() + var[1:]
        getters.append(getter)

        # Prepend "set" in every variable and change
        # the first character to uppercase
        setter = "set" + var[0].capitalize() + var[1:]
        setters.append(setter)

    for i in range(len(variables)):

        # Print the getter method
        print("public " + datatypes[i] + " " + getters[i] +
              "() {\n\treturn " + variables[i] + ";\n}\n")

        # Print the setter method
        print("public void " + setters[i] + "(" + datatypes[i] +
              " " + variables[i] + ") {\n\tthis." + variables[i] +
              " = " + variables[i] + ";\n}\n")

# Driver function
if __name__=="__main__":
    # The list of variables
    variables = ["abc", "empId", "GFG", "x"]

    # And the list of the variables's corresponding
    # datatypes
    datatypes = ["int", "float", "double" , "String"]

    print_getter_setter(variables, datatypes)
```

**输出:**

```
public int getAbc() {
    return abc;
}

public void setAbc(int abc) {
    this.abc = abc;
}

public float getEmpId() {
    return empId;
}

public void setEmpId(float empId) {
    this.empId = empId;
}

public double getGFG() {
    return GFG;
}

public void setGFG(double GFG) {
    this.GFG = GFG;
}

public String getX() {
    return x;
}

public void setX(String x) {
    this.x = x;
}
```