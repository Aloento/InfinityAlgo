# 🎯 Entry, Take Profit and Stop Loss

[Got ideas?\
Request a feature](https://infinityalgo.canny.io/?utm_source=docs\&utm_medium=banner)

![](<../.gitbook/assets/image (27)>)

### Settings Panel

**📊 Settings Overview**

* 📍 Entry Price
* 💰 Take Profit
* 🛑 Stop Loss
* 🔄 Trailing Stop Loss

### Entry Level Display

![](<../.gitbook/assets/image (28)>)

Purpose: Shows your position entry with dotted line

Enabled

![](<../.gitbook/assets/image (29)>)

### TP Levels Configuration

![](<../.gitbook/assets/image (30)>)

Important: TP levels only work with "Percentage" exit type

Setup Process:

{% stepper %}
{% step %}
### Enable TP Levels

Toggle ON the TP levels you want.
{% endstep %}

{% step %}
### Set Percentage

Define profit % for each level.
{% endstep %}

{% step %}
### Assign Position %

Set how much to exit at each TP.
{% endstep %}

{% step %}
### Verify Total = 100%

Sum of all exit % must equal 100.
{% endstep %}
{% endstepper %}

Configuration Examples:

Single TP

{% code title="Single TP" %}
```
Single TP:
TP1: 2% profit, exit 100%
```
{% endcode %}

Multiple TPs

{% code title="Multiple TPs" %}
```
Multiple TPs:
TP1: 1% profit, exit 50%
TP2: 2% profit, exit 30%
TP3: 3% profit, exit 20%
Total: 100% ✅
```
{% endcode %}

Visual Display: Enable "Show TP Prices" for dotted lines on chart

![](<../.gitbook/assets/image (31)>)

Line visualization with all 6 TPs enabled

### Stop Loss Setup

Configure separately for Long and Short positions

![](<../.gitbook/assets/image (32)>)

SL Settings

Long Position SL

* Set % below entry for longs
* Example: 2% = Exit if -2%

Short Position SL

* Set % above entry for shorts
* Example: 2% = Exit if -2%

Visual Display: Enable "Show SL Price" for dotted line on chart

![](<../.gitbook/assets/image (33)>)

Line visualization SL enabled

### Advanced SL Management

Three Trailing Modes Available:

![](<../.gitbook/assets/image (34)>)

Mode — Description — How It Works

* None — Static stop loss — SL stays at initial level
* Breakeven — Move to entry — SL moves to entry price after trigger
* Moving Target — Follow TP levels — SL trails up to previous TP levels

Setup Process:

{% stepper %}
{% step %}
### Select Trailing Mode

Choose from None, Breakeven, or Moving Target.
{% endstep %}

{% step %}
### Set Trigger Point

Select which TP triggers the trailing (TP1–TP6).
{% endstep %}

{% step %}
### Monitor Status

Chart shows (BE) or (TP1), (TP2), etc. next to SL.
{% endstep %}
{% endstepper %}

Example Configurations:

Breakeven Mode

{% code title="Breakeven Mode" %}
```
Breakeven Mode:
- Mode: Breakeven
- Trigger: After TP1
- Result: SL moves to entry when TP1 hits
- Display: "Stop loss (BE)"
```
{% endcode %}

Moving Target Mode

{% code title="Moving Target Mode" %}
```
Moving Target Mode:
- Mode: Moving Target
- Trigger: After TP2
- Result:
  * After TP2: SL → Entry
  * After TP3: SL → TP1
  * After TP4: SL → TP2
- Display: "Stop loss (TP1)", etc.
```
{% endcode %}

Pro Tip: Moving Target mode locks in profits progressively as each TP level is reached

### Visual Indicators

SL Status — Label Display — Meaning

* Normal — "Stop loss: \[price]" — Static SL active
* Breakeven — "Stop loss (BE): \[price]" — SL moved to entry
* Trailing TP1 — "Stop loss (TP1): \[price]" — SL at TP1 level
* Trailing TP2 — "Stop loss (TP2): \[price]" — SL at TP2 level

Entry Line Behavior: When SL is at breakeven, the entry line dims to avoid visual overlap

### Visual Display & Behavior

What shows on chart:

Entry

* Display: Dotted line (`···········`)
* When visible: When enabled
* Special notes: Dims when SL at BE

TP Levels

* Display: Dotted line (`···········`)
* When visible: Percentage mode only
* Special notes: Replaced by dots when hit

Stop Loss

* Display: Dotted line (`···········`)
* When visible: When enabled
* Special notes: Shows trailing status

Dynamic Display:

* TP lines disappear and become dot markers when hit
* SL label updates to show current mode (BE, TP1, TP2, etc.)
* Entry line dims when SL is at breakeven to reduce clutter

Chart Examples:

Active TP Lines\
![Before TP Hit](<../.gitbook/assets/image (35)>)\
Lines show pending TP levels

TP Hit Markers\
![After TP Hit](<../.gitbook/assets/image (36)>)\
Dots mark executed TPs

### Visual Indicators Guide

TP Level Status

* 📊 Pending TP — Dotted line — Ready to trigger (label shows target)
* ✅ TP Hit — Dot marker (●) — Level executed (line disappears)
* 🔄 Position Closed — Dots remain — Trade complete (all lines cleared)

SL Trailing Status

* 📍 Static — "Stop loss: \[price]" — Fixed SL position (initial state)
* 🟢 Breakeven — "Stop loss (BE): \[price]" — Moved to entry (risk-free trade)
* 📈 Trailing — "Stop loss (TP#): \[price]" — Following TP levels (profits locked)

### Quick Setup Templates

Conservative (Single TP + Breakeven)

{% code title="Conservative" %}
```
TP1: 2% profit, exit 100%
SL: 1% loss
Trailing: Breakeven after TP1
Risk/Reward: 2:1 → Risk-free after TP
```
{% endcode %}

Scaled Exit (Multiple TP + Moving Target)

{% code title="Scaled Exit" %}
```
TP1: 1% profit, exit 50%
TP2: 2% profit, exit 30%
TP3: 3% profit, exit 20%
SL: 2% loss
Trailing: Moving Target after TP1
Result: Progressive profit locking
```
{% endcode %}

Aggressive (Wide Targets + Late Trailing)

{% code title="Aggressive" %}
```
TP1: 3% profit, exit 40%
TP2: 5% profit, exit 30%
TP3: 8% profit, exit 30%
SL: 3% loss
Trailing: Moving Target after TP2
Result: Maximum profit potential
```
{% endcode %}

### Pro Tips

Best Practices:

* Always verify TP percentages = 100%
* Use Breakeven mode for conservative trading
* Use Moving Target to lock in progressive profits
* Set trailing trigger based on your confidence level
* Monitor the SL label for current protection status

Trailing Tips:

* Breakeven after TP1 = Quick risk elimination
* Moving Target after TP2 = Balance between profit and protection
* No trailing = Maximum profit potential but constant risk

Remember:

* TP lines only show in "Percentage" exit mode
* Trailing SL requires at least one TP to be enabled
* Moving Target mode requires multiple TPs for best results

Last updated 2 months ago

This site uses cookies to deliver its service and to analyze traffic. By browsing this site, you accept the [privacy policy](https://infinityalgo.com/privacy/).
