# ⚙️ Example of settings

Master every setting in Infinity Algo V3.0 Backtest. This guide covers all configuration options with practical examples for different trading styles.

{% hint style="info" %}
**Prerequisites:** Already ran your first backtest? If not, start with the Backtesting Overview first.
{% endhint %}

---

### 🎯 Configuration Philosophy

#### Two Approaches

{% tabs %}
{% tab title="🤖 AI-Optimized" %}

#### Let AI Handle It

**How it works:**

1. Enable AI Optimization
2. Select performance metric
3. AI adjusts sensitivity/thresholds
4. You control exits and risk

**Best for:**

- Most traders
- Market adaptation
- Consistent results

{% code title="ai-setup:" %}

```
AI Optimization: ON
Performance Metric: Total Profit
Signal Mode: AI
Sensitivity Range: Balanced
Update Frequency: 1000 bars
```

{% endcode %}

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FGBUMw9YAKG8RANQxwEEq%2Fimage.png?alt=media&#x26;token=f069b73f-c104-4f59-af54-056a9af3b859" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="🎯 Manual Control" %}

#### Direct Configuration

**When to use:**

- Testing specific ideas
- Learning parameter impact
- Personal preference
- Predictable behavior

**You control everything:**

- Sensitivity (5-28)
- Thresholds (60-80/20-40)
- All exit parameters
  {% endtab %}
  {% endtabs %}

---

### 📊 Exit Strategies Explained

#### Choose Your Exit Style

{% tabs %}
{% tab title="Percentage Exit" %}

#### Fixed Targets & Stops

**How it works:**

- Exit at predetermined %
- Up to 6 take profit levels
- Partial position exits
- Fixed stop loss

**Perfect for:**

- ✅ Beginners
- ✅ Scalping
- ✅ Consistent results
- ✅ Risk management

{% code title="percentage-config.txt" %}

```
Exit Type: Percentage
TP1: 1% (exit 50%)
TP2: 2% (exit 30%)
TP3: 3% (exit 20%)
Stop Loss: 2%
```

{% endcode %}

#### Configuration Examples

| Style           | TP1  | TP2 | TP3 | Stop Loss |
| --------------- | ---- | --- | --- | --------- |
| **Scalping**    | 0.5% | 1%  | -   | 0.5%      |
| **Day Trading** | 1%   | 2%  | 3%  | 1.5%      |
| **Swing**       | 3%   | 5%  | 8%  | 3%        |
| {% endtab %}    |      |     |     |           |

{% tab title="Signals Exit" %}

#### Dynamic Market-Based

**How it works:**

- Exit on technical signals
- Adapts to momentum
- Captures full moves
- No fixed targets

{% code title="signals-config.txt" %}

```
Exit Type: Signals
Use TP Signals: ON
Min Profit Before Exit: 0.5%
Adapt to Volatility: ON
```

{% endcode %}

**Best for:**

- ✅ Trending markets
- ✅ Experienced traders
- ✅ Larger moves
- ⚠️ Higher variance
  {% endtab %}

{% tab title="Opposite Signal" %}

#### Maximum Trend Capture

**How it works:**

- Hold until reversal signal
- No profit targets
- No stop loss
- Pure trend following

**Example:**

- Long exits on Sell signal
- Short exits on Buy signal

{% hint style="warning" %}
**Advanced only:** Requires strong psychology and risk management
{% endhint %}
{% endtab %}
{% endtabs %}

---

### 💰 Position Management

#### Pyramiding (Scaling In)

{% columns %}
{% column width="50%" %}
**What is it?** Adding to winning positions

**Settings:**

- `More Entries`: Enable/Disable
- `Pyramiding`: 1-10 additions
- Size per addition
  {% endcolumn %}

{% column %}
{% code title="pyramid-setup:" %}

```
Pyramiding: 2
Entry 1: 33% capital
Entry 2: 33% at +1%
Entry 3: 34% at +2%
Max Risk: 2% total
```

{% endcode %}
{% endcolumn %}
{% endcolumns %}

#### Risk Levels

| Experience       | Pyramiding | Risk Per Trade | Position Size |
| ---------------- | ---------- | -------------- | ------------- |
| **Beginner**     | 0          | 1%             | 100% entry    |
| **Intermediate** | 1          | 1.5%           | 50% + 50%     |
| **Advanced**     | 2-3        | 2%             | 33% each      |
| **Expert**       | 3+         | 2%             | Custom        |

---

### 🎨 Configuration by Trading Style

#### Quick Reference Templates

{% tabs %}
{% tab title="⚡ Scalping" %}
{% code title="scalping-config.txt" %}

```
Timeframe: 1-5 min
Sensitivity: 5-9
Thresholds: 75/25
Exit Type: Percentage
TP1: 0.5% (100%)
Stop Loss: 0.5%
Pyramiding: 0
```

{% endcode %}
{% endtab %}

{% tab title="📊 Day Trading" %}
{% code title="daytrading-config:" %}

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

{% endcode %}
{% endtab %}

{% tab title="📈 Swing Trading" %}
{% code title="swing-config:" %}

```
Timeframe: 4H-Daily
Sensitivity: 15-21
Thresholds: 70/30
Exit Type: Signals
Min Profit: 1%
Stop Loss: 3-5%
Pyramiding: 1-2
```

{% endcode %}
{% endtab %}

{% tab title="📅 Position Trading" %}
{% code title="position-config:" %}

```
Timeframe: Daily-Weekly
Sensitivity: 22-28
Thresholds: 65/35
Exit Type: Opposite Signal
Stop Loss: Optional (5-10%)
Pyramiding: 2-3
```

{% endcode %}
{% endtab %}
{% endtabs %}

---

### 🧪 Testing Your Configuration

#### Systematic Approach

{% stepper %}
{% step %}

#### Document Settings

Write down every parameter before testing
{% endstep %}

{% step %}

#### Run Baseline

Test on last 6 months first
{% endstep %}

{% step %}

#### Stress Test

Test worst market periods:

- March 2020
- May 2021
- 2022 bear market
  {% endstep %}

{% step %}

#### Compare Results

Look for consistency across periods
{% endstep %}

{% step %}

#### Refine One Variable

Change only one setting at a time
{% endstep %}
{% endstepper %}

---

### 📈 Performance Targets by Style

| Trading Style   | Min Profit Factor | Max Drawdown | Win Rate | Avg RRR |
| --------------- | ----------------- | ------------ | -------- | ------- |
| **Scalping**    | 1.3               | 10%          | 60%+     | 1:1     |
| **Day Trading** | 1.5               | 15%          | 50%+     | 1.5:1   |
| **Swing**       | 2.0               | 20%          | 40%+     | 2:1     |
| **Position**    | 2.5               | 25%          | 35%+     | 3:1     |

---

### ❓ Configuration FAQ

<details>

<summary><strong>Which exit type is best for beginners?</strong></summary>

Start with **Percentage Exit**:

- Predictable results
- Easy to understand
- Better risk control
- Consistent outcomes

Move to Signals/Opposite after 50+ trades experience.

</details>

<details>

<summary><strong>Should I use pyramiding?</strong></summary>

**Progressive approach:**

1. First 30 trades: No pyramiding
2. After profitable: Add 1 level
3. After 100 trades: Consider 2
4. Expert only: 3+

Always keep total risk under 2%.

</details>

<details>

<summary><strong>How do I know if settings are over-optimized?</strong></summary>

**Warning signs:**

- Small changes = big result differences
- Amazing backtest, poor live results
- Only works on one symbol
- Requires perfect conditions

**Solution:** Test on multiple timeframes and symbols.

</details>

---

{% hint style="success" %}
**Next Step:** Configure your settings based on your trading style, then test thoroughly. Remember: consistency beats perfection.
{% endhint %}
