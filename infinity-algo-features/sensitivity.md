# 🛠️ Sensitivity

Adjust how responsive the indicator is to market movements.

![Sensitivity Setting](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FVJdz2CCVZaqVVf9TYMlI%2Fsensitivty.png?alt=media&token=1da4121b-a197-4d51-b03b-e719e5d0cffa)

---

### 📊 How It Works

{% columns %}
{% column width="50%" %}

#### Lower Values (5-15)

**More Signals**

- ✅ More opportunities
- ✅ Active trading
- ⚠️ More false signals
- 📈 Short-term focus
  {% endcolumn %}

{% column %}

#### Higher Values (16-28)

**Better Quality**

- ✅ Fewer false signals
- ✅ Higher conviction
- ⚠️ Less opportunities
- 📈 Long-term focus
  {% endcolumn %}
  {% endcolumns %}

---

### 🎯 Settings by Trading Style

| Trading Style   | Timeframe | Sensitivity | Signals/Day |
| --------------- | --------- | ----------- | ----------- |
| **Scalping**    | 1-5 min   | 5-10        | Many        |
| **Day Trading** | 5-30 min  | 10-15       | 5-10        |
| **Intraday**    | 1H-4H     | 15-20       | 3-5         |
| **Swing**       | 4H-Daily  | 18-25       | 1-3         |
| **Position**    | Daily+    | 22-28       | Few         |

---

### 🤖 Mode-Specific Behavior

{% tabs %}
{% tab title="Normal/Smart" %}

#### Manual Control

- **You control** sensitivity directly
- **Start with:** 14-18 (balanced)
- **Adjust based** on results

{% code title="Recommended" %}

```
Scalping: 5-10
Day Trading: 10-15
Swing: 18-25
```

{% endcode %}
{% endtab %}

{% tab title="HL Sniper" %}

#### Precision Mode

- **Optimal range:** 15-20
- **Works on** all timeframes
- **No extremes** needed

{% hint style="info" %}
V3.0 uses advanced algorithm - extreme values no longer recommended
{% endhint %}
{% endtab %}

{% tab title="AI Modes" %}

#### Automatic

- **Setting ignored** - AI controls it
- **Leave at** default value
- **AI optimizes** continuously

{% hint style="success" %}
No adjustment needed - AI handles everything
{% endhint %}
{% endtab %}
{% endtabs %}

---

### 📈 Visual Comparison

Sensitivity = 18 (Balanced):

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FCVa7ynhpCE31YwzFtP3G%2Fimage.png?alt=media&#x26;token=d7bd11ea-09f1-4727-9f80-1f15a9f33c31" alt=""><figcaption><p><strong>Fewer signals, higher quality</strong></p></figcaption></figure>

Sensitivity = 5 (Low):

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FFYi3Quh2YdQtGBxAxAOV%2Fimage.png?alt=media&#x26;token=756c963d-aa32-4fdc-9ee6-e152449ae703" alt=""><figcaption><p><strong>Many signals, more noise</strong></p></figcaption></figure>

---

### ⚡ Quick Start Guide

{% stepper %}
{% step %}

#### Identify Your Style

Scalper? Day trader? Swing trader?
{% endstep %}

{% step %}

#### Use Table Above

Find your timeframe and recommended range
{% endstep %}

{% step %}

#### Start Middle

Begin with middle of your range, adjust from there
{% endstep %}

{% step %}

#### Fine-Tune

Too many signals? Increase value Too few? Decrease value
{% endstep %}
{% endstepper %}

---

### 💡 Pro Tips

{% hint style="success" %}
**Best Practices:**

- Lower timeframes → Lower sensitivity
- Higher timeframes → Higher sensitivity
- Start conservative, adjust gradually
- Document what works for each pair
  {% endhint %}

{% hint style="warning" %}
**Remember:** Using AI modes? This setting doesn't matter - AI optimizes it automatically
{% endhint %}
