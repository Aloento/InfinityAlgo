# 🔔 Dashboard Alerts

The Infinity Dashboard includes 20 professional alert conditions covering every major signal type. These alerts can trigger notifications, webhooks, or automated trading through TradingView's alert system.

{% columns %}
{% column width="50%" %}

#### Alert Categories

- 📦 **Order Block Alerts** (6 types)
- 📊 **MTF Alignment Alerts** (6 types)
- 🧭 **Market Structure Alerts** (4 types)
- ☁️ **Cloud Band Alerts** (4 types)
  {% endcolumn %}

{% column %}

#### Alert Benefits

- Real-time signal notifications
- Webhook automation support
- Multi-platform integration
- Customizable conditions
  {% endcolumn %}
  {% endcolumns %}

{% hint style="info" %}
**Pro Tip:** Start with 2-3 key alerts to avoid notification overload. Add more as you refine your strategy.
{% endhint %}

---

### 📦 Order Block Alerts

#### Zone Entry/Exit Alerts

| Alert Name               | Trigger Condition                 | Best Use                    | Priority |
| ------------------------ | --------------------------------- | --------------------------- | -------- |
| **Entered Bullish OB**   | Price enters demand zone          | Potential long entry setup  | High     |
| **Entered Bearish OB**   | Price enters supply zone          | Potential short entry setup | High     |
| **Exit from Bullish OB** | Price leaves demand zone upward   | Potential long entry setup  | Medium   |
| **Exit from Bearish OB** | Price leaves supply zone downward | Potential short entry setup | Medium   |

#### Zone Break Alerts

| Alert Name                | Trigger Condition              | Best Use                       | Priority |
| ------------------------- | ------------------------------ | ------------------------------ | -------- |
| **Bullish OB Break Down** | Demand zone broken/invalidated | Exit longs, zone flip warning  | High     |
| **Bearish OB Break Up**   | Supply zone broken/invalidated | Exit shorts, zone flip warning | High     |

{% code title="Setup Example" overflow="wrap" %}

```
1. Create Alert → Condition: Infinity Dashboard
2. Select: "Entered Bullish OB"
3. Options: Once Per Bar Close
4. Actions: Notification + Webhook (optional)
```

{% endcode %}

---

### 📊 MTF Alignment Alerts

#### Alignment Strength Alerts

| Alert Name                     | Trigger Condition        | Rarity | Power   | Recommended Action |
| ------------------------------ | ------------------------ | ------ | ------- | ------------------ |
| **MTF Strong Bullish**         | 6+ timeframes bullish    | Common | High    | Standard position  |
| **MTF Strong Bearish**         | 6+ timeframes bearish    | Common | High    | Standard position  |
| **MTF Full Bullish Alignment** | All 8 timeframes bullish | Rare   | Maximum | Larger position    |
| **MTF Full Bearish Alignment** | All 8 timeframes bearish | Rare   | Maximum | Larger position    |

#### Bias Change Alerts

| Alert Name                  | Trigger Condition                      | Best Use                   | Timing |
| --------------------------- | -------------------------------------- | -------------------------- | ------ |
| **MTF Bias Flip → Bullish** | Average crosses into bullish territory | Trend change early warning | Early  |
| **MTF Bias Flip → Bearish** | Average crosses into bearish territory | Trend change early warning | Early  |

{% hint style="success" %}
**High Value Alert:** MTF Full Alignment alerts are rare but extremely powerful - consider larger positions or tighter monitoring when these trigger.
{% endhint %}

---

### 🧭 Market Structure Alerts

#### Structure Break Alerts

| Alert Name        | Signal Type               | Importance  | Action             | Visual      |
| ----------------- | ------------------------- | ----------- | ------------------ | ----------- |
| **Bullish CHoCH** | Trend reversal to bullish | 🔥 Critical | Major long signal  | Dashed line |
| **Bearish CHoCH** | Trend reversal to bearish | 🔥 Critical | Major short signal | Dashed line |
| **Bullish BOS**   | Uptrend continuation      | 📊 Moderate | Add to longs       | Solid line  |
| **Bearish BOS**   | Downtrend continuation    | 📊 Moderate | Add to shorts      | Solid line  |

{% hint style="warning" %}
**Alert Priority:** CHoCH > BOS (reversals more significant than continuations)

- Use CHoCH for position entry
- Use BOS for position management
  {% endhint %}

---

### ☁️ Cloud Band Alerts

#### Breakout & Cross Alerts

| Alert Name              | Trigger Condition                       | Market State       | Signal Strength |
| ----------------------- | --------------------------------------- | ------------------ | --------------- |
| **Cloud Breakout Up**   | Close above upper cloud + rising slope  | Strong momentum    | Very High       |
| **Cloud Breakout Down** | Close below lower cloud + falling slope | Strong momentum    | Very High       |
| **Cloud Midband ↑**     | Price crosses above midband             | Bias shift bullish | Medium          |
| **Cloud Midband ↓**     | Price crosses below midband             | Bias shift bearish | Medium          |

---

### ⚙️ Alert Configuration Guide

#### Step-by-Step Setup

{% stepper %}
{% step %}

#### Open Alert Dialog

Click the alarm clock icon in the top toolbar or press **Alt+A**
{% endstep %}

{% step %}

#### Select Condition

Choose **"Infinity Dashboard"** from the condition dropdown
{% endstep %}

{% step %}

#### Choose Alert Type

Select from the 20 available alert conditions listed above
{% endstep %}

{% step %}

#### Configure Options

- **Frequency:** Once Per Bar Close (recommended)
- **Expiration:** Open-ended or specific date
- **Alert name:** Custom description
  {% endstep %}

{% step %}

#### Set Actions

- Notify on App
- Show Popup
- Send Email
- Webhook URL (for automation)
- Play Sound
  {% endstep %}
  {% endstepper %}

#### Alert Frequency Options

| Setting                | Behavior                             | Best For                | Notes               |
| ---------------------- | ------------------------------------ | ----------------------- | ------------------- |
| **Once Per Bar**       | Triggers every bar meeting condition | Active monitoring       | Can be noisy        |
| **Once Per Bar Close** | Triggers on confirmed close          | Stable signals          | ✅ Recommended      |
| **Once**               | Triggers once then deactivates       | Single event monitoring | Manual reset needed |

---

### 🎯 Alert Strategies

{% tabs %}
{% tab title="🛡️ Conservative" %}
**Focus on high-probability signals:**

```
1. MTF Strong Bullish/Bearish
2. Bullish/Bearish CHoCH
3. Cloud Breakout Up/Down
```

**Total alerts:** 6 **Best for:** Beginners, swing traders
{% endtab %}

{% tab title="⚔️ Aggressive" %}
**Catch every opportunity:**

```
1. All Order Block entries/exits
2. All MTF alignments
3. All BOS signals
4. All Cloud crosses
```

**Total alerts:** 20 **Best for:** Active traders, scalpers
{% endtab %}

{% tab title="⚖️ Balanced" %}
**Recommended setup:**

```
1. MTF Strong alignments (trend)
2. CHoCH only (reversals)
3. Order Block entries (zones)
4. Cloud breakouts (momentum)
```

**Total alerts:** 10 **Best for:** Most traders
{% endtab %}
{% endtabs %}

---

---

### 💡 Pro Tips

#### Alert Optimization

1. **Start simple:** Begin with 2-3 alerts, add more gradually
2. **Use "Once Per Bar Close":** Reduces false signals significantly
3. **Combine conditions:** Multiple confirmations = higher probability
4. **Time-based filters:** Avoid alerts during low-liquidity hours
5. **Test first:** Paper trade alerts before live trading

#### Alert Fatigue Prevention

{% columns %}
{% column width="50%" %}
**Organization:**

- Group similar alerts
- Use different notification sounds
- Color-code by importance
- Name alerts clearly
  {% endcolumn %}

{% column %}
**Management:**

- Set quiet hours
- Disable during ranging markets
- Review and prune weekly
- Use alert expiration dates
  {% endcolumn %}
  {% endcolumns %}

---

### ⚠️ Common Issues

<details>

<summary><strong>Alert not triggering</strong></summary>

- Verify indicator is loaded on chart
- Check alert condition matches current version
- Ensure "Once Per Bar Close" for stability
- Confirm TradingView plan has available alert slots
- Check that the specific condition is met

</details>

<details>

<summary><strong>Too many alerts</strong></summary>

- Reduce to core signals only
- Increase timeframe (fewer triggers)
- Use stronger conditions (Full alignment vs Strong)
- Set expiration dates
- Group similar alerts together

</details>

<details>

<summary><strong>False signals</strong></summary>

- Always use "Once Per Bar Close"
- Avoid alerts on timeframes < 5 minutes
- Combine multiple confirmations
- Check market conditions (ranging vs trending)
- Review alert logic periodically

</details>

<details>

<summary><strong>Webhook not working</strong></summary>

- Verify webhook URL is correct
- Check JSON format validity
- Test with simple message first
- Ensure receiving service is online
- Check firewall/security settings

</details>

---

### 📚 Quick Reference

#### Alert Cheat Sheet

{% columns %}
{% column width="50%" %}
**Order Blocks:**

- Entry = Potential setup
- Exit = Take profit
- Break = Zone invalidated

**MTF Dashboard:**

- Strong = 6+ timeframes
- Full = All 8 timeframes
- Flip = Trend change
  {% endcolumn %}

{% column %}
**Market Structure:**

- CHoCH = Reversal (priority)
- BOS = Continuation

**Cloud Bands:**

- Breakout = Momentum
- Midband = Bias shift
  {% endcolumn %}
  {% endcolumns %}

#### Alert Setup Checklist

- [ ] Select Infinity Dashboard condition
- [ ] Choose specific alert type
- [ ] Set to "Once Per Bar Close"
- [ ] Configure notification method
- [ ] Test with paper trading
- [ ] Set appropriate expiration
- [ ] Name alert descriptively

---

_For additional support with alerts, visit our_[_FAQ_](https://infinity.aloen.to/faq-and-troubleshoot) _or_ [_contact support._](https://infinityalgo.com/#contact)
