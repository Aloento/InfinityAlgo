# 📉📈 EMA Length

Set the trend filter that determines whether signals follow or counter the trend.

![EMA Length Setting](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2F4BHg7t8TgXExrbCoG9RM%2Fema.png?alt=media&token=f730df12-fad7-490a-9ab3-d1f07ebf888c)

---

### 🎯 How It Works

The EMA acts as a trend filter, changing how signals behave:

{% tabs %}
{% tab title="📈 Smart Signals" %}

#### Trend-Following Mode

**Buy when:**

- Price is **above** EMA
- Confirms uptrend

**Sell when:**

- Price is **below** EMA
- Confirms downtrend

{% hint style="success" %}
**Use for:** Trading with the trend, safer entries, trending markets
{% endhint %}
{% endtab %}

{% tab title="📉 Normal Signals" %}

#### Counter-Trend Mode

**Buy when:**

- Price is **below** EMA
- Looking for reversal up

**Sell when:**

- Price is **above** EMA
- Looking for reversal down

{% hint style="warning" %}
**Use for:** Mean reversion, catching reversals, ranging markets
{% endhint %}
{% endtab %}
{% endtabs %}

---

### 📊 Common EMA Settings

| EMA Length | Type         | Best For         | Signal Frequency |
| ---------- | ------------ | ---------------- | ---------------- |
| **20**     | Short-term   | Scalping         | Many signals     |
| **50**     | Medium       | Day trading      | Moderate         |
| **100**    | Intermediate | Swing trading    | Balanced         |
| **200**    | Long-term    | Position trading | Few signals      |

---

### ⚡ Quick Strategy Guide

{% columns %}
{% column width="50%" %}

#### Trend Following Setup

**Settings:**

- Signal Mode: `Smart`
- EMA Length: `200`
- Market: Trending

**Result:** Trade only with major trend
{% endcolumn %}

{% column %}

#### Mean Reversion Setup

**Settings:**

- Signal Mode: `Normal`
- EMA Length: `20`
- Market: Ranging

**Result:** Catch quick reversals
{% endcolumn %}
{% endcolumns %}

---

### 🎨 Visual Example

| Scenario        | Smart Signal         | Normal Signal        |
| --------------- | -------------------- | -------------------- |
| **Price > EMA** | ✅ Buy signals only  | ✅ Sell signals only |
| **Price < EMA** | ✅ Sell signals only | ✅ Buy signals only  |

---

### 💡 Pro Combinations

{% hint style="info" %}
**Popular Setups:**

**Conservative Trend:**

- Smart + EMA 200 = Long-term trend trades

**Aggressive Scalping:**

- Normal + EMA 20 = Quick reversals

**Balanced Swing:**

- Smart + EMA 50 = Medium-term momentum
  {% endhint %}

---

### ⚠️ Important Notes

- **HL Sniper/AI modes:** EMA still filters but with different logic
- **Higher EMA = Fewer signals** but higher quality
- **Lower EMA = More signals** but more noise
- Start with EMA 50 for balanced results

{% hint style="success" %}
**Quick Tip:** Match EMA to your timeframe - 20 for intraday, 50 for swing, 200 for position
{% endhint %}
