# 🎨 Visual Settings

Enhance your chart readability with dynamic colors and visual market insights.

![Visual Settings Panel](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2F7PQBwyVUPgmxl8inMLVo%2Fimage.png?alt=media&token=3cdd0452-b0c0-4e49-a16b-b76a30f72793)

---

### 🎨 Color Options

{% tabs %}
{% tab title="🌈 Bar Color" %}

#### Signal-Based Bar Colors

**What it does:** Colors candles based on last signal direction

**How it works:**

- After Buy → Bullish color
- After Sell → Bearish color
- Shows current bias

{% code title="color-logic.txt" %}

```
Buy Signal → Green bars
↓
Continue green until...
↓
Sell Signal → Red bars
```

{% endcode %}

#### Visual Comparison

**Enabled**

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FSJMue2YpvoKJiBhtGgo3%2F2025-08-20_17-14-52.jpg?alt=media&#x26;token=c7cf0a2f-7abc-4977-955c-207f1630702a" alt=""><figcaption><p> <strong>Clear trend direction</strong></p></figcaption></figure>

**Disabled**

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FcvTHxZFELPrOJ5GNNwFp%2F2025-08-20_17-14-13.jpg?alt=media&#x26;token=410faf01-4ca5-48fb-8c83-b873d723e8e8" alt=""><figcaption><p> <strong>Standard candles</strong></p></figcaption></figure>
{% endtab %}

{% tab title="🟣 Signal Strength" %}

#### Momentum Weakening Indicator

**What it does:** Purple shades show signal strength fading

![Signal Strength Settings](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FjCH5xz6YvJ5oH8YqhrfI%2Fimage.png?alt=media&token=b326090d-f63e-4864-bfb0-790fad3105e4)

**Color Meanings:**

| Color            | Indicates         | Action                  |
| ---------------- | ----------------- | ----------------------- |
| **Light Purple** | Initial weakening | Watch for reversal      |
| **Dark Purple**  | Strong weakening  | Potential exit/reversal |
| **Theme Color**  | Strong trend      | Continue position       |

#### Visual Example

![Purple Strength Coloring](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FvGvIo2LSm6fs99t4Bro0%2F2025-08-20_17-09-08.jpg?alt=media&token=b5eb03c8-3981-42fa-8df8-7a8f4549db19)

{% hint style="info" %}
**Pro Tip:** Purple bars often precede trend reversals - use for early exits
{% endhint %}
{% endtab %}

{% tab title="🎨 Background" %}

#### Dynamic Background Gradient

**What it does:** Background color shows market momentum

![Background Settings](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FPwfAZ9z3wrX6DBs0gtPs%2Fimage.png?alt=media&token=e7c2027a-952e-4e30-83e7-813a193a92bb)

**How it works:**

- Gradient based on oscillator
- Bearish → Bullish colors
- Smooth transitions
- Ambient market feel

{% code title="gradient-zones:" %}

```
Bearish momentum → Red gradient
Neutral → Mixed colors
Bullish momentum → Green gradient
```

{% endcode %}

#### Visual Impact

![Background Gradient](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2F43WDFeZYMUvIXVlGgz7j%2F2025-08-20_17-10-21.jpg?alt=media&token=c1b316d5-d9c6-42da-9828-66c0d49e6842)

**Best for:** Quick market sentiment at a glance
{% endtab %}

{% tab title="👀 Peak Profit" %}

#### Historical Peak Display

**What it does:** Keeps last trade's peak profit visible

![Peak Profit Setting](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2Fj0yBWMg5GX5emtF0I0l9%2Fshowpe.png?alt=media&token=64e71d4f-46f2-4e50-b8d5-8037707837c7)

**Benefits:**

- Review past performance
- Compare with current setup
- Learn from history
- Track improvement

{% hint style="success" %}
**Use for:** Post-trade analysis and strategy refinement
{% endhint %}

#### Chart Example

![Peak Profit Display](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FMRR5mdmHJXZk3aRBwIvI%2F2025-08-20_17-11-22.jpg?alt=media&token=d88afad5-16b3-438c-a257-9ad5e4b6e2c3)
{% endtab %}
{% endtabs %}

---

### 🎨 Visual Combinations

{% columns %}
{% column width="50%" %}

#### Maximum Information

**All features ON:**

- Full color bars
- Purple weakening signals
- Gradient background
- Peak profit display

**Best for:** Active monitoring
{% endcolumn %}

{% column %}

#### Minimal Distraction

**Only essentials:**

- Bar color ON
- Everything else OFF

**Best for:** Clean analysis
{% endcolumn %}
{% endcolumns %}

---

### 💡 Pro Tips

{% hint style="success" %}
**Recommended Combo:**

- ✅ Bar Color - See trend direction
- ✅ Signal Strength - Catch reversals early
- ❌ Background - Keep chart clean
- ✅ Peak Profit - Learn from history
  {% endhint %}

{% hint style="info" %}
**Color Psychology:**

- Purple shades = Caution zone
- Strong colors = Confident trend
- Gradient shift = Momentum change
  {% endhint %}

---

### 📊 Understanding the Colors

#### Quick Reference

{% code title="color-guide.txt" %}

```
Green/Bullish → Active uptrend
Red/Bearish → Active downtrend
Light Purple → Momentum slowing
Dark Purple → Potential reversal
Gradient → Overall market state
```

{% endcode %}

{% hint style="warning" %}
**Remember:** Colors are visual aids, not trade signals. Always confirm with actual signal indicators.
{% endhint %}
