# 📈📉 上轨与下轨阈值 (Upper & Lower Thresholds)

<div data-full-width="true"><figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2Fp7kGhXKobtVav12ue651%2Fimage.png?alt=media&#x26;token=a1599741-bfb6-425d-a9b0-3d7807e268fc" alt=""><figcaption></figcaption></figure></div>

> **快速总结:** 阈值(Thresholds)定义了振荡器(Oscillator)级别,用于触发买入/卖出信号(Buy/Sell Signals)。调整它们可以控制信号频率和质量。

### 📊 功能说明

这些阈值为交易信号设定了**超买(Overbought)**和**超卖(Oversold)**的边界:

| 阈值             | 功能说明     | 穿越方向           | 信号类型                  |
| ---------------- | ------------ | ------------------ | ------------------------- |
| **上轨 (Upper)** | 买入触发水平 | 振荡器穿越**上方** | 🟢 买入信号 (Buy Signal)  |
| **下轨 (Lower)** | 卖出触发水平 | 振荡器穿越**下方** | 🔴 卖出信号 (Sell Signal) |

## ⚙️ 配置指南 (Configuration Guide)

### 上轨阈值 (Upper Threshold) (默认值: 70)

- **较低数值 (60-65):** 更多信号,所需动能(Momentum)较少
- **较高数值 (75-80):** 更少信号,确信度(Conviction)更高

### 下轨阈值 (Lower Threshold) (默认值: 30)

- **较高数值 (35-40):** 更多信号,所需看空(Bearish)动能较少
- **较低数值 (20-25):** 更少信号,看空确认更强

## 🎯 快速设置预设 (Quick Setup Presets)

| 交易风格                     | 上轨 | 下轨 | 结果说明                               |
| ---------------------------- | ---- | ---- | -------------------------------------- |
| **📈 激进型 (Aggressive)**   | 65   | 35   | 信号频率更高                           |
| **⚖️ 均衡型 (Balanced)**     | 70   | 30   | 默认设置 - 适用于大多数市场            |
| **🎖️ 保守型 (Conservative)** | 75   | 25   | 信号较少,高确信度(High-Conviction)信号 |

## 🤖 模式兼容性 (Mode Compatibility)

| 模式                             | 阈值行为                  |
| -------------------------------- | ------------------------- |
| **普通/智能模式 (Normal/Smart)** | ✅ 完全可自定义           |
| **AI 模式 (AI Mode)**            | ⚡ 自动优化(忽略手动设置) |
| **HL 狙击手模式 (HL Sniper)**    | 🚫 不适用(使用不同的逻辑) |
| **AI 狙击手模式 (AI Sniper)**    | ⚡ 通过高级参数自动优化   |

## 💡 专业提示 (Pro Tips)

1. **从默认值开始** (70/30),然后根据结果调整
2. **缩小间距** (例如 65/35) 用于区间震荡(Ranging)市场
3. **扩大间距** (例如 75/25) 用于趋势(Trending)市场
4. **监控胜率(Win Rate)** - 如果过低,扩大阈值间距
5. **检查信号频率** - 如果信号过少,缩小间距

---

> 📝 **注意:** 这些设置仅影响普通(Normal)和智能(Smart)信号模式。AI 驱动的模式会根据市场条件自动优化阈值。
