# ⚙️ Take Profit Settings

Advanced controls for Take Profit signal behavior when using "Signals" exit type.

![TP Settings Panel](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FiDc6ZdeZGnvRvvwpaDBX%2Fimage.png?alt=media&token=becd4d66-1790-4cec-b747-2f1c8f84e2a7)

{% hint style="info" %}
**Note:** These settings only work when `Show Take Profit Signals?` is enabled
{% endhint %}

---

### 🎯 Settings Explained

{% tabs %}
{% tab title="⏲️ Timeframe" %}

#### Higher Timeframe Analysis

**Purpose:** View momentum from bigger picture perspective

**How it works:**

- Sets calculation timeframe for TP signals
- Higher TF = More stable signals
- Filters out market noise

{% code title="recommended:" %}

```
Chart TF → TP TF
1 min    → 3-5 min
5 min    → 15 min
15 min   → 30-60 min
1 hour   → 4 hour
```

{% endcode %}

{% hint style="success" %}
**Best Practice:** Use 2-3x your chart timeframe for reliable signals
{% endhint %}
{% endtab %}

{% tab title="🛠️ Smoothing" %}

#### Signal Sensitivity Control

**Purpose:** Adjust how reactive TP signals are

| Smoothing         | Effect                     | Best For      |
| ----------------- | -------------------------- | ------------- |
| **Low (1-5)**     | More signals, sensitive    | Scalping      |
| **Medium (5-10)** | Balanced                   | Day trading   |
| **High (10-20)**  | Fewer, significant signals | Swing trading |

**Visual Impact:**

{% code title="smoothing-effect:" %}

```
Low:  TP→TP→TP→TP→TP (many signals)
High: TP------→TP (few major signals)
```

{% endcode %}
{% endtab %}

{% tab title="💸 Price Offset" %}

#### Minimum Profit Filter

**Purpose:** Prevent exits before meaningful profit

**What it does:**

- Sets minimum profit % required
- No TP signals below this level
- Protects from premature exits

{% code title="examples:" %}

```
Offset: 0.5%
Trade at +0.3% → No TP
Trade at +0.7% → TP allowed

Offset: 1.0%
Trade at +0.9% → No TP
Trade at +1.2% → TP allowed
```

{% endcode %}

{% hint style="warning" %}
**Important:** Match offset to your profit goals and spread costs
{% endhint %}
{% endtab %}
{% endtabs %}

---

### ⚡ Quick Setup Guide

#### By Trading Style

| Style             | Timeframe | Smoothing | Offset   |
| ----------------- | --------- | --------- | -------- |
| **Scalping**      | 2x chart  | 3-5       | 0.2-0.5% |
| **Day Trading**   | 3x chart  | 5-10      | 0.5-1%   |
| **Swing Trading** | 4x chart  | 10-15     | 1-2%     |

---

### 📊 Combined Effect

#### All Settings Working Together

{% stepper %}
{% step %}

#### Check Offset

Is trade profit > minimum offset?

- No → No TP signal
- Yes → Continue
  {% endstep %}

{% step %}

#### Analyze Momentum

Check higher timeframe momentum

- Weak → No signal
- Strong → Continue
  {% endstep %}

{% step %}

#### Apply Smoothing

Is momentum sustained?

- No → Wait
- Yes → Show TP signal
  {% endstep %}
  {% endstepper %}

---

### 💡 Pro Tips

{% columns %}
{% column width="50%" %}

#### For Clean Signals

- ✅ Higher timeframe (3x+)
- ✅ More smoothing (10+)
- ✅ Higher offset (1%+)

**Result:** Fewer, quality exits
{% endcolumn %}

{% column %}

#### For Active Trading

- ✅ Lower timeframe (2x)
- ✅ Less smoothing (5)
- ✅ Lower offset (0.5%)

**Result:** More exit opportunities
{% endcolumn %}
{% endcolumns %}

---

### 🎯 Common Configurations

{% hint style="success" %}
**Conservative Setup:**

- Timeframe: 4x chart
- Smoothing: 15
- Offset: 1.5%

**Balanced Setup:**

- Timeframe: 3x chart
- Smoothing: 10
- Offset: 0.75%

**Aggressive Setup:**

- Timeframe: 2x chart
- Smoothing: 5
- Offset: 0.3%
  {% endhint %}

---

### ⚠️ Important Notes

- These settings work **only** with "Signals" exit type
- Higher values = Fewer but better signals
- Test settings in different market conditions
- Adjust based on your trading results

{% hint style="info" %}
**Remember:** Quality over quantity - better to miss some exits than exit too early
{% endhint %}
