# Cupoy-Course-D10
[課程網址](https://www.cupoy.com/marathon-mission/00000174C4BC1B93000000016375706F795F70726572656C656173654355/00000176D59E20B70000000F6375706F795F72656C656173654349/)  
Cupoy Python資料科學 課程作業 D10 Pandas 資料索引操作 (資料過濾、選擇與合併)</br>

作業目標:<br>
1. 運用索引找出需要資料<br>
2. 合併資料的分法應用  

作業重點:<br>
1. 分辨索引loc、iloc差別
2. 分辨合併資料方法的不同，因應不同情況使用Merge, join, concatenate  

題目:<br>
讀取STOCK_DAY_0050_202009.csv串聯STOCK_DAY_0050_202010.csv，並且找出open小於close的資料  

```py
import pandas as pd
```

```py
#讀取STOCK_DAY_0050_202009.csv、STOCK_DAY_0050_202010.csv
stock1=pd.read_csv('STOCK_DAY_0050_202009.csv')
stock2=pd.read_csv('STOCK_DAY_0050_202010.csv')
```

```py
#串聯
stock=stock1.append(stock2)
stock
```

```
output:
    date	open	high	low	close
    0	109/09/01	102.45	103.35	101.85	103.35
    1	109/09/02	103.65	104.05	102.30	103.00
    2	109/09/03	103.70	104.30	103.20	103.30
    3	109/09/04	102.00	102.70	101.90	102.55
    4	109/09/07	102.55	103.05	101.90	102.40
    5	109/09/08	102.75	103.10	102.45	103.00
    6	109/09/09	101.75	102.35	101.15	102.30
    7	109/09/10	102.80	103.35	102.60	103.20
    8	109/09/11	103.20	103.35	102.80	103.25
    9	109/09/14	103.50	104.55	103.25	104.55
    10	109/09/15	104.45	105.20	104.25	104.95
    11	109/09/16	106.55	107.00	106.35	106.55
    12	109/09/17	106.05	106.35	105.10	105.40
    13	109/09/18	105.40	105.70	104.85	105.30
    14	109/09/21	105.20	105.90	104.35	104.45
    15	109/09/22	104.30	104.30	102.95	103.10
    16	109/09/23	103.50	103.50	102.40	102.95
    17	109/09/24	101.55	101.80	100.25	100.45
    18	109/09/25	100.75	101.45	100.05	100.65
    19	109/09/28	101.35	102.30	101.00	102.30
    20	109/09/29	102.75	103.50	102.15	102.55
    21	109/09/30	102.75	103.45	102.60	103.00
    0	109/10/05	103.45	104.05	103.00	103.05
    1	109/10/06	104.00	104.35	103.85	104.25
    2	109/10/07	104.00	105.00	103.50	104.80
    3	109/10/08	105.45	106.35	105.30	106.20
    4	109/10/12	106.70	107.70	106.70	107.05
    5	109/10/13	107.35	107.60	106.20	107.10
    6	109/10/14	107.05	107.20	106.45	106.70
    7	109/10/15	106.50	106.50	105.10	105.70
    8	109/10/16	105.70	106.30	105.10	105.25
    9	109/10/19	105.65	106.60	105.60	106.60
    10	109/10/20	106.40	106.45	106.00	106.00
    11	109/10/21	106.00	106.55	105.65	105.95
    12	109/10/22	105.70	106.10	105.50	106.10
    13	109/10/23	106.50	106.65	105.65	106.10
    14	109/10/26	106.10	106.60	105.80	106.10
    15	109/10/27	105.75	105.75	105.15	105.50
    16	109/10/28	105.50	105.50	104.80	105.00
    17	109/10/29	104.00	104.10	103.25	103.85
    18	109/10/30	103.55	103.60	102.70	103.00
```

```py
#找出open小於close的資料
stock[stock.open<stock.close]
```

```
output:
    date	open	high	low	close
    0	109/09/01	102.45	103.35	101.85	103.35
    3	109/09/04	102.00	102.70	101.90	102.55
    5	109/09/08	102.75	103.10	102.45	103.00
    6	109/09/09	101.75	102.35	101.15	102.30
    7	109/09/10	102.80	103.35	102.60	103.20
    8	109/09/11	103.20	103.35	102.80	103.25
    9	109/09/14	103.50	104.55	103.25	104.55
    10	109/09/15	104.45	105.20	104.25	104.95
    19	109/09/28	101.35	102.30	101.00	102.30
    21	109/09/30	102.75	103.45	102.60	103.00
    1	109/10/06	104.00	104.35	103.85	104.25
    2	109/10/07	104.00	105.00	103.50	104.80
    3	109/10/08	105.45	106.35	105.30	106.20
    4	109/10/12	106.70	107.70	106.70	107.05
    9	109/10/19	105.65	106.60	105.60	106.60
    12	109/10/22	105.70	106.10	105.50	106.10
```