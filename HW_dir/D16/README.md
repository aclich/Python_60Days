# Cupoy-Course-D16
[課程網址](https://www.cupoy.com/marathon-mission/00000174C4BC1B93000000016375706F795F70726572656C656173654355/00000176E0F09B13000000196375706F795F72656C656173654349/)  
Cupoy Python資料科學 課程作業 D16 pandas 時間序列</br>

作業目標:<br>
1. 熟悉時間序列資料運算  
2. 敘述統計量應用在時間序列資料上  


作業重點:<br>
1. 須注意時間的間隔問題，例如:一周、一年...  
2. 敘述統計量一樣可以應用在時間序列資料上  

題目 : 運下列時間序列資料做運算<br>

```py
index = pd.date_range("1/1/2019", periods=20, freq='D')
series = pd.Series(range(20), index=index)
```

1. 將所有轉為周資料  
2. 將周資料的值取平均  

```py
import numpy as np
import pandas as pd
index = pd.date_range('1/1/2019', periods=20, freq='D')
series = pd.Series(range(20), index=index)
series
```

```
output:
  2019-01-01     0
  2019-01-02     1
  2019-01-03     2
  2019-01-04     3
  2019-01-05     4
  2019-01-06     5
  2019-01-07     6
  2019-01-08     7
  2019-01-09     8
  2019-01-10     9
  2019-01-11    10
  2019-01-12    11
  2019-01-13    12
  2019-01-14    13
  2019-01-15    14
  2019-01-16    15
  2019-01-17    16
  2019-01-18    17
  2019-01-19    18
  2019-01-20    19
  Freq: D, dtype: int64  
```

```py
#1. 將所有轉為周資料
series.to_period(freq="W").resample(rule='W').sum()
```
```
output:
  2018-12-31/2019-01-06     15
  2019-01-07/2019-01-13     63
  2019-01-14/2019-01-20    112
  Freq: W-SUN, dtype: int64
```

```py
#2. 將周資料的值取平均
series.to_period(freq='W').resample(rule='W').mean()
```

```
output: 
  2018-12-31/2019-01-06     2.5
  2019-01-07/2019-01-13     9.0
  2019-01-14/2019-01-20    16.0
  Freq: W-SUN, dtype: float64
```
