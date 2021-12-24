# 使用布尔模型和向量空间模型的文档检索

> 原文:[https://www . geesforgeks . org/document-retrieval-use-boolean-model-and-vector-space-model/](https://www.geeksforgeeks.org/document-retrieval-using-boolean-model-and-vector-space-model/)

### 布尔模型

它是一个基于集合论和布尔代数的简单检索模型。查询被设计成具有精确语义的布尔表达式。检索策略基于二元决策准则。布尔模型认为索引项在文档中存在或不存在。

**问题:**

考虑 5 个包含 6 个术语的文档

> 文档 1 =“术语 1 术语 3”
> 
> 文件 2 = '条款 2 条款 4 条款 6 '
> 
> 文件 3 = '条款 1 条款 2 条款 3 条款 4 条款 5 '
> 
> 文件 4 = '条款 1 条款 3 条款 6 '
> 
> 文件 5 = '条款 3 条款 4 '

布尔模型中的文档

<figure class="table">

|   | **术语 1** | **第 2 项** | **第 3 项** | **第 4 项** | **术语 5** | **第 6 项** |
| **文件 1** | one | Zero | one | Zero | Zero | Zero |
| **文件 2** | Zero | one | Zero | one | Zero | one |
| **文件 3** | one | one | one | one | one | Zero |
| **文件 4** | one | Zero | one | Zero | Zero | one |
| **文件 5** | Zero | Zero | one | one | Zero | Zero |

</figure>

考虑查询:*查找由术语 1 和术语 3 组成的文档，而不是术语 2 (* **术语 1 ∧术语 3 ∧术语 2)**

<figure class="table">

|   | **术语 1** | **第 2 项** | **第 3 项** | 术语 4 | 术语 5 | 术语 6 |
| 文档 | **1** | **1** | **1** | Zero | Zero | Zero |
| 文档 | **0** | **0** | **0** | one | Zero | one |
| 文档 | **1** | **0** | **1** | one | one | Zero |
| 文档 | **1** | **1** | **1** | Zero | Zero | one |
| 文档 | **0** | **1** | **1** | one | Zero | Zero |

</figure>

> 文档 1 : 1 ∧ 1∧ 1 = 1
> 
> 文档 2 : 0 ∧ 0 ∧ 0 = 0
> 
> 文档 3 : 1 ∧ 1 ∧ 0 = 0
> 
> 文件 4 : 1 ∧ 1 ∧ 1 = 1
> 
> 文档 5 : 0 ∧ 1 ∧ 1 = 0

基于以上计算**文档 1 和文档 4** 与给定的查询相关

作为输入给出的 CSV 文件:

> 文件，条款 1，条款 2，条款 3
> 
> 文件 1，冰淇淋，芒果，荔枝
> 
> 文件 2，曲棍球，板球，运动
> 
> 文件 3，荔枝，芒果，巧克力
> 
> 文档 4，不错，不错，可爱

**代码:展示文档检索布尔模型实现的 Python 代码**

## 计算机编程语言

```
import pandas
# module to read the contents of the file from a csv file

from contextlib import redirect_stdout
# module to redirect the output to a text file

terms = []
# list to store the terms present in the documents

keys = []
# list to store the names of the documents

vec_Dic = {}
# dictionary to store the name of the document and the boolean vector as list

dicti = {}
# dictionary to store the name of the document and the terms present in it as a
# vector

dummy_List = []
# list for performing some operations and clearing them

def filter(documents, rows, cols):
    '''function to read and separate the name of the documents and the terms
    present in it to a separate list  from the data frame and also create a
    dictionary which has the name of the document as key and the terms present in
    it as the list of strings  which is the value of the key'''

    for i in range(rows):
        for j in range(cols):
            # traversal through the data frame

            if(j == 0):
                # first column has the name of the document in the csv file
                keys.append(documents.loc[i].iat[j])
            else:
                dummy_list.append(documents.loc[i].iat[j])
                # dummy list to update the terms in the dictionary

                if documents.loc[i].iat[j] not in terms:
                    # add the terms to the list if it is not present else continue
                    terms.append(documents.loc[i].iat[j])

        copy = dummy_List.copy()
        # copying the the dummy list to a different list

        dicti.update({documents.loc[i].iat[0]: copy})
        # adding the key value pair to a dictionary

        dummy_List.clear()
        # clearing the dummy list

def bool_Representation(dicti, rows, cols):
    '''In this fuction we get a boolean representation of the terms present in the
    documents in the form of lists, later we create a dictionary which contains
    the the name of the documents as key and value as the list of boolean values
    representing the terms present in the document'''

    terms.sort()
    # we sort the elements in the alphabetical order for the convience, the order
    # of the term does not make any difference

    for i in (dicti):
        # for every document in the dictionary we check for each string present in
        # the list

        for j in terms:
            # if the string is present in the list we append 1 else we append 0

            if j in dicti[i]:
                dummy_List.append(1)
            else:
                dummy_List.append(0)
            # appending 1 or 0 for obtaining the boolean representation

        copy = dummy_List.copy()
        # copying the the dummy list to a different list

        vec_Dic.update({i: copy})
        # adding the key value pair to a dictionary

        dummy_List.clear()
        # clearing the dummy list

def query_Vector(query):
    '''In this function we represent the query in the form of boolean vector'''

    qvect = []
    # query vector which is returned at the end of the function

    for i in terms:
        # if the word present in the list of terms is also present in the query
        # then append 1 else append 0

        if i in query:
            qvect.append(1)
        else:
            qvect.append(0)

    return qvect
    # return the query vector which is obtained in the boolean form

def prediction(q_Vect):
    '''In this function we make the prediction regarding which document is related
    to the given query by performing the boolean operations'''

    dictionary = {}
    listi = []
    count = 0
    # initialisation of the dictionary , list and a variable which is further
    # required for performing the computation

    term_Len = len(terms)
    # number of terms present in the term list

    for i in vec_Dic:
        # for every document in the dictionary containing the terms present in it
        # the form of boolean vector

        for t in range(term_Len):
            if(q_Vect[t] == vec_Dic[i][t]):
                # if the words present in the query is also present in the
                # document or if the words present in the query is also absent in
                # the document

                count += 1
                # increase the value of count variable by one
                # the condition in which words present in document and absent in
                #query , present in query and absent in document is not considered

        dictionary.update({i: count})
        # dictionary updation here the name of the document is the key and the
        # count variable computed earlier is the value

        count = 0
        # reinitialisaion of count variable to 0

    for i in dictionary:
        listi.append(dictionary[i])
        # here we append the count value to list

    listi = sorted(listi, reverse=True)
    # we sort the list in the descending order which is needed to rank the
    #documents according to the relevance

    ans = ' '
    # variable to store the name of the document which is most relevant

    with open('output.txt', 'w') as f:
        with redirect_stdout(f):
            # to redirect the output to a text file

            print("ranking of the documents")

            for count, i in enumerate(listi):
                key = check(dictionary, i)
                # Function call to get the key when the value is known
                if count == 0:
                    ans = key
                    # to store the name of the document which is most relevant

                print(key, "rank is", count+1)
                # print the name of the document along with its rank

                dictionary.pop(key)
                # remove the key from the dictionary after printing

            print(ans, "is the most relevant document for the given query")
            # to print the name of the document which is most relevant

def check(dictionary, val):
    '''Function to return the key when the value is known'''

    for key, value in dictionary.items():
        if(val == value):
            # if the given value is same as the value present in the dictionary
            # return the key

            return key

def main():
    documents = pandas.read_csv(r'documents.csv')
    # to read the data from the csv file as a dataframe

    rows = len(documents)
    # to get the number of rows

    cols = len(documents.columns)
    # to get the number of columns

    filter(documents, rows, cols)
    # function call to read and separate the name of the documents and the terms
    # present in it to a separate list  from the data frame and also create a
    # dictionary which has the name of the document as key and the terms present in
    # it as the list of strings  which is the value of the key

    bool_representation(dicti, rows, cols)
    # In this fuction we get a boolean representation of the terms present in the
    # documents in the form of lists, later we create a dictionary which contains
    # the the name of the documents as key and value as the list of boolean values
    #representing the terms present in the document

    print("Enter query")
    query = input()
    # to get the query input from the user, the below input is given for obtaining
    # the output as in output.txt file
    # hockey is a national sport

    query = query.split(' ')
    # spliting the query as a list of strings

    q_Vect = query_Vector(query)
    # function call to represent the query in the form of boolean vector

    prediction(q_Vect)
    # Function call to make the prediction regarding which document is related to
    # the given query by performing the boolean operations

main()
```

**输出:**查询时在文本文件中得到的输出为*“曲棍球是一项民族运动”*

> 文档的排名
> 
> 文档
> 
> 文档
> 
> 文档
> 
> 文档

**文档 2 是与给定查询最相关的文档**

### **向量空间模型:**

**代码:展示文档检索向量空间模型实现的 Python 代码**

## 计算机编程语言

```
# implementation of vector space model for document retrieval

import pandas
# module to read the contents of the file from a csv file

from contextlib import redirect_stdout
# module to redirect the output to a text file

import math
# module to perform mathematical functions

terms = []
# list to store the terms present in the documents

keys = []
# list to store the names of the documents

vec_Dic = {}
# dictionary to store the name of the document and the weight as list

dicti = {}
# dictionary to store the name of the document and the terms present in it as a
# vector

dummy_List = []
# list for performing some operations and clearing them

term_Freq = {}
# dictionary to store the term and the number of times of its occurrence in the
# documents

idf = {}
# dictionary to store the term and the inverse document frequency

weight = {}
# dictionary to store the term and the weight which is the product of term
# frequency and inverse document frequency

def filter(documents, rows, cols):
    '''function to read and separate the name of the documents and the terms
    present in it to a separate list  from the data frame and also create a
    dictionary which has the name of the document as key and the terms present
    in it as the list of strings  which is the value of the key'''

    for i in range(rows):
        for j in range(cols):
            # traversal through the data frame

            if(j == 0):
                # first column has the name of the document in the csv file
                keys.append(documents.loc[i].iat[j])
            else:
                dummy_List.append(documents.loc[i].iat[j])
                # dummy list to update the terms in the dictionary

                if documents.loc[i].iat[j] not in terms:
                    # add the terms to the list if it is not present else continue
                    terms.append(documents.loc[i].iat[j])

        copy = dummy_List.copy()
        # copying the the dummy list to a different list

        dicti.update({documents.loc[i].iat[0]: copy})
        # adding the key value pair to a dictionary

        dummy_List.clear()
        # clearing the dummy list

def compute_Weight(doc_Count, cols):
    '''Function to compute the weight for each of the terms in the document.
    Here the weight is calculated with the help of term frequency and
    inverse document frequency'''

    for i in terms:
        # initially adding all the elements into the dictionary and initialising
        # the values as zero
        if i not in term_Freq:
            term_Freq.update({i: 0})

    for key, value in dicti.items():
        # to get the number of occurrence of each terms
        for k in value:
            if k in term_Freq:
                term_Freq[k] += 1
                # value incremented by one if the term is found in the documents

    idf = term_Freq.copy()
    # copying the term frequency dictionary to a dictionary named idf which is
    # further neede for computation

    for i in term_Freq:
        term_Freq[i] = term_Freq[i]/cols
        # term frequency is number of occurrence divided by total number of
        # documents

    for i in idf:
        if idf[i] != doc_Count:
            idf[i] = math.log2(cols / idf[i])
            # inverse document frequency log of total number of documents divided
            # by number of occurrence of the terms
        else:
            idf[i] = 0
            # this is to avoid the zero division error

    for i in idf:
        weight.update({i: idf[i]*term_Freq[i]})
        # weight is the product of term frequency and the inverse document
        # frequency

    for i in dicti:
        for j in dicti[i]:
            dummy_List.append(weight[j])

        copy = dummy_List.copy()
        vec_Dic.update({i: copy})
        dummy_List.clear()
        # above operations performed to get the dictionary of weighted vector
        # for each of the documents

def get_Weight_For_Query(query):
    '''function to get the weight for each terms present in the query, here we
    consider the term frequency as the weight of the terms'''

    query_Freq = {}
    # initialisation of the dictionary with query terms as key and its weight as
    # the values

    for i in terms:
        # initially adding all the elements into the dictionary and initialising
        # the values as zero
        if i not in query_Freq:
            query_Freq.update({i: 0})

    for val in query:
        # to get the number of occurrence of each terms
        if val in query_Freq:
            query_Freq[val] += 1
            # value incremented by one if the term is found in the documents

    for i in query_Freq:
        query_Freq[i] = query_Freq[i] / len(query)
        # term frequency obtained by dividing the number of occurrence of terms by
        # total number of terms in the query

    return query_Freq
    # return the dictionary in which the key is the term and the value is the
    # weight

def similarity_Computation(query_Weight):
    ''' Function to calculate the similarity measure in which the weight of the
    query and the document is multiplied in the numerator and the the weight is
    squared and squareroot is taken the weights of the query and document'''

    numerator = 0
    denomi1 = 0
    denomi2 = 0
    # initialisation of the variables with zero which is needed for computation

    similarity = {}
    # initialisation of dictionary which has the name of document as key and the
    # similarity measure as value

    for document in dicti:
        for terms in dicti[document]:
            # cosine similarity is calculated

            numerator += weight[terms] * query_Weight[terms]
            denomi1 += weight[terms] * weight[terms]
            denomi2 += query_Weight[terms] * query_Weight[terms]
            # the summation values of the weight is calculated and later they are
            # divided

        if denomi1 != 0 and denomi2 != 0:
            # to avoid the zero division error

            simi = numerator / (math.sqrt(denomi1) * math.sqrt(denomi2))
            similarity.update({document: simi})
            #dictionary is updated

            numerator = 0
            denomi2 = 0
            denomi1 = 0
            # reinitialisation of the variables to zero

    return (similarity)
    # the dictionary containing similarity measure as the value

def prediction(similarity, doc_count):
    '''Function to predict the document which is relevant to the query '''

    with open('output.txt', 'w') as f:
        with redirect_stdout(f):
            # to redirect the output to a text file

            ans = max(similarity, key=similarity.get)
            print(ans, "is the most relevant document")
            # to print the name of the document which is most relevant

            print("ranking of the documents")
            for i in range(doc_count):
                ans = max(similarity, key=lambda x: similarity[x])
                print(ans, "rank is", i+1)
                # to print the document name and its rank

                similarity.pop(ans)

def main():
    documents = pandas.read_csv(r'documents.csv')
    # to read the data from the csv file as a dataframe

    rows = len(documents)
    # to get the number of rows

    cols = len(documents.columns)
    # to get the number of columns

    filter(documents, rows, cols)
    # function call to read and separate the name of the documents and the terms
    # present in it to a separate list  from the data frame and also create a
    # dictionary which has the name of the document as key and the terms present
    # in it as the list of strings  which is the value of the key

    compute_Weight(rows, cols)
    # Function to compute the weight for each of the terms in the document.
    # Here the weight is calculated with the help of term frequency and inverse
    # document frequency

    print("Enter the query")
    query = input()
    # to get the query input from the user, the below input is given for obtaining
    # the output as in output.txt file
    # one three three

    query = query.split(' ')
    # spliting the query as a list of strings

    query_Weight = get_Weight_For_Query(query)
    # function call to get the weight for each terms present in the query, here we
    # consider the term frequency as the weight of the terms'''

    similarity = similarity_Computation(query_Weight)
    # Function call to calculate the similarity measure in which the weight of the
    # query and the document is multiplied in the numerator and the weight is
    # squared and squareroot is taken the weights of the query and document

    prediction(similarity, rows)
    # Function call to predict the document which is relevant to the query

main()
```

**输出:**查询时在文本文件中得到的输出为*“一三三”*

> 文档的排名
> 
> 文档 3 等级为 1
> 
> 文档 2 等级为 2
> 
> 文档 1 等级为 3
> 
> 文档 4 等级为 4

**文档 3 是最相关的文档**