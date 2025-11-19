# 🔄 Next Signals Must Be Opposite Signal

<a href="https://infinityalgo.canny.io/?utm_source=docs&#x26;utm_medium=banner" class="button primary">Got ideas? Request a feature</a>

Control whether signals must alternate directions or can repeat.

![Opposite Signal Setting](<../.gitbook/assets/image (13)>)

#### How It Works

Enabled (strict alternation) vs Disabled (default — any sequence allowed).

{% stepper %}
{% step %}
### Forced Alternation

Pattern: Buy → Sell → Buy → Sell

* Clean reversals only
* One position at a time
* No consecutive signals

Example:

* Last signal: Buy ✅
* Next possible: Only Sell
* Filters out: Any Buy signals

```
Buy ✅ → Sell ✅ → Buy ✅ → Sell ✅
         ↓ Skips Buy signals
```
{% endstep %}

{% step %}
### Any Signal Allowed

Pattern: Buy → Buy → Sell → Buy → Sell → Sell

* Multiple entries allowed
* Trend following possible
* Pyramiding friendly
* All signals shown

Example:

* Last signal: Buy ✅
* Next possible: Buy OR Sell
* Shows: All valid signals

```
Buy ✅ → Buy ✅ → Buy ✅ → Sell ✅
         ↓ Shows all signals
```
{% endstep %}
{% endstepper %}

***

#### Quick Comparison

| Feature             |          Enabled |          Disabled |
| ------------------- | ---------------: | ----------------: |
| Signal Pattern      | Buy → Sell → Buy |      Any sequence |
| Consecutive Signals |          ❌ Never |         ✅ Allowed |
| Best Market         |          Ranging |          Trending |
| Position Style      |    One at a time | Multiple possible |
| Signal Frequency    |            Fewer |              More |

***

#### When to Use

**Enable For**

* Range trading
* Mean reversion
* Single position only
* Clean reversals
* Volatile markets

**Disable For**

* Trend following
* Pyramiding strategies
* Strong trends
* Multiple entries
* Momentum trading

***

{% hint style="info" %}
Best Practice: Enable for ranging markets, disable for trending markets.

Note: This overrides "Toggle Same Signal Consecutively" when enabled — it's the stricter rule.

Remember: Enabling this reduces signal frequency but increases clarity.
{% endhint %}

[Previous 🔁 Toggle Same Signal Consecutively](toggle-same-signal-consecutively.md) · [Next 💪 Peak Profit/Leverage](peak-profit-leverage.md)

Last updated 3 months ago

***

This page links to the privacy policy: https://infinityalgo.com/privacy/
