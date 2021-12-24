# 使用 Python 从头开始网格搜索

> 原文:[https://www . geesforgeks . org/grid-从头开始搜索-使用-python/](https://www.geeksforgeeks.org/grid-searching-from-scratch-using-python/)

网格搜索是一种寻找模型精度最高的超参数最佳组合的方法。在对任何算法应用网格搜索之前，数据被分为训练集和验证集，验证集用于验证模型。在验证集上测试具有所有可能的超参数组合的模型，以选择最佳组合。

**实施:**

网格搜索可以应用于任何超参数算法，其性能可以通过调整超参数来提高。例如，我们可以通过在一组 K 值上验证网格搜索的性能来对 K 近邻应用网格搜索。通过使用一组学习速率值，我们可以用逻辑回归做同样的事情，以找到逻辑回归达到最佳精度的最佳学习速率。

本次实施使用的糖尿病数据集可从[链接](https://github.com/mohit baliyan/References)下载。

它有 8 个特征列，如“*年龄”*、“*葡萄糖”*心电图，以及 108 名患者的目标变量“*结果”*。因此，在本文中，我们将训练一个逻辑回归分类器模型来预测有这种信息的患者是否存在糖尿病。

**代码:从头开始实现逻辑回归网格搜索**

## python 3

```py
# Importing libraries

import numpy as np
import pandas as pd
from sklearn.model_selection import train_test_split

# Grid Searching in Logistic Regression
class LogitRegression() :
    def __init__( self, learning_rate, iterations ) :        
        self.learning_rate = learning_rate        
        self.iterations = iterations

    # Function for model training            
    def fit( self, X, Y ) :        
        # no_of_training_examples, no_of_features        
        self.m, self.n = X.shape

        # weight initialization        
        self.W = np.zeros( self.n )        
        self.b = 0        
        self.X = X        
        self.Y = Y

        # gradient descent learning                
        for i in range( self.iterations ) :            
            self.update_weights()            
        return self

    # Helper function to update weights in gradient descent    
    def update_weights( self ) :           
        A = 1 / ( 1 + np.exp( - ( self.X.dot( self.W ) + self.b ) ) )

        # calculate gradients        
        tmp = ( A - self.Y.T )        
        tmp = np.reshape( tmp, self.m )        
        dW = np.dot( self.X.T, tmp ) / self.m         
        db = np.sum( tmp ) / self.m 

        # update weights    
        self.W = self.W - self.learning_rate * dW    
        self.b = self.b - self.learning_rate * db        
        return self

    # Hypothetical function  h( x )     
    def predict( self, X ) :    
        Z = 1 / ( 1 + np.exp( - ( X.dot( self.W ) + self.b ) ) )        
        Y = np.where( Z > 0.5, 1, 0 )        
        return Y

# Driver code

def main() :

    # Importing dataset    
    df = pd.read_csv( "diabetes.csv" )
    X = df.iloc[:,:-1].values
    Y = df.iloc[:,-1:].values

    # Splitting dataset into train and validation set
    X_train, X_valid, Y_train, Y_valid = train_test_split( 
      X, Y, test_size = 1/3, random_state = 0 )

    # Model training    
    max_accuracy = 0

    # learning_rate choices    
    learning_rates = [ 0.1, 0.2, 0.3, 0.4, 0.5, 
                      0.01, 0.02, 0.03, 0.04, 0.05 ]

    # iterations choices    
    iterations = [ 100, 200, 300, 400, 500 ]

    # available combination of learning_rate and iterations

    parameters = []    
    for i in learning_rates :        
        for j in iterations :            
            parameters.append( ( i, j ) )

    print("Available combinations : ",  parameters )

    # Applying linear searching in list of available combination
    # to achieved maximum accuracy on CV set

    for k in range( len( parameters ) ) :        
        model = LogitRegression( learning_rate = parameters[k][0], 
                                iterations = parameters[k][1] )

        model.fit( X_train, Y_train )

        # Prediction on validation set
        Y_pred = model.predict( X_valid )

        # measure performance on validation set

        correctly_classified = 0

        # counter    
        count = 0

        for count in range( np.size( Y_pred ) ) :            
            if Y_valid[count] == Y_pred[count] :                
                correctly_classified = correctly_classified + 1   

        curr_accuracy = ( correctly_classified / count ) * 100

        if max_accuracy < curr_accuracy :            
            max_accuracy = curr_accuracy

    print( "Maximum accuracy achieved by our model through grid searching : ", max_accuracy )

if __name__ == "__main__" :     
    main()
```

**输出:**

```py
Available combinations :  [(0.1, 100), (0.1, 200), (0.1, 300), (0.1, 400), 
(0.1, 500), (0.2, 100), (0.2, 200), (0.2, 300), (0.2, 400), (0.2, 500), 
(0.3, 100), (0.3, 200), (0.3, 300), (0.3, 400), (0.3, 500), (0.4, 100), 
(0.4, 200), (0.4, 300), (0.4, 400), (0.4, 500), (0.5, 100), (0.5, 200), 
(0.5, 300), (0.5, 400), (0.5, 500), (0.01, 100), (0.01, 200), (0.01, 300),
(0.01, 400), (0.01, 500), (0.02, 100), (0.02, 200), (0.02, 300), (0.02, 400), 
(0.02, 500), (0.03, 100), (0.03, 200), (0.03, 300), (0.03, 400), (0.03, 500), 
(0.04, 100), (0.04, 200), (0.04, 300), (0.04, 400), (0.04, 500), (0.05, 100), 
(0.05, 200), (0.05, 300), (0.05, 400), (0.05, 500)]

Maximum accuracy achieved by our model through grid searching :  60.0

```

在上面，我们对学习速率和迭代次数的所有可能组合应用网格搜索，以找到模型的峰值，在该峰值处模型达到最高精度。

**代码:sklearn**

## python 3

```py
# Importing Libraries

import pandas as pd
import numpy as np
from sklearn.linear_model import LogisticRegression
from sklearn.model_selection import GridSearchCV

# Driver Code

def main() :    
    # Importing dataset    
    df = pd.read_csv( "diabetes.csv" )
    X = df.iloc[:,:-1].values
    Y = df.iloc[:,-1:].values

    # Splitting dataset into train and test set
    X_train, X_test, Y_train, Y_test = train_test_split( 
      X, Y, test_size = 1/3, random_state = 0 )

    # Model training    
    max_accuracy = 0

    # grid searching for learning rate    
    parameters = { 'C' : [ 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 ] }

    model = LogisticRegression()        
    grid = GridSearchCV( model, parameters )    
    grid.fit( X_train, Y_train )

    # Prediction on test set
    Y_pred = grid.predict( X_test )

    # measure performance    
    correctly_classified = 0

    # counter    
    count = 0

    for count in range( np.size( Y_pred ) ) :            
        if Y_test[count] == Y_pred[count] :            
            correctly_classified = correctly_classified + 1   

    accuracy = ( correctly_classified / count ) * 100

    print( "Maximum accuracy achieved by sklearn model through grid searching : ", np.round( accuracy, 2 ) )

if __name__ == "__main__" :     
    main()
```

逻辑回归网格搜索的实现

**输出:**

```py
Maximum accuracy achieved by sklearn model through grid searching :  62.86

```

**注:**网格搜索在为数学上复杂的模型调整超参数方面起着至关重要的作用。