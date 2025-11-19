# 📉📈 EMA Length

[Got ideas?\
Request a feature](https://infinityalgo.canny.io/?utm_source=docs\&utm_medium=banner)

Set the trend filter that determines whether signals follow or counter the trend.

![EMA illustration](<../.gitbook/assets/image (40)>)

***

🎯 How It Works

The EMA acts as a trend filter, changing how signals behave:

* Smart Signals
* Normal Signals

Trend-Following Mode

Buy when:

* Price is **above** EMA
* Confirms uptrend

Sell when:

* Price is **below** EMA
* Confirms downtrend

Use for: Trading with the trend, safer entries, trending markets

Counter-Trend Mode

Buy when:

* Price is **below** EMA
* Looking for reversal up

Sell when:

* Price is **above** EMA
* Looking for reversal down

Use for: Mean reversion, catching reversals, ranging markets

***

📊 Common EMA Settings

| EMA Length | Type         | Best For         | Signal Frequency |
| ---------- | ------------ | ---------------- | ---------------- |
| 20         | Short-term   | Scalping         | Many signals     |
| 50         | Medium       | Day trading      | Moderate         |
| 100        | Intermediate | Swing trading    | Balanced         |
| 200        | Long-term    | Position trading | Few signals      |

***

⚡ Quick Strategy Guide

{% stepper %}
{% step %}
### Trend Following Setup

Settings:

* Signal Mode: `Smart`
* EMA Length: `200`
* Market: Trending

Result: Trade only with major trend
{% endstep %}

{% step %}
### Mean Reversion Setup

Settings:

* Signal Mode: `Normal`
* EMA Length: `20`
* Market: Ranging

Result: Catch quick reversals
{% endstep %}
{% endstepper %}

***

🎨 Visual Example

| Scenario    | Smart Signal        | Normal Signal       |
| ----------- | ------------------- | ------------------- |
| Price > EMA | ✅ Buy signals only  | ✅ Sell signals only |
| Price < EMA | ✅ Sell signals only | ✅ Buy signals only  |

***

💡 Pro Combinations

Popular Setups:

* Conservative Trend:
  * Smart + EMA 200 = Long-term trend trades
* Aggressive Scalping:
  * Normal + EMA 20 = Quick reversals
* Balanced Swing:
  * Smart + EMA 50 = Medium-term momentum

***

⚠️ Important Notes

* **HL Sniper/AI modes:** EMA still filters but with different logic
* **Higher EMA = Fewer signals** but higher quality
* **Lower EMA = More signals** but more noise
* Start with EMA 50 for balanced results

Quick Tip: Match EMA to your timeframe - 20 for intraday, 50 for swing, 200 for position

[Previous📈📉 Upper & Lower Thresholds](upper-and-lower-thresholds.md) · [Next🔔 Show Signals](show-signals.md)

Last updated 3 months ago

[privacy policy](https://infinityalgo.com/privacy/)
