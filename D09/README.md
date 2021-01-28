# Cupoy-Course-D09
[課程網址](https://www.cupoy.com/marathon-mission/00000174C4BC1B93000000016375706F795F70726572656C656173654355/00000175495A7361000000246375706F795F72656C656173654349/)  
Cupoy Python資料科學 課程作業 D09 使用 Pandas 讀寫各種常用的檔案格式</br>

作業目標:  
1.讀取各種檔案格式  
2.輸出各種檔案格式  
作業重點:<br>
1.不同檔案讀取方式皆不同，須了解檔案格式中的邏輯，例如:csv是以逗號分隔<br>
2.讀取、輸出檔案的程式碼不同，須注意使用方式  

題目:  
讀取資料夾中boston.csv讀取其欄位CHAS、NOX、RM，輸出成.xlsx檔案  

```py
import numpy as np 
```
```py
#讀取資料夾中boston.csv讀取其欄位CHAS、NOX、RM，輸出成.xlsx檔案
boston=pd.read_csv('boston.csv',header=0,usecols=['CHAS','NOX','RM'])
boston.to_excel('boston.xlsx',sheet_name='boston')
pd.read_excel('boston.xlsx')
```

```
output:
	Unnamed: 0	CHAS	NOX	RM
    0	0	0	0.538	6.575
    1	1	0	0.469	6.421
    2	2	0	0.469	7.185
    3	3	0	0.458	6.998
    4	4	0	0.458	7.147
    ...	...	...	...	...
    501	501	0	0.573	6.593
    502	502	0	0.573	6.120
    503	503	0	0.573	6.976
    504	504	0	0.573	6.794
    505	505	0	0.573	6.030

    506 rows × 4 columns
```
