# 📊 MTF Dashboard

## 📊 MTF Dashboard

Monitor 8 timeframes simultaneously to identify trend alignment and market consensus across multiple time horizons.

---

#### 🎯 What is MTF Dashboard?

The Multi-Timeframe (MTF) Dashboard provides a comprehensive view of market conditions across 8 different timeframes in a single, easy-to-read table. It analyzes trend direction and volatility for each timeframe, helping you identify when multiple timeframes align for high-probability setups.

{% hint style="info" %}
**Key Insight:** When 6+ timeframes show the same trend direction, the probability of continuation increases significantly.
{% endhint %}

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FcRDWitMUWx9ddlGM2IKe%2Fimage.png?alt=media&#x26;token=ef9b81d1-d2ad-42c9-b731-1da9d47e7d34" alt="MTF Dashboard Screenshot"><figcaption><p>Multi-Timeframe Dashboard </p></figcaption></figure>

---

#### 📈 Dashboard Components

**Column 1: Timeframe**

Displays your selected timeframes with visual indicators:

- ⚡ **Ultra-fast** (1-3 min) - Scalping
- 🔍 **Fast** (5-15 min) - Day trading
- 🕒 **Medium** (30-60 min) - Intraday
- 🕐 **Slow** (2-4 hours) - Swing entries
- 📅 **Daily+** - Position/trend

**Column 2: Trend Status**

Shows market direction based on momentum analysis:

| Status         | Emoji | Meaning                            | Trading Implication               |
| -------------- | ----- | ---------------------------------- | --------------------------------- |
| **Overbought** | 🔥    | Strong upward momentum, extended   | Consider taking profits on longs  |
| **Oversold**   | ❄️    | Strong downward momentum, extended | Consider taking profits on shorts |
| **Bullish**    | 🚀    | Upward trend, healthy momentum     | Look for long opportunities       |
| **Bearish**    | 🧸    | Downward trend, healthy momentum   | Look for short opportunities      |

**Column 3: Volatility**

Displays market volatility with trend indicators:

| Level      | Emoji | Meaning            | Best For                       |
| ---------- | ----- | ------------------ | ------------------------------ |
| **High**   | 🌋    | Large price swings | Scalping, breakout trades      |
| **Normal** | ⚖️    | Average movement   | Standard strategies            |
| **Low**    | 💤    | Tight ranges       | Range trading, avoid breakouts |

**Trend Arrows:**

- 📈 Rising volatility (expansion coming)
- 📉 Falling volatility (consolidation)
- ➡️ Stable volatility

---

#### ⚙️ Configuration

**Basic Settings**

| Setting                | Options                           | Description                    |
| ---------------------- | --------------------------------- | ------------------------------ |
| **Show MTF Dashboard** | On/Off                            | Toggle dashboard visibility    |
| **Dashboard Location** | Top Right/Left, Bottom Right/Left | Screen position                |
| **Dashboard Style**    | Pro Neutral, Semantic Heatmap     | Visual presentation style      |
| **TF 1-8**             | Any timeframe                     | Select 8 timeframes to monitor |

**Dashboard Style Options**

{% tabs %}
{% tab title="Pro Neutral" %}
**Professional zebra row design**

- Clean alternating row backgrounds
- Consistent text colors throughout
- Easier on the eyes for extended viewing
- Professional appearance for screenshots
- Best for: Traders who prefer minimal visual distraction

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FTkK49ur6Pm4pFv33c7gr%2Fimage.png?alt=media&#x26;token=2f7ebff5-5239-475a-a736-dca114e72a40" alt="" width="375"><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Semantic Heatmap" %}
**Color-coded cells for quick scanning**

- Dynamic cell colors based on conditions
- Instant visual recognition of market state
- Trend strength shown through color intensity
- Volatility levels with distinct color coding
- Best for: Quick market assessment and pattern recognition

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FtKnuWrhinxGjLYRodnvf%2Fimage.png?alt=media&#x26;token=ad2c417a-d96d-4d7a-b99b-ed27d2514186" alt="" width="375"><figcaption></figcaption></figure>
{% endtab %}
{% endtabs %}

**Recommended Timeframe Sets**

{% tabs %}
{% tab title="⚡ Scalping" %}
{% code overflow="wrap" %}

```
TF1: 1        # 1 minute
TF2: 3        # 3 minutes
TF3: 5        # 5 minutes
TF4: 15       # 15 minutes
TF5: 30       # 30 minutes
TF6: 60       # 1 hour
TF7: 240      # 4 hours
TF8: D        # Daily
```

{% endcode %}

**Focus:** Quick trades with higher timeframe confirmation
{% endtab %}

{% tab title="📊 Day Trading" %}
{% code overflow="wrap" %}

```
TF1: 5        # 5 minutes
TF2: 15       # 15 minutes
TF3: 30       # 30 minutes
TF4: 60       # 1 hour
TF5: 2h       # 2 hours
TF6: 240      # 4 hours
TF7: D        # Daily
TF8: W        # Weekly
```

{% endcode %}

**Focus:** Intraday positions with trend alignment
{% endtab %}

{% tab title="🏔️ Swing Trading" %}
{% code overflow="wrap" %}

```
TF1: 60       # 1 hour
TF2: 2h       # 2 hours
TF3: 240      # 4 hours
TF4: 6h       # 6 hours
TF5: 12h      # 12 hours
TF6: D        # Daily
TF7: W        # Weekly
TF8: M        # Monthly
```

{% endcode %}

**Focus:** Multi-day positions with strong trends
{% endtab %}

{% tab title="🎯 Custom" %}
You can input custom timeframes like:

- `90` for 90 minutes
- `3h` for 3 hours
- `2d` for 2 days
- Mix any combination that suits your strategy
  {% endtab %}
  {% endtabs %}

---

#### 📖 Reading the Dashboard

**The AVG Row (Bottom Summary)**

{% columns %}
{% column width="50%" %}
**Trend Bias**

The **⭐ AVG** row provides overall market assessment:

- 🚀 **Bullish** = Majority uptrend
- 🧸 **Bearish** = Majority downtrend
- ⚖️ **Neutral** = Mixed signals
  {% endcolumn %}

{% column %}
**Volatility Summary**

Shows dominant market conditions:

- Dominant volatility level (High/Normal/Low)
- Expansion or contraction trend
- Overall market agreement strength
  {% endcolumn %}
  {% endcolumns %}

{% hint style="success" %}
**Pro Tip:** The AVG row gives you the "market consensus" - when it shows strong bias, follow that direction.
{% endhint %}

---

#### 🎯 Trading Signals

**High-Probability Setups**

{% stepper %}
{% step %}
**Strong Alignment (6+ Timeframes)**

- **Signal:** 6 or more timeframes same direction
- **Action:** Trade in alignment direction
- **Alert Available:** "MTF Strong Bullish/Bearish"
  {% endstep %}

{% step %}
**Full Alignment (8/8 Timeframes)**

- **Signal:** All 8 timeframes same direction
- **Action:** Maximum position size opportunity
- **Alert Available:** "MTF Full Alignment"
  {% endstep %}

{% step %}
**Bias Flip**

- **Signal:** AVG row changes from Bearish to Bullish (or vice versa)
- **Action:** Prepare for trend change
- **Alert Available:** "MTF Bias Flip"
  {% endstep %}
  {% endstepper %}

---

#### 🔔 Alert Configuration

Available alerts for MTF Dashboard:

| Alert Name                     | Triggers When              | Use Case                 |
| ------------------------------ | -------------------------- | ------------------------ |
| **MTF Strong Bullish**         | 6+ timeframes bullish      | Entry signal for longs   |
| **MTF Strong Bearish**         | 6+ timeframes bearish      | Entry signal for shorts  |
| **MTF Full Bullish Alignment** | All 8 timeframes bullish   | Rare strong trend signal |
| **MTF Full Bearish Alignment** | All 8 timeframes bearish   | Rare strong trend signal |
| **MTF Bias Flip → Bullish**    | Overall bias turns bullish | Trend reversal signal    |
| **MTF Bias Flip → Bearish**    | Overall bias turns bearish | Trend reversal signal    |

---

#### 💡 Pro Strategies

**Strategy 1: Alignment Confluence**

Wait for strong MTF alignment (6+) to coincide with:

- Order block test
- Cloud band edge
- Key support/resistance

**Strategy 2: Timeframe Cascade**

1. Higher timeframes turn bullish first
2. Wait for lower timeframes to align
3. Enter on lowest timeframe signal

**Strategy 3: Volatility Filter**

- **High volatility + Alignment** = Breakout trade
- **Low volatility + Alignment** = Wait for expansion
- **Normal volatility + Alignment** = Standard entry

---

#### ⚠️ Common Mistakes

{% hint style="warning" %}
**Avoid These Errors:**

1. **Trading against strong alignment** - Don't fight 6+ timeframe consensus
2. **Ignoring higher timeframes** - They set the dominant trend
3. **Over-weighting fast timeframes** - Balance your analysis
4. **Not waiting for alignment** - Patience for high-probability setups
   {% endhint %}

---

#### 🛠️ Troubleshooting

<details>

<summary><strong>Dashboard not showing any data</strong></summary>

- Ensure "Show MTF Dashboard" is enabled
- Check that you have enough historical data loaded
- Verify timeframe inputs are valid (e.g., "5", "15", "60", "D")

</details>

<details>

<summary><strong>Some timeframes show "n/a"</strong></summary>

- The timeframe may be invalid or not available
- Try standard timeframes: 1, 5, 15, 30, 60, 240, D, W
- Custom timeframes need specific format (e.g., "90" for 90 minutes)

</details>

<details>

<summary><strong>Dashboard updates slowly</strong></summary>

- This is normal - it updates with each new bar close
- Higher timeframes update less frequently
- Use lower timeframes for more responsive data

</details>

---

**Best Practices**

1. Start with standard timeframe sets
2. Choose a dashboard style that suits your trading approach
3. Wait for 6+ timeframe alignment
4. Confirm with other dashboard features
5. Use alerts to catch alignment changes
6. Respect the overall AVG bias

---

_Need help? Check our_ [_FAQ_](https://infinity.aloen.to/faq/faq-and-troubleshoot) _or_ [_contact support_](https://infinityalgo.com/#contact)_._
