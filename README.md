# High-Frequency Factor Construction Using Order and Trade Data | 基于逐笔委托和逐笔成交数据构造高频因子

<div align="center">

**Quantitative Finance | A-Share Market | 量化金融 | A 股市场**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![Research](https://img.shields.io/badge/Research-High-Frequency%20Trading-green.svg)]()

**Author | 作者**: Chao Feng / YichuanAlex (Zixi Jiang)  
**Email | 邮箱**: jiangzixi1527435659@gmail.com  
**Last Updated | 最后更新**: 2026-03-24

</div>

---

## Overview | 项目概述

**English:**  
This quantitative finance project constructs high-frequency alpha factors using order book and trade data from the Chinese A-share market. Based on the methodology from "Forecasting high-frequency excess stock returns via data analytics and machine learning", we implement various factors capturing order flow dynamics, trade imbalance, and market microstructure patterns.

**中文:**  
本量化金融项目使用中国 A 股市场的逐笔委托和逐笔成交数据构建高频 Alpha 因子。基于《Forecasting high-frequency excess stock returns via data analytics and machine learning》的方法论，我们实现了多种捕捉订单流动态、交易不平衡和市场微观结构模式的因子。

---

## Research Background | 研究背景

**English:**  
High-frequency trading data contains rich information about market microstructure and investor behavior. By analyzing order flow and trade patterns at the tick level, we can construct predictive factors for short-term price movements. This project focuses on the Chinese A-share market, utilizing detailed order and trade data to develop actionable trading signals.

**中文:**  
高频交易数据包含有关市场微观结构和投资者行为的丰富信息。通过分析 tick 级别的订单流和交易模式，我们可以构建预测短期价格变动的因子。本项目聚焦中国 A 股市场，利用详细的委托和成交数据开发可交易的信号。

---

## Research Objectives | 研究目标

**English:**
1. Construct high-frequency factors from order book data (order arrival patterns, queue positions)
2. Build trade-based factors (trade imbalance, aggressive buying/selling)
3. Implement snapshot-based factors (bid-ask spread, order book imbalance)
4. Evaluate factor performance using IC and other metrics
5. Develop a comprehensive factor library for high-frequency trading

**中文:**
1. 从委托数据构建高频因子（订单到达模式、队列位置）
2. 构建基于成交的因子（成交不平衡、主动买卖）
3. 实现基于快照的因子（买卖价差、订单簿不平衡）
4. 使用 IC 等指标评估因子表现
5. 开发用于高频交易的综合因子库

---

## Methodology | 研究方法

**English:**
- **Data Source**: A-share stock high-frequency data (order, trade, snapshot)
- **Sample Stock**: 000001.SZ (Ping An Bank)
- **Time Period**: January 2021
- **Data Types**:
  - Order data (逐笔委托): Order arrival time, price, volume, type
  - Trade data (逐笔成交): Trade execution details
  - Snapshot data (行情快照): Bid-ask quotes, order book depth
- **Factor Categories**:
  - Order flow factors (A1, A2, ...): Order arrival patterns
  - Trade imbalance factors: Buy-sell pressure
  - Liquidity factors: Spread, depth, turnover
  - Volatility factors: Price fluctuation metrics

**中文:**
- **数据来源**: A 股股票高频数据（委托、成交、快照）
- **样本股票**: 000001.SZ（平安银行）
- **时间**: 2021 年 1 月
- **数据类型**:
  - 逐笔委托：订单到达时间、价格、数量、类型
  - 逐笔成交：成交执行详情
  - 行情快照：买卖报价、订单簿深度
- **因子类别**:
  - 订单流因子（A1、A2...）：订单到达模式
  - 交易不平衡因子：买卖压力
  - 流动性因子：价差、深度、换手率
  - 波动率因子：价格波动指标

---

## Project Structure | 项目结构

```
基于逐笔委托和逐笔成交数据构造高频因子/
│
├── README.md                              # Project documentation | 项目文档
│
├── data/                                  # Data files | 数据文件
│   ├── order_stkhf202101_000001sz.csv     # Order data | 逐笔委托数据
│   ├── trade_stkhf202101_000001sz.csv     # Trade data | 逐笔成交数据
│   ├── snap_stkhf202101_000001sz.csv      # Snapshot data | 行情快照数据
│   └── queue_stkhf202101_000001sz.csv     # Queue data | 队列数据
│
├── functions.py                           # Factor calculation functions | 因子计算函数
├── high-frequency-factors.ipynb           # Main analysis notebook | 主分析 Notebook
│
└── Forecasting high‐frequency excess stock returns via data analytics and machine.pdf
                                           # Reference paper | 参考文献
```

---

## Factor Library | 因子库

**English:**
The project implements the following factor categories:

### Order Flow Factors | 订单流因子
- **A1**: Number of orders arriving in the last 60 seconds
- **A2**: Total number of arrived orders up to current time
- **A3+**: Additional order flow metrics

### Trade Imbalance Factors | 交易不平衡因子
- Buy-sell volume imbalance
- Aggressive order ratio
- Trade direction indicators

### Liquidity Factors | 流动性因子
- Bid-ask spread
- Order book depth
- Turnover rate
- Market impact

### Volatility Factors | 波动率因子
- High-low range
- Price fluctuation frequency
- Return volatility

**中文:**
项目实现了以下因子类别：

### 订单流因子
- **A1**: 过去 60 秒到达的订单数量
- **A2**: 截至当前的累计订单数量
- **A3+**: 其他订单流指标

### 交易不平衡因子
- 买卖量不平衡
- 主动订单比例
- 交易方向指标

### 流动性因子
- 买卖价差
- 订单簿深度
- 换手率
- 市场冲击

### 波动率因子
- 高低点区间
- 价格波动频率
- 收益率波动率

---

## Installation and Usage | 安装与使用

### Prerequisites | 前置条件

**English:**
- Python 3.8 or higher
- pip package manager
- Jupyter Notebook/Lab

**中文:**
- Python 3.8 或更高版本
- pip 包管理器
- Jupyter Notebook/Lab

### Installation Steps | 安装步骤

**English:**
```bash
# 1. Clone the repository
git clone https://github.com/YichuanAlex/High_Frequency_Factors.git

# 2. Navigate to project directory
cd High_Frequency_Factors

# 3. Install required packages
pip install pandas numpy jupyter matplotlib seaborn
```

**中文:**
```bash
# 1. 克隆仓库
git clone https://github.com/YichuanAlex/High_Frequency_Factors.git

# 2. 进入项目目录
cd High_Frequency_Factors

# 3. 安装所需包
pip install pandas numpy jupyter matplotlib seaborn
```

### Running the Analysis | 运行分析

**English:**
```bash
# Open Jupyter Notebook
jupyter notebook high-frequency-factors.ipynb

# Run cells sequentially to:
# 1. Load order and trade data
# 2. Calculate high-frequency factors
# 3. Evaluate factor performance
# 4. Generate trading signals
```

**中文:**
```bash
# 打开 Jupyter Notebook
jupyter notebook high-frequency-factors.ipynb

# 按顺序运行单元格：
# 1. 加载委托和成交数据
# 2. 计算高频因子
# 3. 评估因子表现
# 4. 生成交易信号
```

---

## Data Format | 数据格式

**English:**
### Order Data | 委托数据
```csv
Exchflg,Code,Code_Mkt,Qdate,Qtime,SetNo,OrderRecNo,OrderPr,OrderVol,OrderKind,FunctionCode
```

### Trade Data | 成交数据
```csv
Exchflg,Code,Code_Mkt,Qdate,Qtime,TradeRecNo,TradePr,TradeVol,TradeAmount,TradeKind
```

### Snapshot Data | 快照数据
```csv
Exchflg,Code,Code_Mkt,Qdate,Qtime,BidPr1,BidVol1,AskPr1,AskVol1,...
```

**中文:**
### 委托数据
```csv
交易所标识，代码，市场代码，日期，时间，set 编号，订单记录号，委托价格，委托数量，委托类型，功能代码
```

### 成交数据
```csv
交易所标识，代码，市场代码，日期，时间，成交记录号，成交价格，成交数量，成交金额，成交类型
```

### 快照数据
```csv
交易所标识，代码，市场代码，日期，时间，买一价，买一量，卖一价，卖一量，...
```

---

## Reference | 参考文献

**English:**
- Chen, C., et al. (2021). "Forecasting high-frequency excess stock returns via data analytics and machine learning."
- Original implementation by Chao Feng (2023)

**中文:**
- Chen, C., 等。(2021). "Forecasting high-frequency excess stock returns via data analytics and machine learning."
- 原始实现：Chao Feng (2023)

---

## License | 许可证

**English:**
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

**中文:**
本项目采用 MIT 许可证 - 详见 [LICENSE](LICENSE) 文件。

---

## Contact | 联系方式

**English:**
- **Original Author**: Chao Feng
- **Current Maintainer**: Zixi Jiang (YichuanAlex)
- **Email**: jiangzixi1527435659@gmail.com
- **GitHub**: https://github.com/YichuanAlex

**中文:**
- **原作者**: Chao Feng
- **当前维护者**: 姜子曦 (YichuanAlex)
- **邮箱**: jiangzixi1527435659@gmail.com
- **GitHub**: https://github.com/YichuanAlex

---

## Keywords | 关键词

**English:**  
High-Frequency Trading, Factor Construction, Order Flow, A-Share Market, Quantitative Finance, Market Microstructure, Trading Signals, Machine Learning

**中文:**  
高频交易、因子构建、订单流、A 股市场、量化金融、市场微观结构、交易信号、机器学习

---

<div align="center">

**Thank you for your interest in this research!**  
**感谢您对本研究的关注!**

⭐ **If you find this project helpful, please give it a star!**  
**如果您觉得本项目有帮助，请给个星星!**

</div>
