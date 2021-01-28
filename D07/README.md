# Cupoy-Course-D07
[課程網址](https://www.cupoy.com/marathon-mission/00000174C4BC1B93000000016375706F795F70726572656C656173654355/0000017549469591000000226375706F795F72656C656173654349/)  
Cupoy Python資料科學 課程作業 D07 NumPy 的矩陣函式與線性代數應用</br>

作業目標<br>
活用矩陣運算，實做線性代數<br>
作業重點<br>
線性代數公式應用<br>
矩陣相乘維度需要對好，例如:2X3矩陣乘上3X5矩陣得到2X5矩陣  

題目:<br>
array1 = np.array([[10, 8], [3, 5]]) <br>
1. 運用上列array計算反矩陣，乘上原矩陣，並觀察是否為單位矩陣?  
2. 運用上列array計算特徵值、特徵向量?  
3. 運用上列array計算SVD?  

```py
import numpy as np
#1. 運用上列array計算反矩陣，乘上原矩陣，並觀察是否為單位矩陣?
array1 = np.array([[10, 8], [3, 5]])
array1 @ np.linalg.inv(array1)
```
```
output:
    array([[1., 0.],
           [0., 1.]])
```

```py
#2. 運用上列array計算特徵值、特徵向量?
print("eigenvalues=%s \neigenvectors=\n%s" % np.linalg.eig(array1))
```
```
output: 
    eigenvalues=[13.  2.] 
    eigenvectors=
    [[ 0.93632918 -0.70710678]
     [ 0.35112344  0.70710678]]
```
```py
#3. 運用上列array計算SVD?
print("U:\n%s \nSigma:%s \nVh:\n%s "%np.linalg.svd(array1))
```
```
output: 
    U:
    [[-0.91663818 -0.39971796]
     [-0.39971796  0.91663818]] 
    Sigma:[13.94721714  1.86417116] 
    Vh:
    [[-0.74319741 -0.6690722 ]
     [-0.6690722   0.74319741]] 
```
