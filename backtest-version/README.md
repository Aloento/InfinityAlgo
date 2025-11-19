# Backtest version

The Infinity Algo V3.0 Backtest version enables comprehensive strategy testing with automated position management. Test your ideas before risking real capital.

{% hint style="success" %}
**Quick Navigation:**

- **First time?** Start here for overview
- **Need configuration help?** → [Configuration Guide](https://docs.infinityalgo.com/backtest/backtest-version/example-of-settings)
- **Want fixed settings?** → [Settings Spreadsheet](https://docs.infinityalgo.com/backtest/backtest-version/settings-spreadsheet)
  {% endhint %}

---

### 🎯 What is Backtesting?

#### Purpose & Benefits

{% columns %}
{% column width="50%" %}
**Why Backtest:**

- Test without real money
- Validate strategy logic
- Understand drawdowns
- Build confidence
- Learn indicator behavior
  {% endcolumn %}

{% column %}
**What You'll Learn:**

- Expected win rate
- Average profit/loss
- Maximum drawdown
- Optimal settings
- Risk tolerance needed
  {% endcolumn %}
  {% endcolumns %}

#### ⚠️ Important Disclaimers

{% hint style="warning" %}
**Reality Check:**

- Historical performance ≠ Future results
- Backtests exclude spreads, slippage, emotions
- Markets change - strategies must adapt
- This is education, not financial advice
  {% endhint %}

---

### 📊 TradingView Plan Limitations

Your testing power depends on your subscription:

| Plan             | Historical Bars | Deep Backtesting | Recommendation                  |
| ---------------- | --------------- | ---------------- | ------------------------------- |
| **Basic** (Free) | 5,000           | ❌               | Test concepts only              |
| **Essential**    | 10,000          | ❌               | Basic validation                |
| **Plus**         | 10,000          | ❌               | Casual testing                  |
| **Premium** ⭐   | 20,000          | ✅               | **Minimum for serious testing** |
| **Expert**       | 25,000          | ✅               | Professional traders            |
| **Ultimate**     | 40,000          | ✅               | Maximum capability              |

{% hint style="info" %}
**🚀 Deep Backtesting Feature** (Premium+ only)

Tests on ALL available data (up to 2M bars) instead of just visible chart:

- Essential for lower timeframes
- Required for statistical significance
- Provides reliable results

**Without it:** Limited to chart bars only
{% endhint %}

---

### 🚀 Quick Start Guide

{% stepper %}
{% step %}

#### Install Backtest Version

1. Remove standard Infinity Algo
2. Add "Infinity Algo V3.0 Backtest" from Invite-Only
3. You'll see "Strategy Tester" tab appear
   {% endstep %}

{% step %}

#### Open Strategy Tester

1. Click "Strategy Tester" at bottom
2. Check "Overview" tab first
3. Note the date range tested
4. Verify minimum 30 trades
   {% endstep %}

{% step %}

#### Run First Test

Use defaults initially:

- Don't change anything yet
- Let it run with standard settings
- Document baseline performance
- This is your reference point
  {% endstep %}

{% step %}

#### Review Key Numbers

Focus on these first:

- **Net Profit** - Is it positive?
- **Win Rate** - What percentage wins?
- **Max Drawdown** - Can you handle it?
- **Total Trades** - Enough data?
  {% endstep %}
  {% endstepper %}

---

### 📈 Understanding the Strategy Tester

#### Key Tabs Explained

{% tabs %}
{% tab title="Overview" %}
**What you see:**

- Net profit/loss
- Total trades
- Win rate percentage
- Profit factor
- Max drawdown

**Quick interpretation:**

- Green = profitable
- 30+ trades = meaningful
- Check drawdown first
  {% endtab %}

{% tab title="Performance Summary" %}
**Detailed metrics:**

- Average trade
- Best/worst trade
- Consecutive wins/losses
- Risk metrics
- Time in market

**Use for:**

- Deep analysis
- Risk assessment
- Strategy comparison
  {% endtab %}

{% tab title="List of Trades" %}
**Every trade detailed:**

- Entry/exit prices
- Profit/loss
- Duration
- Signal type

**Use for:**

- Verify logic
- Find patterns
- Debug issues
  {% endtab %}
  {% endtabs %}

---

### ⚡ Backtest vs Live Differences

#### What Backtests Include

✅ Historical price data ✅ Your strategy logic ✅ Entry/exit signals ✅ Position sizing

#### What They Don't Include

❌ Spread costs ❌ Slippage ❌ Commission fees ❌ Emotional decisions ❌ Connection issues ❌ Exchange downtime

{% hint style="danger" %}
**Rule of Thumb:** Reduce backtest returns by 30-50% for realistic expectations
{% endhint %}

---

### 🎯 Next Steps

#### Your Path Forward

{% columns %}
{% column width="50%" %}
**1. Learn Configuration** → Configuration Guide

- Exit strategies
- Position management
- Risk settings
  {% endcolumn %}

{% column %}
**2. Understand Philosophy** → Why Dynamic Optimization

- AI vs static settings
- Market adaptation
- Common mistakes
  {% endcolumn %}
  {% endcolumns %}

#### Related Resources

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><strong>Example of settings</strong>⚙️<br>Detailed settings and strategies</td><td></td><td><a href="backtest-version/settings-spreadsheet">settings-spreadsheet</a></td></tr><tr><td><strong>Automated Alerts</strong> 🔔<br>Backtest version alerts</td><td></td><td><a href="backtest-version/alerts-backtest-version">alerts-backtest-version</a></td></tr></tbody></table>

{% hint style="success" %}
**Ready to start?** Open Strategy Tester and run your first test with default settings. Document the results - this is your baseline for improvement.
{% endhint %}
