# 📊 MTF Dashboard

[Got ideas? Request a feature](https://infinityalgo.canny.io/?utm_source=docs\&utm_medium=banner)

## 📊 MTF Dashboard

Monitor 8 timeframes simultaneously to identify trend alignment and market consensus across multiple time horizons.

***

### 🎯 What is MTF Dashboard?

The Multi-Timeframe (MTF) Dashboard provides a comprehensive view of market conditions across 8 different timeframes in a single, easy-to-read table. It analyzes trend direction and volatility for each timeframe, helping you identify when multiple timeframes align for high-probability setups.

Key Insight: When 6+ timeframes show the same trend direction, the probability of continuation increases significantly.

![MTF Dashboard Screenshot](<../.gitbook/assets/image (74)>)

Multi-Timeframe Dashboard

***

### 📈 Dashboard Components

#### Column 1: Timeframe

Displays your selected timeframes with visual indicators:

* ⚡ Ultra-fast (1-3 min) - Scalping
* 🔍 Fast (5-15 min) - Day trading
* 🕒 Medium (30-60 min) - Intraday
* 🕐 Slow (2-4 hours) - Swing entries
* 📅 Daily+ - Position/trend

#### Column 2: Trend Status

Shows market direction based on momentum analysis.

* Overbought 🔥 — Strong upward momentum, extended. Trading implication: Consider taking profits on longs.
* Oversold ❄️ — Strong downward momentum, extended. Trading implication: Consider taking profits on shorts.
* Bullish 🚀 — Upward trend, healthy momentum. Trading implication: Look for long opportunities.
* Bearish 🧸 — Downward trend, healthy momentum. Trading implication: Look for short opportunities.

#### Column 3: Volatility

Displays market volatility with trend indicators.

* High 🌋 — Large price swings. Best for: Scalping, breakout trades.
* Normal ⚖️ — Average movement. Best for: Standard strategies.
* Low 💤 — Tight ranges. Best for: Range trading, avoid breakouts.

Trend Arrows:

* 📈 Rising volatility (expansion coming)
* 📉 Falling volatility (consolidation)
* ➡️ Stable volatility

***

### ⚙️ Configuration

#### Basic Settings

* Show MTF Dashboard: On/Off — Toggle dashboard visibility
* Dashboard Location: Top Right/Left, Bottom Right/Left — Screen position
* Dashboard Style: Pro Neutral, Semantic Heatmap — Visual presentation style
* TF 1-8: Any timeframe — Select 8 timeframes to monitor

#### Dashboard Style Options

Pro Neutral

* Professional zebra row design:
  * Clean alternating row backgrounds
  * Consistent text colors throughout
  * Easier on the eyes for extended viewing
  * Professional appearance for screenshots
  * Best for: Traders who prefer minimal visual distraction

![Dashboard Style](<../.gitbook/assets/image (75)>)

Color-coded cells for quick scanning:

* Dynamic cell colors based on conditions
* Instant visual recognition of market state
* Trend strength shown through color intensity
* Volatility levels with distinct color coding
* Best for: Quick market assessment and pattern recognition

![Color-coded cells](<../.gitbook/assets/image (76)>)

#### Recommended Timeframe Sets

{% tabs %}
{% tab title="Scalping" %}
TF1: 1 # 1 minute\
TF2: 3 # 3 minutes\
TF3: 5 # 5 minutes\
TF4: 15 # 15 minutes\
TF5: 30 # 30 minutes\
TF6: 60 # 1 hour\
TF7: 240 # 4 hours\
TF8: D # Daily

Focus: Quick trades with higher timeframe confirmation
{% endtab %}

{% tab title="Day Trading" %}
TF1: 5 # 5 minutes\
TF2: 15 # 15 minutes\
TF3: 30 # 30 minutes\
TF4: 60 # 1 hour\
TF5: 2h # 2 hours\
TF6: 240 # 4 hours\
TF7: D # Daily\
TF8: W # Weekly

Focus: Intraday positions with trend alignment
{% endtab %}

{% tab title="Swing Trading" %}
TF1: 60 # 1 hour\
TF2: 2h # 2 hours\
TF3: 240 # 4 hours\
TF4: 6h # 6 hours\
TF5: 12h # 12 hours\
TF6: D # Daily\
TF7: W # Weekly\
TF8: M # Monthly

Focus: Multi-day positions with strong trends
{% endtab %}

{% tab title="Custom" %}
You can input custom timeframes like:

* `90` for 90 minutes
* `3h` for 3 hours
* `2d` for 2 days

Mix any combination that suits your strategy.
{% endtab %}
{% endtabs %}

***

### 📖 Reading the Dashboard

#### The AVG Row (Bottom Summary)

Trend Bias: The ⭐ AVG row provides overall market assessment:

* 🚀 Bullish = Majority uptrend
* 🧸 Bearish = Majority downtrend
* ⚖️ Neutral = Mixed signals

Volatility Summary:

* Dominant volatility level (High/Normal/Low)
* Expansion or contraction trend
* Overall market agreement strength

Pro Tip: The AVG row gives you the "market consensus" - when it shows strong bias, follow that direction.

***

### 🎯 Trading Signals

{% stepper %}
{% step %}
### Strong Alignment (6+ Timeframes)

* Signal: 6 or more timeframes same direction
* Action: Trade in alignment direction
* Alert Available: "MTF Strong Bullish/Bearish"
{% endstep %}

{% step %}
### Full Alignment (8/8 Timeframes)

* Signal: All 8 timeframes same direction
* Action: Maximum position size opportunity
* Alert Available: "MTF Full Alignment"
{% endstep %}

{% step %}
### Bias Flip

* Signal: AVG row changes from Bearish to Bullish (or vice versa)
* Action: Prepare for trend change
* Alert Available: "MTF Bias Flip"
{% endstep %}
{% endstepper %}

***

### 🔔 Alert Configuration

Available alerts for MTF Dashboard:

* MTF Strong Bullish — Triggers when 6+ timeframes bullish — Use Case: Entry signal for longs
* MTF Strong Bearish — Triggers when 6+ timeframes bearish — Use Case: Entry signal for shorts
* MTF Full Bullish Alignment — Triggers when all 8 timeframes bullish — Use Case: Rare strong trend signal
* MTF Full Bearish Alignment — Triggers when all 8 timeframes bearish — Use Case: Rare strong trend signal
* MTF Bias Flip → Bullish — Triggers when overall bias turns bullish — Use Case: Trend reversal signal
* MTF Bias Flip → Bearish — Triggers when overall bias turns bearish — Use Case: Trend reversal signal

***

### 💡 Pro Strategies

{% stepper %}
{% step %}
### Alignment Confluence

Wait for strong MTF alignment (6+) to coincide with:

* Order block test
* Cloud band edge
* Key support/resistance
{% endstep %}

{% step %}
### Timeframe Cascade

* Higher timeframes turn bullish first
* Wait for lower timeframes to align
* Enter on lowest timeframe signal
{% endstep %}

{% step %}
### Volatility Filter

* High volatility + Alignment = Breakout trade
* Low volatility + Alignment = Wait for expansion
* Normal volatility + Alignment = Standard entry
{% endstep %}
{% endstepper %}

***

### ⚠️ Common Mistakes

{% stepper %}
{% step %}
Avoid trading against strong alignment — Don't fight 6+ timeframe consensus
{% endstep %}

{% step %}
Avoid ignoring higher timeframes — They set the dominant trend
{% endstep %}

{% step %}
Avoid over-weighting fast timeframes — Balance your analysis
{% endstep %}

{% step %}
Don't skip waiting for alignment — Patience for high-probability setups
{% endstep %}
{% endstepper %}

***

### 🛠️ Troubleshooting

<details>

<summary>Dashboard not showing any data</summary>

* Ensure "Show MTF Dashboard" is enabled
* Check that you have enough historical data loaded
* Verify timeframe inputs are valid (e.g., "5", "15", "60", "D")

</details>

<details>

<summary>Some timeframes show "n/a"</summary>

* The timeframe may be invalid or not available
* Try standard timeframes: 1, 5, 15, 30, 60, 240, D, W
* Custom timeframes need specific format (e.g., "90" for 90 minutes)

</details>

<details>

<summary>Dashboard updates slowly</summary>

* This is normal - it updates with each new bar close
* Higher timeframes update less frequently
* Use lower timeframes for more responsive data

</details>

***

### Best Practices

1. Start with standard timeframe sets
2. Choose a dashboard style that suits your trading approach
3. Wait for 6+ timeframe alignment
4. Confirm with other dashboard features
5. Use alerts to catch alignment changes
6. Respect the overall AVG bias

***

Need help? Check our FAQ or contact support:

* FAQ: https://docs.infinityalgo.com/faq/faq-and-troubleshoot
* Contact support: https://infinityalgo.com/#contact

Last updated 2 months ago

This site uses cookies to deliver its service and to analyze traffic. By browsing this site, you accept the privacy policy: https://infinityalgo.com/privacy/
