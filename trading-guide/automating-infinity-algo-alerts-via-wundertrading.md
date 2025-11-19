# 🔄 Automating Infinity Algo Alerts via WunderTrading

[Got ideas? Request a feature](https://infinityalgo.canny.io/?utm_source=docs\&utm_medium=banner)

Connect Infinity Algo signals to WunderTrading for automated trading with flexible position management.

***

#### 🎯 Two Trading Workflows

**🔄 Swing Trade**

Auto-Flip Positions (Futures Only)

What it does:

* Automatic Long ↔ Short flipping
* Just two alerts needed
* Bot handles position reversal
* With Swing Trade ON, Enter-Long/Enter-Short flip positions automatically

Best for:

* ✅ Futures trading only
* ✅ Trending markets
* ✅ Minimal alerts
* ✅ Always in position

Setup Requirements

```
Swing Trade: ON (Futures only!)
Alerts: 2 total
- Buy Signal → Enter-Long
- Sell Signal → Enter-Short
(Exit-All only for flattening without opening opposite)
```

{% hint style="info" %}
Swing trade functionality is only available for Futures markets.
{% endhint %}

***

**🎯 Explicit Exit**

Manual Position Control

What it does:

* Full control over exits
* No position overlap
* Works on Spot & Futures
* Clear entry/exit separation

Best for:

* ✅ Spot trading
* ✅ Risk management
* ✅ Position gaps
* ✅ More control

Setup Requirements

```
Swing Trade: OFF
Alerts: 3+ total
- Entry → Enter-Long/Enter-Short
- Exit → Exit-Long/Exit-Short
- Optional re-entry
```

Perfect for traders who want complete control over position timing

***

#### ⚙️ Step 1–3: Build Bot, Configure Entries & Create Alerts

{% stepper %}
{% step %}
### Step 1 — Build Signal Bot in WunderTrading

Navigate to WunderTrading:

* Log in → Bots → Signal Bot → Create bot

Configure General tab settings:

| Field            | Value                       |
| ---------------- | --------------------------- |
| Name             | e.g. `Infinity Algo BTC`    |
| Exchange/API     | Select your exchange API    |
| Pairs            | Select up to 10 pairs in UI |
| Timeframe label  | Any (just a label)          |
| Multiple entries | ON for scale-ins            |
| Swing trade      | ON for auto-flip (Futures)  |

Note: Pairs must be selected in the bot UI. JSON cannot override pair selection.
{% endstep %}

{% step %}
### Step 2 — Configure Entries & Get Webhook

Entries tab configuration:

| Setting             | Value               |
| ------------------- | ------------------- |
| Bot start condition | _TradingView Alert_ |
| Bot settings format | **JSON**            |

After saving, your bot will display:

* Webhook URL: Copy the exact URL shown in your bot's Alerts tab
* Alert comments: Copy exactly as shown (default: `Enter-Long`, `Enter-Short`, `Exit-All`)

{% hint style="warning" %}
Critical:

* Copy the exact webhook URL from your bot — don't guess the format
* Comment codes are case-sensitive and may change if you edit bot Name/Exchange/Timeframe/Pair
* After any bot edits, update your TradingView alerts to match
{% endhint %}
{% endstep %}

{% step %}
### Step 3 — Create TradingView Alerts

Standard Alert Settings:

| Field       | Value                                                         |
| ----------- | ------------------------------------------------------------- |
| Condition   | Select your Infinity Algo signal (e.g., "Buy Signal - Smart") |
| Options     | Once Per Bar Close (prevents duplicate orders)                |
| Webhook URL | Paste the exact URL from your bot's Alerts tab                |
| Message     | JSON template (see below)                                     |

Use the exact comment codes shown in your bot's sidebar (case-sensitive).
{% endstep %}
{% endstepper %}

***

#### 📝 JSON Templates

Important: Use the exact comment codes shown in your bot's sidebar (e.g., `Enter-Long`, not `ENTER-LONG`)

<details>

<summary>enter_long.json (Long Entry)</summary>

{% code title="enter_long.json" %}
```json
{
  "code": "Enter-Long",            // must match your bot's comment EXACTLY
  "orderType": "market",
  "amountPerTradeType": "quote",   // quote currency (e.g., USDT on BTC/USDT)
  "amountPerTrade": 150,

  "takeProfits": [
    { "priceDeviation": 0.01, "portfolio": 0.25 },
    { "priceDeviation": 0.02, "portfolio": 0.25 },
    { "priceDeviation": 0.03, "portfolio": 0.25 },
    { "priceDeviation": 0.04, "portfolio": 0.15 },
    { "priceDeviation": 0.05, "portfolio": 0.07 },
    { "priceDeviation": 0.06, "portfolio": 0.03 }
  ],

  "stopLoss": { "priceDeviation": 0.01 },
  "reduceOnly": true,              // prevents exits from increasing size (Futures only)
  "placeConditionalOrdersOnExchange": false
}
```
{% endcode %}

Note: TP portfolios must sum to exactly 1.0 (100%)

</details>

<details>

<summary>enter_short.json (Short Entry)</summary>

{% code title="enter_short.json" %}
```json
{
  "code": "Enter-Short",
  "orderType": "market",
  "amountPerTradeType": "quote",
  "amountPerTrade": 150,

  "takeProfits": [
    { "priceDeviation": 0.01, "portfolio": 0.25 },
    { "priceDeviation": 0.02, "portfolio": 0.25 },
    { "priceDeviation": 0.03, "portfolio": 0.25 },
    { "priceDeviation": 0.04, "portfolio": 0.15 },
    { "priceDeviation": 0.05, "portfolio": 0.07 },
    { "priceDeviation": 0.06, "portfolio": 0.03 }
  ],

  "stopLoss": { "priceDeviation": 0.01 },
  "reduceOnly": true
}
```
{% endcode %}

</details>

<details>

<summary>exit_long.json (Exit Long)</summary>

{% code title="exit_long.json" %}
```json
{
  "code": "Exit-Long",
  "orderType": "market",
  "reduceOnly": true
}
```
{% endcode %}

</details>

<details>

<summary>exit_short.json (Exit Short)</summary>

{% code title="exit_short.json" %}
```json
{
  "code": "Exit-Short",
  "orderType": "market",
  "reduceOnly": true
}
```
{% endcode %}

</details>

<details>

<summary>exit_all.json (Exit All)</summary>

{% code title="exit_all.json" %}
```json
{
  "code": "Exit-All",
  "orderType": "market",
  "reduceOnly": true
}
```
{% endcode %}

Closes all positions at market.

</details>

Skip exit\_long/exit\_short templates if using Swing Trade ON.

***

#### ⚡ Quick Comparison

| Feature          |  Swing Trade ON |            Explicit Exit |
| ---------------- | --------------: | -----------------------: |
| Market Type      | ⚠️ Futures only |         ✅ Spot & Futures |
| Alerts Needed    |     2 (minimal) | 3+ (entry/exit/re-entry) |
| Position Control |  Automatic flip |           Manual control |
| Position Gaps    |           Never |                 Possible |
| Complexity       |          Simple |                 Moderate |

***

#### 🎯 Pick Your Workflow

If you want…

A) Ping-pong (auto flip) — Long → Short → Long with just two alerts

* Turn Swing trade = ON in bot (Futures only)
* Buy alert → `Enter-Long` JSON
* Sell alert → `Enter-Short` JSON
* Use `Exit-All` only when you want to flatten without opening opposite

B) Explicit exit first — Never overlap positions; more control

* Leave Swing trade = OFF
* Entry alert → `Enter-Long` or `Enter-Short` JSON
* Exit alert → `Exit-Long` or `Exit-Short` JSON
* (Optional) second entry alert to reverse

***

#### 🚀 Advanced Features

Multiple TPs

* Add up to **6 TP steps**
* Portfolios must sum to **1.0**
* Multi-pair requires `priceDeviation` (decimals, not %)
* Single-pair can use `price`

Example: 6-Level TP

```
"takeProfits": [
  { "priceDeviation": 0.01, "portfolio": 0.30 },
  { "priceDeviation": 0.02, "portfolio": 0.25 },
  { "priceDeviation": 0.03, "portfolio": 0.20 },
  { "priceDeviation": 0.04, "portfolio": 0.15 },
  { "priceDeviation": 0.05, "portfolio": 0.07 },
  { "priceDeviation": 0.06, "portfolio": 0.03 }
]
```

Sum = 1.0 (100%) ✅

Multiple Entries

* Enable in bot settings for DCA on consecutive signals, building larger positions, averaging entry price
* Works with both workflows

amountPerTradeType options:

Spot markets:

* `quote` — Quote currency (e.g., USDT)
* `base` — Base currency (e.g., BTC)
* `percents` — Percentage of balance

Derivatives/Futures:

* `quote` — Quote currency
* `contracts` — Number of contracts
* `percents` — Percentage of balance

***

#### 🧠 Pro Tips

* Multi-pair bots: Use `priceDeviation` (decimals like 0.02 for 2%), not `price` for TP/SL
* priceDeviation format — Use decimals (0.02) not percentages (2%)
* Portfolio sum — TP portfolios must add up to exactly 1.0 (100%)
* reduceOnly — Applies to exits; has no effect on Spot markets
* Comment codes — Copy exactly from your bot; they change if you edit bot settings
* Strategy alerts — Use `alert()` function with `{{strategy.order.comment}}` for strategies
* Paper test first — WunderTrading log shows "Signal executed" if webhook parsed correctly

***

#### 🛠️ Troubleshooting Checklist

| Symptom                     | Likely cause / fix                                                            |
| --------------------------- | ----------------------------------------------------------------------------- |
| No deal appears             | `code` in JSON doesn't match bot's Alert comment exactly (check case!)        |
| Bot opens but doesn't close | Swing trade OFF and you forgot exit alert – or `reduceOnly:false` caused flip |
| Webhook error 400           | JSON syntax error or using `%` instead of decimals (use `0.02`, not `2%`)     |
| Duplicate deals             | Alert set to "Once Per Bar" instead of "Once Per Bar Close"                   |
| Multi-pair TP/SL fails      | Must use `priceDeviation` (decimals), not `price`                             |
| Comments changed            | Bot edits can change comment codes — update alerts after any bot changes      |

***

#### 🔤 JSON Key Reference

| Key                                | What it does             | Details                                                                                  |
| ---------------------------------- | ------------------------ | ---------------------------------------------------------------------------------------- |
| `code`                             | Alert comment identifier | Must match bot's comment exactly (case-sensitive!)                                       |
| `orderType`                        | Order execution type     | `market` or `limit`                                                                      |
| `amountPerTradeType`               | Position size unit       | Spot: `quote`/`base`/`percents` — Futures: `quote`/`contracts`/`percents`                |
| `amountPerTrade`                   | Position size            | Value depends on type above                                                              |
| `takeProfits`                      | Array of partial exits   | `priceDeviation`: decimal (0.02 = 2%) — `portfolio`: fraction to close (must sum to 1.0) |
| `stopLoss`                         | Stop loss configuration  | `priceDeviation`: decimal from entry                                                     |
| `reduceOnly`                       | Prevent size increase    | `true` → exits only decrease position (Futures only, no effect on Spot)                  |
| `placeConditionalOrdersOnExchange` | Where orders execute     | `false` = managed by bot — `true` = on exchange                                          |

***

#### 🎯 Which Workflow Should You Use?

Choose Swing Trade if:

* Trading Futures only
* Want minimal alerts
* Trust your signals
* Always in position

Choose Explicit Exit if:

* Trading Spot markets
* Need position control
* Want gap periods
* Risk management focus

Pro Tip: Start with Explicit Exit to learn, then switch to Swing Trade for Futures efficiency

***

#### 📚 Resources

Official WunderTrading Documentation:

* Main Docs: https://help.wundertrading.com/en/
* Signal Bot Form Guide: https://help.wundertrading.com/en/articles/10458409-signal-bot-comprehensive-form-guide
* JSON Guide: https://help.wundertrading.com/en/articles/10475473-signal-bot-comprehensive-json-guide
* TradingView Setup: https://help.wundertrading.com/en/articles/5173846-how-to-set-up-a-tradingview-bot-signal-bot-in-wundertrading
* Troubleshooting: https://help.wundertrading.com/en/articles/5173235-my-signal-bot-does-not-work

Important Reminders:

* WunderTrading is a third-party service with separate subscription costs
* Always test with small amounts or paper trading first
* Comment codes are case-sensitive and can change when you edit bot settings
* Manual trading via TradingView is always available as an alternative

Last updated 2 months ago

Was this helpful?
