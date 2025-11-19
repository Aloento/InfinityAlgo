# 🧠 AI Optimization

Transform Infinity Algo into a self-improving system that adapts to markets automatically.

{% hint style="success" %}
**Quick Start:** Enable AI → Select mode (Static/Walk-Forward) → Choose metric → Let AI optimize
{% endhint %}

---

#### 🚀 Quick Setup

{% stepper %}
{% step %}
**Enable AI**

Turn ON `🧠 Enable AI Optimization` in settings
{% endstep %}

{% step %}
**Choose Mode**

- **Backtesting?** → `Static (Full History)`
- **Live Trading?** → `Walk-Forward`
  {% endstep %}

{% step %}
**Select Signal Type**

Choose `AI` or `AI Sniper` in Signal Mode
{% endstep %}
{% endstepper %}

**That's it!** Default settings work for most users.

---

#### 🎯 How AI Works

| 1️⃣ **Simulate**                            | 2️⃣ **Evaluate**               | 3️⃣ **Apply**                  |
| ------------------------------------------ | ----------------------------- | ----------------------------- |
| Tests 100s-1000s of parameter combinations | Scores each using your metric | Implements best configuration |

**Walk-Forward:** Periodically re-optimizes on a rolling in-sample window and validates out-of-sample, reducing overfitting.

---

#### ⚙️ Core Settings

{% tabs %}
{% tab title="🧠 AI Modes" %}
**Optimization Modes**

| Mode             | How It Works          | Use For      |
| ---------------- | --------------------- | ------------ |
| **Walk-Forward** | Updates every N bars  | Live trading |
| **Static**       | Optimizes once, locks | Backtesting  |

{% hint style="info" %}
**Tip:** Start with Static for testing, switch to Walk-Forward for live
{% endhint %}
{% endtab %}

{% tab title="🔄 Update Frequency" %}
**Walk-Forward Only**

{% code title="frequency-guide.txt" %}

```
100 bars (default) → Ultra-responsive (high CPU)
200-1000 bars     → Balanced ✅
1000-5000 bars    → Very stable, slower to adapt

Examples on 1h chart:
- 100 bars = ~4 days
- 1000 bars = ~42 days
- 5000 bars = ~208 days
```

{% endcode %}

Lower = More responsive but intensive | Higher = More stable and efficient
{% endtab %}

{% tab title="🧪 Sensitivity Range" %}
**Parameter Space**

| Range           | Values | Best For         |
| --------------- | ------ | ---------------- |
| **Very Fast**   | 5-9    | Scalping         |
| **Fast**        | 10-14  | Day Trading      |
| **Balanced** ✅ | 10-20  | Most Strategies  |
| **Medium**      | 15-21  | Swing Trading    |
| **Slow**        | 22-28  | Position Trading |
| **Auto**        | 5-28   | Full exploration |
| {% endtab %}    |        |                  |

{% tab title="📊 Optimization Metric" %}
**Choose Your Goal**

**Quick Selection:**

| Your Style      | Use This Metric | Why                 |
| --------------- | --------------- | ------------------- |
| **Scalping**    | Win Rate        | Consistency matters |
| **Day Trading** | Sharpe Ratio    | Balance risk/return |
| **Swing**       | Sortino Ratio   | Downside protection |
| **Position**    | Calmar Ratio    | Avoid drawdowns     |

**All Available Metrics:**

- **Classic:** Total Profit, Win Rate, Average P\&L, Gain-to-Pain
- **Risk-Adjusted:** Sharpe, Sortino, Calmar, Martin
- **Advanced:** SQN (System Quality Number), Robust ML Score

{% hint style="warning" %}
**Important:** High win rate ≠ profitability. A 90% win rate with large losses can be unprofitable.
{% endhint %}

{% hint style="info" %}
Not sure? Use **Total Profit** for testing, **Sharpe Ratio** for live trading
{% endhint %}
{% endtab %}
{% endtabs %}

---

#### 📈 Simulation Settings

**AI Sim TP% (Testing Only)**

{% hint style="warning" %}
**Note:** These are internal simulation parameters - they do NOT create real orders
{% endhint %}

{% columns %}
{% column width="60%" %}
**What they do:**

- Help AI evaluate strategies
- Set internal profit targets
- Default: 1.0% both directions
  {% endcolumn %}

{% column %}
{% code title="sim-settings:" %}

```
Long TP: 1.0%
Short TP: 1.0%
Purpose: AI testing only
Real trades: Not affected
```

{% endcode %}
{% endcolumn %}
{% endcolumns %}

---

#### 📊 Dashboard Display

**Live Monitoring**

When enabled, see:

- ✅ Current optimal sensitivity
- ✅ Selected thresholds
- ✅ Win rate & metrics
- ✅ Confidence score
- ✅ Mode status

**Status Indicators:**

- `STATIC (LOCKED)` - One-time optimization complete
- `OPTIMIZING` - Currently calculating
- `SIMULATED` - Results ready

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FyXoT69oiyDH6NCl2F5SM%2Fimage.png?alt=media&#x26;token=5061bb2e-8f38-48b3-84be-3f1f094a376a" alt="" width="486"><figcaption></figcaption></figure>

---

#### 💡 Best Practices

{% tabs %}
{% tab title="🎯 Getting Started" %}

1. Use **Static** for initial testing
2. Select **Balanced** sensitivity
3. Default 100 bar frequency
4. Match metric to goals
5. **Walk-Forward needs \~535 bars** for first optimization
6. **Static needs \~5000 bars** total
   {% endtab %}

{% tab title="⚡ Optimization" %}

- **Lower timeframes** → Complex calculations
- **Monitor dashboard** → Track selections
- **Small adjustments** → Better results
- **Patience required** → AI needs time
  {% endtab %}

{% tab title="📈 Performance" %}
**Limits:**

- Max lookback: 5000 bars
- Lower frequency = Higher CPU
- Static = One calculation only at bar 4900
- Higher TF = Better performance
  {% endtab %}
  {% endtabs %}

---

#### 🔧 Troubleshooting

| Problem          | Solution                         |
| ---------------- | -------------------------------- |
| **Timeout**      | Use Static or increase frequency |
| **No signals**   | Check AI Optimization is ON      |
| **Poor results** | Try different metric/range       |
| **No dashboard** | Enable in settings               |
| **Static fails** | Need 5000+ bars data             |

---

#### ⚡ Quick Reference

{% columns %}
{% column width="50%" %}
**For Testing**

- Mode: `Static`
- Range: `Balanced`
- Metric: `Total Profit`
- Frequency: N/A
- Min bars: 5000
  {% endcolumn %}

{% column %}
**For Live Trading**

- Mode: `Walk-Forward`
- Range: `Balanced`
- Metric: Your preference
- Frequency: `100` (default)
- Min bars: 535
  {% endcolumn %}
  {% endcolumns %}

---

#### 📚 Understanding Performance Metrics

<details>

<summary><strong>Detailed Metric Explanations</strong></summary>

{% hint style="info" %}
**Note:** Infinity Algo computes metrics on **per-trade returns** with risk-free rate and MAR = 0. Industry definitions typically use time-series (daily/monthly) returns.
{% endhint %}

**Classic Metrics**

| Metric           | Formula                   | Best For            |
| ---------------- | ------------------------- | ------------------- |
| **Total Profit** | Sum of all P\&L           | Quick assessment    |
| **Win Rate**     | Wins ÷ Total trades × 100 | Consistency check   |
| **Average P\&L** | Total P\&L ÷ Trades       | Trade quality       |
| **Gain-to-Pain** | Σ gains / \|Σ losses\|    | Risk/reward balance |

---

**Risk-Adjusted Metrics**

**Sharpe Ratio - Industry Standard**

- **Formula:** Excess return (over risk-free) ÷ Standard deviation
- **Infinity Algo:** Uses risk-free = 0
- **Pros:** Most widely used, easy comparison, considers total volatility
- **Cons:** Penalizes upside volatility, assumes normal distribution
- **Benchmarks:** \~1 = Good | \~2 = Very good | 3+ = Outstanding

**Sortino Ratio - Downside Focus**

- **Formula:** Excess return (over target/MAR) ÷ Downside deviation
- **Infinity Algo:** Uses MAR = 0
- **Pros:** Only penalizes bad volatility, better for trend following
- **Cons:** Requires defining target return, less standardized
- **Benchmarks:** >1 = Good | >2 = Very good | >3 = Excellent

**Calmar Ratio - Drawdown Protection**

- **Formula:** CAGR ÷ Maximum drawdown (commonly 36 months)
- **Pros:** Focus on capital preservation, easy to understand
- **Cons:** Based on single worst event, backward-looking
- **Benchmarks:** >1 = Good | 3-5 = Strong

**Martin Ratio - Ulcer Performance**

- **Formula:** Excess return ÷ Ulcer Index (RMS of drawdowns)
- **Pros:** Considers all drawdowns, smooth equity curve focus
- **Cons:** Less known/comparable, complex calculation
- **Use:** Compare across your strategies

**SQN - System Quality Number**

- **Formula:** (Expectancy ÷ Std Dev) × √Number of trades
- **Pros:** Accounts for sample size, good for system comparison
- **Cons:** Requires sufficient trades for validity
- **Benchmarks:** >2 = Good | >3 = Excellent | >5 = Superb

---

**Choosing by Trading Style**

| Style                | Primary Metrics   | Secondary Metrics |
| -------------------- | ----------------- | ----------------- |
| **Scalping**         | Win Rate + Sharpe | Total Profit      |
| **Day Trading**      | Sharpe + Win Rate | Average P\&L      |
| **Swing Trading**    | Sortino + Calmar  | Gain-to-Pain      |
| **Position Trading** | Calmar + Martin   | Sortino           |

{% hint style="warning" %}
**Remember:** Win rate alone is misleading. A strategy with 30% win rate but 3:1 reward/risk is more profitable than 70% win rate with 1:3 reward/risk.
{% endhint %}

{% hint style="info" %}
**AI Mode Selection:**

- **Intraday/Mean-reversion:** Optimizes for Sharpe + Win Rate
- **Trend/Swing trading:** Prioritizes Sortino + Calmar
- **Multi-metric:** Balances all metrics for robust performance
  {% endhint %}

</details>

---

{% hint style="success" %}
**Bottom Line:** Let AI handle optimization while you focus on trading decisions and risk management.
{% endhint %}
