# 🔔 Dashboard Alerts

[Got ideas? Request a feature](https://infinityalgo.canny.io/?utm_source=docs\&utm_medium=banner)

The Infinity Dashboard includes 20 professional alert conditions covering every major signal type. These alerts can trigger notifications, webhooks, or automated trading through TradingView's alert system.

Alert Categories

* 📦 Order Block Alerts (6 types)
* 📊 MTF Alignment Alerts (6 types)
* 🧭 Market Structure Alerts (4 types)
* ☁️ Cloud Band Alerts (4 types)

Alert Benefits

* Real-time signal notifications
* Webhook automation support
* Multi-platform integration
* Customizable conditions

{% hint style="info" %}
Pro Tip: Start with 2-3 key alerts to avoid notification overload. Add more as you refine your strategy.
{% endhint %}

***

📦 Order Block Alerts

Zone Entry/Exit Alerts

* Entered Bullish OB
  * Trigger: Price enters demand zone
  * Best use: Potential long entry setup
  * Priority: High
* Entered Bearish OB
  * Trigger: Price enters supply zone
  * Best use: Potential short entry setup
  * Priority: High
* Exit from Bullish OB
  * Trigger: Price leaves demand zone upward
  * Best use: Potential long exit/management
  * Priority: Medium
* Exit from Bearish OB
  * Trigger: Price leaves supply zone downward
  * Best use: Potential short exit/management
  * Priority: Medium

Zone Break Alerts

* Bullish OB Break Down
  * Trigger: Demand zone broken/invalidated
  * Best use: Exit longs, zone flip warning
  * Priority: High
* Bearish OB Break Up
  * Trigger: Supply zone broken/invalidated
  * Best use: Exit shorts, zone flip warning
  * Priority: High

Setup Example

{% code title="Setup Example" %}
```
1. Create Alert → Condition: Infinity Dashboard
2. Select: "Entered Bullish OB"
3. Options: Once Per Bar Close
4. Actions: Notification + Webhook (optional)
```
{% endcode %}

***

📊 MTF Alignment Alerts

Alignment Strength Alerts

* MTF Strong Bullish
  * Trigger: 6+ timeframes bullish
  * Rarity: Common
  * Power: High
  * Recommended action: Standard position
* MTF Strong Bearish
  * Trigger: 6+ timeframes bearish
  * Rarity: Common
  * Power: High
  * Recommended action: Standard position
* MTF Full Bullish Alignment
  * Trigger: All 8 timeframes bullish
  * Rarity: Rare
  * Power: Maximum
  * Recommended action: Larger position
* MTF Full Bearish Alignment
  * Trigger: All 8 timeframes bearish
  * Rarity: Rare
  * Power: Maximum
  * Recommended action: Larger position

Bias Change Alerts

* MTF Bias Flip → Bullish
  * Trigger: Average crosses into bullish territory
  * Best use: Trend change early warning
  * Timing: Early
* MTF Bias Flip → Bearish
  * Trigger: Average crosses into bearish territory
  * Best use: Trend change early warning
  * Timing: Early

{% hint style="info" %}
High Value Alert: MTF Full Alignment alerts are rare but extremely powerful — consider larger positions or tighter monitoring when these trigger.
{% endhint %}

***

🧭 Market Structure Alerts

Structure Break Alerts

* Bullish CHoCH
  * Signal type: Trend reversal to bullish
  * Importance: 🔥 Critical
  * Action: Major long signal
  * Visual: Dashed line
* Bearish CHoCH
  * Signal type: Trend reversal to bearish
  * Importance: 🔥 Critical
  * Action: Major short signal
  * Visual: Dashed line
* Bullish BOS
  * Signal type: Uptrend continuation
  * Importance: 📊 Moderate
  * Action: Add to longs
  * Visual: Solid line
* Bearish BOS
  * Signal type: Downtrend continuation
  * Importance: 📊 Moderate
  * Action: Add to shorts
  * Visual: Solid line

{% hint style="info" %}
Alert Priority: CHoCH > BOS (reversals more significant than continuations)

* Use CHoCH for position entry
* Use BOS for position management
{% endhint %}

***

☁️ Cloud Band Alerts

Breakout & Cross Alerts

* Cloud Breakout Up
  * Trigger: Close above upper cloud + rising slope
  * Market state: Strong momentum
  * Signal strength: Very High
* Cloud Breakout Down
  * Trigger: Close below lower cloud + falling slope
  * Market state: Strong momentum
  * Signal strength: Very High
* Cloud Midband ↑
  * Trigger: Price crosses above midband
  * Market state: Bias shift bullish
  * Signal strength: Medium
* Cloud Midband ↓
  * Trigger: Price crosses below midband
  * Market state: Bias shift bearish
  * Signal strength: Medium

***

⚙️ Alert Configuration Guide

Step-by-Step Setup

{% stepper %}
{% step %}
### Open Alert Dialog

Click the alarm clock icon in the top toolbar or press Alt+A
{% endstep %}

{% step %}
### Select Condition

Choose "Infinity Dashboard" from the condition dropdown
{% endstep %}

{% step %}
### Choose Alert Type

Select from the 20 available alert conditions listed above
{% endstep %}

{% step %}
### Configure Options

* Frequency: Once Per Bar Close (recommended)
* Expiration: Open-ended or specific date
* Alert name: Custom description
{% endstep %}

{% step %}
### Set Actions

* Notify on App
* Show Popup
* Send Email
* Webhook URL (for automation)
* Play Sound
{% endstep %}
{% endstepper %}

Alert Frequency Options

* Once Per Bar
  * Behavior: Triggers every bar meeting condition
  * Best for: Active monitoring
  * Notes: Can be noisy
* Once Per Bar Close
  * Behavior: Triggers on confirmed close
  * Best for: Stable signals
  * Notes: ✅ Recommended
* Once
  * Behavior: Triggers once then deactivates
  * Best for: Single event monitoring
  * Notes: Manual reset needed

***

🎯 Alert Strategies

Focus on high-probability signals (Conservative)

* MTF Strong Bullish/Bearish
* Bullish/Bearish CHoCH
* Cloud Breakout Up/Down\
  Total alerts: 6 — Best for: Beginners, swing traders

Catch every opportunity (Aggressive)

* All Order Block entries/exits
* All MTF alignments
* All BOS signals
* All Cloud crosses\
  Total alerts: 20 — Best for: Active traders, scalpers

Recommended setup (Balanced)

* MTF Strong alignments (trend)
* CHoCH only (reversals)
* Order Block entries (zones)
* Cloud breakouts (momentum)\
  Total alerts: 10 — Best for: Most traders

Example configurations:

{% code title="Conservative Example" %}
```
1. MTF Strong Bullish/Bearish
2. Bullish/Bearish CHoCH
3. Cloud Breakout Up/Down
```
{% endcode %}

{% code title="Aggressive Example" %}
```
1. All Order Block entries/exits
2. All MTF alignments
3. All BOS signals
4. All Cloud crosses
```
{% endcode %}

{% code title="Recommended Example" %}
```
1. MTF Strong alignments (trend)
2. CHoCH only (reversals)
3. Order Block entries (zones)
4. Cloud breakouts (momentum)
```
{% endcode %}

***

💡 Pro Tips

Alert Optimization

1. Start simple: Begin with 2-3 alerts, add more gradually
2. Use "Once Per Bar Close": Reduces false signals significantly
3. Combine conditions: Multiple confirmations = higher probability
4. Time-based filters: Avoid alerts during low-liquidity hours
5. Test first: Paper trade alerts before live trading

Alert Fatigue Prevention

Organization

* Group similar alerts
* Use different notification sounds
* Color-code by importance
* Name alerts clearly

Management

* Set quiet hours
* Disable during ranging markets
* Review and prune weekly
* Use alert expiration dates

***

⚠️ Common Issues

<details>

<summary>Alert not triggering</summary>

* Verify indicator is loaded on chart
* Check alert condition matches current version
* Ensure "Once Per Bar Close" for stability
* Confirm TradingView plan has available alert slots
* Check that the specific condition is met

</details>

<details>

<summary>Too many alerts</summary>

* Reduce to core signals only
* Increase timeframe (fewer triggers)
* Use stronger conditions (Full alignment vs Strong)
* Set expiration dates
* Group similar alerts together

</details>

<details>

<summary>False signals</summary>

* Always use "Once Per Bar Close"
* Avoid alerts on timeframes < 5 minutes
* Combine multiple confirmations
* Check market conditions (ranging vs trending)
* Review alert logic periodically

</details>

<details>

<summary>Webhook not working</summary>

* Verify webhook URL is correct
* Check JSON format validity
* Test with simple message first
* Ensure receiving service is online
* Check firewall/security settings

</details>

***

📚 Quick Reference

Alert Cheat Sheet

* Order Blocks: Entry = Potential setup, Exit = Take profit, Break = Zone invalidated
* MTF Dashboard: Strong = 6+ timeframes, Full = All 8 timeframes, Flip = Trend change
* Market Structure: CHoCH = Reversal (priority), BOS = Continuation
* Cloud Bands: Breakout = Momentum, Midband = Bias shift

Alert Setup Checklist

* Select Infinity Dashboard condition
* Choose specific alert type
* Set to "Once Per Bar Close"
* Configure notification method
* Test with paper trading
* Set appropriate expiration
* Name alert descriptively

***

For additional support with alerts, visit our [FAQ](../faq-and-troubleshoot/) or [contact support.](https://infinityalgo.com/#contact)

Last updated 2 months ago

Was this helpful?

This site uses cookies to deliver its service and to analyze traffic. By browsing this site, you accept the [privacy policy](https://infinityalgo.com/privacy/).

Accept | Reject
