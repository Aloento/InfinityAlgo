# 📊 MTF 仪表板 (Multi-Timeframe Dashboard)

## 📊 MTF 仪表板 (Multi-Timeframe Dashboard)

同时监控 8 个时间周期(timeframe)，识别趋势对齐和跨多个时间范围的市场共识。

---

#### 🎯 什么是 MTF 仪表板？

多时间周期(Multi-Timeframe, MTF)仪表板在一个易于阅读的表格中提供 8 个不同时间周期的全面市场条件视图。它分析每个时间周期的趋势方向和波动率，帮助您识别多个时间周期对齐时的高概率设置(high-probability setups)。

{% hint style="info" %}
**关键洞察:** 当 6 个或以上时间周期显示相同的趋势方向时，延续(continuation)的概率会显著增加。
{% endhint %}

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FcRDWitMUWx9ddlGM2IKe%2Fimage.png?alt=media&#x26;token=ef9b81d1-d2ad-42c9-b731-1da9d47e7d34" alt="MTF 仪表板截图"><figcaption><p>多时间周期仪表板</p></figcaption></figure>

---

#### 📈 仪表板组件

**第 1 列：时间周期**

显示您选择的时间周期及视觉指示：

- ⚡ **超快速**(Ultra-fast) (1-3 分钟) - 超短线(Scalping)
- 🔍 **快速**(Fast) (5-15 分钟) - 日内交易(Day trading)
- 🕒 **中等**(Medium) (30-60 分钟) - 日内交易(Intraday)
- 🕐 **缓慢**(Slow) (2-4 小时) - 波段入场(Swing entries)
- 📅 **每日及以上**(Daily+) - 持仓/趋势(Position/trend)

**第 2 列：趋势状态**

根据动量分析(momentum analysis)显示市场方向：

| 状态                 | 符号 | 含义                 | 交易意义       |
| -------------------- | ---- | -------------------- | -------------- |
| **超买**(Overbought) | 🔥   | 强劲的上升动量，延伸 | 考虑对多头平仓 |
| **超卖**(Oversold)   | ❄️   | 强劲的下降动量，延伸 | 考虑对空头平仓 |
| **看涨**(Bullish)    | 🚀   | 上升趋势，健康的动量 | 寻找做多机会   |
| **看跌**(Bearish)    | 🧸   | 下降趋势，健康的动量 | 寻找做空机会   |

**第 3 列：波动率**

用趋势指标显示市场波动率：

| 等级             | 符号 | 含义         | 最适用于           |
| ---------------- | ---- | ------------ | ------------------ |
| **高**(High)     | 🌋   | 大幅价格波动 | 超短线、突破交易   |
| **正常**(Normal) | ⚖️   | 平均移动     | 标准策略           |
| **低**(Low)      | 💤   | 紧密区间     | 区间交易、避免突破 |

**趋势箭头：**

- 📈 波动率上升(上升扩展可能到来)
- 📉 波动率下降(固结到来)
- ➡️ 波动率稳定

---

#### ⚙️ 配置

**基础设置**

| 设置                | 选项                 | 说明                      |
| ------------------- | -------------------- | ------------------------- |
| **显示 MTF 仪表板** | 开启/关闭            | 切换仪表板可见性          |
| **仪表板位置**      | 右上/左上、右下/左下 | 屏幕位置                  |
| **仪表板风格**      | 专业中性、语义热力图 | 视觉呈现风格              |
| **时间周期 1-8**    | 任何时间周期         | 选择 8 个要监控的时间周期 |

**仪表板风格选项**

{% tabs %}
{% tab title="专业中性" %}
**专业的斑马纹行设计**

- 清晰的交替行背景
- 整体始终的文本颜色
- 对长时间观看舒适
- 用于截图时呈现专业外观
- 最适合：偏好视觉干扰最小的交易者

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FTkK49ur6Pm4pFv33c7gr%2Fimage.png?alt=media&#x26;token=2f7ebff5-5239-475a-a736-dca114e72a40" alt="" width="375"><figcaption></figcaption></figure>
{% endtab %}

{% tab title="语义热力图" %}
**基于条件的色编单元格，便于快速扫描**

- 根据条件的动态单元格颜色
- 即时视觉识别市场状态
- 趋势强度通过色彩强度显示
- 波动率等级有独特的色编
- 最适合：快速市场评估和模式识别

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FtKnuWrhinxGjLYRodnvf%2Fimage.png?alt=media&#x26;token=ad2c417a-d96d-4d7a-b99b-ed27d2514186" alt="" width="375"><figcaption></figcaption></figure>
{% endtab %}
{% endtabs %}

**推荐的时间周期组合**

{% tabs %}
{% tab title="⚡ 超短线交易" %}
{% code overflow="wrap" %}

```
TF1: 1        # 1 分钟
TF2: 3        # 3 分钟
TF3: 5        # 5 分钟
TF4: 15       # 15 分钟
TF5: 30       # 30 分钟
TF6: 60       # 1 小时
TF7: 240      # 4 小时
TF8: D        # 日线
```

{% endcode %}

**焦点：**快速交易并获得更高时间周期确认
{% endtab %}

{% tab title="📊 日内交易" %}
{% code overflow="wrap" %}

```
TF1: 5        # 5 分钟
TF2: 15       # 15 分钟
TF3: 30       # 30 分钟
TF4: 60       # 1 小时
TF5: 2h       # 2 小时
TF6: 240      # 4 小时
TF7: D        # 日线
TF8: W        # 周线
```

{% endcode %}

**焦点：**日内持仓，趋势对齐
{% endtab %}

{% tab title="🏔️ 波段交易" %}
{% code overflow="wrap" %}

```
TF1: 60       # 1 小时
TF2: 2h       # 2 小时
TF3: 240      # 4 小时
TF4: 6h       # 6 小时
TF5: 12h      # 12 小时
TF6: D        # 日线
TF7: W        # 周线
TF8: M        # 月线
```

{% endcode %}

**焦点：**多日持仓，具有强劲趋势
{% endtab %}

{% tab title="🎯 自定义" %}
您可以输入自定义时间周期，如：

- `90` 代表 90 分钟
- `3h` 代表 3 小时
- `2d` 代表 2 天
- 混合任何适合您策略的组合
  {% endtab %}
  {% endtabs %}

---

#### 📖 阅读仪表板

**AVG 行（底部汇总）**

{% columns %}
{% column width="50%" %}
**趋势偏好**

**⭐ AVG** 行提供总体市场评估：

- 🚀 **看涨**(Bullish) = 大多数上升趋势
- 🧸 **看跌**(Bearish) = 大多数下降趋势
- ⚖️ **中性**(Neutral) = 混合信号
  {% endcolumn %}

{% column %}
**波动率汇总**

显示主要市场条件：

- 主要波动率等级(高/正常/低)
- 扩展或固结趋势
- 整体市场一致性强度
  {% endcolumn %}
  {% endcolumns %}

{% hint style="success" %}
**专业提示：** AVG 行给出"市场共识" - 当它显示强烈偏好时，就按照那个方向交易。
{% endhint %}

---

#### 🎯 交易信号

**高概率设置(High-Probability Setups)**

{% stepper %}
{% step %}
**强对齐**(Strong Alignment) (6+ 个时间周期)

- **信号：** 6 个或以上时间周期同向
- **行动：** 按照对齐方向交易
- **可用警报：** "MTF 强看涨/看跌"(MTF Strong Bullish/Bearish)
  {% endstep %}

{% step %}
**完全对齐**(Full Alignment) (8/8 个时间周期)

- **信号：** 全部 8 个时间周期同向
- **行动：** 最大头寸规模机会
- **可用警报：** "MTF 完全对齐"(MTF Full Alignment)
  {% endstep %}

{% step %}
**偏好翻转**(Bias Flip)

- **信号：** AVG 行从看跌变为看涨(或反之)
- **行动：** 为趋势改变做准备
- **可用警报：** "MTF 偏好翻转"(MTF Bias Flip)
  {% endstep %}
  {% endstepper %}

---

#### 🔔 警报配置

MTF 仪表板可用的警报：

| 警报名称                | 触发条件              | 用例             |
| ----------------------- | --------------------- | ---------------- |
| **MTF 强看涨**          | 6+ 个时间周期看涨     | 做多入场信号     |
| **MTF 强看跌**          | 6+ 个时间周期看跌     | 做空入场信号     |
| **MTF 完全看涨对齐**    | 全部 8 个时间周期看涨 | 罕见的强趋势信号 |
| **MTF 完全看跌对齐**    | 全部 8 个时间周期看跌 | 罕见的强趋势信号 |
| **MTF 偏好翻转 → 看涨** | 总体偏好转为看涨      | 趋势反转信号     |
| **MTF 偏好翻转 → 看跌** | 总体偏好转为看跌      | 趋势反转信号     |

---

#### 💡 专业策略

**策略 1：对齐汇聚(Alignment Confluence)**

等待强 MTF 对齐(6+)同时出现：

- 订单块(Order block)测试
- 云带(Cloud band)边界
- 关键支撑/阻力

**策略 2：时间周期级联(Timeframe Cascade)**

1. 更高时间周期首先转为看涨
2. 等待更低时间周期对齐
3. 在最低时间周期信号处入场

**策略 3：波动率过滤器(Volatility Filter)**

- **高波动 + 对齐** = 突破交易(Breakout trade)
- **低波动 + 对齐** = 等待扩展(expansion)
- **正常波动 + 对齐** = 标准入场

---

#### ⚠️ 常见错误

{% hint style="warning" %}
**避免这些错误：**

1. **逆势强对齐交易** - 不要对抗 6+ 个时间周期共识
2. **忽视更高时间周期** - 它们设定主导趋势
3. **过度权衡快速时间周期** - 平衡您的分析
4. **不等待对齐** - 耐心等待高概率设置
   {% endhint %}

---

#### 🛠️ 故障排除

<details>

<summary><strong>仪表板不显示任何数据</strong></summary>

- 确保"显示 MTF 仪表板"已启用
- 检查您加载的历史数据是否充分
- 验证时间周期输入有效(例如 "5"、"15"、"60"、"D")

</details>

<details>

<summary><strong>某些时间周期显示 "n/a"</strong></summary>

- 时间周期可能无效或不可用
- 尝试标准时间周期：1、5、15、30、60、240、D、W
- 自定义时间周期需要特定格式(例如 "90" 表示 90 分钟)

</details>

<details>

<summary><strong>仪表板更新缓慢</strong></summary>

- 这是正常的 - 每个新小时棒(bar)关闭时更新
- 更高时间周期更新频率较低
- 使用低时间周期获得更快响应数据

</details>

---

**最佳实践**

1. 从标准时间周期组合开始
2. 选择适合您交易方法的仪表板风格
3. 等待 6+ 个时间周期对齐
4. 用其他仪表板功能确认
5. 使用警报捕捉对齐变化
6. 尊重总体 AVG 偏好

---

_需要帮助？查看我们的_ [_常见问题_](https://infinity.aloen.to/faq-and-troubleshoot) _或_ [_联系支持_](https://infinityalgo.com/#contact)_。_
