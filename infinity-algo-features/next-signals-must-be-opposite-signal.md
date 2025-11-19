# 🔄 Next Signals Must Be Opposite Signal

Control whether signals must alternate directions or can repeat.

![Opposite Signal Setting](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FWY4Pufa0V6EpJ22zwf4e%2Fimage.png?alt=media&token=17731877-84c5-4888-80f4-ff996322358d)

---

### 🎯 How It Works

{% tabs %}
{% tab title="✅ Enabled" %}

#### Forced Alternation

**Pattern:** Buy → Sell → Buy → Sell

✅ Clean reversals only ✅ One position at a time ✅ No consecutive signals ✅&#x20;

**Example:**

- Last signal: Buy ✅
- Next possible: Only Sell
- Filters out: Any Buy signals
  {% endtab %}

{% tab title="❌ Disabled (Default)" %}

#### Any Signal Allowed

**Pattern:** Buy → Buy → Sell → Buy → Sell → Sell

✅ Multiple entries allowed ✅ Trend following possible ✅ Pyramiding friendly ✅ All signals shown

**Example:**

- Last signal: Buy ✅
- Next possible: Buy OR Sell
- Shows: All valid signals
  {% endtab %}
  {% endtabs %}

---

### 📊 Quick Comparison

| Feature                 | Enabled       | Disabled          |
| ----------------------- | ------------- | ----------------- |
| **Signal Pattern**      | Buy→Sell→Buy  | Any sequence      |
| **Consecutive Signals** | ❌ Never      | ✅ Allowed        |
| **Best Market**         | Ranging       | Trending          |
| **Position Style**      | One at a time | Multiple possible |
| **Signal Frequency**    | Fewer         | More              |

---

### 🎨 When to Use

{% columns %}
{% column width="50%" %}

#### ✅ **Enable For:**

- Range trading
- Mean reversion
- Single position only
- Clean reversals
- Volatile markets
  {% endcolumn %}

{% column %}

#### ❌ **Disable For:**

- Trend following
- Pyramiding strategies
- Strong trends
- Multiple entries
- Momentum trading
  {% endcolumn %}
  {% endcolumns %}

---

### 📈 Visual Example

#### Enabled (Alternating)

{% code title="pattern-enabled.txt" %}

```
Buy ✅ → Sell ✅ → Buy ✅ → Sell ✅
         ↓ Skips Buy signals
```

{% endcode %}

#### Disabled (Any Sequence)

{% code title="pattern-disabled.txt" %}

```
Buy ✅ → Buy ✅ → Buy ✅ → Sell ✅
         ↓ Shows all signals
```

{% endcode %}

---

### 💡 Pro Tips

{% hint style="success" %}
**Best Practice:** Enable for ranging markets, disable for trending markets
{% endhint %}

{% hint style="info" %}
**Note:** This overrides "Toggle Same Signal Consecutively" when enabled - it's the stricter rule
{% endhint %}

{% hint style="warning" %}
**Remember:** Enabling this reduces signal frequency but increases clarity
{% endhint %}

\\
