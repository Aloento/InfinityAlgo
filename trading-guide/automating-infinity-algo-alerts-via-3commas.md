# 🔄 Automating Infinity Algo Alerts via 3Commas

Connect Infinity Algo signals directly to 3Commas for automated trading execution.

---

### 🎯 Three Integration Methods

{% tabs %}
{% tab title="🔄 Reversal Bot" %}
**Automatic Position Flipping**

**What it does:**

- Switches Long ↔ Short automatically
- One bot handles both directions
- Closes opposite position before opening new

**Best for:**

- ✅ Trending markets
- ✅ Active trading
- ✅ Maximum efficiency
- ✅ Less alert management

{% code title="Setup Requirements" %}

```
Direction: Reversal (both)
Pairs: Single or Multi-pair (up to 200)
Alerts: 2 total
- Buy Signal → enter_long
- Sell Signal → enter_short
```

{% endcode %}

{% hint style="info" %}
**Reversal Behavior:**

- **Spot:** With Reverse position ON, opposite signal closes & flips; OFF ignores opposite signals
- **Futures Hedge Mode ON:** Enable "Reverse position" to flip positions
- **Futures Hedge Mode OFF:** Bot automatically closes opposite before opening new
  {% endhint %}

For simplicity, we recommend one pair per bot for reversal workflows.
{% endtab %}

{% tab title="🎯 Clean Exit" %}
**Exit Without Disabling Bot**

**What it does:**

- Closes position cleanly
- Bot stays active for next signal
- No manual re-enabling needed

**Best for:**

- ✅ Continuous trading
- ✅ Quick re-entry
- ✅ Automated workflow
- ✅ Active strategies

{% code title="Setup Requirements" %}

```
Direction: Long or Short
Alerts: 3 total
- Entry: enter_long/enter_short
- Exit: exit_long/exit_short
- Re-entry: enter_long/enter_short
```

{% endcode %}

{% hint style="success" %}
**Pro Tip:** Exit signals use market execution only - limit orders on exits will be rejected
{% endhint %}
{% endtab %}

{% tab title="⏹️ Panic Stop" %}
**Disable Bot & Close All**

**What it does:**

- Closes all positions at market
- Disables bot completely
- Requires manual re-enable

**Best for:**

- ✅ Emergency stops
- ✅ End of session
- ✅ Risk events
- ✅ Manual intervention

{% code title="Setup Requirements" %}

```
Action: disable
Sub-action: market_close
Note: Bot must be manually re-enabled
```

{% endcode %}

{% hint style="danger" %}
**Warning:** Bot will NOT auto-restart on next signal - you must manually enable it again
{% endhint %}
{% endtab %}
{% endtabs %}

---

### ⚙️ Step 1: Configure Signal Bot

**Navigate to 3Commas:**

1. **Log in** → 3Commas.io
2. **Bots** → **Signal Bot** → **Create Bot**
3. Configure with these settings:

| Setting        | Value                          |
| -------------- | ------------------------------ |
| **Name**       | e.g. Infinity Algo BTC         |
| **Exchange**   | Select your exchange           |
| **Pairs**      | Single or Multi (up to 200)    |
| **Alert Type** | Custom Signal                  |
| **Direction**  | Long / Short / Reversal (both) |
| **TP/SL**      | Set here or via webhook        |
| **Risk Caps**  | Max Investment, Leverage       |

For multi-pair bots, also set **Max active SmartTrades**.

---

### 📩 Step 2: Get Webhook Credentials

After saving your bot, find **"Message for deal start signal"** and copy:

{% code title="Your Unique Credentials" overflow="wrap" %}

```json
{
  "secret": "ab12cd34.ef56gh78…", // Keep this private!
  "bot_uuid": "f1a2b3c4-…-9d0e1f2a", // Your bot's ID
  "action": "enter_long",
  "tv_exchange": "{{exchange}}",
  "tv_instrument": "{{ticker}}"
}
```

{% endcode %}

{% hint style="danger" %}
**Security:** Never share your `secret` token - it controls your bot! Signal Bots no longer accept old `bot_id`/`email_token` pairs.
{% endhint %}

---

### 📊 Step 3: Create TradingView Alerts

**Alert Configuration**

| Field           | Value                                          |
| --------------- | ---------------------------------------------- |
| **Condition**   | Match your Infinity Algo signal exactly        |
| **Options**     | ✅ **Once Per Bar Close** (not "Once Per Bar") |
| **Webhook URL** | `https://api.3commas.io/signal_bots/webhooks`  |
| **Message**     | JSON template with YOUR-SECRET & YOUR-UUID     |

{% hint style="info" %}
**Important:** Alert condition must match your Infinity Algo signal names exactly, including any numeric prefixes
{% endhint %}

---

### 📝 JSON Templates

{% hint style="warning" %}
**Required Fields:** All signals must include `secret`, `bot_uuid`, `action`, `tv_exchange`, and `tv_instrument`
{% endhint %}

{% tabs %}
{% tab title="🟢 Long Entry" %}
{% code title="enter\_long.json" overflow="wrap" lineNumbers="true" %}

```json
{
  "secret": "YOUR-SECRET",
  "bot_uuid": "YOUR-UUID",
  "action": "enter_long",

  "tv_exchange": "{{exchange}}",
  "tv_instrument": "{{ticker}}",

  "order": {
    "amount": 150,
    "currency_type": "quote",
    "order_type": "market"
  },

  "take_profit": {
    "enabled": true,
    "steps": [
      { "order_type": "limit", "price_percent": 1, "volume_percent": 25 },
      { "order_type": "limit", "price_percent": 2, "volume_percent": 25 },
      { "order_type": "limit", "price_percent": 3, "volume_percent": 25 },
      { "order_type": "market", "price_percent": 4, "volume_percent": 25 }
    ]
  },

  "stop_loss": {
    "enabled": true,
    "order_type": "market",
    "trigger_price_percent": 1
  },

  "max_lag": 300,
  "timestamp": "{{timenow}}"
}
```

{% endcode %}

**Note:** For limit entry, add `"price"` or `"price_percent"` with optional `"price_percent_ref_type"`
{% endtab %}

{% tab title="🔴 Short Entry" %}
{% code title="enter\_short.json" overflow="wrap" lineNumbers="true" %}

```json
{
  "secret": "YOUR-SECRET",
  "bot_uuid": "YOUR-UUID",
  "action": "enter_short",

  "tv_exchange": "{{exchange}}",
  "tv_instrument": "{{ticker}}",

  "order": {
    "amount": 150,
    "currency_type": "quote",
    "order_type": "market"
  },

  "take_profit": {
    "enabled": true,
    "steps": [
      { "order_type": "limit", "price_percent": 1, "volume_percent": 25 },
      { "order_type": "limit", "price_percent": 2, "volume_percent": 25 },
      { "order_type": "limit", "price_percent": 3, "volume_percent": 25 },
      { "order_type": "market", "price_percent": 4, "volume_percent": 25 }
    ]
  },

  "stop_loss": {
    "enabled": true,
    "order_type": "market",
    "trigger_price_percent": 1
  },

  "max_lag": 300,
  "timestamp": "{{timenow}}"
}
```

{% endcode %}
{% endtab %}

{% tab title="✅ Exit Long" %}
{% code title="exit\_long.json" overflow="wrap" %}

```json
{
  "secret": "YOUR-SECRET",
  "bot_uuid": "YOUR-UUID",
  "action": "exit_long",

  "tv_exchange": "{{exchange}}",
  "tv_instrument": "{{ticker}}",

  "order": {
    "amount": 100,
    "currency_type": "position_percent"
  },

  "max_lag": 300,
  "timestamp": "{{timenow}}"
}
```

{% endcode %}

**Note:** Exit orders are market-only - don't add `"order_type": "limit"`
{% endtab %}

{% tab title="❌ Exit Short" %}
{% code title="exit\_short.json" overflow="wrap" %}

```json
{
  "secret": "YOUR-SECRET",
  "bot_uuid": "YOUR-UUID",
  "action": "exit_short",

  "tv_exchange": "{{exchange}}",
  "tv_instrument": "{{ticker}}",

  "order": {
    "amount": 100,
    "currency_type": "position_percent"
  },

  "max_lag": 300,
  "timestamp": "{{timenow}}"
}
```

{% endcode %}
{% endtab %}

{% tab title="⏹️ Panic Stop" %}
{% code title="disable\_bot.json" overflow="wrap" %}

```json
{
  "secret": "YOUR-SECRET",
  "bot_uuid": "YOUR-UUID",
  "action": "disable",

  "tv_exchange": "{{exchange}}",
  "tv_instrument": "{{ticker}}",

  "positions_sub_action": "market_close",

  "max_lag": 300,
  "timestamp": "{{timenow}}"
}
```

{% endcode %}

{% hint style="danger" %}
This disables the bot completely - manual re-enable required!
{% endhint %}
{% endtab %}
{% endtabs %}

---

### ⚡ Quick Reference

| Parameter                  | Purpose                   | Values                                                 |
| -------------------------- | ------------------------- | ------------------------------------------------------ |
| **price_percent**          | TP distance from entry    | Integer: 1 = 1%, 2 = 2%                                |
| **volume_percent**         | % of position to close    | Must sum to 100%                                       |
| **trigger_price_percent**  | Stop loss distance        | Integer: 1 = 1% loss                                   |
| **currency_type**          | Order size unit           | `quote`, `base`, `margin_percent`, `position_percent`  |
| **amount**                 | Position size             | Number based on currency_type                          |
| **max_lag**                | Reject stale signals      | Seconds (300 = 5 min)                                  |
| **timestamp**              | Signal freshness          | Always use `{{timenow}}`                               |
| **price_percent_ref_type** | Price reference for limit | `current_price`, `base_entry_price`, `avg_entry_price` |

---

### 🎯 Which Method Should You Use?

| Feature            | 🔄 Reversal Bot  | 🎯 Clean Exit           | ⏹️ Panic Stop   |
| ------------------ | ---------------- | ----------------------- | --------------- |
| **Best For**       | Trending markets | Continuous trading      | Emergency stops |
| **Alerts Needed**  | 2 (minimal)      | 3 (entry/exit/re-entry) | 1 (stop all)    |
| **Position State** | Always in        | Flexible gaps           | Fully closed    |
| **Bot Status**     | ✅ Always active | ✅ Always active        | ❌ Disabled     |
| **Re-entry**       | Automatic        | Automatic               | Manual required |
| **Ideal Trader**   | Active/Confident | Flexible/Cautious       | Risk-averse     |

{% columns %}
{% column width="50%" %}
**Choose Reversal if you:**

- Trade trending pairs
- Trust your signals
- Want set-and-forget
  {% endcolumn %}

{% column %}
**Choose Clean Exit if you:**

- Need position control
- Trade multiple pairs
- Want gap periods
  {% endcolumn %}
  {% endcolumns %}

---

### 🚀 Advanced Features

{% tabs %}
{% tab title="📈 Multiple TPs" %}
**Up to 8 Take Profit Levels**

- UI supports up to 4 levels
- JSON supports up to 8 levels
- Volumes must total **100%**
- Can mix limit & market orders
- Trailing only on last step

{% code title="Example: 8-Level TP with Trailing" %}

```json
"take_profit": {
  "enabled": true,
  "steps": [
    { "order_type": "limit", "price_percent": 1, "volume_percent": 20 },
    { "order_type": "limit", "price_percent": 2, "volume_percent": 20 },
    { "order_type": "limit", "price_percent": 3, "volume_percent": 15 },
    { "order_type": "limit", "price_percent": 4, "volume_percent": 15 },
    { "order_type": "limit", "price_percent": 5, "volume_percent": 10 },
    { "order_type": "limit", "price_percent": 6, "volume_percent": 10 },
    { "order_type": "limit", "price_percent": 7, "volume_percent": 5 },
    { "order_type": "market", "price_percent": 8, "volume_percent": 5,
      "trailing": { "enabled": true, "percent": 0.2 }
    }
  ]
}
```

{% endcode %}
{% endtab %}

{% tab title="🛡️ Trailing Stop" %}
**Dynamic Stop Loss**

{% code title="Trailing Stop Configuration" %}

```json
"stop_loss": {
  "enabled": true,
  "order_type": "market",
  "trigger_price_percent": 2,
  "trailing": {
    "enabled": true,
    "percent": 0.5
  }
}
```

{% endcode %}

Trails 0.5% behind highest profit
{% endtab %}

{% tab title="🤖 Bot Filters" %}
**Price Deviation & Deal Close Conditions**

In bot configuration (not JSON):

- **Price deviation filters**: Prevent unfavorable entries
- **Minimum profit**: May block exits until profit target met

If exits don't close, check your bot's **Minimum profit/Deal close conditions**
{% endtab %}
{% endtabs %}

---

### 🛠️ Troubleshooting Checklist

| ✅ Check                 | Details                                                         |
| ------------------------ | --------------------------------------------------------------- |
| **Valid Credentials**    | JSON must include valid `secret` and `bot_uuid`                 |
| **Required Fields**      | Always include `tv_exchange` and `tv_instrument` in ALL signals |
| **Correct Webhook URL**  | Must be exactly `https://api.3commas.io/signal_bots/webhooks`   |
| **Alert Timing**         | Alerts fire **Once Per Bar Close** (not "Once Per Bar")         |
| **One Alert Per Action** | Never combine entry & exit in one JSON                          |
| **Field Names**          | Use `price_percent` not `price_deviation`                       |
| **Volumes Sum to 100**   | All `volume_percent` must total exactly 100                     |
| **Exit Orders**          | Exit signals use market execution only - no limit orders        |
| **Signal Freshness**     | Include `max_lag` and `timestamp` to prevent stale signals      |
| **Bot Re-enabling**      | If using `disable`, must manually re-enable bot                 |
| **Exit Not Working**     | Check bot's Minimum profit/Deal close conditions                |

---

### 📖 JSON Field Glossary

| Field                        | Purpose                  | Values & Rules                                                                            |
| ---------------------------- | ------------------------ | ----------------------------------------------------------------------------------------- |
| **`secret`**                 | Private bot token        | **Required** - Copy exactly from Step 2                                                   |
| **`bot_uuid`**               | Unique Signal Bot ID     | **Required** - Copy from Step 2                                                           |
| **`action`**                 | Bot command              | **Required** - `enter_long`, `enter_short`, `exit_long`, `exit_short`, `disable`          |
| **`tv_exchange`**            | TradingView exchange     | **Required** - Always `{{exchange}}`                                                      |
| **`tv_instrument`**          | TradingView pair         | **Required** - Always `{{ticker}}`                                                        |
| **`positions_sub_action`**   | When action is `disable` | <p><code>market_close</code> → flatten & disable<br><code>cancel</code> → cancel only</p> |
| **`order.amount`**           | Position size            | Based on `currency_type` setting                                                          |
| **`order.order_type`**       | Entry order type         | `market` or `limit` (limit needs `price` or `price_percent`)                              |
| **`currency_type`**          | Unit for amount          | `quote`, `base`, `margin_percent`, `position_percent`                                     |
| **`price`**                  | Exact limit price        | For limit orders - exact price value                                                      |
| **`price_percent`**          | TP/limit distance        | Integer: 1 = 1%, 2 = 2%                                                                   |
| **`price_percent_ref_type`** | Reference for percent    | `current_price`, `base_entry_price`, `avg_entry_price`                                    |
| **`volume_percent`**         | % to close at each TP    | 1-100 (must sum to 100%)                                                                  |
| **`trigger_price_percent`**  | Stop loss trigger        | Integer: 1 = 1% loss                                                                      |
| **`max_lag`**                | Signal age limit         | Seconds (300 = 5 minutes)                                                                 |
| **`timestamp`**              | Current time             | Always `{{timenow}}`                                                                      |

---

### 📚 Resources

{% hint style="info" %}
**Official 3Commas Documentation:**

- **Signal Bot Guide:** [**https://help.3commas.io/en/articles/8529406-signal-bot-custom-signal-type**](https://help.3commas.io/en/articles/8529406-signal-bot-custom-signal-type)
- **JSON Format Guide:** <https://help.3commas.io/en/articles/8894481-signal-bot-json-file-in-custom-signal-type>
- **Signal Bot FAQ:** <https://help.3commas.io/en/articles/8637909-signal-bot-faq>
- **Getting Started:** <https://help.3commas.io/en/collections/3181386-getting-started>
  {% endhint %}

{% hint style="warning" %}
**Important Reminders:**

- 3Commas is a third-party service with separate subscription costs
- Signal Bots require a paid TradingView plan for webhooks
- Exit orders are market-only (limit orders will be rejected)
- Always test with small amounts or Demo account first
- Manual trading via TradingView is always available as an alternative
  {% endhint %}
