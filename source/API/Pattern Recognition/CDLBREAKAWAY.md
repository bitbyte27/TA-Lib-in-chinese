# CDLBREAKAWAY

## 指标概述
中文名称：分离

用法：出现五日分离形态，是短期反转信号。

调用方法：talib.CDLBREAKAWAY(open, high, low, close)

输出：0代表不符合k线形态，-100表示符合看跌形态，100表示符合看涨形态。

## 指标介绍
第一根K线：长阴（阳）线

第二根K线：阴线向下（上）跳空

第三根K线：阴线或阳线，较前一天最高价更低（高），最低价更低（高）

第四根K线：阴（阳）线，较前一天最高价更低（高），最低价更低（高）

第五根K线：阳（阴）线，收盘价在第一根K线与第二根K线形成的缺口内
