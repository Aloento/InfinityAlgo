# 回测版本 (Backtest version)

Infinity Algo V3.0 回测版本 (Backtest version) 支持全面的策略测试和自动头寸管理 (automated position management)。在用真实资金交易前测试您的想法。

{% hint style="success" %}
**快速导航：**

- **初次使用？** 从这里开始了解概览
- **需要配置帮助？** → [配置指南](https://infinity.aloen.to/backtest-version/example-of-settings)
- **想要预设好的配置？** → [配置电子表格](https://infinity.aloen.to/backtest-version/settings-spreadsheet)
  {% endhint %}

---

### 🎯 什么是回测 (Backtesting)？

#### 目的与优势

{% columns %}
{% column width="50%" %}
**回测的意义：**

- 无需真实资金进行测试
- 验证策略逻辑
- 理解最大回撤 (drawdown)
- 建立交易信心
- 学习指标 (indicator) 行为
  {% endcolumn %}

{% column %}
**您将学到：**

- 预期胜率 (win rate)
- 平均盈亏 (average profit/loss)
- 最大回撤 (maximum drawdown)
- 最优设置 (optimal settings)
- 所需的风险承受能力
  {% endcolumn %}
  {% endcolumns %}

#### ⚠️ 重要免责声明

{% hint style="warning" %}
**现实检查：**

- 历史表现 ≠ 未来结果
- 回测不包含点差 (spreads)、滑点 (slippage)、情绪因素
- 市场在变化 - 策略也必须适应
- 这是教育内容，不是财务建议
  {% endhint %}

---

### 📊 TradingView 计划限制

您的测试能力取决于订阅计划：

| 计划                    | 历史数据条数 (Historical Bars) | 深度回测 (Deep Backtesting) | 推荐说明               |
| ----------------------- | ------------------------------ | --------------------------- | ---------------------- |
| **基础 (Basic)** (免费) | 5,000                          | ❌                          | 仅限概念测试           |
| **基础版 (Essential)**  | 10,000                         | ❌                          | 基础验证               |
| **增强版 (Plus)**       | 10,000                         | ❌                          | 休闲测试               |
| **专业版 (Premium)** ⭐ | 20,000                         | ✅                          | **严肃测试的最低要求** |
| **专家版 (Expert)**     | 25,000                         | ✅                          | 专业交易者             |
| **终极版 (Ultimate)**   | 40,000                         | ✅                          | 最高能力               |

{% hint style="info" %}
**🚀 深度回测功能 (Deep Backtesting Feature)** (仅限专业版及以上)

使用所有可用数据进行测试 (up to 2M bars)，而不仅是可见图表数据：

- 对低时间框架 (lower timeframes) 至关重要
- 统计显著性 (statistical significance) 的必要条件
- 提供可靠的结果

**没有该功能：** 仅限于图表显示的数据条数
{% endhint %}

---

### 🚀 快速开始指南

{% stepper %}
{% step %}

#### 安装回测版本

1. 移除标准版 Infinity Algo
2. 从邀请专用版本中添加 "Infinity Algo V3.0 Backtest"
3. 您将看到 "Strategy Tester" 选项卡出现
   {% endstep %}

{% step %}

#### 打开 Strategy Tester

1. 点击底部的 "Strategy Tester"
2. 首先查看 "Overview" 选项卡
3. 注意测试的日期范围
4. 验证至少进行了 30 笔交易
   {% endstep %}

{% step %}

#### 运行首次测试

初始使用默认设置：

- 暂时不更改任何内容
- 使用标准设置运行
- 记录基准性能 (baseline performance)
- 这是您的参考点
  {% endstep %}

{% step %}

#### 查看关键数据

首先关注这些指标：

- **净利润 (Net Profit)** - 是否为正数？
- **胜率 (Win Rate)** - 百分比多少？
- **最大回撤 (Max Drawdown)** - 您能承受吗？
- **总交易数 (Total Trades)** - 数据充分吗？
  {% endstep %}
  {% endstepper %}

---

### 📈 理解 Strategy Tester

#### 关键选项卡说明

{% tabs %}
{% tab title="Overview" %}
**您将看到：**

- 净利润/亏损 (Net profit/loss)
- 总交易数 (Total trades)
- 胜率百分比 (Win rate percentage)
- 利润因子 (Profit factor)
- 最大回撤 (Max drawdown)

**快速解读：**

- 绿色 = 盈利
- 30 笔以上 = 有统计意义
- 先检查回撤
  {% endtab %}

{% tab title="Performance Summary" %}
**详细指标：**

- 平均交易收益 (Average trade)
- 最佳/最差交易 (Best/worst trade)
- 连胜/连败 (Consecutive wins/losses)
- 风险指标 (Risk metrics)
- 持仓时间 (Time in market)

**用途：**

- 深度分析
- 风险评估
- 策略比较
  {% endtab %}

{% tab title="List of Trades" %}
**每笔交易详情：**

- 入场/出场价格 (Entry/exit prices)
- 盈亏 (Profit/loss)
- 持仓时长 (Duration)
- 信号类型 (Signal type)

**用途：**

- 验证逻辑
- 发现规律
- 调试问题
  {% endtab %}
  {% endtabs %}

---

### ⚡ 回测 vs 实盘交易的差异

#### 回测包括的内容

✅ 历史价格数据 (Historical price data) ✅ 您的策略逻辑 (Your strategy logic) ✅ 入场/出场信号 (Entry/exit signals) ✅ 头寸规模 (Position sizing)

#### 回测不包括的内容

❌ 点差成本 (Spread costs) ❌ 滑点 (Slippage) ❌ 手续费 (Commission fees) ❌ 情绪决策 (Emotional decisions) ❌ 连接问题 (Connection issues) ❌ 交易所停机时间 (Exchange downtime)

{% hint style="danger" %}
**经验法则：** 将回测收益降低 30-50%，以获得更现实的预期
{% endhint %}

---

### 🎯 后续步骤

#### 您的学习路径

{% columns %}
{% column width="50%" %}
**1. 学习配置** → 配置指南

- 出场策略 (Exit strategies)
- 头寸管理 (Position management)
- 风险设置
  {% endcolumn %}

{% column %}
**2. 理解理念** → 为什么使用动态优化 (Dynamic Optimization)

- AI vs 固定设置
- 市场适应性
- 常见错误
  {% endcolumn %}
  {% endcolumns %}

#### 相关资源

<table data-card-size="large" data-view="cards">
  <thead>
    <tr>
      <th></th>
      <th></th>
      <th data-hidden data-card-target data-type="content-ref"></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        <strong>配置示例</strong>⚙️<br />详细配置和策略
      </td>
      <td></td>
      <td>
        <a href="https://infinity.aloen.to/backtest-version/settings-spreadsheet">settings-spreadsheet</a>
      </td>
    </tr>
    <tr>
      <td><strong>自动告警</strong> 🔔<br />回测版本告警</td>
      <td></td>
      <td>
        <a href="https://infinity.aloen.to/backtest-version/alerts-backtest-version"
          >alerts-backtest-version</a
        >
      </td>
    </tr>
  </tbody>
</table>

{% hint style="success" %}
**准备好开始了吗？** 打开 Strategy Tester，使用默认设置运行首次测试。记录结果 - 这是您改进的基准线。
{% endhint %}
