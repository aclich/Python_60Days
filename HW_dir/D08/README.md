# Cupoy-Course-D08
[課程網址](https://www.cupoy.com/marathon-mission/00000174C4BC1B93000000016375706F795F70726572656C656173654355/000001754950A6D9000000236375706F795F72656C656173654349/)  
Cupoy Python資料科學 課程作業 D08 NumPy 結構化陣列 (Structured Arrays)</br>

作業目標<br>
在一個陣列中放入多屬性陣列，進一步對陣列做運算<br>
作業重點<br>
在建立結構化陣列前需要先設定屬性，在做運算時須注意資料屬性  

題目:<br>
name_list = ['小明','小華','小菁','小美','小張','John','Mark','Tom']<br>
sex_list = ['boy','boy','girl','girl','boy','boy','boy','boy']<br>
weight_list = [67.5,75.3,50.1,45.5,80.8,90.4,78.4,70.7]<br>
rank_list = [8,1,5,4,7,6,2,3]<br>
myopia_list = [True,True,False,False,True,True,False,False]<br>
1. 將上列list依照['name', 'sex', 'weight', 'rank', 'myopia']順序擺入array，並且資料型態順序擺入[Unicode,Unicode,float,int,boolean]<br>
2. 呈上題，將array中體重(weight)數據集取出算出全部平均體重  
3. 呈上題，進一步算出男生(sex欄位是boy)平均體重、女生(sex欄位是girl)平均體重  

```py
import numpy as np 
name_list = ['小明','小華','小菁','小美','小張','John','Mark','Tom']
sex_list = ['boy','boy','girl','girl','boy','boy','boy','boy']
weight_list = [67.5,75.3,50.1,45.5,80.8,90.4,78.4,70.7]
rank_list = [8,1,5,4,7,6,2,3]
myopia_list = [True,True,False,False,True,True,False,False]
```
```py
#1. 將上列list依照['name', 'sex', 'weight', 'rank', 'myopia']順序擺入array，並且資料型態順序擺入[Unicode,Unicode,float,int,boolean]
dt=np.dtype({'names':('name','sex','weight','rank','myopia'),'formats':((str,8),'U8','f8','i8','b1')})
array1=np.zeros(8,dtype=dt)
array1['name'],array1['sex'],array1['weight'],array1['rank'],array1['myopia']=name_list,sex_list,weight_list,rank_list,myopia_list
array1
```

```
output:
    array([('小明', 'boy', 67.5, 8,  True), ('小華', 'boy', 75.3, 1,  True),
        ('小菁', 'girl', 50.1, 5, False), ('小美', 'girl', 45.5, 4, False),
        ('小張', 'boy', 80.8, 7,  True), ('John', 'boy', 90.4, 6,  True),
        ('Mark', 'boy', 78.4, 2, False), ('Tom', 'boy', 70.7, 3, False)],
        dtype=[('name', '<U8'), ('sex', '<U8'), ('weight', '<f8'), ('rank', '<i8'), ('myopia', '?')])
```

```py
#2. 呈上題，將array中體重(weight)數據集取出算出全部平均體重
np.average(array1['weight'])
```
```
output:69.8375
```
```py
#3. 呈上題，進一步算出男生(sex欄位是boy)平均體重
np.average(array1[array1['sex'] == 'boy']['weight'])
```
```
output:77.18333333333332 
```
```py
#3. 呈上題，進一步算出女生(sex欄位是girl)平均體重
np.average(array1[array1['sex']=='girl']['weight'])
```
```
output:47.8 
```
