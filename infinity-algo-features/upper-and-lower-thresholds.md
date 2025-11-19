# 📈📉 Upper & Lower Thresholds

<div data-full-width="true"><figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2Fp7kGhXKobtVav12ue651%2Fimage.png?alt=media&#x26;token=a1599741-bfb6-425d-a9b0-3d7807e268fc" alt=""><figcaption></figcaption></figure></div>

> **Quick Summary:** Thresholds define the oscillator levels that trigger buy/sell signals. Adjust them to control signal frequency and quality.

### 📊 What They Do

These thresholds set the **overbought** and **oversold** boundaries for trade signals:

| Threshold | Function           | Crossing Direction           | Signal Type    |
| --------- | ------------------ | ---------------------------- | -------------- |
| **Upper** | Buy trigger level  | Oscillator crosses **above** | 🟢 Buy Signal  |
| **Lower** | Sell trigger level | Oscillator crosses **below** | 🔴 Sell Signal |

### ⚙️ Configuration Guide

#### Upper Threshold (Default: 70)

- **Lower values (60-65):** More signals, less momentum required
- **Higher values (75-80):** Fewer signals, stronger conviction

#### Lower Threshold (Default: 30)

- **Higher values (35-40):** More signals, less bearish momentum needed
- **Lower values (20-25):** Fewer signals, stronger bearish confirmation

### 🎯 Quick Setup Presets

| Trading Style       | Upper | Lower | Result                          |
| ------------------- | ----- | ----- | ------------------------------- |
| **📈 Aggressive**   | 65    | 35    | More frequent signals           |
| **⚖️ Balanced**     | 70    | 30    | Default - good for most markets |
| **🎖️ Conservative** | 75    | 25    | Fewer, high-conviction signals  |

### 🤖 Mode Compatibility

| Mode             | Threshold Behavior                          |
| ---------------- | ------------------------------------------- |
| **Normal/Smart** | ✅ Fully customizable                       |
| **AI Mode**      | ⚡ Auto-optimized (manual settings ignored) |
| **HL Sniper**    | 🚫 Not applicable (uses different logic)    |
| **AI Sniper**    | ⚡ Auto-optimized via advanced parameters   |

### 💡 Pro Tips

1. **Start with defaults** (70/30) and adjust based on results
2. **Narrow the gap** (e.g., 65/35) for ranging markets
3. **Widen the gap** (e.g., 75/25) for trending markets
4. **Monitor win rate** - if too low, widen the thresholds
5. **Check signal frequency** - if too few signals, narrow the gap

---

> 📝 **Note:** These settings only affect Normal and Smart signal modes. AI-powered modes automatically optimize thresholds based on market conditions.
