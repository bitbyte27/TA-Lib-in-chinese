## CDLBELTHOLD

## 指标概述
中文名称：Belt-hold 捉腰带线（意译：光脚阳与光头阴）。<br>
用法：较长的“光脚阳线”为买点，较长的“光头阴线”为卖点。<br>
调用方法：talib.CDLBELTHOLD(open, high, low, close)<br>
输出：当形态为“光脚阳”时，100代表符合k线形态；当形态为“光头阴”时，-100表示符合形态。<br>

## 指标介绍
1、较长的红色实心阳线，或较长的绿色实体阴线。<br>
2、几乎没有下影线或上影线，即“光脚阳”和“光头阴”。<br>

## 图例
![](/assets/CDLBELTHOLD_sh600000_+100.png)
<br>
当形态为“光脚阳”时，100代表符合k线形态，上图中最后1根K线，即为CDLBELTHOLD
<br>
<br>
![](/assets/CDLBELTHOLD_sh600000_-100.png)
<br>
当形态为“光头阴”时，-100表示符合形态，上图中最后3根K线，均为CDLBELTHOLD

## 使用案例

```python
# 展示DataFrame中的数据
df
```
<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>股票代码</th>
      <th>开盘价</th>
      <th>最高价</th>
      <th>最低价</th>
      <th>收盘价</th>
    </tr>
    <tr>
      <th>交易日期</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2016-12-30</th>
      <td>sh600000</td>
      <td>16.07</td>
      <td>16.23</td>
      <td>16.04</td>
      <td>16.21</td>
    </tr>
    <tr>
      <th>2017-01-03</th>
      <td>sh600000</td>
      <td>16.21</td>
      <td>16.44</td>
      <td>16.17</td>
      <td>16.30</td>
    </tr>
    <tr>
      <th>2017-01-04</th>
      <td>sh600000</td>
      <td>16.29</td>
      <td>16.35</td>
      <td>16.18</td>
      <td>16.33</td>
    </tr>
    <tr>
      <th>2017-01-05</th>
      <td>sh600000</td>
      <td>16.30</td>
      <td>16.38</td>
      <td>16.24</td>
      <td>16.30</td>
    </tr>
    <tr>
      <th>2017-01-06</th>
      <td>sh600000</td>
      <td>16.30</td>
      <td>16.30</td>
      <td>16.13</td>
      <td>16.18</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2017-03-23</th>
      <td>sh600000</td>
      <td>15.80</td>
      <td>15.92</td>
      <td>15.79</td>
      <td>15.88</td>
    </tr>
    <tr>
      <th>2017-03-24</th>
      <td>sh600000</td>
      <td>15.85</td>
      <td>16.00</td>
      <td>15.83</td>
      <td>15.96</td>
    </tr>
    <tr>
      <th>2017-03-27</th>
      <td>sh600000</td>
      <td>15.97</td>
      <td>16.13</td>
      <td>15.90</td>
      <td>16.04</td>
    </tr>
    <tr>
      <th>2017-03-28</th>
      <td>sh600000</td>
      <td>16.11</td>
      <td>16.13</td>
      <td>15.97</td>
      <td>16.01</td>
    </tr>
    <tr>
      <th>2017-03-29</th>
      <td>sh600000</td>
      <td>16.01</td>
      <td>16.11</td>
      <td>15.80</td>
      <td>15.87</td>
    </tr>
  </tbody>
</table>
<p>58 rows × 5 columns</p>
</div>

```python
# 赋值开、高、收、低价格，np.array格式。
open_p = df['开盘价'].values
high_p = df['最高价'].values
low_p = df['最低价'].values
close_p = df['收盘价'].values
```

```python
# 展示open_p中的数据
open_p
```

    array([ 16.07,  16.21,  16.29,  16.3 ,  16.3 ,  16.24,  16.18,  16.24,
            16.18,  16.1 ,  16.23,  16.46,  16.42,  16.43,  16.58,  16.66,
            16.58,  16.69,  16.69,  16.82,  16.75,  16.65,  16.63,  16.68,
            16.76,  16.88,  16.87,  16.82,  16.88,  16.78,  16.62,  16.88,
            16.88,  16.78,  16.67,  16.69,  16.58,  16.58,  16.62,  16.42,
            16.37,  16.38,  16.4 ,  16.37,  16.23,  16.23,  16.34,  16.24,
            16.27,  16.3 ,  16.24,  16.15,  15.98,  15.8 ,  15.85,  15.97,
            16.11,  16.01])

```python
# 调用函数
talib.CDLBELTHOLD(open_p, high_p, low_p, close_p)
```

    array([   0,    0,    0,    0,    0,    0,    0,    0,    0,    0,    0,
              0,    0,  100,    0,    0,  100,    0,    0,    0,    0,    0,
              0,    0,    0,    0, -100,    0,    0,    0,  100,    0,    0,
              0,    0,    0,    0,    0, -100,    0,    0,    0,    0,    0,
              0,    0, -100,    0,    0,    0, -100, -100, -100,    0,    0,
              0,    0,    0])


## 在A股市场效果
遍历A股所有股票（包含退市），考察从上市至2017年1季度，所有出现

```python
# 展现统计结果
df.groupby(pattern_name)[[str(i)+'天后涨跌幅' for i in 1, 3, 5, 10]].describe()
```

<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>交易日期</th>
      <th>开盘价_后复权</th>
      <th>最高价_后复权</th>
      <th>最低价_后复权</th>
      <th>收盘价_后复权</th>
      <th>1天后涨跌幅</th>
      <th>3天后涨跌幅</th>
      <th>5天后涨跌幅</th>
      <th>10天后涨跌幅</th>
      <th>CDLBELTHOLD</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1999-12-06</td>
      <td>26.300060</td>
      <td>26.350060</td>
      <td>25.600058</td>
      <td>25.660058</td>
      <td>-0.002338</td>
      <td>-0.011691</td>
      <td>0.010134</td>
      <td>-0.016367</td>
      <td>-100</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1999-12-14</td>
      <td>25.700077</td>
      <td>26.000078</td>
      <td>25.700077</td>
      <td>26.000078</td>
      <td>0.017308</td>
      <td>-0.016153</td>
      <td>-0.032693</td>
      <td>-0.051539</td>
      <td>100</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1999-12-16</td>
      <td>26.500094</td>
      <td>26.500094</td>
      <td>25.950092</td>
      <td>26.000092</td>
      <td>-0.016154</td>
      <td>-0.032693</td>
      <td>-0.048078</td>
      <td>-0.016540</td>
      <td>-100</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2000-01-11</td>
      <td>27.250047</td>
      <td>27.300047</td>
      <td>26.120045</td>
      <td>26.200045</td>
      <td>-0.041221</td>
      <td>-0.076335</td>
      <td>-0.078626</td>
      <td>-0.061450</td>
      <td>-100</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2000-01-12</td>
      <td>26.000055</td>
      <td>26.000055</td>
      <td>24.800052</td>
      <td>25.120053</td>
      <td>-0.008758</td>
      <td>-0.028662</td>
      <td>-0.039411</td>
      <td>-0.028264</td>
      <td>-100</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>1411737</th>
      <td>2017-03-03</td>
      <td>58.989946</td>
      <td>58.989946</td>
      <td>56.509948</td>
      <td>56.649948</td>
      <td>0.021183</td>
      <td>0.067079</td>
      <td>0.016947</td>
      <td>0.042895</td>
      <td>-100</td>
    </tr>
    <tr>
      <th>1411738</th>
      <td>2017-03-16</td>
      <td>58.679963</td>
      <td>61.729961</td>
      <td>58.679963</td>
      <td>60.829961</td>
      <td>-0.028769</td>
      <td>0.045208</td>
      <td>0.006082</td>
      <td>-0.118691</td>
      <td>100</td>
    </tr>
    <tr>
      <th>1411739</th>
      <td>2017-03-21</td>
      <td>60.659965</td>
      <td>63.579963</td>
      <td>60.429965</td>
      <td>63.579963</td>
      <td>0.005033</td>
      <td>-0.012898</td>
      <td>-0.023750</td>
      <td>-0.188109</td>
      <td>100</td>
    </tr>
    <tr>
      <th>1411740</th>
      <td>2017-03-23</td>
      <td>64.379929</td>
      <td>64.379929</td>
      <td>59.429934</td>
      <td>61.199932</td>
      <td>0.025490</td>
      <td>0.014216</td>
      <td>-0.124019</td>
      <td>-0.248202</td>
      <td>-100</td>
    </tr>
    <tr>
      <th>1411741</th>
      <td>2017-03-28</td>
      <td>183.990190</td>
      <td>184.000190</td>
      <td>170.600176</td>
      <td>170.740176</td>
      <td>-0.021905</td>
      <td>-0.098044</td>
      <td>-0.074616</td>
      <td>-0.157784</td>
      <td>-100</td>
    </tr>
  </tbody>
</table>
<p>1411742 rows × 10 columns</p>
</div>




```python
# 展现统计结果
df.groupby(pattern_name)[[str(i)+'天后涨跌幅' for i in 1, 3, 5, 10]].describe().stack()
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th></th>
      <th>1天后涨跌幅</th>
      <th>3天后涨跌幅</th>
      <th>5天后涨跌幅</th>
      <th>10天后涨跌幅</th>
    </tr>
    <tr>
      <th>CDLBELTHOLD</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th rowspan="8" valign="top">-100</th>
      <th>count</th>
      <td>726130.000000</td>
      <td>7.261300e+05</td>
      <td>726130.000000</td>
      <td>7.261300e+05</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>-0.001479</td>
      <td>2.660137e-04</td>
      <td>0.002486</td>
      <td>5.289425e-03</td>
    </tr>
    <tr>
      <th>std</th>
      <td>0.032718</td>
      <td>5.839915e-02</td>
      <td>0.081645</td>
      <td>1.189107e-01</td>
    </tr>
    <tr>
      <th>min</th>
      <td>-0.473855</td>
      <td>-5.250677e-01</td>
      <td>-0.904411</td>
      <td>-9.135528e-01</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>-0.015365</td>
      <td>-2.796031e-02</td>
      <td>-0.035202</td>
      <td>-4.993038e-02</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>0.000501</td>
      <td>-4.688430e-07</td>
      <td>0.000755</td>
      <td>9.601724e-09</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>0.013556</td>
      <td>2.759770e-02</td>
      <td>0.038514</td>
      <td>5.407989e-02</td>
    </tr>
    <tr>
      <th>max</th>
      <td>8.481658</td>
      <td>1.113675e+01</td>
      <td>15.208114</td>
      <td>2.303857e+01</td>
    </tr>
    <tr>
      <th rowspan="8" valign="top">100</th>
      <th>count</th>
      <td>685612.000000</td>
      <td>6.856120e+05</td>
      <td>685612.000000</td>
      <td>6.856120e+05</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>0.004587</td>
      <td>8.245119e-03</td>
      <td>0.010596</td>
      <td>1.679681e-02</td>
    </tr>
    <tr>
      <th>std</th>
      <td>0.041654</td>
      <td>7.692737e-02</td>
      <td>0.094117</td>
      <td>1.281074e-01</td>
    </tr>
    <tr>
      <th>min</th>
      <td>-0.893692</td>
      <td>-8.794397e-01</td>
      <td>-0.878739</td>
      <td>-8.813090e-01</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>-0.012281</td>
      <td>-2.239355e-02</td>
      <td>-0.030695</td>
      <td>-4.406014e-02</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>0.001575</td>
      <td>4.237609e-03</td>
      <td>0.004695</td>
      <td>7.617861e-03</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>0.018147</td>
      <td>3.342256e-02</td>
      <td>0.043421</td>
      <td>6.467764e-02</td>
    </tr>
    <tr>
      <th>max</th>
      <td>13.196428</td>
      <td>2.254286e+01</td>
      <td>24.911694</td>
      <td>2.218961e+01</td>
    </tr>
  </tbody>
</table>
</div>
