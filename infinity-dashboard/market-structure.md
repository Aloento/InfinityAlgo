# 🧭 Market Structure

[Got ideas? Request a feature](https://infinityalgo.canny.io/?utm_source=docs\&utm_medium=banner)

Track Break of Structure (BOS) and Change of Character (CHoCH) to identify trend continuations and reversals using institutional price action concepts.

***

#### 🎯 What is Market Structure?

Market Structure analysis identifies when price breaks key swing points, signaling either trend continuation (BOS) or trend reversal (CHoCH). This institutional approach helps you stay on the right side of the market by tracking how price respects or violates previous highs and lows.

Key Concepts

* **BOS (Break of Structure)** — Trend continuation signal
* **CHoCH (Change of Character)** — Trend reversal signal
* **Swing Highs/Lows** — Key levels that define structure
* **Trend Direction** — Bullish or bearish market flow

Why It Works

Market structure shows the "footprints" of institutional order flow, revealing when smart money is accumulating or distributing. This gives you a roadmap of market intent.

Trading Edge: CHoCH signals are rarer but mark major trend transitions — these are your highest value signals.

![Market Structure Image](<../.gitbook/assets/image (92)>)

***

#### 📊 Understanding the Signals

BOS — Break of Structure\
CHoCH — Change of Character

What it means (BOS)

* Price breaks a key level in the direction of the current trend
* Confirms trend strength and continuation
* Shows institutional commitment to the direction

Visual appearance (BOS)

* **Solid line** from swing point to break
* Label showing **"BOS"**
* Color matches trend direction
* Darker shade (lower importance than CHoCH)

Trading implication (BOS)

* Add to existing positions or maintain trend bias

![BOS Image](<../.gitbook/assets/image (93)>)

What it means (CHoCH)

* Price breaks structure AGAINST the current trend
* Signals potential trend reversal
* More significant than BOS

Visual appearance (CHoCH)

* **Dashed line** from swing point to break
* Label showing **"CHoCH"**
* Brighter color (higher importance)
* More prominent than BOS

Trading implication (CHoCH)

* Consider closing counter-trend positions and preparing for reversal

![CHoCH Image](<../.gitbook/assets/image (94)>)

***

#### 📖 Signal Types & Trading Implications

| Signal            |          Line Style | Meaning               | Action                       |
| ----------------- | ------------------: | --------------------- | ---------------------------- |
| **Bullish BOS**   |         Solid green | Uptrend continuing    | Add to longs / Stay long     |
| **Bearish BOS**   |           Solid red | Downtrend continuing  | Add to shorts / Stay short   |
| **Bullish CHoCH** | Dashed bright green | Reversal to uptrend   | Exit shorts / Consider longs |
| **Bearish CHoCH** |   Dashed bright red | Reversal to downtrend | Exit longs / Consider shorts |

Pro Tip: CHoCH signals are rarer but more powerful — they mark major trend transitions where institutional bias shifts.

***

#### ⚙️ Configuration Settings

Basic Settings

| Setting                    | Options | Default | Description                 |
| -------------------------- | ------: | ------: | --------------------------- |
| 🧭 Enable Market Structure |  On/Off |     OFF | Toggle BOS/CHoCH detection  |
| 🎨 Color Bars by Structure |  On/Off |     OFF | Tint candles by trend       |
| 🔍 Sensitivity             |    5-50 |      15 | Swing detection sensitivity |

Sensitivity Guide

{% stepper %}
{% step %}
### Lower (5–15)

* More signals, faster reaction
* Catches minor swings
* More noise and false signals
* Best for: Scalping, fast timeframes
{% endstep %}

{% step %}
### Medium (15–25)

* Balanced signal frequency
* Standard swing detection
* Good signal-to-noise ratio
* Best for: Most trading styles
{% endstep %}

{% step %}
### Higher (25–50)

* Fewer signals, major swings only
* Very clean structure
* May miss smaller moves
* Best for: Higher timeframes, position trading
{% endstep %}
{% endstepper %}

***

#### 🎯 Trading Strategies

{% stepper %}
{% step %}
### Trend Following with BOS

Setup:

* Identify trend direction from first BOS
* Enter/add on each BOS in trend direction
* Exit on opposite CHoCH
* Re-enter on new trend BOS

Best for: Strong trending markets
{% endstep %}

{% step %}
### CHoCH Reversal Trading

Setup:

* Wait for CHoCH signal
* Confirm with order block or support/resistance
* Enter in new trend direction
* Stop below/above structure

Best for: Range extremes and major reversals
{% endstep %}

{% step %}
### Structure + Order Blocks

Setup:

* CHoCH occurs at order block
* Wait for retest of zone
* Enter on rejection
* Target next structure level

Best for: High-probability reversals
{% endstep %}
{% endstepper %}

***

#### 🎨 Bar Coloring

When "Color Bars by Market Structure" is enabled:

Trend Colors

* 🟢 Green tint — Bullish structure active
* 🔴 Red tint — Bearish structure active
* ⚪ Normal — No clear structure

Benefits

* Instant visual trend confirmation
* Reduces need to analyze swings
* Helps avoid counter-trend trades
* Clean chart appearance

![Bar Coloring Image](<../.gitbook/assets/image (95)>)

***

#### 🔔 Alert Configuration

| Alert Name        |                Triggers When | Use Case                 | Priority  |
| ----------------- | ---------------------------: | ------------------------ | --------- |
| **Bullish CHoCH** |   Bearish → Bullish reversal | Major long entry signal  | 🔥 HIGH   |
| **Bearish CHoCH** |   Bullish → Bearish reversal | Major short entry signal | 🔥 HIGH   |
| **Bullish BOS**   |   Uptrend continuation break | Add to longs             | 📊 MEDIUM |
| **Bearish BOS**   | Downtrend continuation break | Add to shorts            | 📊 MEDIUM |

Alert Priority: CHoCH alerts are more significant than BOS — consider larger position sizes or tighter monitoring when these trigger.

***

#### 💡 Pro Tips

Reading Market Flow

{% stepper %}
{% step %}
**Strong Trend**

* Multiple BOS in same direction
{% endstep %}

{% step %}
**Weakening Trend**

* BOS signals getting closer
{% endstep %}

{% step %}
**Reversal Warning**

* Failed BOS attempts
{% endstep %}

{% step %}
**Reversal Confirmed**

* CHoCH with volume
{% endstep %}
{% endstepper %}

Timeframe Coordination

* Higher TF CHoCH: Major trend change
* Lower TF BOS: Entry timing
* Aligned structures: Highest probability
* Conflicting structures: Stay out

Risk Management

| Component       | Guideline                                 |
| --------------- | ----------------------------------------- |
| Stop placement  | Beyond the structure that triggered entry |
| Target          | Next unbroken structure level             |
| Position sizing | Larger on CHoCH, smaller on BOS           |
| Risk per trade  | Lower on BOS, standard on CHoCH           |

***

#### ⚠️ Common Mistakes

{% stepper %}
{% step %}
Trading every BOS — Filter with trend and context
{% endstep %}

{% step %}
Ignoring CHoCH — These are major reversal signals
{% endstep %}

{% step %}
Wrong sensitivity — Adjust for your timeframe
{% endstep %}

{% step %}
Fighting the structure — Respect what market shows
{% endstep %}

{% step %}
Not waiting for close — Structure needs candle close confirmation
{% endstep %}
{% endstepper %}

***

#### 🛠️ Troubleshooting

No BOS/CHoCH signals appearing

* Enable "Market Structure (BOS/CHoCH)" in settings
* Check sensitivity (try default 15 first)
* Ensure enough price history is loaded
* Some ranging markets won't produce signals
* Verify the timeframe has enough volatility

Too many signals (noisy)

* Increase sensitivity value (try 20–30)
* Focus on higher timeframes (15m+)
* Use bar coloring to filter noise visually
* Consider disabling on very low timeframes (1–5m)

Signals appear late

* This is normal — structure needs swing confirmation
* Lower sensitivity for faster signals (accepts more false signals)
* Use for trend confirmation, not precise entry timing
* Combine with Order Blocks for better entries

Conflicting with other indicators

* Market structure is trend-based
* May conflict with mean-reversion indicators
* Trust structure for trend direction
* Use other indicators for entry precision

***

#### 📊 Combining with Other Features

Powerful Combinations

With Order Blocks

* CHoCH at order block = High-probability reversal
* BOS from order block = Continuation entry
* Structure break + fresh OB = Momentum trade
* Failed break at OB = Reversal setup

With MTF Dashboard

* Structure break + MTF alignment = Strong signal
* CHoCH + MTF flip = Major reversal
* BOS + 6+ TF aligned = High conviction
* Conflicting signals = Stay out

With Cloud Bands

* Structure break + Cloud breakout = Momentum trade
* CHoCH at cloud edge = Reversal setup
* BOS within cloud = Weak signal
* Structure + cloud alignment = Strong trend

***

#### 📚 Quick Reference

Signal Hierarchy

1. CHoCH — Most important (reversal)
2. BOS — Trend confirmation
3. Failed breaks — Warning signs

Visual Cues

* Line Styles:
  * Solid line = BOS (continuation)
  * Dashed line = CHoCH (reversal)
* Colors:
  * Bright = Higher importance
  * Muted = Lower importance
* Labels:
  * BOS = Break of Structure
  * CHoCH = Change of Character
* Bar Colors:
  * Green tint = Bullish trend
  * Red tint = Bearish trend

Best Practices Checklist

* Wait for candle close confirmation
* Prioritize CHoCH over BOS signals
* Combine with Order Blocks for entries
* Match sensitivity to your timeframe
* Trust the structure trend direction
* Use bar coloring for quick assessment
* Set alerts for CHoCH signals

***

<details>

<summary>Additional support</summary>

For additional support, visit our FAQ or contact support:

* FAQ: https://docs.infinityalgo.com/faq/faq-and-troubleshoot
* Contact: https://infinityalgo.com/#contact

</details>

Last updated 2 months ago

Was this helpful?
