# 🔔 Alerts

[Got ideas? Request a feature](https://infinityalgo.canny.io/?utm_source=docs\&utm_medium=banner)

Note: Use the non-backtest version

Infinity Algo V3.0 offers customizable alerts to keep you informed of important trading opportunities and market conditions. Setting up alerts helps ensure timely responses to key signals, directly enhancing your trading effectiveness.

***

📋 How to Set Up Alerts

{% stepper %}
{% step %}
### Desktop Alert Setup

#### Open Alert Dialog

Right-click on your TradingView chart or press `ALT + A`

![](<../.gitbook/assets/image (78)>)

Alert Menu Access
{% endstep %}

{% step %}
### Desktop — Select Indicator

Choose **Infinity Algo V3.0** from the indicators list

![](<../.gitbook/assets/image (79)>)

Indicator Selection
{% endstep %}

{% step %}
### Desktop — Configure Alert

Select your preferred alert condition from the available options

![](<../.gitbook/assets/image (80)>)

Alert Selection
{% endstep %}

{% step %}
### Desktop — Configure Notifications

Select your preferred notifications from the available options

![](<../.gitbook/assets/image (81)>)

TradingView Notification
{% endstep %}
{% endstepper %}

{% stepper %}
{% step %}
### Mobile Alert Setup — Step 1: Click Settings

Tap the **Settings** icon in the bottom right corner

![Settings Button](<../.gitbook/assets/image (82)>)
{% endstep %}

{% step %}
### Mobile — Step 2: Click on Alerts

Select **Alerts** from the tools menu

![Alerts Option](<../.gitbook/assets/image (83)>)
{% endstep %}

{% step %}
### Mobile — Step 3: Create Alert

Tap the **Create alert** button

![Create Alert Button](<../.gitbook/assets/image (84)>)
{% endstep %}

{% step %}
### Mobile — Step 4: Select Infinity Algo

Choose **Infinity Algo V3.0** from the condition dropdown

![Select Infinity Algo](<../.gitbook/assets/image (85)>)
{% endstep %}

{% step %}
### Mobile — Step 5: Select Alert Type

Pick your desired signal from the list

![Alert Type Selection](<../.gitbook/assets/image (86)>)
{% endstep %}

{% step %}
### Mobile — Step 6: Select Notification Type

Enable your preferred notification methods

![Notification Settings](<../.gitbook/assets/image (87)>)
{% endstep %}
{% endstepper %}

***

🎯 Available Alert Conditions

Quick reference

* Entry (Long) signals: 1.0 — 1.4 (Once Per Bar Close) — Buy signals
* Entry (Short) signals: 1.5 — 1.9 (Once Per Bar Close) — Sell signals
* Take Profits: 2.0 — 2.1 (Once Per Bar) — Profit targets
* Stop Loss: 2.2 — 2.3 (Once Per Bar) — Risk management
* Pre-Signals: 2.4 — 2.5 (Once Per Bar Close) — Early warnings

Detailed alert list

Entry Signals — Buy

* 1.0 Buy Signal - Normal — Counter-trend buy signals
* 1.1 Buy Signal - Smart — Trend-following buy signals
* 1.2 Normal or Smart Buy — Triggers for either type
* 1.3 Buy Signal - HL Sniper — Precision buy entry signals
* 1.4 Buy Signal - AI ⭐ — AI optimized signals

Entry Signals — Sell

* 1.5 Sell Signal - Normal — Counter-trend sell signals
* 1.6 Sell Signal - Smart — Trend-following sell signals
* 1.7 Normal or Smart Sell — Triggers for either type
* 1.8 Sell Signal - HL Sniper — Precision sell entry signals
* 1.9 Sell Signal - AI ⭐ — AI optimized signals

Note: The 1.4 and 1.9 alerts work for BOTH standard AI and AI Sniper modes

Take Profit Alerts

* 2.0 Take Profit Long — Long position profit target hit
* 2.1 Take Profit Short — Short position profit target hit

Stop Loss Alerts

* 2.2 Stop Loss Long Hit — Stop loss triggered on long
* 2.3 Stop Loss Short Hit — Stop loss triggered on short

Early Warning System (Pre-signals)

* 2.4 Possible Long Coming — Potential buy signal ahead
* 2.5 Possible Short Coming — Potential sell signal ahead

Critical recommendation: Use "Once Per Bar" for exits to trigger immediately when price touches levels.

***

⚠️ Critical Alert Settings

{% hint style="warning" %}
MUST READ: Incorrect trigger settings will cause missed trades or false alerts!
{% endhint %}

Entry Signals Configuration

* Trigger: Once Per Bar Close — Confirms signal on candle close
  * Why: Prevents false alerts from wicks and avoids premature entries
  * Never use: Once Per Bar (will trigger on temporary price movements)

Exit Signals Configuration

* Trigger: Once Per Bar (or faster) — Immediate execution needed
  * Why: Instant TP/SL triggers protect profits and limit losses
  * Never use: Once Per Bar Close (delays exit until candle closes)

***

🧩 Optional — TradingView Variables (Placeholders) — Advanced

Add these to the alert message so your alerts include live data. (Work on indicator alerts.)

Placeholders and examples

* \{{exchange\}} — Exchange — Example: BINANCE
* \{{ticker\}} — Symbol — Example: BTCUSDT
* \{{interval\}} — Chart timeframe — Example: 15 (=15m)
* \{{time\}} — Bar time (UTC) — Example: 2025-01-01T12:00:00Z
* \{{timenow\}} — Alert fire time (UTC) — Example: 2025-01-01T12:00:03Z
* \{{open\}} \{{high\}} \{{low\}} \{{close\}} — O/H/L/C of the bar — Example: 43250.5
* \{{volume\}} — Bar volume — Example: 1234.56
* \{{syminfo.currency\}} — Quote currency — Example: USD
* \{{syminfo.basecurrency\}} — Base (for FX/crypto pairs) — Example: BTC or na

How it works

1. Create template: Add placeholders in your alert message (example screenshot shown).
2. Get live data: Variables are replaced with actual values once alert is received.

Example template to copy:

```
🟢 LONG SIGNAL - {{ticker}}

📍 MARKET INFORMATION
Exchange: {{exchange}}
Symbol: {{ticker}}
Currency: {{syminfo.currency}}
Base Currency: {{syminfo.basecurrency}}

📈 PRICE DATA
Open: {{open}}
High: {{high}}
Low: {{low}}
Close: {{close}}
Volume: {{volume}}

⏱️ TIMING
Timeframe: {{interval}}
Bar Time: {{time}}
Alert Triggered: {{timenow}}
```

![](<../.gitbook/assets/image (88)>)

***

Quick Copy-Paste Templates

<details>

<summary>Simple Long</summary>

```
🟢 LONG {{ticker}} @ {{close}}
{{exchange}} | {{interval}} | {{timenow}}
```

</details>

<details>

<summary>Detailed Long</summary>

```
🟢 BUY SIGNAL TRIGGERED
Symbol: {{ticker}}
Entry: {{close}}
Exchange: {{exchange}}
Timeframe: {{interval}}
Volume: {{volume}}
Time: {{timenow}}
```

</details>

<details>

<summary>Professional Long</summary>

```
═══ LONG ENTRY ═══
{{exchange}}:{{ticker}}
Price: {{close}}
Range: {{low}} - {{high}}
Volume: {{volume}}
{{interval}} timeframe
═════════════════
```

</details>

<details>

<summary>Simple Short</summary>

```
🔴 SHORT {{ticker}} @ {{close}}
{{exchange}} | {{interval}} | {{timenow}}
```

</details>

<details>

<summary>Detailed Short</summary>

```
🔴 SELL SIGNAL TRIGGERED
Symbol: {{ticker}}
Entry: {{close}}
Exchange: {{exchange}}
Timeframe: {{interval}}
Volume: {{volume}}
Time: {{timenow}}
```

</details>

<details>

<summary>Risk-Focused Short</summary>

```
⚠️ SHORT POSITION OPENED
{{ticker}} at {{close}}
Daily High: {{high}}
Risk Level: Monitor Closely
Time: {{timenow}}
```

</details>

<details>

<summary>TP Long Hit</summary>

```
✅ TAKE PROFIT (LONG)
{{ticker}}: Target Reached at {{close}}
Entry → Exit: Profit Locked
{{interval}} | {{timenow}}
```

</details>

<details>

<summary>TP Short Hit</summary>

```
✅ TAKE PROFIT (SHORT)
{{ticker}}: Target Reached at {{close}}
Short Covered Successfully
{{interval}} | {{timenow}}
```

</details>

<details>

<summary>Multi-TP Alert</summary>

```
💰 TP LEVEL HIT - {{ticker}}
Price: {{close}}
Partial Exit Recommended
Remaining Position: Hold
Time: {{timenow}}
```

</details>

<details>

<summary>SL Long Hit</summary>

```
🛑 STOP LOSS (LONG)
{{ticker}}: Stop Hit at {{close}}
Position Closed - Risk Management Active
{{interval}} | {{timenow}}
```

</details>

<details>

<summary>SL Short Hit</summary>

```
🛑 STOP LOSS (SHORT)
{{ticker}}: Stop Hit at {{close}}
Short Position Closed
{{interval}} | {{timenow}}
```

</details>

<details>

<summary>Urgent SL</summary>

```
⚠️ STOP LOSS TRIGGERED ⚠️
{{ticker}} @ {{close}}
IMMEDIATE ACTION: Position Closed
Protect Capital
Time: {{timenow}}
```

</details>

<details>

<summary>Possible Long Coming</summary>

```
⏳ POSSIBLE LONG SETUP
{{ticker}} preparing for entry
Current: {{close}}
Watch Level: {{high}}
Timeframe: {{interval}}
Stand By...
```

</details>

<details>

<summary>Possible Short Coming</summary>

```
⏳ POSSIBLE SHORT SETUP
{{ticker}} preparing for entry
Current: {{close}}
Watch Level: {{low}}
Timeframe: {{interval}}
Stand By...
```

</details>

***

🔍 Troubleshooting Guide

<details>

<summary>Alert not triggering</summary>

Possible causes:

* Wrong signal mode

Solutions:

* Verify settings match alert settings
* Check "Once Per Bar Close"
* Enable AI if using AI alerts

</details>

<details>

<summary>Too many alerts</summary>

Possible causes:

* Sensitivity too low

Solutions:

* Use combined alerts
* Increase sensitivity
* Switch to a higher timeframe

</details>

<details>

<summary>False alerts</summary>

Possible causes:

* Wrong trigger setting

Solutions:

* Use "Once Per Bar Close" for entries
* Check for repainting
* Verify timeframe

</details>

<details>

<summary>Missing TP/SL</summary>

Possible causes:

* Wrong trigger type

Solutions:

* Must use "Once Per Bar" (not "Once Per Bar Close")

</details>

***

💡 Pro Tips & Best Practices

Alert Naming and Management

* Name your alerts clearly — include timeframe and signal type
* Test alerts first — use "Once" frequency to verify setup
* Use alert messages — customize with ticker, timeframe, and action
* Consider multiple timeframes — set alerts on different charts
* Regular review — update alerts as market conditions change

Mobile Notifications

* Enable push notifications in TradingView mobile app
* Configure email alerts for backup
* Consider webhook integration for automated systems

***

✅ Summary Checklist

* Entry signals: Once Per Bar Close
* Exit signals: Once Per Bar or faster
* AI alerts work for both AI modes
* Name alerts descriptively
* Test before live trading
* Review settings regularly

By following these guidelines, you'll maximize the effectiveness of Infinity Algo's alert system and never miss important trading opportunities.

Last updated 2 months ago

For privacy details: https://infinityalgo.com/privacy/
