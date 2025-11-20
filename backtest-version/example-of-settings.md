# ⚙️ 设置示例

掌握 Infinity Algo V3.0 回测版本 (Backtest) 中的每个设置。本指南涵盖所有配置选项,并为不同的交易风格提供实用示例。

{% hint style="info" %}
**前提条件:** 已经运行过第一次回测了吗? 如果没有,请先从回测概述 (Backtesting Overview) 开始。
{% endhint %}

---

### 🎯 配置理念 (Configuration Philosophy)

#### 两种方法

{% tabs %}
{% tab title="🤖 AI 优化" %}

#### 让 AI 处理

**工作原理:**

1. 启用 AI 优化 (AI Optimization)
2. 选择性能指标 (Performance Metric)
3. AI 调整灵敏度/阈值
4. 您控制退出和风险

**最适合:**

- 大多数交易者
- 市场适应
- 一致的结果

{% code title="ai-setup:" %}

```
AI Optimization: ON
Performance Metric: Total Profit
Signal Mode: AI
Sensitivity Range: Balanced
Update Frequency: 1000 bars
```

{% endcode %}

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FGBUMw9YAKG8RANQxwEEq%2Fimage.png?alt=media&#x26;token=f069b73f-c104-4f59-af54-056a9af3b859" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="🎯 手动控制" %}

#### 直接配置

**何时使用:**

- 测试特定想法
- 学习参数影响
- 个人偏好
- 可预测的行为

**您控制一切:**

- 灵敏度 (Sensitivity) (5-28)
- 阈值 (Thresholds) (60-80/20-40)
- 所有退出参数
  {% endtab %}
  {% endtabs %}

---

### 📊 退出策略详解 (Exit Strategies Explained)

#### 选择您的退出风格

{% tabs %}
{% tab title="百分比退出 (Percentage Exit)" %}

#### 固定目标与止损

**工作原理:**

- 在预定百分比处退出
- 最多 6 个止盈 (Take Profit) 水平
- 部分仓位退出
- 固定止损 (Stop Loss)

**完美适合:**

- ✅ 初学者
- ✅ 剥头皮交易 (Scalping)
- ✅ 一致的结果
- ✅ 风险管理

{% code title="percentage-config.txt" %}

```
Exit Type: Percentage
TP1: 1% (exit 50%)
TP2: 2% (exit 30%)
TP3: 3% (exit 20%)
Stop Loss: 2%
```

{% endcode %}

#### 配置示例

| 风格                       | TP1  | TP2 | TP3 | 止损 (Stop Loss) |
| -------------------------- | ---- | --- | --- | ---------------- |
| **剥头皮 (Scalping)**      | 0.5% | 1%  | -   | 0.5%             |
| **日内交易 (Day Trading)** | 1%   | 2%  | 3%  | 1.5%             |
| **波段交易 (Swing)**       | 3%   | 5%  | 8%  | 3%               |
| {% endtab %}               |      |     |     |                  |

{% tab title="信号退出 (Signals Exit)" %}

#### 基于市场的动态退出

**工作原理:**

- 根据技术信号退出
- 适应动量 (Momentum)
- 捕捉完整走势
- 无固定目标

{% code title="signals-config.txt" %}

```
Exit Type: Signals
Use TP Signals: ON
Min Profit Before Exit: 0.5%
Adapt to Volatility: ON
```

{% endcode %}

**最适合:**

- ✅ 趋势市场
- ✅ 有经验的交易者
- ✅ 更大的走势
- ⚠️ 更高的波动性 (Variance)
  {% endtab %}

{% tab title="反向信号 (Opposite Signal)" %}

#### 最大化趋势捕捉

**工作原理:**

- 持有直到反转信号出现
- 无止盈目标
- 无止损
- 纯趋势跟随 (Trend Following)

**示例:**

- 多头在卖出 (Sell) 信号时退出
- 空头在买入 (Buy) 信号时退出

{% hint style="warning" %}
**仅限高级用户:** 需要强大的心理素质和风险管理
{% endhint %}
{% endtab %}
{% endtabs %}

---

### 💰 仓位管理 (Position Management)

#### 金字塔加仓 (Pyramiding) (逐步增仓 Scaling In)

{% columns %}
{% column width="50%" %}
**这是什么?** 在盈利仓位上加仓

**设置:**

- `More Entries(更多入场)`: 启用/禁用
- `Pyramiding(金字塔加仓)`: 1-10 次加仓
- 每次加仓的规模
  {% endcolumn %}

{% column %}
{% code title="pyramid-setup:" %}

```
Pyramiding: 2
Entry 1: 33% capital
Entry 2: 33% at +1%
Entry 3: 34% at +2%
Max Risk: 2% total
```

{% endcode %}
{% endcolumn %}
{% endcolumns %}

#### 风险等级

| 经验水平                | 金字塔加仓 | 每笔交易风险 | 仓位规模        |
| ----------------------- | ---------- | ------------ | --------------- |
| **初学者 (Beginner)**   | 0          | 1%           | 100% 入场       |
| **中级 (Intermediate)** | 1          | 1.5%         | 50% + 50%       |
| **高级 (Advanced)**     | 2-3        | 2%           | 各 33%          |
| **专家 (Expert)**       | 3+         | 2%           | 自定义 (Custom) |

---

### 🎨 按交易风格的配置

#### 快速参考模板

{% tabs %}
{% tab title="⚡ 剥头皮 (Scalping)" %}
{% code title="scalping-config.txt" %}

```
Timeframe: 1-5 min
Sensitivity: 5-9
Thresholds: 75/25
Exit Type: Percentage
TP1: 0.5% (100%)
Stop Loss: 0.5%
Pyramiding: 0
```

{% endcode %}
{% endtab %}

{% tab title="📊 日内交易 (Day Trading)" %}
{% code title="daytrading-config:" %}

```
Timeframe: 15-60 min
Sensitivity: 10-14
Thresholds: 70/30
Exit Type: Percentage
TP1: 1% (50%)
TP2: 2% (50%)
Stop Loss: 1.5%
Pyramiding: 0-1
```

{% endcode %}
{% endtab %}

{% tab title="📈 波段交易 (Swing Trading)" %}
{% code title="swing-config:" %}

```
Timeframe: 4H-Daily
Sensitivity: 15-21
Thresholds: 70/30
Exit Type: Signals
Min Profit: 1%
Stop Loss: 3-5%
Pyramiding: 1-2
```

{% endcode %}
{% endtab %}

{% tab title="📅 仓位交易 (Position Trading)" %}
{% code title="position-config:" %}

```
Timeframe: Daily-Weekly
Sensitivity: 22-28
Thresholds: 65/35
Exit Type: Opposite Signal
Stop Loss: Optional (5-10%)
Pyramiding: 2-3
```

{% endcode %}
{% endtab %}
{% endtabs %}

---

### 🧪 测试您的配置

#### 系统方法

{% stepper %}
{% step %}

#### 记录设置

测试前写下每个参数
{% endstep %}

{% step %}

#### 运行基准测试 (Baseline)

先在过去 6 个月上测试
{% endstep %}

{% step %}

#### 压力测试 (Stress Test)

在最糟糕的市场时期测试:

- 2020 年 3 月
- 2021 年 5 月
- 2022 年熊市
  {% endstep %}

{% step %}

#### 比较结果

寻找不同时期的一致性
{% endstep %}

{% step %}

#### 细化一个变量

一次只更改一个设置
{% endstep %}
{% endstepper %}

---

### 📈 按风格划分的性能目标

| 交易风格                   | 最低盈利因子 (Min Profit Factor) | 最大回撤 (Max Drawdown) | 胜率 (Win Rate) | 平均风报比 (Avg RRR) |
| -------------------------- | -------------------------------- | ----------------------- | --------------- | -------------------- |
| **剥头皮 (Scalping)**      | 1.3                              | 10%                     | 60%+            | 1:1                  |
| **日内交易 (Day Trading)** | 1.5                              | 15%                     | 50%+            | 1.5:1                |
| **波段交易 (Swing)**       | 2.0                              | 20%                     | 40%+            | 2:1                  |
| **仓位交易 (Position)**    | 2.5                              | 25%                     | 35%+            | 3:1                  |

---

### ❓ 配置常见问题 (Configuration FAQ)

<details>

<summary><strong>哪种退出类型最适合初学者?</strong></summary>

从**百分比退出 (Percentage Exit)** 开始:

- Predictable results
- Easy to understand
- Better risk control
- Consistent outcomes

在 50+笔交易经验后再转向信号/反向信号退出。

</details>

<details>

<summary><strong>我应该使用金字塔加仓 (Pyramiding) 吗?</strong></summary>

**渐进方法:**

1. 前 30 笔交易: 不使用金字塔加仓
2. 盈利后: 添加 1 个级别
3. 100 笔交易后: 考虑 2 个级别
4. 仅限专家: 3+ 个级别

始终将总风险控制在 2% 以下。

</details>

<details>

<summary><strong>如何知道设置是否过度优化 (Over-optimized)?</strong></summary>

**警告信号:**

- 小的更改 = 大的结果差异
- 回测表现惊人,实盘结果很差
- 只在一个商品上有效
- 需要完美的条件

**解决方案:** 在多个时间框架和商品上测试。

</details>

---

{% hint style="success" %}
**下一步:** 根据您的交易风格配置设置,然后彻底测试。记住:一致性胜过完美。
{% endhint %}
