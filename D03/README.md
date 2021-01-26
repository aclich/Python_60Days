# Cupoy-Course-D03
Cupoy Python資料科學 課程作業 D03 NumPy 陣列運算及數學 Universal Functions (ufunc)</br>
</br>

作業目標:  
嘗試練習log的函式並應用  
作業重點:  
學員需要複習log的轉換方式  
熟悉運用指數函數以及對數函數  
</br>  

題目:  
運用投影片中的分貝公式回答下列問題。  
1.正常的談話的聲壓為20000微巴斯卡，請問多少分貝?  
2.30分貝的聲壓會是50分貝的幾倍?  

```py
import numpy as np
```

```py
#1.正常的談話的聲壓為20000微巴斯卡，請問多少分貝?
#請寫下程式
V1 = 20000
V0 = 20
def cal_GdB(V1:int):
    GdB=20*np.log10(V1/20)
    return GdB
cal_GdB(V1)
```
```
output: 60.0
```

```py
#2.30分貝的聲壓會是50分貝的幾倍? #公式移項過後可以得到 V1 = ? #請寫下程式
def cal_V1(GdB:int):
    V1=20*(10**(GdB/20))
    return V1
cal_V1(30)/cal_V1(50)
```
```
output: 0.09999999999999999
```
