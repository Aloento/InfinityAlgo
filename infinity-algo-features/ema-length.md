# 📉📈 EMA 长度 (EMA Length)

设置趋势过滤器 (Trend Filter)，决定信号是跟随趋势还是逆向趋势。

![EMA 长度设置](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2F4BHg7t8TgXExrbCoG9RM%2Fema.png?alt=media&token=f730df12-fad7-490a-9ab3-d1f07ebf888c)

---

### 🎯 工作原理 (How It Works)

EMA 充当趋势过滤器，改变信号的行为方式：

{% tabs %}
{% tab title="📈 智能信号 (Smart Signals)" %}

#### 趋势跟随模式 (Trend-Following Mode)

**买入条件：**

- 价格 **高于** EMA
- 确认上升趋势

**卖出条件：**

- 价格 **低于** EMA
- 确认下降趋势

{% hint style="success" %}
**适用于：** 顺势交易、更安全的入场、趋势明显的市场
{% endhint %}
{% endtab %}

{% tab title="📉 普通信号 (Normal Signals)" %}

#### 逆势模式 (Counter-Trend Mode)

**买入条件：**

- 价格 **低于** EMA
- 寻找向上反转

**卖出条件：**

- 价格 **高于** EMA
- 寻找向下反转

{% hint style="warning" %}
**适用于：** 均值回归 (Mean Reversion)、捕捉反转、震荡市场
{% endhint %}
{% endtab %}
{% endtabs %}

---

### 📊 常见 EMA 设置 (Common EMA Settings)

| EMA 长度 | 类型   | 最适合                      | 信号频率 |
| -------- | ------ | --------------------------- | -------- |
| **20**   | 短期   | 超短线交易 (Scalping)       | 信号频繁 |
| **50**   | 中期   | 日内交易 (Day Trading)      | 中等频率 |
| **100**  | 中长期 | 波段交易 (Swing Trading)    | 适中     |
| **200**  | 长期   | 持仓交易 (Position Trading) | 信号稀少 |

---

### ⚡ 快速策略指南 (Quick Strategy Guide)

{% columns %}
{% column width="50%" %}

#### 趋势跟随设置 (Trend Following Setup)

**设置：**

- 信号模式：`智能 (Smart)`
- EMA 长度：`200`
- 市场：趋势明显

**结果：** 仅在主趋势方向交易
{% endcolumn %}

{% column %}

#### 均值回归设置 (Mean Reversion Setup)

**设置：**

- 信号模式：`普通 (Normal)`
- EMA 长度：`20`
- 市场：震荡

**结果：** 捕捉快速反转
{% endcolumn %}
{% endcolumns %}

---

### 🎨 可视化示例 (Visual Example)

| 场景           | 智能信号 (Smart Signal) | 普通信号 (Normal Signal) |
| -------------- | ----------------------- | ------------------------ |
| **价格 > EMA** | ✅ 仅显示买入信号       | ✅ 仅显示卖出信号        |
| **价格 < EMA** | ✅ 仅显示卖出信号       | ✅ 仅显示买入信号        |

---

### 💡 专业组合方案 (Pro Combinations)

{% hint style="info" %}
**常用设置方案：**

**保守趋势交易：**

- 智能 (Smart) + EMA 200 = 长期趋势交易

**激进超短线交易：**

- 普通 (Normal) + EMA 20 = 快速反转

**平衡波段交易：**

- 智能 (Smart) + EMA 50 = 中期动量交易
  {% endhint %}

---

### ⚠️ 重要提示 (Important Notes)

- **HL Sniper/AI 模式：** EMA 仍会过滤，但使用不同的逻辑
- **EMA 越大 = 信号越少** 但质量更高
- **EMA 越小 = 信号越多** 但噪音也更多
- 建议从 EMA 50 开始获得平衡的结果

{% hint style="success" %}
**快速提示：** 根据时间周期匹配 EMA - 日内交易用 20，波段交易用 50，持仓交易用 200
{% endhint %}
