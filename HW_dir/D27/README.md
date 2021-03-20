# Cupoy-Course-D27
[課程網址](https://www.cupoy.com/marathon-mission/00000174C4BC1B93000000016375706F795F70726572656C656173654355/000001754A8936E30000002D6375706F795F72656C656173654349/)  
Cupoy Python資料科學 課程作業 D27 用機率分布描述亂中有序的世界－離散型分配 (1)</br>

## 作業:
今天學到2種分配，包含，   
離散均勻分配( Discrete Uniform Distribution )   
伯努利分配( Bernoulli Distribution )   

今天我們透過作業中的問題，回想今天的內容吧! 


### 丟一個銅板，丟了100次，出現正面 50 次的機率有多大。
(提示: 先想是哪一種分配，然後透過 python 語法進行計算)


```py
import matplotlib.pyplot as plt
import numpy as np
import pandas as pd
from scipy import stats
import math
import statistics

# 這是 bermoulli分配
p = 0.5 # 假設是公平硬幣
n = 100  # 重複實驗 100次,
r = 50 # 計算出現50次正面


# 2.計算二項分佈的概率質量分佈 (probability mass function)
# 之所以稱為質量，是因為離散的點
# P(X=x) --> 是機率
probs = stats.binom.pmf(r, n, p)
print(probs)
```

output:
```
0.07958923738717888
```