# CDLENGULFING

# 指标概述

中文名称：鲸吞型。

用法：鲸吞型通常代表趋势反转，虽然本指标不考虑趋势，但必须要区分在牛市中下跌趋势出现的鲸吞型，还是在熊市中上升趋势出现的鲸吞型。

调用方法：talib.CDLENGULFING(open, high, low, close)

可选参数：penetration，一根k线在另一根k线范围内的渗透百分比

输出：看涨行情中符合形态输出80或100，看跌行情中符合形态输出-80或-100，不符合则输出0。
	若第二根实体线完全吞没第一根实体线（上下两端均超出第一根实体线），输出100或-100
	若两根实体线有其中一端处于水平状态，输出80或-80

# 指标介绍

第一根k线：阴（阳）实体线。

第二根k线：阳（阴）实体线吞没前一根实体线。