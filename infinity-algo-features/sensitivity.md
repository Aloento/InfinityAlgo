# 🛠️ 灵敏度 (Sensitivity)

调整指标对市场波动的响应程度。

![灵敏度设置](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FVJdz2CCVZaqVVf9TYMlI%2Fsensitivty.png?alt=media&token=1da4121b-a197-4d51-b03b-e719e5d0cffa)

---

## 📊 工作原理

{% columns %}
{% column width="50%" %}

### 较低数值 (5-15)

更多信号

- ✅ 交易机会更多
- ✅ 活跃交易
- ⚠️ 虚假信号较多
- 📈 短期关注
  {% endcolumn %}

{% column %}

### 较高数值 (16-28)

更好的质量

- ✅ 虚假信号更少
- ✅ 信号确定性更高
- ⚠️ 交易机会较少
- 📈 长期关注
  {% endcolumn %}
  {% endcolumns %}

---

### 🎯 按交易风格的设置

| 交易风格 (Trading Style)   | 时间周期 (Timeframe) | 灵敏度 (Sensitivity) | 每日信号数 (Signals/Day) |
| -------------------------- | -------------------- | -------------------- | ------------------------ |
| **剥头皮 (Scalping)**      | 1-5 分钟             | 5-10                 | 多个                     |
| **日内交易 (Day Trading)** | 5-30 分钟            | 10-15                | 5-10                     |
| **盘中交易 (Intraday)**    | 1 小时-4 小时        | 15-20                | 3-5                      |
| **波段交易 (Swing)**       | 4 小时-日线          | 18-25                | 1-3                      |
| **头寸交易 (Position)**    | 日线及以上           | 22-28                | 较少                     |

---

### 🤖 各模式特定行为

{% tabs %}
{% tab title="标准 (Normal)/智能 (Smart)" %}

#### 手动控制

- **您可以直接控制**灵敏度
- **建议起点：** 14-18（平衡设置）
- **根据结果调整**

{% code title="推荐设置" %}

```
剥头皮 (Scalping): 5-10
日内交易 (Day Trading): 10-15
波段交易 (Swing): 18-25
```

{% endcode %}
{% endtab %}

{% tab title="HL 狙击手 (HL Sniper)" %}

#### 精准模式 (Precision Mode)

- **最优范围：** 15-20
- **适用于**所有时间周期
- **无需极端数值**

{% hint style="info" %}
V3.0 采用先进算法 - 不再推荐使用极端数值
{% endhint %}
{% endtab %}

{% tab title="人工智能 (AI) 模式" %}

#### 自动化

- **设置被忽略** - AI 负责控制
- **保留**默认值
- **AI 持续优化**

{% hint style="success" %}
无需调整 - AI 处理一切
{% endhint %}
{% endtab %}
{% endtabs %}

---

### 📈 视觉对比

灵敏度 (Sensitivity) = 18（平衡设置）：

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FCVa7ynhpCE31YwzFtP3G%2Fimage.png?alt=media&#x26;token=d7bd11ea-09f1-4727-9f80-1f15a9f33c31" alt=""><figcaption><p><strong>信号较少，质量更高</strong></p></figcaption></figure>

灵敏度 (Sensitivity) = 5（低值）：

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FFYi3Quh2YdQtGBxAxAOV%2Fimage.png?alt=media&#x26;token=756c963d-aa32-4fdc-9ee6-e152449ae703" alt=""><figcaption><p><strong>信号众多，噪音较多</strong></p></figcaption></figure>

---

### ⚡ 快速入门指南

{% stepper %}
{% step %}

#### 确定您的交易风格

剥头皮交易者？日内交易者？波段交易者？
{% endstep %}

{% step %}

#### 使用上方表格

找到您的时间周期和推荐范围
{% endstep %}

{% step %}

#### 从中间开始

从您范围的中间值开始，然后从那里调整
{% endstep %}

{% step %}

#### 微调

信号过多？增加数值。信号过少？降低数值。
{% endstep %}
{% endstepper %}

---

### 💡 专业提示

{% hint style="success" %}
**最佳实践：**

- 较短时间周期 → 较低灵敏度
- 较长时间周期 → 较高灵敏度
- 从保守设置开始，逐步调整
- 记录每个交易对的有效设置
  {% endhint %}

{% hint style="warning" %}
**记住：**使用 AI 模式？此设置无关紧要 - AI 会自动优化
{% endhint %}
