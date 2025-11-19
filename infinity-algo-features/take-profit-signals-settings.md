# 💰 Take Profit Signals Settings

Configure how dynamic exit signals appear when using "Signals" exit type.

---

### 🎯 Settings Overview

{% tabs %}
{% tab title="💹 Show TP Signals" %}

#### Master Switch

**Controls:** Whether TP signals appear at all

✅ **Enabled:** Shows "TP" icons when momentum suggests taking profit ❌ **Disabled:** No TP signals displayed

#### Enabled

![TP Signals On](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2F1FsbCrdUAj6wv9jxpu0L%2Fon.png?alt=media&token=15eed396-a4cc-4d0a-a918-172483241a54) **Shows all TP opportunities**

#### Disabled

![TP Signals Off](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FAmEOMFdtiTphNzwyGyt6%2Foff.png?alt=media&token=6b233f92-eae4-4e96-a921-376fe47c3df0) **No TP signals shown**
{% endtab %}

{% tab title="📈 Higher Level Only" %}

#### Progressive Filter

**Controls:** Whether new TP must be at better price

✅ **Enabled:** Only shows TPs at higher profit levels ❌ **Disabled:** Shows all TPs regardless of level

#### Enabled (Clean)

![Higher Level On](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2Ff2F3vgCje7HEF9KqNhje%2Fimage.png?alt=media&token=5642400f-b0e2-41ff-94cc-a714c2090ddd) **Progressive TPs only**

#### Disabled (All)

![Higher Level Off](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FGhS75RynaPINRwGxFdGm%2Fimage.png?alt=media&token=6b041085-0875-4e9f-9bdd-8c4252f68093) **Shows every TP signal**
{% endtab %}
{% endtabs %}

---

### 📊 Quick Comparison

| Setting               | Purpose        | When Enabled    | When Disabled |
| --------------------- | -------------- | --------------- | ------------- |
| **Show TP Signals**   | Master control | TP icons appear | No TP signals |
| **Higher Level Only** | Filter quality | Progressive TPs | All TPs shown |

---

### ⚡ Recommended Setup

{% hint style="success" %}
**Best Practice:** Enable BOTH settings together

This gives you:

- ✅ Clean charts
- ✅ Progressive exits
- ✅ Quality signals only
- ✅ No redundant alerts
  {% endhint %}

---

### 🎨 How They Work Together

#### Both Enabled (Recommended)

{% code title="signal-pattern.txt" %}

```
Entry → TP1 at 1% → TP2 at 2% → TP3 at 3%
         ↑ Each TP at higher profit level
```

{% endcode %}

#### Show TP On, Higher Level Off

{% code title="all-signals.txt" %}

```
Entry → TP at 1% → TP at 0.8% → TP at 1.5% → TP at 1.2%
         ↑ Shows all TPs, even lower ones
```

{% endcode %}

---

### 💡 Use Cases

{% columns %}
{% column width="50%" %}

#### Enable Both For

- Scaling out systematically
- Clean chart experience
- Quality over quantity
- Trend following
  {% endcolumn %}

{% column %}

#### Disable Filter For

- Aggressive profit taking
- Volatile markets
- Scalping strategies
- Maximum signals
  {% endcolumn %}
  {% endcolumns %}

---

### 📈 Visual Impact

| Both Enabled              | Filter Disabled        |
| ------------------------- | ---------------------- |
| Fewer, cleaner signals    | More frequent signals  |
| Progressive profit levels | Any profit level       |
| Best for most traders     | For aggressive traders |

{% hint style="info" %}
**Remember:** These settings only work when Exit Type is set to "Signals"
{% endhint %}
