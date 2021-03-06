## CDLADVANCEBLOCK

## 指标概述
中文名称：Advance Block 推进块（意译：三阳上影，强弩之末）。<br>
用法：该指标是一个看跌的指标，特别是在上升趋势中，出现该指标，说明上涨乏力，要及时减仓，以避风险。<br>
调用方法：talib.CDLADVANCEBLOCK(open, high, low, close)<br>
输出：面临“强弩之末”时，-100表示符合形态。<br>

## 指标介绍
1、三根收盘价连续抬升的红色实心阳线。<br>
2、后一根阳线的开盘价在前一根阳线的实体里或接近实体，而非明显的跳空高开。<br>
3、第一根K线，没有上影线（光头阳）或者只有短短的上影线。<br>
4、第二根、第三根K线，或者仅第三根K线，红色实心阳线变小，上影线变长，而显示出无力上攻的信号。<br>

## 图例
![](/assets/CDLADVANCEBLOCK_sh600000.png)
<br>
上图中最后3根K线，即为CDLADVANCEBLOCK

## 使用案例

```python
# 展示DataFrame中的数据
df
```
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
      <th>2016-10-20</th>
      <td>sh600000</td>
      <td>16.27</td>
      <td>16.34</td>
      <td>16.25</td>
      <td>16.29</td>
    </tr>
    <tr>
      <th>2016-10-21</th>
      <td>sh600000</td>
      <td>16.29</td>
      <td>16.34</td>
      <td>16.22</td>
      <td>16.30</td>
    </tr>
    <tr>
      <th>2016-10-24</th>
      <td>sh600000</td>
      <td>16.30</td>
      <td>16.58</td>
      <td>16.27</td>
      <td>16.47</td>
    </tr>
    <tr>
      <th>2016-10-25</th>
      <td>sh600000</td>
      <td>16.48</td>
      <td>16.50</td>
      <td>16.36</td>
      <td>16.42</td>
    </tr>
    <tr>
      <th>2016-10-26</th>
      <td>sh600000</td>
      <td>16.40</td>
      <td>16.42</td>
      <td>16.30</td>
      <td>16.32</td>
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
      <th>2016-12-29</th>
      <td>sh600000</td>
      <td>16.09</td>
      <td>16.15</td>
      <td>15.99</td>
      <td>16.07</td>
    </tr>
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
  </tbody>
</table>
<p>55 rows × 5 columns</p>

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

    array([ 16.27,  16.29,  16.3 ,  16.48,  16.4 ,  16.3 ,  16.19,  16.23,
            16.26,  16.21,  16.19,  16.3 ,  16.39,  16.45,  16.47,  16.55,
            16.56,  16.53,  16.59,  16.59,  16.58,  16.59,  16.59,  16.67,
            16.68,  16.93,  16.89,  17.15,  17.21,  17.28,  17.15,  17.1 ,
            16.95,  17.28,  17.17,  17.15,  17.14,  17.34,  17.36,  17.17,
            17.13,  16.7 ,  16.65,  16.52,  16.26,  16.32,  16.17,  16.13,
            16.25,  16.14,  16.09,  16.07,  16.21,  16.29,  16.3 ])

```python
# 调用函数
talib.CDLADVANCEBLOCK(open_p, high_p, low_p, close_p)
```

    array([   0,    0,    0,    0,    0,    0,    0,    0,    0,    0,    0,
              0, -100,    0,    0,    0,    0,    0,    0,    0,    0,    0,
              0,    0,    0,    0,    0,    0,    0,    0,    0,    0,    0,
              0,    0,    0,    0,    0,    0,    0,    0,    0,    0,    0,
              0,    0,    0,    0,    0,    0,    0,    0,    0, -100,    0])

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
      <th></th>
      <th>1天后涨跌幅</th>
      <th>3天后涨跌幅</th>
      <th>5天后涨跌幅</th>
      <th>10天后涨跌幅</th>
    </tr>
    <tr>
      <th>CDLADVANCEBLOCK</th>
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
      <td>62784.000000</td>
      <td>62784.000000</td>
      <td>62784.000000</td>
      <td>62784.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>0.000119</td>
      <td>0.004523</td>
      <td>0.006442</td>
      <td>0.017072</td>
    </tr>
    <tr>
      <th>std</th>
      <td>0.030498</td>
      <td>0.054688</td>
      <td>0.073876</td>
      <td>0.115896</td>
    </tr>
    <tr>
      <th>min</th>
      <td>-0.275208</td>
      <td>-0.347059</td>
      <td>-0.409694</td>
      <td>-0.571264</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>-0.015102</td>
      <td>-0.024431</td>
      <td>-0.032573</td>
      <td>-0.041165</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>-0.000794</td>
      <td>0.001667</td>
      <td>0.003052</td>
      <td>0.010477</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>0.014002</td>
      <td>0.029456</td>
      <td>0.039598</td>
      <td>0.066041</td>
    </tr>
    <tr>
      <th>max</th>
      <td>0.415842</td>
      <td>0.729107</td>
      <td>4.678090</td>
      <td>8.708289</td>
    </tr>
  </tbody>
</table>
</div>
