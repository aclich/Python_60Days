# Cupoy-Course-D05
[課程網址](https://www.cupoy.com/marathon-mission/00000174C4BC1B93000000016375706F795F70726572656C656173654355/00000175492912FB0000001E6375706F795F72656C656173654349/)  
Cupoy Python資料科學 課程作業 D04 NumPy 陣列邏輯函式 (Logic functions)</br>
</br>

作業目標<br>
計算有缺失值的資料，統計量實作<br>
作業重點<br>
當遇到缺失值有函式可以處理，不須額外寫程式刪除<br>
計算統計量時不能出現缺失值

題目:<br>
english_score = np.array([55,89,76,65,48,70])<br>
math_score = np.array([60,85,60,68,np.nan,60])<br>
chinese_score = np.array([65,90,82,72,66,77])<br>
上3列共六位同學的英文、數學、國文成績，第一個元素代表第一位同學，舉例第一位同學英文55分、數學60分、國文65分，今天第五位同學因某原因沒來考試，導致數學成績缺值，運用上列數據回答下列問題。<br>
1. 請計算各科成績平均、最大值、最小值、標準差，其中數學缺一筆資料可忽略?  
2. 第五位同學補考數學後成績為55，請計算補考後數學成績平均、最大值、最小值、標準差?  
3. 用補考後資料找出與國文成績相關係數最高的學科?  

```py
import numpy as np
english_score = np.array([55,89,76,65,48,70])
math_score = np.array([60,85,60,68,np.nan,60])
chinese_score = np.array([65,90,82,72,66,77])
```

```py
#1. 請計算各科成績平均、最大值、最小值、標準差，其中數學缺一筆資料可忽略?
def func1(score:list):
    return np.nanmean(score), np.nanmax(score), np.nanmin(score), np.nanstd(score)
 
print("English avg:%f max:%f min:%f std:%f" % func1(english_score))
print("math avg:%f max:%f min:%f std:%f" % func1(math_score))
print("Chinese avg:%f max:%f min:%f std:%f" % func1(chinese_score))
```
```
output: 
    english avg:67.166667 max:89.000000 min:48.000000 std:13.433995
    math avg:66.600000 max:85.000000 min:60.000000 std:9.707729
    chinese avg:75.333333 max:90.000000 min:65.000000 std:8.825468
```

```py
#2. 第五位同學補考數學後成績為55，請計算補考後數學成績平均、最大值、最小值、標準差?
math_score[4]=55
print("math avg:%f max:%f min:%f std:%f" % func1(math_score))
```
```
output: math avg:64.666667 max:85.000000 min:55.000000 std:9.860133
```
```py
#3. 用補考後資料找出與國文成績相關係數最高的學科?
print(f"Chinese & math corrcoef:\n{np.corrcoef(chinese_score,math_score)}")
print(f"Chinese & English corrcoef:\n{np.corrcoef(chinese_score,english_score)}")
```
```
chinese & math corrcoef:
[[1.         0.74056803]
 [0.74056803 1.        ]]
Chinese & English corrcoef:
[[1.         0.97792828]
 [0.97792828 1.        ]]
```
