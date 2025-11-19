# 📦 Order Blocks

Identify institutional supply and demand zones with volume analysis to find high-probability reversal and continuation areas.

***

🎯 What are Order Blocks?

Order Blocks represent areas where institutional traders likely placed large orders, creating zones of supply (resistance) and demand (support). These zones often act as magnets for price, providing excellent entry and exit opportunities.

* Buy Zones (Bullish OB) — Demand areas where buyers stepped in
* Sell Zones (Bearish OB) — Supply areas where sellers took control
* Volume Metrics — Buy/sell pressure within each zone

Why they work

Order blocks show where "smart money" entered positions, giving you institutional-level insight into market structure and potential reversal points.

Trading Edge: Fresh order blocks with high directional volume (>70%) provide the highest probability setups.

![Order Blocks image](<../.gitbook/assets/image (6)>)

***

📊 Understanding Order Block Components

Zone Structure

Each order block displays:

* Colored Box — The zone boundaries (Entry/exit area)
* Volume Bar — Buy (green) / Sell (red) split (Strength indicator)
* Text Label — Zone type and metrics (Quick reference)

Volume Metrics Display

![Volume metrics image](<../.gitbook/assets/image (7)>)

Example text label:

```
Buy Zone / Bullish OB
72.474K | B/S 60/40%
```

Reading the metrics:

* 72.474K — Total volume in the zone
* 60% Buy — Bullish pressure dominance
* 40% Sell — Minimal selling

Pro Tip: Zones with >70% directional volume are strongest. 50/50 splits indicate indecision — avoid these zones.

***

⚙️ Configuration Settings

Basic Settings

* Show Buy Sell Zones: On/Off — Default: ON — Enable/disable order blocks
* Show Only Nearest Boxes: On/Off — Default: ON — Display only closest zone to price
* Extend Boxes Indefinitely: On/Off — Default: OFF — Keep zones visible until broken
* Show Breaks: On/Off — Default: OFF — Mark when zones are broken
* Show Exit Markers: On/Off — Default: OFF — Display exit signals from zones
* Exit Trigger Mode: Close/Wick — Default: Wick — How exits are detected
* Show OB Details: On/Off — Default: ON — Display metrics, midline, volume bars

Advanced Settings

* Sensitivity — Zone detection sensitivity (1-100). Higher = fewer, larger zones
* OB Mitigation Method — When zone is "broken": Close = strict, Wick = sensitive, Mid = balanced
* Hide Overlap — Auto-hide overlapping zones (keeps chart clean)
* Fib Factor — Breakout confirmation (0-1). Higher = stricter bias changes
* Max OBs per Side — Maximum zones displayed (3-5 for clean charts, 10+ for analysis)
* OB Max History — Lookback period in bars (Lower for performance, higher for context)

***

📖 Types of Order Blocks

{% stepper %}
{% step %}
### Fresh Order Blocks

* Characteristics: Never been tested by price
* Probability: Highest for reaction
* Strategy: First test often produces best move
{% endstep %}

{% step %}
### Tested Order Blocks

* Characteristics: Price touched but didn't break
* Probability: Medium strength
* Strategy: Look for multiple confluences
{% endstep %}

{% step %}
### Broken Order Blocks

* Characteristics: Price closed through zone
* Probability: Often flips role
* Strategy: Old support becomes resistance (and vice versa)
{% endstep %}
{% endstepper %}

***

🎯 Trading Signals

Entry Signals

Zone Test Entry (Best for: Conservative traders, trending markets)

* Setup:
  1. Price approaches fresh order block
  2. Look for slowdown or rejection candles
  3. Enter at zone edge or midline
  4. Stop below/above zone

Break and Retest (Best for: Aggressive traders, reversal plays)

* Setup:
  1. Zone breaks (triangle marker appears)
  2. Price returns to test old zone
  3. Enter on rejection
  4. Stop beyond zone extreme

Midline Precision (Best for: Scalpers, precise entries)

* Setup:
  1. Wait for price to reach zone midline
  2. Look for reaction at this level
  3. Enter with tight stop
  4. Target opposite zone

Exit Signals

![Exit signal image](<../.gitbook/assets/image (8)>)

Exit Markers show when price leaves a zone:

* ⬆️ Green arrow = Exiting bullish zone upward (bullish continuation)
* ⬇️ Red arrow = Exiting bearish zone downward (bearish continuation)

Exit Trigger Modes:

* Close — Bar must close outside zone (conservative)
* Wick — Any price spike through zone (aggressive)

Break Signals

![Break signals image](<../.gitbook/assets/image (9)>)

Break Markers indicate when a zone is definitively broken:

* 🔻 Red triangle down = Bullish zone broken (bearish signal)
* 🔺 Green triangle up = Bearish zone broken (bullish signal)

Understanding Breaks:

* When Zones Break:
  * Price closes beyond zone boundary
  * Volume confirms the move
  * Zone loses its effectiveness
  * Often flips from support to resistance (or vice versa)
* Trading Breaks:
  * Immediate signal for trend continuation
  * Wait for retest for safer entry
  * Old support becomes new resistance (and vice versa)

Mitigation Methods (determines when a break occurs)

* Close — Bar closes beyond zone edge (Conservative)
* Wick — Any price spike through zone (Aggressive)
* Mid — Close crosses zone midline (Balanced approach)

Important: Once broken, zones often reverse roles — previous support becomes resistance and vice versa. Watch for retests of broken zones.

***

📊 Volume Analysis

Reading Buy/Sell Pressure

* Green portion = Buying volume percentage
* Red portion = Selling volume percentage
* Bar width = Proportional to zone width

Strength Interpretation

* 80/20 split — Very strong zone
* 70/30 split — Strong zone
* 60/40 split — Moderate strength
* 50/50 split — Neutral, avoid

Quick Rule: Trade zones with >70% directional volume for best results Avoid: 50/50 split zones show indecision

***

💡 Pro Strategies

Strategy 1: Zone-to-Zone Trading

* Trade from one order block to the opposite side:
  1. Enter at demand zone (bullish OB)
  2. Target supply zone (bearish OB)
  3. Reverse at supply
  4. Target demand zone
* Best when: Clear range-bound market with defined zones

Strategy 2: Confluence Stacking

* Strongest setups have multiple factors:
  * Order block + MTF alignment (6+ timeframes)
  * Order block + Cloud band edge
  * Order block + Market structure level (BOS/CHoCH)
  * Order block + Round numbers
* Best when: Looking for high-probability entries

Strategy 3: Volume Gradient Trading

* Focus on zones with extreme volume imbalances:
  * Enter zones with >80% directional volume
  * Avoid zones with <60% directional volume
  * Use midline for partial profits
  * Hold runners to opposite extreme zone
* Best when: Trending markets with clear momentum

***

🔔 Alert Configuration

Common alerts and triggers:

* Entered Bullish OB — Price enters buy zone (Potential long entry)
* Entered Bearish OB — Price enters sell zone (Potential short entry)
* Bullish OB Break Down — Buy zone broken (Zone invalidation/flip)
* Bearish OB Break Up — Sell zone broken (Zone invalidation/flip)
* Exit from Bullish OB — Leaving buy zone up (Potential long exit/continuation)
* Exit from Bearish OB — Leaving sell zone down (Potential short exit/continuation)

***

⚙️ Optimization Tips

Scalping / Day Trading / Swing Trading / Analysis Mode

Preset examples:

```
Show Only Nearest: ON
Extend Boxes: OFF
Exit Trigger Mode: Wick
Max OBs: 3 per side
Sensitivity: 10-15 (more zones)
OB Max History: 500 bars
Mitigation: Wick
```

```
Show Only Nearest: ON
Extend Boxes: OFF
Exit Trigger Mode: Close
Max OBs: 5 per side
Sensitivity: 15-20 (balanced)
OB Max History: 1000 bars
Mitigation: Close
```

```
Show Only Nearest: OFF
Extend Boxes: ON
Exit Trigger Mode: Close
Max OBs: 10 per side
Sensitivity: 20-30 (quality zones)
OB Max History: 2000 bars
Mitigation: Mid
```

```
Show Only Nearest: OFF
Extend Boxes: ON
Exit Trigger Mode: Close
Max OBs: 10+ per side
Show OB Details: ON
Show Breaks: ON
Show Exit Markers: ON
All visual features enabled
```

***

⚠️ Common Mistakes

Critical Errors to Avoid:

1. Trading every zone — Focus on fresh, high-volume zones only
2. Ignoring volume metrics — 50/50 zones are weak, avoid them
3. Not waiting for confirmation — Let price react to the zone first
4. Fighting broken zones — Respect when zones fail and flip
5. Using too many zones — Creates analysis paralysis, keep it clean
6. Wrong Exit Trigger Mode — Match to your trading style

***

🛠️ Troubleshooting

<details>

<summary>No order blocks showing</summary>

* Check "Show Buy Sell Zones" is enabled
* Increase "OB Max History" setting (try 1000+)
* Ensure you have enough chart history loaded
* Try adjusting sensitivity (lower = more zones)
* Check if price has been trending without pullbacks

</details>

<details>

<summary>Too many overlapping boxes</summary>

* Enable "Show Only Nearest Boxes"
* Enable "Hide Overlap" option (if available)
* Reduce "Max OBs per Side" to 3-5
* Increase sensitivity for fewer, larger zones

</details>

<details>

<summary>Volume metrics showing "n/a"</summary>

* Need more historical data loaded
* Increase "OB Max History" to 1000+
* Some instruments may lack volume data
* Check if volume is available for your symbol

</details>

<details>

<summary>Zones disappearing unexpectedly</summary>

* This is normal when zones are "mitigated" (broken)
* Check your "OB Mitigation Method" setting
* Broken zones are removed to keep chart clean
* Consider enabling "Extend Boxes" to keep them visible

</details>

<details>

<summary>Exit markers not showing</summary>

* Enable "Show Exit Markers" in settings
* Check "Exit Trigger Mode" (Wick vs Close)
* Ensure price actually exited the zone
* May need to wait for bar close (if using Close mode)

</details>

***

📚 Quick Reference

Visual Elements

* Green zones = Demand/Support (Bullish OB)
* Red zones = Supply/Resistance (Bearish OB)
* Dashed midline = Zone center/target
* Split bars = Volume distribution

Markers

* Triangle up = Bearish zone broken (bullish)
* Triangle down = Bullish zone broken (bearish)
* Arrow up = Exiting zone upward
* Arrow down = Exiting zone downward

Best Practices Checklist

* Focus on fresh, untested zones
* Confirm with volume metrics (>70% directional)
* Use midlines for precise targets
* Combine with MTF dashboard alignment
* Respect broken zones as role reversals
* Match Exit Trigger Mode to your style
* Keep chart clean with nearest zones only

***

🔗 Related & Support

For additional support, visit our FAQ or contact support:

* FAQ: https://docs.infinityalgo.com/faq/faq-and-troubleshoot
* Contact support: https://infinityalgo.com/#contact

Last updated 2 months ago

Was this helpful?
