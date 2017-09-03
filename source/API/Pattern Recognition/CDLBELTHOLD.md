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
![](/assets/CDLADVANCEBLOCK_sh600000.png)
<br>

## 使用案例

```python
# 展示DataFrame中的数据
df
```


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


## 在A股市场效果
遍历A股所有股票（包含退市），考察从上市至2017年1季度，所有出现

```python
# 展现统计结果
df.groupby(pattern_name)[[str(i)+'天后涨跌幅' for i in 1, 3, 5, 10]].describe()
```
