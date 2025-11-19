# 📦 Order Blocks

Identify institutional supply and demand zones with volume analysis to find high-probability reversal and continuation areas.

---

### 🎯 What are Order Blocks?

Order Blocks represent areas where institutional traders likely placed large orders, creating zones of supply (resistance) and demand (support). These zones often act as magnets for price, providing excellent entry and exit opportunities.

{% columns %}
{% column width="50%" %}

#### Key Components

- 🟢 **Buy Zones (Bullish OB)** - Demand areas where buyers stepped in
- 🔴 **Sell Zones (Bearish OB)** - Supply areas where sellers took control
- 📊 **Volume Metrics** - Buy/sell pressure within each zone
  {% endcolumn %}

{% column %}

#### Why They Work

Order blocks show where "smart money" entered positions, giving you institutional-level insight into market structure and potential reversal points.
{% endcolumn %}
{% endcolumns %}

{% hint style="info" %}
**Trading Edge:** Fresh order blocks with high directional volume (>70%) provide the highest probability setups.
{% endhint %}

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FqWinTDlo8kKvx1JL7Xj5%2Fimage.png?alt=media&#x26;token=6e1067a5-86cf-4672-871a-9a16ad43efba" alt=""><figcaption></figcaption></figure>

---

### 📊 Understanding Order Block Components

#### Zone Structure

Each order block displays:

| Component       | Description                    | Trading Use        |
| --------------- | ------------------------------ | ------------------ |
| **Colored Box** | The zone boundaries            | Entry/exit area    |
| **Volume Bar**  | Buy (green) / Sell (red) split | Strength indicator |
| **Text Label**  | Zone type and metrics          | Quick reference    |

#### Volume Metrics Display

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2Fh1izCFW1EGBddiL18gMq%2Fimage.png?alt=media&#x26;token=5dc58c40-d818-487b-91e2-7a51a13f6866" alt=""><figcaption></figcaption></figure>

{% code overflow="wrap" %}

```
Buy Zone / Bullish OB
72.474K | B/S 60/40%
```

{% endcode %}

**Reading the metrics:**

- **72.474K** - Total volume in the zone
- **60% Buy** - Bullish pressure dominance
- **40% Sell** - Minimal selling

{% hint style="success" %}
**Pro Tip:** Zones with >70% directional volume are strongest. 50/50 splits indicate indecision - avoid these zones.
{% endhint %}

---

### ⚙️ Configuration Settings

#### Basic Settings

| Setting                          | Options    | Default | Description                           |
| -------------------------------- | ---------- | ------- | ------------------------------------- |
| **📦 Show Buy Sell Zones**       | On/Off     | ON      | Enable/disable order blocks           |
| **🔍 Show Only Nearest Boxes**   | On/Off     | ON      | Display only closest zone to price    |
| **📏 Extend Boxes Indefinitely** | On/Off     | OFF     | Keep zones visible until broken       |
| **💥 Show Breaks**               | On/Off     | OFF     | Mark when zones are broken            |
| **🏁 Show Exit Markers**         | On/Off     | OFF     | Display exit signals from zones       |
| **📤 Exit Trigger Mode**         | Close/Wick | Wick    | How exits are detected                |
| **📊 Show OB Details**           | On/Off     | ON      | Display metrics, midline, volume bars |

#### Advanced Settings

| Setting                     | Description                        | Impact                                           |
| --------------------------- | ---------------------------------- | ------------------------------------------------ |
| **🔍 Sensitivity**          | Zone detection sensitivity (1-100) | Higher = fewer, larger zones                     |
| **🧱 OB Mitigation Method** | When zone is "broken"              | Close = strict, Wick = sensitive, Mid = balanced |
| **🧩 Hide Overlap**         | Auto-hide overlapping zones        | Keeps chart clean                                |
| **📐 Fib Factor**           | Breakout confirmation (0-1)        | Higher = stricter bias changes                   |
| **🔢 Max OBs per Side**     | Maximum zones displayed            | 3-5 for clean charts, 10+ for analysis           |
| **📜 OB Max History**       | Lookback period in bars            | Lower for performance, higher for context        |

---

### 📖 Types of Order Blocks

{% stepper %}
{% step %}

#### Fresh Order Blocks

- **Characteristics:** Never been tested by price
- **Probability:** Highest for reaction
- **Strategy:** First test often produces best move
  {% endstep %}

{% step %}

#### Tested Order Blocks

- **Characteristics:** Price touched but didn't break
- **Probability:** Medium strength
- **Strategy:** Look for multiple confluences
  {% endstep %}

{% step %}

#### Broken Order Blocks

- **Characteristics:** Price closed through zone
- **Probability:** Often flips role
- **Strategy:** Old support becomes resistance (and vice versa)
  {% endstep %}
  {% endstepper %}

---

### 🎯 Trading Signals

#### Entry Signals

{% tabs %}
{% tab title="Zone Test Entry" %}
**Setup:**

1. Price approaches fresh order block
2. Look for slowdown or rejection candles
3. Enter at zone edge or midline
4. Stop below/above zone

**Best for:** Conservative traders, trending markets
{% endtab %}

{% tab title="Break and Retest" %}
**Setup:**

1. Zone breaks (triangle marker appears)
2. Price returns to test old zone
3. Enter on rejection
4. Stop beyond zone extreme

**Best for:** Aggressive traders, reversal plays
{% endtab %}

{% tab title="Midline Precision" %}
**Setup:**

1. Wait for price to reach zone midline
2. Look for reaction at this level
3. Enter with tight stop
4. Target opposite zone

**Best for:** Scalpers, precise entries
{% endtab %}
{% endtabs %}

#### Exit Signals

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FjCA67ZY8Wh8pyt6FWWC3%2Fimage.png?alt=media&#x26;token=1d85db68-9204-43a5-9b20-ccfc3e578350" alt=""><figcaption><p>Exit signal showing price leaving a bullish order block with upward momentum</p></figcaption></figure>

**Exit Markers** show when price leaves a zone:

- ⬆️ **Green arrow** = Exiting bullish zone upward (bullish continuation)
- ⬇️ **Red arrow** = Exiting bearish zone downward (bearish continuation)

**Exit Trigger Modes:**

- **Close** - Bar must close outside zone (conservative)
- **Wick** - Any price spike through zone (aggressive)

**Break Signals**

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2F1kpbqzKrFD0jrwA6mNzm%2F2025-09-12_07-55-30.jpg?alt=media&#x26;token=279ae1ff-696d-4830-9d79-c68858392b08" alt="" width="357"><figcaption><p>Break signals mark zone invalidation and potential role reversal</p></figcaption></figure>

**Break Markers** indicate when a zone is definitively broken:

- 🔻 **Red triangle down** = Bullish zone broken (bearish signal)
- 🔺 **Green triangle up** = Bearish zone broken (bullish signal)

**Understanding Breaks:**

{% columns %}
{% column width="50%" %}
**When Zones Break:**

- Price closes beyond zone boundary
- Volume confirms the move
- Zone loses its effectiveness
- Often flips from support to resistance (or vice versa)
  {% endcolumn %}

{% column %}
**Trading Breaks:**

- Immediate signal for trend continuation
- Wait for retest for safer entry
- Old support becomes new resistance
- Old resistance becomes new support
  {% endcolumn %}
  {% endcolumns %}

**Mitigation Methods** (determines when a break occurs):

| Method    | Trigger Condition            | Best For          |
| --------- | ---------------------------- | ----------------- |
| **Close** | Bar closes beyond zone edge  | Conservative      |
| **Wick**  | Any price spike through zone | Aggressive        |
| **Mid**   | Close crosses zone midline   | Balanced approach |

{% hint style="warning" %}
**Important:** Once broken, zones often reverse roles - previous support becomes resistance and vice versa. Watch for retests of broken zones.
{% endhint %}

---

---

### 📊 Volume Analysis

#### Reading Buy/Sell Pressure

{% columns %}
{% column width="60%" %}
The colored bars within zones show:

- **Green portion** = Buying volume percentage
- **Red portion** = Selling volume percentage
- **Bar width** = Proportional to zone width

**Strength Interpretation:**

- **80/20 split** = Very strong zone
- **70/30 split** = Strong zone
- **60/40 split** = Moderate strength
- **50/50 split** = Neutral, avoid
  {% endcolumn %}

{% column %}
{% hint style="success" %}
**Quick Rule:** Trade zones with >70% directional volume for best results
{% endhint %}

{% hint style="warning" %}
**Avoid:** 50/50 split zones show indecision
{% endhint %}
{% endcolumn %}
{% endcolumns %}

---

### 💡 Pro Strategies

#### Strategy 1: Zone-to-Zone Trading

Trade from one order block to the opposite side:

1. Enter at demand zone (bullish OB)
2. Target supply zone (bearish OB)
3. Reverse at supply
4. Target demand zone

**Best when:** Clear range-bound market with defined zones

#### Strategy 2: Confluence Stacking

Strongest setups have multiple factors:

- Order block + MTF alignment (6+ timeframes)
- Order block + Cloud band edge
- Order block + Market structure level (BOS/CHoCH)
- Order block + Round numbers

**Best when:** Looking for high-probability entries

#### Strategy 3: Volume Gradient Trading

Focus on zones with extreme volume imbalances:

- Enter zones with >80% directional volume
- Avoid zones with <60% directional volume
- Use midline for partial profits
- Hold runners to opposite extreme zone

**Best when:** Trending markets with clear momentum

---

### 🔔 Alert Configuration

| Alert Name                | Triggers When          | Use Case               |
| ------------------------- | ---------------------- | ---------------------- |
| **Entered Bullish OB**    | Price enters buy zone  | Potential long entry   |
| **Entered Bearish OB**    | Price enters sell zone | Potential short entry  |
| **Bullish OB Break Down** | Buy zone broken        | Zone invalidation/flip |
| **Bearish OB Break Up**   | Sell zone broken       | Zone invalidation/flip |
| **Exit from Bullish OB**  | Leaving buy zone up    | Potential long entry   |
| **Exit from Bearish OB**  | Leaving sell zone down | Potential long entry   |

---

### ⚙️ Optimization Tips

{% tabs %}
{% tab title="⚡ Scalping" %}

```
Show Only Nearest: ON
Extend Boxes: OFF
Exit Trigger Mode: Wick
Max OBs: 3 per side
Sensitivity: 10-15 (more zones)
OB Max History: 500 bars
Mitigation: Wick
```

{% endtab %}

{% tab title="📊 Day Trading" %}

```
Show Only Nearest: ON
Extend Boxes: OFF
Exit Trigger Mode: Close
Max OBs: 5 per side
Sensitivity: 15-20 (balanced)
OB Max History: 1000 bars
Mitigation: Close
```

{% endtab %}

{% tab title="🏔️ Swing Trading" %}

```
Show Only Nearest: OFF
Extend Boxes: ON
Exit Trigger Mode: Close
Max OBs: 10 per side
Sensitivity: 20-30 (quality zones)
OB Max History: 2000 bars
Mitigation: Mid
```

{% endtab %}

{% tab title="📈 Analysis Mode" %}

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

{% endtab %}
{% endtabs %}

---

### ⚠️ Common Mistakes

{% hint style="danger" %}
**Critical Errors to Avoid:**

1. **Trading every zone** - Focus on fresh, high-volume zones only
2. **Ignoring volume metrics** - 50/50 zones are weak, avoid them
3. **Not waiting for confirmation** - Let price react to the zone first
4. **Fighting broken zones** - Respect when zones fail and flip
5. **Using too many zones** - Creates analysis paralysis, keep it clean
6. **Wrong Exit Trigger Mode** - Match to your trading style
   {% endhint %}

---

### 🛠️ Troubleshooting

<details>

<summary><strong>No order blocks showing</strong></summary>

- Check "Show Buy Sell Zones" is enabled
- Increase "OB Max History" setting (try 1000+)
- Ensure you have enough chart history loaded
- Try adjusting sensitivity (lower = more zones)
- Check if price has been trending without pullbacks

</details>

<details>

<summary><strong>Too many overlapping boxes</strong></summary>

- Enable "Show Only Nearest Boxes"
- Enable "Hide Overlap" option (if available)
- Reduce "Max OBs per Side" to 3-5
- Increase sensitivity for fewer, larger zones

</details>

<details>

<summary><strong>Volume metrics showing "n/a"</strong></summary>

- Need more historical data loaded
- Increase "OB Max History" to 1000+
- Some instruments may lack volume data
- Check if volume is available for your symbol

</details>

<details>

<summary><strong>Zones disappearing unexpectedly</strong></summary>

- This is normal when zones are "mitigated" (broken)
- Check your "OB Mitigation Method" setting
- Broken zones are removed to keep chart clean
- Consider enabling "Extend Boxes" to keep them visible

</details>

<details>

<summary><strong>Exit markers not showing</strong></summary>

- Enable "Show Exit Markers" in settings
- Check "Exit Trigger Mode" (Wick vs Close)
- Ensure price actually exited the zone
- May need to wait for bar close (if using Close mode)

</details>

---

### 📚 Quick Reference

#### Visual Elements

{% columns %}
{% column width="50%" %}
**Zone Colors:**

- 🟢 **Green zones** = Demand/Support (Bullish OB)
- 🔴 **Red zones** = Supply/Resistance (Bearish OB)
- ➖ **Dashed midline** = Zone center/target
- 📊 **Split bars** = Volume distribution
  {% endcolumn %}

{% column %}
**Markers:**

- 🔺 **Triangle up** = Bearish zone broken (bullish)
- 🔻 **Triangle down** = Bullish zone broken (bearish)
- ⬆️ **Arrow up** = Exiting zone upward
- ⬇️ **Arrow down** = Exiting zone downward
  {% endcolumn %}
  {% endcolumns %}

#### Best Practices Checklist

- [ ] Focus on fresh, untested zones
- [ ] Confirm with volume metrics (>70% directional)
- [ ] Use midlines for precise targets
- [ ] Combine with MTF dashboard alignment
- [ ] Respect broken zones as role reversals
- [ ] Match Exit Trigger Mode to your style
- [ ] Keep chart clean with nearest zones only

---

### 🔗 Related Features

---

_For additional support, visit our_[_FAQ_](https://infinity.aloen.to/faq/faq-and-troubleshoot) _or_ [_contact support_](https://infinityalgo.com/#contact)_._
