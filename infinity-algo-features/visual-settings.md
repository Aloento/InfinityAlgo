# 🎨 视觉设置 (Visual Settings)

通过动态色彩和可视化市场洞察增强您的图表可读性。

![视觉设置面板 (Visual Settings Panel)](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2F7PQBwyVUPgmxl8inMLVo%2Fimage.png?alt=media&token=3cdd0452-b0c0-4e49-a16b-b76a30f72793)

---

## 🎨 颜色选项 (Color Options)

{% tabs %}
{% tab title="🌈 Bar Color" %}

### 基于信号的 K 线颜色 (Signal-Based Bar Colors)

**作用：** 根据最后一个信号方向为蜡烛线着色

**工作原理：**

- 买入信号后 → 看涨色彩 (Bullish color)
- 卖出信号后 → 看跌色彩 (Bearish color)
- 显示当前市场偏向 (bias)

{% code title="color-logic.txt" %}

```
买入信号 (Buy Signal) → 绿色K线
↓
继续绿色直到...
↓
卖出信号 (Sell Signal) → 红色K线
```

{% endcode %}

### 视觉对比 (Visual Comparison)

**启用 (Enabled)**

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FSJMue2YpvoKJiBhtGgo3%2F2025-08-20_17-14-52.jpg?alt=media&#x26;token=c7cf0a2f-7abc-4977-955c-207f1630702a" alt=""><figcaption><p><strong>清晰的趋势方向 (Clear trend direction)</strong></p></figcaption></figure>

**禁用 (Disabled)**

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FcvTHxZFELPrOJ5GNNwFp%2F2025-08-20_17-14-13.jpg?alt=media&#x26;token=410faf01-4ca5-48fb-8c83-b873d723e8e8" alt=""><figcaption><p><strong>标准K线 (Standard candles)</strong></p></figcaption></figure>
{% endtab %}

{% tab title="🟣 Signal Strength" %}

### 动量衰弱指示器 (Momentum Weakening Indicator)

**作用：** 紫色阴影显示信号强度衰退

![信号强度设置 (Signal Strength Settings)](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FjCH5xz6YvJ5oH8YqhrfI%2Fimage.png?alt=media&token=b326090d-f63e-4864-bfb0-790fad3105e4)

**颜色含义 (Color Meanings)：**

| 颜色 (Color)              | 指示 (Indicates)             | 操作 (Action)                           |
| ------------------------- | ---------------------------- | --------------------------------------- |
| **浅紫色 (Light Purple)** | 初期衰弱 (Initial weakening) | 观察反转信号 (Watch for reversal)       |
| **深紫色 (Dark Purple)**  | 强烈衰弱 (Strong weakening)  | 潜在出场/反转 (Potential exit/reversal) |
| **主题色 (Theme Color)**  | 强势趋势 (Strong trend)      | 继续持仓 (Continue position)            |

### 视觉示例 (Visual Example)

![紫色强度着色 (Purple Strength Coloring)](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FvGvIo2LSm6fs99t4Bro0%2F2025-08-20_17-09-08.jpg?alt=media&token=b5eb03c8-3981-42fa-8df8-7a8f4549db19)

{% hint style="info" %}
**专业提示 (Pro Tip)：** 紫色 K 线通常先于趋势反转出现 - 用于提早出场
{% endhint %}
{% endtab %}

{% tab title="🎨 Background" %}

### 动态背景渐变 (Dynamic Background Gradient)

**作用：** 背景颜色显示市场动量

![背景设置 (Background Settings)](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FPwfAZ9z3wrX6DBs0gtPs%2Fimage.png?alt=media&token=e7c2027a-952e-4e30-83e7-813a193a92bb)

**工作原理 (How it works)：**

- 基于振荡器 (oscillator) 的渐变
- 看跌 → 看涨颜色
- 平滑过渡
- 环境市场感觉

{% code title="gradient-zones:" %}

```
看跌动量 (Bearish momentum) → 红色渐变
中性 (Neutral) → 混合色彩
看涨动量 (Bullish momentum) → 绿色渐变
```

{% endcode %}

### 视觉效果 (Visual Impact)

![背景渐变 (Background Gradient)](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2F43WDFeZYMUvIXVlGgz7j%2F2025-08-20_17-10-21.jpg?alt=media&token=c1b316d5-d9c6-42da-9828-66c0d49e6842)

**最佳用途 (Best for)：** 一目了然地快速判断市场情绪 (Quick market sentiment at a glance)
{% endtab %}

{% tab title="👀 Peak Profit" %}

### 历史峰值显示 (Historical Peak Display)

**作用：** 保持最后一笔交易的峰值利润可见

![峰值利润设置 (Peak Profit Setting)](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2Fj0yBWMg5GX5emtF0I0l9%2Fshowpe.png?alt=media&token=64e71d4f-46f2-4e50-b8d5-8037707837c7)

**优势 (Benefits)：**

- 审查过往表现
- 与当前设置进行比较
- 从历史中学习
- 追踪改进进度

{% hint style="success" %}
**用途 (Use for)：** 交易后分析和策略优化
{% endhint %}

### 图表示例 (Chart Example)

![峰值利润显示 (Peak Profit Display)](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FMRR5mdmHJXZk3aRBwIvI%2F2025-08-20_17-11-22.jpg?alt=media&token=d88afad5-16b3-438c-a257-9ad5e4b6e2c3)
{% endtab %}
{% endtabs %}

---

## 🎨 视觉组合 (Visual Combinations)

{% columns %}
{% column width="50%" %}

### 最大信息量 (Maximum Information)

**所有功能已启用 (All features ON)：**

- 完整的颜色 K 线
- 紫色衰弱信号
- 渐变背景
- 峰值利润显示

**最佳用途 (Best for)：** 主动监控 (Active monitoring)
{% endcolumn %}

{% column %}

### 最小干扰 (Minimal Distraction)

**仅启用必要功能 (Only essentials)：**

- K 线颜色 ON
- 其他所有功能 OFF

**最佳用途 (Best for)：** 清晰分析 (Clean analysis)
{% endcolumn %}
{% endcolumns %}

---

## 💡 专业提示 (Pro Tips)

{% hint style="success" %}
**推荐组合 (Recommended Combo)：**

- ✅ K 线颜色 (Bar Color) - 查看趋势方向
- ✅ 信号强度 (Signal Strength) - 早期捕捉反转
- ❌ 背景 (Background) - 保持图表清晰
- ✅ 峰值利润 (Peak Profit) - 从历史中学习
  {% endhint %}

{% hint style="info" %}
**颜色心理学 (Color Psychology)：**

- 紫色阴影 = 警惕区域 (Caution zone)
- 强烈颜色 = 确信趋势 (Confident trend)
- 渐变转变 = 动量变化 (Momentum change)
  {% endhint %}

---

## 📊 理解颜色 (Understanding the Colors)

### 快速参考 (Quick Reference)

{% code title="color-guide.txt" %}

```
绿色/看涨 (Green/Bullish) → 活跃上升趋势 (Active uptrend)
红色/看跌 (Red/Bearish) → 活跃下降趋势 (Active downtrend)
浅紫色 (Light Purple) → 动量放缓 (Momentum slowing)
深紫色 (Dark Purple) → 潜在反转 (Potential reversal)
渐变 (Gradient) → 整体市场状态 (Overall market state)
```

{% endcode %}

{% hint style="warning" %}
**记住 (Remember)：** 颜色是视觉辅助工具，不是交易信号。始终通过实际信号指标确认。
{% endhint %}
