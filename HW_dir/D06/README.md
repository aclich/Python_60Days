# Cupoy-Course-D06
[課程網址](https://www.cupoy.com/marathon-mission/00000174C4BC1B93000000016375706F795F70726572656C656173654355/00000175493C2AF4000000216375706F795F72656C656173654349/)  
Cupoy Python資料科學 課程作業 D06 使用 NumPy 存取各種檔案內容</br>
</br>

作業目標<br>
讀取存取陣列資料<br>
作業重點<br>
多陣列存一起需要存成npz，讀取須注意npz中有多個陣列 
</br>  

題目:<br>
1. 將下兩列array存成npz檔<br>
array1 = np.array(range(30))<br>
array2 = np.array([2,3,5])<br>
2. 讀取剛剛的npz檔，加入下列array一起存成新的npz檔   

```py
#. 將下兩列array存成npz檔
array1 = np.array(range(30))
array2 = np.array([2,3,5])
import numpy as np
with open('hw.npz', 'wb') as f:
    np.savez(f,array1=array1,array2=array2)
```

```py
#2. 讀取剛剛的npz檔，加入下列array一起存成新的npz檔
array3 = np.array([[4,5,6], [1,2,3]])
npzfile=np.load('hw.npz')
with open('hw2.npz', 'wb') as f:
    np.savez(f,array1=npzfile['array1'],array2=npzfile['array2'],array3=array3)
```

```py
npzfile=np.load('hw2.npz')
for i in npzfile:
    print(i,npzfile[i])
```
```
output: 
    array1 [ 0  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29]
    array2 [2 3 5]
    array3 [[4 5 6]
            [1 2 3]]
```
