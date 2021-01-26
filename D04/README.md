# Cupoy-Course-D04
[課程網址](https://www.cupoy.com/marathon-mission/00000174C4BC1B93000000016375706F795F70726572656C656173654355/00000175491F33860000001D6375706F795F72656C656173654349/)
Cupoy Python資料科學 課程作業 D04 NumPy 陣列邏輯函式 (Logic functions)</br>
</br>

作業目標:  
熟悉邏輯運算<br>
作業重點<br>
五大類邏輯函式與其對應的函式操作  
作業重點:  
學員需要複習log的轉換方式  
熟悉運用指數函數以及對數函數  
</br>  

題目:<br>
english_score = np.array([55,89,76,65,48,70])<br>
math_score = np.array([60,85,60,68,55,60])<br>
chinese_score = np.array([65,90,82,72,66,77])<br>
上3列共六位同學的英文、數學、國文成績，第一個元素代表第一位同學，舉例第一位同學英文55分、數學60分、國文65分，運用上列數據回答下列問題。<br>
1. 有多少學生英文成績比數學成績高?  
2. 是否全班同學最高分都是國文?  

```py
import numpy as np
english_score = np.array([55,89,76,65,48,70])
math_score = np.array([60,85,60,68,55,60])
chinese_score = np.array([65,90,82,72,66,77])
```

```py
#1.有多少學生英文成績比數學成績高?
np.count_nonzero(np.array(english_score>math_score) == True )
```
```
output: 3
```

```py
#2.是否全班同學最高分都是國文?
np.all(np.array(np.logical_and(chinese_score > math_score,chinese_score > english_score)))
```
```
output: True
```
