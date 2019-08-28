# Handling Missing Data
There are several methods used in literature and textbooks for treating missingness in data. A summary of these methods is shown in figure below[1]. In addition, there are certain drawbacks associated with each of these methods when used for data mining and one needs to be careful to avoid bias or the under- or over-estimation of variability. 

<p align = "center">
<img src = "https://github.com/hahmadraza/Handling-Missing-Data-using-ML-techniques/blob/master/Images/missing%20Data%20Mechanism.jpg">
</p>

Methods Used
1) Imputation Using Constant Value
2) Imputation Using k-NN
3) BiScaler imputation
## Imputation Using Constant Value
Zero or Constant imputation; as the name suggests , it replaces the missing values with either zero or any constant value specified. In figure below a part of data is shown before and after applying imputation using constant value. Constant value used was 1.

<p align = "center">
<img src = "https://github.com/hahmadraza/Handling-Missing-Data-using-ML-techniques/blob/master/Images/Constant_Imputation.jpg">
</p>

### Pros:
• It Works well in practice with categorical features.  
• It is Easy and Fast.
### Cons:
• It does not consider the correlations between different observed features.  
• It gives poor results on encoded categorical features.  
• It does not consider the uncertainty in imputations.  
• It can introduce bias in the data.  

<p align = "center">
<img src = "https://github.com/hahmadraza/Handling-Missing-Data-using-ML-techniques/blob/master/Images/Result_Constant_Value.jpg">
</p>

<p align = "center">
<img src = "https://github.com/hahmadraza/Handling-Missing-Data-using-ML-techniques/blob/master/Images/CM_constant_vlaue.jpg">
</p>

## Imputation Using k-NN
The k nearest neighbors' algorithm is used for simple classification. It uses feature similarity to predict the values of any new data point in the data. This means that the new data point is assigned a predicted value based on how closely it is similar to the neighbor points in the training set. This can be very useful in making predictions about the missing values by finding the k nearest neighbors to the observation with missing data and then imputing them based on the non-missing values in the neighborhood.
It works on the principle of finding minimum distance from the query instance to the training samples to determine K- nearest neighbors. After finding K such neighbors, simple majority of these neighbors is taken to predict the value of query instance. A graph for KNN with 30 neighbors is shown in figiure below[2].

<p align = "center">
<img src = "https://github.com/hahmadraza/Handling-Missing-Data-using-ML-techniques/blob/master/Images/KNN_Imputation.jpg">
</p>

### Pros
•It can be much more accurate than the simple mean, median or most frequent imputation methods (It depends on the dataset).  
### Cons
• It is computationally expensive because it works by storing the whole training dataset in memory.  
• It is quite sensitive to outliers in the data.  

<p align = "center">
<img src = "https://github.com/hahmadraza/Handling-Missing-Data-using-ML-techniques/blob/master/Images/Result_KNN.jpg">
</p>

<p align = "center">
<img src = "https://github.com/hahmadraza/Handling-Missing-Data-using-ML-techniques/blob/master/Images/CM_KNN.jpg">
</p>

# BiScaler imputation: 
It is an iterative estimation of row or column means and standard deviations to get doubly normalized matrix [3]. It is not guaranteed to converge but works well in practice. It brings the two approaches nuclear-norm-regularized matrix approximation [4] and maximum-margin matrix factorization [5] together, leading to an efficient algorithm for large matrix factorization and completion that outperforms both of these.

<p align = "center">
<img src = "https://github.com/hahmadraza/Handling-Missing-Data-using-ML-techniques/blob/master/Images/Reult_Biscalar.jpg">
</p>

<p align = "center">
<img src = "https://github.com/hahmadraza/Handling-Missing-Data-using-ML-techniques/blob/master/Images/CM_Biscalar.jpg">
</p>

# Results
<p align = "center">
<img src = "https://github.com/hahmadraza/Handling-Missing-Data-using-ML-techniques/blob/master/Images/Rsults.JPG">
</p>
# References

[1] https://archive.ics.uci.edu/ml/datasets/human+activity+recognition+using+smartphones

[2] https://towardsdatascience.com/6-different-ways-to-compensate-for-missing-values-data-imputation-with-examples-6022d9ca0779

[3] https://arxiv.org/pdf/1410.2596.pdf

[4] Rahul Mazumder, Trevor Hastie, and Rob Tibshirani. Spectral regularization algorithms for learning large incomplete matrices. Journal of Machine Learning Research, 11:2287–2322, 2010.

[5] Nathan Srebro, Jason Rennie, and Tommi Jaakkola. Maximum margin matrix factorization. Advances in Neural Information Processing Systems, 17, 2005.
