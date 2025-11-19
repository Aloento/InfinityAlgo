# ⚙️ Example of settings

[Got ideas? Request a feature](https://infinityalgo.canny.io/?utm_source=docs\&utm_medium=banner)

Master every setting in Infinity Algo V3.0 Backtest. This guide covers all configuration options with practical examples for different trading styles.

**Prerequisites:** Already ran your first backtest? If not, start with the Backtesting Overview first.

***

🎯 Configuration Philosophy

Two Approaches

* 🤖 AI-Optimized
* 🎯 Manual Control

Let AI Handle It

How it works:

{% stepper %}
{% step %}
### Enable AI Optimization

Enable AI Optimization in the settings to let the system tune parameters.
{% endstep %}

{% step %}
### Select performance metric

Choose the metric (e.g., Total Profit) you want AI to optimize.
{% endstep %}

{% step %}
### AI adjusts sensitivity/thresholds

AI will modify sensitivity and thresholds within the configured ranges.
{% endstep %}

{% step %}
### You control exits and risk

Keep full control of exits and risk-related parameters while AI handles signals.
{% endstep %}
{% endstepper %}

Best for:

* Most traders
* Market adaptation
* Consistent results

ai-setup:

```
AI Optimization: ON
Performance Metric: Total Profit
Signal Mode: AI
Sensitivity Range: Balanced
Update Frequency: 1000 bars
```

![](<../.gitbook/assets/image (89)>)

Direct Configuration

When to use:

* Testing specific ideas
* Learning parameter impact
* Personal preference
* Predictable behavior

You control everything:

* Sensitivity (5-28)
* Thresholds (60-80/20-40)
* All exit parameters

***

📊 Exit Strategies Explained

Choose Your Exit Style

* Percentage Exit
* Signals Exit
* Opposite Signal

Fixed Targets & Stops

How it works:

* Exit at predetermined %
* Up to 6 take profit levels
* Partial position exits
* Fixed stop loss

Perfect for:

* ✅ Beginners
* ✅ Scalping
* ✅ Consistent results
* ✅ Risk management

percentage-config.txt

```
Exit Type: Percentage
TP1: 1% (exit 50%)
TP2: 2% (exit 30%)
TP3: 3% (exit 20%)
Stop Loss: 2%
```

Configuration Examples

| Style       | TP1  | TP2 | TP3 | Stop Loss |
| ----------- | ---- | --- | --- | --------- |
| Scalping    | 0.5% | 1%  | -   | 0.5%      |
| Day Trading | 1%   | 2%  | 3%  | 1.5%      |
| Swing       | 3%   | 5%  | 8%  | 3%        |

Dynamic Market-Based

How it works:

* Exit on technical signals
* Adapts to momentum
* Captures full moves
* No fixed targets

signals-config.txt

```
Exit Type: Signals
Use TP Signals: ON
Min Profit Before Exit: 0.5%
Adapt to Volatility: ON
```

Best for:

* ✅ Trending markets
* ✅ Experienced traders
* ✅ Larger moves
* ⚠️ Higher variance

Maximum Trend Capture

How it works:

* Hold until reversal signal
* No profit targets
* No stop loss
* Pure trend following

Example:

* Long exits on Sell signal
* Short exits on Buy signal

Advanced only: Requires strong psychology and risk management

***

💰 Position Management

Pyramiding (Scaling In)

What is it? Adding to winning positions

Settings:

* `More Entries`: Enable/Disable
* `Pyramiding`: 1-10 additions
* Size per addition

pyramid-setup:

```
Pyramiding: 2
Entry 1: 33% capital
Entry 2: 33% at +1%
Entry 3: 34% at +2%
Max Risk: 2% total
```

Risk Levels

| Experience   | Pyramiding | Risk Per Trade | Position Size |
| ------------ | ---------- | -------------- | ------------- |
| Beginner     | 0          | 1%             | 100% entry    |
| Intermediate | 1          | 1.5%           | 50% + 50%     |
| Advanced     | 2-3        | 2%             | 33% each      |
| Expert       | 3+         | 2%             | Custom        |

***

🎨 Configuration by Trading Style

Quick Reference Templates

* ⚡ Scalping
* 📊 Day Trading
* 📈 Swing Trading
* 📅 Position Trading

scalping-config.txt

```
Timeframe: 1-5 min
Sensitivity: 5-9
Thresholds: 75/25
Exit Type: Percentage
TP1: 0.5% (100%)
Stop Loss: 0.5%
Pyramiding: 0
```

daytrading-config:

```
Timeframe: 15-60 min
Sensitivity: 10-14
Thresholds: 70/30
Exit Type: Percentage
TP1: 1% (50%)
TP2: 2% (50%)
Stop Loss: 1.5%
Pyramiding: 0-1
```

swing-config:

```
Timeframe: 4H-Daily
Sensitivity: 15-21
Thresholds: 70/30
Exit Type: Signals
Min Profit: 1%
Stop Loss: 3-5%
Pyramiding: 1-2
```

position-config:

```
Timeframe: Daily-Weekly
Sensitivity: 22-28
Thresholds: 65/35
Exit Type: Opposite Signal
Stop Loss: Optional (5-10%)
Pyramiding: 2-3
```

***

🧪 Testing Your Configuration

Systematic Approach

{% stepper %}
{% step %}
### Document settings

Write down every parameter before testing.
{% endstep %}

{% step %}
### Run baseline

Test on the last 6 months first to get a baseline result.
{% endstep %}

{% step %}
### Stress test

Test worst market periods (e.g., March 2020, May 2021, 2022 bear market).
{% endstep %}

{% step %}
### Compare results

Look for consistency across periods.
{% endstep %}

{% step %}
### Refine one variable

Change only one setting at a time and retest.
{% endstep %}
{% endstepper %}

***

📈 Performance Targets by Style

| Trading Style | Min Profit Factor | Max Drawdown | Win Rate | Avg RRR |
| ------------- | ----------------- | ------------ | -------- | ------- |
| Scalping      | 1.3               | 10%          | 60%+     | 1:1     |
| Day Trading   | 1.5               | 15%          | 50%+     | 1.5:1   |
| Swing         | 2.0               | 20%          | 40%+     | 2:1     |
| Position      | 2.5               | 25%          | 35%+     | 3:1     |

***

❓ Configuration FAQ

<details>

<summary>Which exit type is best for beginners?</summary>

Start with Percentage Exit:

* Predictable results
* Easy to understand
* Better risk control
* Consistent outcomes

Move to Signals/Opposite after 50+ trades experience.

</details>

<details>

<summary>Should I use pyramiding?</summary>

Progressive approach:

1. First 30 trades: No pyramiding
2. After profitable: Add 1 level
3. After 100 trades: Consider 2
4. Expert only: 3+

Always keep total risk under 2%.

</details>

<details>

<summary>How do I know if settings are over-optimized?</summary>

Warning signs:

* Small changes = big result differences
* Amazing backtest, poor live results
* Only works on one symbol
* Requires perfect conditions

Solution: Test on multiple timeframes and symbols.

</details>

***

Next Step: Configure your settings based on your trading style, then test thoroughly. Remember: consistency beats perfection.

[Previous Backtest version](./) · [Next 📋 Settings Spreadsheet](settings-spreadsheet.md)

Last updated 2 months ago

Was this helpful?

This site uses cookies to deliver its service and to analyze traffic. By browsing this site, you accept the [privacy policy](https://infinityalgo.com/privacy/).

Accept Reject
