# 将 SOP 转换为 POS 的 Python 代码

> 原文:[https://www . geesforgeks . org/python-code-to-convert-sop-to-pos/](https://www.geeksforgeeks.org/python-code-to-convert-sop-to-pos/)

用 python 编写一个程序，将标准的 SOP(乘积之和)形式转换为标准的 POS(乘积之和)形式。

**假设:**输入的 SOP 表达式是标准的。标准操作程序表达式中的变量是连续的，即如果表达式包含变量 A，那么它将分别包含变量 B、C，并且每个产品术语包含按排序顺序排列的字母，即 ABC(不像 BAC)。

**示例:**

```py
Input : ABC'+A'BC+ABC+AB'C 
Output : (A+B+C).(A+B+C').(A+B'+C).(A'+B+C)

Input : A'B+AB'
Output : (A+B).(A'+B')

```

**进场:**

1.  首先将每个乘积项转换为其等价的二进制形式(例如:如果 ABC’则取 1 表示非复合变量(A，B)，取 0 表示补码变量(C)，因此二进制转换为 110)，然后最终等价为其十进制形式(例如:110 = 6)并存储在列表中。
2.  现在，对于 POS 表单，取第 1 步中形成的列表中没有的所有术语，然后将每个术语转换为二进制，从而更改为 SOP 表单。例如:假设 5 不在列表中，那么
    5 == > 101(二进制)
    现在，用补码变量(A，C)
    替换 1，用非复合变量(B)
    替换 0，在变量之间使用“+”
    101 = =>A '+B+C '
    在每个单独的和项使用“.”
    为了更加清晰，在每个术语之间使用括号。
    例:(A'+B+C ')。(A+B+C ')

**Python 代码**

```py
# Python code to convert standard SOP form 
# to standard POS form 

# function to calculate no. of variables 
# used in SOP expression 
def count_no_alphabets(SOP): 
    i = 0
    no_var = 0

    # As expression is standard so total no. 
    # of alphabets will be equal 
    # to alphabets before first '+' character 
    while (SOP[i]!='+'): 

        # checking if character is alphabet             
        if (SOP[i].isalpha()):     
            no_var+= 1
        i+= 1
    return no_var 

# function to calculate the min terms in integers 
def Cal_Min_terms(Min_terms, SOP): 
    a ="" 
    i = 0
    while (i<len(SOP)): 
        if (SOP[i]=='+'): 

            # converting binary to decimal                 
            b = int(a, 2) 

            # insertion of each min term(integer) into the list                 
            Min_terms.append(b) 

            # empty the string         
            a =""                         
            i+= 1
        else: 

            # checking whether variable is complemented or not 
            if(i + 1 != len(SOP) and SOP[i + 1]=="'"): 

                # concatenating the string with '0' 
                a+='0' 

                # incrementing by 2 because 1 for alphabet and 
                # another for "'"                        
                i+= 2                            
            else: 

                # concatenating the string with '1' 
                a+='1'                        
                i+= 1

    # insertion of last min term(integer) into the list     
    Min_terms.append(int(a, 2))             

# function to calculate the max terms in binary then 
# calculate POS form of SOP 
def Cal_Max_terms(Min_terms, no_var, start_alphabet): 

    # declaration of the list 
    Max_terms =[] 

    # calculation of total no. of terms that can be 
    # formed by no_var variables                     
    max = 2**no_var                 
    for i in range(0, max): 

        # checking whether the term is not 
        # present in the min terms 
        if (Min_terms.count(i)== 0): 

            # converting integer to binary and then 
            # taking the value from 2nd index as 1st 
            # two index contains '0b' 
            b = bin(i)[2:] 

            # loop used for inserting 0's before the 
            # binary value so that its length will be 
            # equal to no. of variables present in 
            # each product term         
            while(len(b)!= no_var): 
                b ='0'+b 

            # appending the max terms(integer) in the list 
            Max_terms.append(b)     

    POS ="" 

    # loop till there are max terms                         
    for i in Max_terms: 

        # before every sum term append POS by '('         
        POS = POS+"("

        # acquire the starting variable came from 
        # main function in every sum term             
        value = start_alphabet 

        # loop till there are 0's or 1's in each max term     
        for j in i: 

            # checking for complement variable to be used                 
            if (j =='1'): 

                # concatenating value, ' and + in string POS                 
                POS = POS + value+"'+"

            # checking for uncomplement variable to be used     
            else: 

                # concatenating value and + in string POS                     
                POS = POS + value+"+"

            # increment the alphabet by 1     
            value = chr(ord(value)+1) 

        # for discarding the extra '+' in the last     
        POS = POS[:-1] 

        # appending the POS string by ')." after 
        # every sum term                 
        POS = POS+")."

    # for discarding the extra '.' in the last                     
    POS = POS[:-1]                         
    return POS 

# main function 
def main(): 
    # input1 
    SOP_expr ="ABC'+A'BC + ABC + AB'C"
    Min_terms =[] 
    no_var = count_no_alphabets(SOP_expr) 
    Cal_Min_terms(Min_terms, SOP_expr) 
    POS_expr = Cal_Max_terms(Min_terms, no_var, SOP_expr[0]) 
    print ("Standard POS form of", SOP_expr, " ==> ", POS_expr) 

    # input2 
    SOP_expr ="A'B + AB'"
    Min_terms =[] 
    no_var = count_no_alphabets(SOP_expr) 
    Cal_Min_terms(Min_terms, SOP_expr) 
    POS_expr = Cal_Max_terms(Min_terms, no_var, SOP_expr[0]) 
    print ("Standard POS form of", SOP_expr, " ==> ", POS_expr) 

    # input3 
    SOP_expr ="xyz'+x'y'z'+xy'z"
    Min_terms =[] 
    no_var = count_no_alphabets(SOP_expr) 
    Cal_Min_terms(Min_terms, SOP_expr) 
    POS_expr = Cal_Max_terms(Min_terms, no_var, SOP_expr[0]) 
    print ("Standard POS form of", SOP_expr, " ==> ", POS_expr )

# driver code     
if __name__=="__main__": 
    main() 
```

**Output:**

```py
Standard POS form of ABC'+A'BC + ABC + AB'C  ==>  (A+B+C).(A+B+C').(A+B'+C).(A+B'+C').(A'+B+C).(A'+B+C')
Standard POS form of A'B + AB'  ==>  (A+B).(A+B').(A'+B)
Standard POS form of xyz'+x'y'z'+xy'z  ==>  (x+y+z').(x+y'+z).(x+y'+z').(x'+y+z).(x'+y'+z')

```