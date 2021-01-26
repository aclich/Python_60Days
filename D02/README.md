# Cupoy-Course-D02
Cupoy Python資料科學 課程作業 D02 NumPy 陣列進階操作  
</br>

作業目標:  
熟悉陣列維度轉換，並且會擷取需要資料  
作業重點  
使用reshap須注意order用法  
where可以運用邏輯條件擷取資料  
  
題目:  
1.將下列陣列(array1)，轉成維度為(5X6)的array，順序按列填充。(hint:order="F")  
2.呈上題的array，找出被6除餘1的數的索引  
  
```py
import numpy as np
```

```py
#1.將下列清單(list1)，轉成維度為(5X6)的array，順序按列填充。(hint:order="F")
array1 = np.array(range(30))
array1=array1.reshape(5,6, order="F")
array1
```
```
output:
    array([[ 0,  5, 10, 15, 20, 25],
           [ 1,  6, 11, 16, 21, 26],
           [ 2,  7, 12, 17, 22, 27],
           [ 3,  8, 13, 18, 23, 28],
           [ 4,  9, 14, 19, 24, 29]])
```

```py
#2.呈上題的array，找出被6除餘1的數的索引
np.where(array1%6 == 1)
```
```
output:(array([0, 1, 2, 3, 4], dtype=int32), array([5, 0, 1, 2, 3], dtype=int32))
```
