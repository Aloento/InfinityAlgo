# 🎯 入场价格、止盈和止损 (Entry, Take Profit and Stop Loss)

![设置面板](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2Fs4Vdtl8fxs226HhSzqpQ%2F2025-08-24_22-58-59.jpg?alt=media&token=2f8b4916-5873-46a0-90df-456cf7d0a5ff)

---

#### 📊 设置概览

{% tabs %}
{% tab title="📍 入场价格 (Entry Price)" %}
**入场水平显示**

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FbmAV4XD5r3SZfSR0HzMk%2Fimage.png?alt=media&#x26;token=7594ac6b-efc6-4f88-abf2-3fd9e6b255d1" alt=""><figcaption></figcaption></figure>

**功能：** 使用虚线显示您的持仓入场点

**启用**

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FXzpeeNRhn2frhR8NQGz7%2Fimage.png?alt=media&#x26;token=1594f3f0-fcfe-4af0-b95c-e88696b55034" alt=""><figcaption><p>启用入场价格 (Entry Price) 线条可视化</p></figcaption></figure>
{% endtab %}

{% tab title="💰 止盈 (Take Profit)" %}
**止盈水平 (TP Levels) 配置**

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FGvI8D8QS2rcwWiFgv07e%2Fimage.png?alt=media&#x26;token=a13943f3-a1ad-443b-988b-ace733f1fb0d" alt="" width="375"><figcaption></figcaption></figure>

{% hint style="warning" %}
**重要提示：** 止盈水平仅在"百分比"(Percentage) 出场类型下有效
{% endhint %}

**设置过程：**

{% stepper %}
{% step %}
**启用止盈水平**

切换启用所需的止盈水平
{% endstep %}

{% step %}
**设置百分比**

为每个水平定义利润百分比
{% endstep %}

{% step %}
**分配头寸百分比**

设置每个止盈点出场多少头寸
{% endstep %}

{% step %}
**验证总和 = 100%**

所有出场百分比之和必须等于 100
{% endstep %}
{% endstepper %}

**配置示例：**

{% code title="single-tp:" %}

```
单一止盈 (Single TP)：
TP1: 2% 利润，出场 100%
```

{% endcode %}

{% code title="multiple-tp:" %}

```
多重止盈 (Multiple TPs)：
TP1: 1% 利润，出场 50%
TP2: 2% 利润，出场 30%
TP3: 3% 利润，出场 20%
总计：100% ✅
```

{% endcode %}

**可视化显示：** 启用"显示止盈价格"(Show TP Prices) 在图表上显示虚线

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2Fk20MvZWwDaYvnaK6fyKc%2Fimage.png?alt=media&#x26;token=cd6e1825-394e-41d5-926f-46805c860242" alt=""><figcaption><p>启用全部 6 个止盈水平的线条可视化</p></figcaption></figure>
{% endtab %}

{% tab title="🛑 止损 (Stop Loss)" %}
**止损设置**

**为多头和空头头寸分别配置**

![止损设置](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FhosipOwLOCvCoE8GSggs%2F2025-08-20_16-21-08.jpg?alt=media&token=19c589ba-ca12-45bc-bbc7-f063c9f41d0e)

**多头头寸 (Long Position) 止损**

设置低于入场价格的百分比

- 示例：2% = 当亏损 -2% 时出场

**空头头寸 (Short Position) 止损**

设置高于入场价格的百分比

- 示例：2% = 当亏损 -2% 时出场

**可视化显示：** 启用"显示止损价格"(Show SL Price) 在图表上显示虚线

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FecvM4PErLl9QtSM4um9n%2Fimage.png?alt=media&#x26;token=953f389b-5bfb-48d7-8704-39df5a955e3d" alt=""><figcaption><p>启用止损线条可视化</p></figcaption></figure>
{% endtab %}

{% tab title="🔄 跟踪止损 (Trailing Stop Loss)" %}
**高级止损管理**

**三种跟踪模式可用：**

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FFh3VQlluQErei97fRKJQ%2Fimage.png?alt=media&#x26;token=6f5839e1-749d-4a3f-846f-6496c8486abc" alt=""><figcaption></figcaption></figure>

| 模式 (Mode)                  | 描述         | 工作原理                 |
| ---------------------------- | ------------ | ------------------------ |
| **无 (None)**                | 静态止损     | 止损保持在初始水平       |
| **保本 (Breakeven)**         | 移至入场     | 触发后将止损移至入场价格 |
| **移动目标 (Moving Target)** | 跟踪止盈水平 | 止损跟随至之前的止盈水平 |

**设置过程：**

{% stepper %}
{% step %}
**选择跟踪模式**

从"无"、"保本"或"移动目标"中选择
{% endstep %}

{% step %}
**设置触发点**

选择哪个止盈水平触发跟踪 (TP1-TP6)
{% endstep %}

{% step %}
**监控状态**

图表在止损旁显示 (BE) 或 (TP1), (TP2) 等
{% endstep %}
{% endstepper %}

**配置示例：**

{% code title="breakeven-setup:" %}

```
保本 (Breakeven) 模式：
- 模式：保本
- 触发：TP1 后
- 结果：TP1 触发时止损移至入场点
- 显示："Stop loss (BE)"
```

{% endcode %}

{% code title="moving-target-setup:" %}

```
移动目标 (Moving Target) 模式：
- 模式：移动目标
- 触发：TP2 后
- 结果：
  * TP2 后：止损 → 入场点
  * TP3 后：止损 → TP1
  * TP4 后：止损 → TP2
- 显示："Stop loss (TP1)"，等等
```

{% endcode %}

{% hint style="success" %}
**专业建议：** 移动目标 (Moving Target) 模式能在每个止盈水平触发时逐步锁定利润
{% endhint %}

**可视化指标：**

| 止损状态     | 标签显示                    | 含义             |
| ------------ | --------------------------- | ---------------- |
| **正常**     | "Stop loss: \[price]"       | 静态止损激活     |
| **保本**     | "Stop loss (BE): \[price]"  | 止损已移至入场点 |
| **跟踪 TP1** | "Stop loss (TP1): \[price]" | 止损在 TP1 水平  |
| **跟踪 TP2** | "Stop loss (TP2): \[price]" | 止损在 TP2 水平  |

{% hint style="info" %}
**入场线表现：** 当止损处于保本时，入场线会变暗以避免视觉重叠
{% endhint %}
{% endtab %}
{% endtabs %}

---

#### 📈 可视化显示与行为

**图表上显示的内容：**

| 水平 (Level) | 显示 (Display) | 线条样式      | 何时可见     | 特殊说明           |
| ------------ | -------------- | ------------- | ------------ | ------------------ |
| **入场点**   | 虚线           | `···········` | 启用时       | 止损在保本时变暗   |
| **止盈水平** | 虚线           | `···········` | 仅百分比模式 | 触发时被点标记替换 |
| **止损**     | 虚线           | `···········` | 启用时       | 显示跟踪状态       |

{% hint style="info" %}
**动态显示：**

- 止盈线在触发时消失并变成点标记
- 止损标签更新以显示当前模式 (BE, TP1, TP2 等)
- 当止损处于保本时，入场线会变暗以减少混乱
  {% endhint %}

**图表示例：**

{% columns %}
{% column width="50%" %}
**活跃的止盈线**

![触发前](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FbWGbiHuheTXVKJHpX4KW%2F2025-08-20_16-58-38.jpg?alt=media&token=129a1cd9-330d-463c-aaf2-7c35640196a7) **线条显示待处理的止盈水平**
{% endcolumn %}

{% column %}
**止盈触发标记**

![触发后](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FDzZ7kGlWG30skuBIDGZG%2F2025-08-20_17-00-02.jpg?alt=media&token=7c845ba8-dcab-4cc0-a990-7e14324a9067) **点标记已执行的止盈**
{% endcolumn %}
{% endcolumns %}

---

#### 🎨 可视化指标指南

**止盈水平状态：**

| 状态              | 可视化     | 描述       | 图表状态     |
| ----------------- | ---------- | ---------- | ------------ |
| **📊 待处理止盈** | 虚线       | 准备触发   | 标签显示目标 |
| **✅ 止盈已触发** | 点标记 (●) | 水平已执行 | 线条消失     |
| **🔄 持仓已平仓** | 点保留     | 交易完成   | 所有线条清除 |

**止损跟踪状态：**

| 状态        | 可视化                      | 描述         | 说明       |
| ----------- | --------------------------- | ------------ | ---------- |
| **📍 静态** | "Stop loss: \[price]"       | 固定止损位置 | 初始状态   |
| **🟢 保本** | "Stop loss (BE): \[price]"  | 移至入场     | 无风险交易 |
| **📈 跟踪** | "Stop loss (TP#): \[price]" | 跟随止盈水平 | 利润已锁定 |

---

#### 🎯 快速设置模板

**保守型 (单一止盈 + 保本)**

{% code title="conservative:" %}

```
TP1: 2% 利润，出场 100%
止损：1% 亏损
跟踪：TP1 后保本
风险/收益：2:1 → TP 后无风险
```

{% endcode %}

**分级出场 (多重止盈 + 移动目标)**

{% code title="scaled:" %}

```
TP1: 1% 利润，出场 50%
TP2: 2% 利润，出场 30%
TP3: 3% 利润，出场 20%
止损：2% 亏损
跟踪：TP1 后移动目标
结果：逐步锁定利润
```

{% endcode %}

**激进型 (宽目标 + 晚期跟踪)**

{% code title="aggressive:" %}

```
TP1: 3% 利润，出场 40%
TP2: 5% 利润，出场 30%
TP3: 8% 利润，出场 30%
止损：3% 亏损
跟踪：TP2 后移动目标
结果：最大利润潜力
```

{% endcode %}

---

#### 💡 专业建议

{% hint style="success" %}
**最佳实践：**

- 始终验证止盈百分比 = 100%
- 使用保本模式进行保守交易
- 使用移动目标逐步锁定利润
- 根据您的信心水平设置跟踪触发
- 监控止损标签以获取当前保护状态
  {% endhint %}

{% hint style="info" %}
**跟踪建议：**

- **TP1 后保本** = 快速消除风险
- **TP2 后移动目标** = 利润与保护之间的平衡
- **无跟踪** = 最大利润潜力但风险持续
  {% endhint %}

{% hint style="warning" %}
**记住：**

- 止盈线仅在"百分比"出场模式中显示
- 跟踪止损需要至少启用一个止盈水平
- 移动目标模式需要多个止盈水平以获得最佳结果
  {% endhint %}
