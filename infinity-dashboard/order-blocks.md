# 📦 订单块 (Order Blocks)

通过成交量分析识别机构供应和需求区域，找到高概率的反转和延续交易点。

---

### 🎯 什么是订单块 (Order Blocks)?

订单块代表机构交易者可能下达大额订单的区域，形成供应区（阻力/Resistance）和需求区（支撑/Support）。这些区域通常对价格具有磁吸效应，提供了出色的入场和出场机会。

{% columns %}
{% column width="50%" %}

#### 关键组成部分 (Key Components)

- 🟢 **买入区 (Buy Zones / 看涨 OB)** - 买家介入的需求区域
- 🔴 **卖出区 (Sell Zones / 看跌 OB)** - 卖家掌控的供应区域
- 📊 **成交量指标 (Volume Metrics)** - 每个区域内的买卖压力
  {% endcolumn %}

{% column %}

#### 为什么它们有效 (Why They Work)

订单块显示"聪明资金"进场的位置，使您能够从机构级别洞察市场结构和潜在反转点。
{% endcolumn %}
{% endcolumns %}

{% hint style="info" %}
**交易优势 (Trading Edge):** 具有高方向成交量（>70%）的新订单块提供最高概率的交易设置。
{% endhint %}

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FqWinTDlo8kKvx1JL7Xj5%2Fimage.png?alt=media&#x26;token=6e1067a5-86cf-4672-871a-9a16ad43efba" alt=""><figcaption></figcaption></figure>

---

### 📊 理解订单块组成 (Understanding Order Block Components)

#### 区域结构 (Zone Structure)

每个订单块显示以下内容：

| 组成部分                  | 描述                          | 交易用途      |
| ------------------------- | ----------------------------- | ------------- |
| **彩色框 (Colored Box)**  | 区域边界                      | 入场/出场区域 |
| **成交量条 (Volume Bar)** | 买入（绿色）/卖出（红色）分布 | 强度指标      |
| **文本标签 (Text Label)** | 区域类型和指标                | 快速参考      |

#### 成交量指标显示 (Volume Metrics Display)

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2Fh1izCFW1EGBddiL18gMq%2Fimage.png?alt=media&#x26;token=5dc58c40-d818-487b-91e2-7a51a13f6866" alt=""><figcaption></figcaption></figure>

{% code overflow="wrap" %}

```
买入区 / 看涨 OB
72.474K | B/S 60/40%
```

{% endcode %}

**读取指标的方法 (Reading the metrics):**

- **72.474K** - 该区域内的总成交量
- **60% 买入 (Buy)** - 看涨压力优势
- **40% 卖出 (Sell)** - 极少卖方

{% hint style="success" %}
**专业提示 (Pro Tip):** 方向成交量 >70% 的区域最强。50/50 分布表示犹豫不决 - 应避免这些区域。
{% endhint %}

---

### ⚙️ 配置设置 (Configuration Settings)

#### 基础设置 (Basic Settings)

| 设置                                            | 选项      | 默认值 | 描述                     |
| ----------------------------------------------- | --------- | ------ | ------------------------ |
| **📦 显示买卖区 (Show Buy Sell Zones)**         | 开/关     | 开     | 启用/禁用订单块          |
| **🔍 仅显示最近的框 (Show Only Nearest Boxes)** | 开/关     | 开     | 仅显示离价格最近的区域   |
| **📏 无限扩展框 (Extend Boxes Indefinitely)**   | 开/关     | 关     | 直到被突破前保持区域可见 |
| **💥 显示突破 (Show Breaks)**                   | 开/关     | 关     | 标记区域何时被突破       |
| **🏁 显示出场标记 (Show Exit Markers)**         | 开/关     | 关     | 显示区域出场信号         |
| **📤 出场触发模式 (Exit Trigger Mode)**         | 收盘/灯芯 | 灯芯   | 如何检测出场信号         |
| **📊 显示 OB 细节 (Show OB Details)**           | 开/关     | 开     | 显示指标、中线、成交量条 |

#### 高级设置 (Advanced Settings)

| 设置                                      | 描述                     | 影响                                  |
| ----------------------------------------- | ------------------------ | ------------------------------------- |
| **🔍 灵敏度 (Sensitivity)**               | 区域检测灵敏度（1-100）  | 越高 = 越少但更大的区域               |
| **🧱 OB 消减方法 (OB Mitigation Method)** | 区域被"突破"时的处理方式 | Close = 严格，Wick = 灵敏，Mid = 平衡 |
| **🧩 隐藏重叠 (Hide Overlap)**            | 自动隐藏重叠的区域       | 保持图表整洁                          |
| **📐 斐波那契系数 (Fib Factor)**          | 突破确认（0-1）          | 越高 = 偏差变化越严格                 |
| **🔢 每侧最大 OB (Max OBs per Side)**     | 显示的最大区域数         | 3-5 用于整洁图表，10+ 用于分析        |
| **📜 OB 最大历史 (OB Max History)**       | 回溯周期（以柱数计）     | 低值性能好，高值提供更多上下文        |

---

### 📖 订单块类型 (Types of Order Blocks)

{% stepper %}
{% step %}

#### 新订单块 (Fresh Order Blocks)

- **特征 (Characteristics):** 从未被价格测试过
- **概率 (Probability):** 最高反应概率
- **策略 (Strategy):** 第一次测试通常产生最好的走势
  {% endstep %}

{% step %}

#### 已测试订单块 (Tested Order Blocks)

- **特征 (Characteristics):** 价格接触但未突破
- **概率 (Probability):** 中等强度
- **策略 (Strategy):** 寻找多重汇聚 (Multiple Confluences)
  {% endstep %}

{% step %}

#### 已突破订单块 (Broken Order Blocks)

- **特征 (Characteristics):** 价格收盘穿过区域
- **概率 (Probability):** 通常翻转角色
- **策略 (Strategy):** 旧的支撑变成阻力（反之亦然）
  {% endstep %}
  {% endstepper %}

---

### 🎯 交易信号 (Trading Signals)

#### 入场信号 (Entry Signals)

{% tabs %}
{% tab title="区域测试入场 (Zone Test Entry)" %}
**设置 (Setup):**

1. 价格接近新订单块
2. 寻找拒绝蜡烛 (Rejection Candles) 或放缓迹象
3. 在区域边缘或中线处入场
4. 止损设在区域下方/上方

**最适用于 (Best for):** 保守交易者，趋势市场
{% endtab %}

{% tab title="突破并复测 (Break and Retest)" %}
**设置 (Setup):**

1. 区域突破（出现三角形标记）
2. 价格返回测试旧区域
3. 在拒绝处入场
4. 止损设在区域极值外

**最适用于 (Best for):** 激进交易者，反转交易
{% endtab %}

{% tab title="中线精确入场 (Midline Precision)" %}
**设置 (Setup):**

1. 等待价格到达区域中线
2. 寻找在此水平的反应
3. 以紧止损入场
4. 目标为对面区域

**最适用于 (Best for):** 超短线交易者 (Scalpers)，精确入场
{% endtab %}
{% endtabs %}

#### 出场信号 (Exit Signals)

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FjCA67ZY8Wh8pyt6FWWC3%2Fimage.png?alt=media&#x26;token=1d85db68-9204-43a5-9b20-ccfc3e578350" alt=""><figcaption><p>出场信号显示价格以向上动量离开看涨订单块</p></figcaption></figure>

**Exit Markers** show when price leaves a zone:

- ⬆️ **Green arrow** = Exiting bullish zone upward (bullish continuation)
- ⬇️ **红色箭头** = 向下离开看跌区域（看跌延续）

**出场触发模式 (Exit Trigger Modes):**

- **收盘 (Close)** - K 线必须收盘在区域外（保守）
- **灯芯 (Wick)** - 任何价格尖峰穿过区域（激进）

**突破信号 (Break Signals)**

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2F1kpbqzKrFD0jrwA6mNzm%2F2025-09-12_07-55-30.jpg?alt=media&#x26;token=279ae1ff-696d-4830-9d79-c68858392b08" alt="" width="357"><figcaption><p>突破信号标记区域失效和潜在的角色翻转</p></figcaption></figure>

**突破标记 (Break Markers)** 指示区域何时被明确突破：

- 🔻 **红色向下三角** = 看涨区域被突破（看跌信号）
- 🔺 **绿色向上三角** = 看跌区域被突破（看涨信号）

**理解突破 (Understanding Breaks):**

{% columns %}
{% column width="50%" %}
**当区域被突破时 (When Zones Break):**

- 价格收盘穿过区域边界
- 成交量确认该走势
- 区域失去有效性
- 通常从支撑翻转为阻力（反之亦然）
  {% endcolumn %}

{% column %}
**交易突破 (Trading Breaks):**

- 趋势延续的直接信号
- 等待复测以获得更安全的入场
- 旧支撑变成新阻力
- 旧阻力变成新支撑
  {% endcolumn %}
  {% endcolumns %}

**消减方法 (Mitigation Methods)**（确定何时发生突破）：

| 方法             | 触发条件             | 最适用于 |
| ---------------- | -------------------- | -------- |
| **收盘 (Close)** | K 线收盘穿过区域边缘 | 保守     |
| **灯芯 (Wick)**  | 任何价格尖峰穿过区域 | 激进     |
| **中点 (Mid)**   | 收盘穿过区域中线     | 平衡方法 |

{% hint style="warning" %}
**重要提示 (Important):** 一旦突破，区域通常会翻转角色 - 之前的支撑变成阻力，反之亦然。注意已突破区域的复测。
{% endhint %}

---

---

### 📊 成交量分析 (Volume Analysis)

#### 读取买卖压力 (Reading Buy/Sell Pressure)

{% columns %}
{% column width="60%" %}
区域内的彩色条显示：

- **绿色部分** = 买入成交量百分比
- **红色部分** = 卖出成交量百分比
- **条形宽度** = 与区域宽度成正比

**强度解读 (Strength Interpretation):**

- **80/20 分布** = 非常强的区域
- **70/30 分布** = 强区域
- **60/40 分布** = 中等强度
- **50/50 分布** = 中性，应避免
  {% endcolumn %}

{% column %}
{% hint style="success" %}
**快速规则 (Quick Rule):** 交易方向成交量 >70% 的区域以获得最佳结果
{% endhint %}

{% hint style="warning" %}
**应避免 (Avoid):** 50/50 分布区域显示犹豫不决
{% endhint %}
{% endcolumn %}
{% endcolumns %}

---

### 💡 专业策略 (Pro Strategies)

#### 策略 1：区域间交易 (Strategy 1: Zone-to-Zone Trading)

从一个订单块交易到对面：

1. 在需求区域（看涨 OB）入场
2. 目标供应区域（看跌 OB）
3. 在供应区反向
4. 目标需求区域

**最适用于 (Best when):** 清晰的区间市场，定义明确的区域

#### 策略 2：汇聚堆积 (Strategy 2: Confluence Stacking)

最强的交易设置有多个因素：

- 订单块 + 多时框对齐（6+ 个时框）
- 订单块 + 云带边缘
- 订单块 + 市场结构水平（BOS/CHoCH - Break of Structure/Change of Character）
- 订单块 + 整数位

**最适用于 (Best when):** 寻找高概率入场

#### Strategy 3: Volume Gradient Trading

专注于成交量极度不平衡的区域：

- 在方向成交量 >80% 的区域入场
- 避免方向成交量 <60% 的区域
- 使用中线获得部分利润
- 持有强势头寸 (Runners) 至对面极值区域

**最适用于 (Best when):** 趋势市场，具有清晰动量

---

### 🔔 警报配置 (Alert Configuration)

| 警报名称                                     | 触发条件         | 用途          |
| -------------------------------------------- | ---------------- | ------------- |
| **进入看涨 OB (Entered Bullish OB)**         | 价格进入买入区域 | 潜在多头入场  |
| **进入看跌 OB (Entered Bearish OB)**         | 价格进入卖出区域 | 潜在空头入场  |
| **看涨 OB 向下突破 (Bullish OB Break Down)** | 买入区域被突破   | 区域失效/翻转 |
| **看跌 OB 向上突破 (Bearish OB Break Up)**   | 卖出区域被突破   | 区域失效/翻转 |
| **离开看涨 OB (Exit from Bullish OB)**       | 向上离开买入区域 | 潜在多头入场  |
| **离开看跌 OB (Exit from Bearish OB)**       | 向下离开卖出区域 | 潜在多头入场  |

---

### ⚙️ 优化提示 (Optimization Tips)

{% tabs %}
{% tab title="⚡ 超短线交易 (Scalping)" %}

```
仅显示最近的框：开
扩展框：关
出场触发模式：灯芯
每侧最大 OB：3
灵敏度：10-15（更多区域）
OB 最大历史：500 柱
消减方法：灯芯
```

{% endtab %}

{% tab title="📊 日内交易 (Day Trading)" %}

```
仅显示最近的框：开
扩展框：关
出场触发模式：收盘
每侧最大 OB：5
灵敏度：15-20（平衡）
OB 最大历史：1000 柱
消减方法：收盘
```

{% endtab %}

{% tab title="🏔️ 波段交易 (Swing Trading)" %}

```
仅显示最近的框：关
扩展框：开
出场触发模式：收盘
每侧最大 OB：10
灵敏度：20-30（质量区域）
OB 最大历史：2000 柱
消减方法：中点
```

{% endtab %}

{% tab title="📈 分析模式 (Analysis Mode)" %}

```
仅显示最近的框：关
扩展框：开
出场触发模式：收盘
每侧最大 OB：10+
显示 OB 细节：开
显示突破：开
显示出场标记：开
启用所有视觉功能
```

{% endtab %}
{% endtabs %}

---

### ⚠️ 常见错误 (Common Mistakes)

{% hint style="danger" %}
**需要避免的关键错误 (Critical Errors to Avoid):**

1. **交易每个区域** - 仅专注于新的、高成交量的区域
2. **忽视成交量指标** - 50/50 区域很弱，应避免
3. **不等待确认** - 让价格先对区域做出反应
4. **与已突破区域对抗** - 尊重区域何时失效和翻转
5. **使用太多区域** - 导致分析瘫痪，保持整洁
6. **错误的出场触发模式** - 匹配您的交易风格
   {% endhint %}

---

### 🛠️ 故障排除 (Troubleshooting)

<details>

<summary><strong>没有显示订单块 (No order blocks showing)</strong></summary>

- 检查"显示买卖区"是否启用
- 增加"OB 最大历史"设置（尝试 1000+）
- 确保已加载足够的图表历史数据
- 尝试调整灵敏度（越低 = 越多区域）
- 检查价格是否处于不带回调的趋势中

</details>

<details>

<summary><strong>重叠框过多 (Too many overlapping boxes)</strong></summary>

- 启用"仅显示最近的框"
- 启用"隐藏重叠"选项（如果可用）
- 将"每侧最大 OB"减少至 3-5
- 增加灵敏度以获得更少的较大区域

</details>

<details>

<summary><strong>成交量指标显示"n/a" (Volume metrics showing "n/a")</strong></summary>

- 需要加载更多历史数据
- 将"OB 最大历史"增加至 1000+
- 某些工具可能缺少成交量数据
- 检查您的交易品种是否有成交量数据

</details>

<details>

<summary><strong>区域意外消失 (Zones disappearing unexpectedly)</strong></summary>

- 这在区域被"消减"（突破）时是正常的
- 检查您的"OB 消减方法"设置
- 已突破的区域被移除以保持图表整洁
- 考虑启用"扩展框"以保持其可见性

</details>

<details>

<summary><strong>出场标记未显示 (Exit markers not showing)</strong></summary>

- 在设置中启用"显示出场标记"
- 检查"出场触发模式"（灯芯 vs 收盘）
- 确保价格确实离开了该区域
- 可能需要等待 K 线收盘（如果使用收盘模式）

</details>

---

### 📚 快速参考 (Quick Reference)

#### 视觉元素 (Visual Elements)

{% columns %}
{% column width="50%" %}
**区域颜色 (Zone Colors):**

- 🟢 **绿色区域** = 需求/支撑（看涨 OB）
- 🔴 **红色区域** = 供应/阻力（看跌 OB）
- ➖ **虚中线** = 区域中心/目标
- 📊 **分割条** = 成交量分布
  {% endcolumn %}

{% column %}
**标记 (Markers):**

- 🔺 **向上三角** = 看跌区域被突破（看涨）
- 🔻 **向下三角** = 看涨区域被突破（看跌）
- ⬆️ **向上箭头** = 向上离开区域
- ⬇️ **向下箭头** = 向下离开区域
  {% endcolumn %}
  {% endcolumns %}

#### 最佳实践清单 (Best Practices Checklist)

- [ ] 专注于新的、未测试的区域
- [ ] 使用成交量指标确认（>70% 方向性）
- [ ] 使用中线获得精确目标
- [ ] 与多时框仪表盘对齐结合
- [ ] 尊重已突破区域的角色翻转
- [ ] 匹配出场触发模式到您的风格
- [ ] 仅显示最近的区域以保持图表整洁

---

### 🔗 相关功能 (Related Features)

---

_如需更多支持，请访问我们的_ [_常见问题解答_](https://infinity.aloen.to/faq-and-troubleshoot) _或_ [_联系支持_](https://infinityalgo.com/#contact)_。_
