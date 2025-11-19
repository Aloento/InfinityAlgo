# 💰 Take Profit Signals Settings

[Got ideas? Request a feature](https://infinityalgo.canny.io/?utm_source=docs\&utm_medium=banner)

Configure how dynamic exit signals appear when using the "Signals" exit type.

***

#### 🎯 Settings Overview

* Show TP Signals
* Higher Level Only

#### Master Switch

Controls whether TP signals appear at all.

* ✅ Enabled: Shows "TP" icons when momentum suggests taking profit
* ❌ Disabled: No TP signals displayed

#### Enabled

{% hint style="info" %}
Shows all TP opportunities (TP signals on)
{% endhint %}

![TP Signals On](../.gitbook/assets/image)

#### Disabled

{% hint style="warning" %}
No TP signals shown (TP signals off)
{% endhint %}

![TP Signals Off](<../.gitbook/assets/image (1)>)

***

#### Progressive Filter

Controls whether new TP must be at a better (higher profit) price.

* ✅ Enabled: Only shows TPs at higher profit levels
* ❌ Disabled: Shows all TPs regardless of level

**Enabled (Clean)**

{% hint style="info" %}
Progressive TPs only
{% endhint %}

![Higher Level On](<../.gitbook/assets/image (2)>)

**Disabled (All)**

{% hint style="warning" %}
Shows every TP signal
{% endhint %}

![Higher Level Off](<../.gitbook/assets/image (3)>)

***

#### 📊 Quick Comparison

| Setting           |        Purpose | When Enabled    | When Disabled |
| ----------------- | -------------: | --------------- | ------------- |
| Show TP Signals   | Master control | TP icons appear | No TP signals |
| Higher Level Only | Filter quality | Progressive TPs | All TPs shown |

***

#### ⚡ Recommended Setup

Best Practice: Enable BOTH settings together

This gives you:

* ✅ Clean charts
* ✅ Progressive exits
* ✅ Quality signals only
* ✅ No redundant alerts

***

#### 🎨 How They Work Together

{% stepper %}
{% step %}
### Both Enabled (Recommended)

Example pattern:

```
Entry → TP1 at 1% → TP2 at 2% → TP3 at 3%
         ↑ Each TP at higher profit level
```
{% endstep %}

{% step %}
### Show TP On, Higher Level Off

Example pattern:

```
Entry → TP at 1% → TP at 0.8% → TP at 1.5% → TP at 1.2%
         ↑ Shows all TPs, even lower ones
```
{% endstep %}
{% endstepper %}

***

#### 💡 Use Cases

Enable Both For:

* Scaling out systematically
* Clean chart experience
* Quality over quantity
* Trend following

Disable Filter For:

* Aggressive profit taking
* Volatile markets
* Scalping strategies
* Maximum signals

***

#### 📈 Visual Impact

* Both Enabled — Fewer, cleaner signals; Progressive profit levels; Best for most traders
* Filter Disabled — More frequent signals; Any profit level; For aggressive traders

{% hint style="info" %}
These settings only work when Exit Type is set to "Signals".
{% endhint %}

Last updated 3 months ago

This site uses cookies to deliver its service and to analyze traffic. By browsing this site, you accept the [privacy policy](https://infinityalgo.com/privacy/).
