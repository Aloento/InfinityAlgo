# 🔁 Toggle Same Signal Consecutively

Prevent or allow the same signal type from repeating consecutively.

![Toggle Setting](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FxUcktpcyHPgm1oG5N6QX%2Fimage.png?alt=media&token=468b781b-8de2-4f9c-943b-9b0c144e0e08)

---

### 🎯 How It Works

{% tabs %}
{% tab title="✅ Enabled (Default)" %}

#### No Consecutive Repeats

**Blocks:** Same signal appearing twice in a row

✅ Cleaner charts ✅ Less noise ✅ Natural rotation ✅ Filtered signals

**Example:**

{% code title="enabled-pattern.txt" %}

```
Smart Buy ✅ → Normal Sell ✅ → Smart Buy ✅
              ↑ Different signal required
```

{% endcode %}
{% endtab %}

{% tab title="❌ Disabled" %}

#### Allows Repeats

**Allows:** Same signal multiple times

✅ All valid signals shown ✅ Good for scaling in ✅ More alerts ⚠️ Can be noisy

**Example:**

{% code title="disabled-pattern.txt" %}

```
Smart Buy ✅ → Smart Buy ✅ → Smart Buy ✅
              ↑ Same signal allowed
```

{% endcode %}
{% endtab %}
{% endtabs %}

---

### 📊 Visual Comparison

{% columns %}
{% column width="50%" %}

#### Enabled (Clean)

![Toggle On](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FfGrui2cM4nd4WCYnaRzx%2Fonm.png?alt=media&token=5f0f64af-3b01-4ea6-9261-35192543cf06) **Fewer, filtered signals**
{% endcolumn %}

{% column %}

#### Disabled (All Signals)

![Toggle Off](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2Fd3MMInqWS3fx09s9shqn%2Fonf.png?alt=media&token=cf000650-a486-4a2f-985c-b58be9968214) **More signals, possible repeats**
{% endcolumn %}
{% endcolumns %}

---

### ⚡ Quick Reference

| Aspect                | Enabled      | Disabled           |
| --------------------- | ------------ | ------------------ |
| **Signal Frequency**  | Lower        | Higher             |
| **Chart Clarity**     | Cleaner      | Busier             |
| **Best For**          | Most traders | Scaling strategies |
| **Noise Level**       | Low          | Higher             |
| **Position Building** | Single entry | Multiple entries   |

---

### 🎨 When to Use

{% columns %}
{% column width="50%" %}

#### Keep Enabled For

- Standard trading
- Clean charts
- Single positions
- Reduced noise
- Most strategies
  {% endcolumn %}

{% column %}

#### Disable Only For

- Scaling into positions
- DCA strategies
- Need every signal
- Aggressive trading
- Testing purposes
  {% endcolumn %}
  {% endcolumns %}

---

### 💡 Important Notes

{% hint style="info" %}
**Priority System:** If "Next Signal Must Be Opposite" is enabled, it overrides this setting completely.
{% endhint %}

{% hint style="success" %}
**Recommendation:** Keep enabled for cleaner trading experience unless you specifically need repeated signals.
{% endhint %}

{% hint style="warning" %}
**Remember:** More signals ≠ better performance. Quality over quantity!
{% endhint %}
