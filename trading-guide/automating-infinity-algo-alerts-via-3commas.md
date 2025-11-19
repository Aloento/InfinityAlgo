# 🔄 Automating Infinity Algo Alerts via 3Commas

[Got ideas? Request a feature](https://infinityalgo.canny.io/?utm_source=docs\&utm_medium=banner)

Connect Infinity Algo signals directly to 3Commas for automated trading execution.

***

🎯 Three Integration Methods

{% stepper %}
{% step %}
### Reversal Bot — 🔄

What it does:

* Switches Long ↔ Short automatically
* One bot handles both directions
* Closes opposite position before opening new

Best for:

* ✅ Trending markets
* ✅ Active trading
* ✅ Maximum efficiency
* ✅ Less alert management

Setup Requirements:

```
Direction: Reversal (both)
Pairs: Single or Multi-pair (up to 200)
Alerts: 2 total
- Buy Signal → enter_long
- Sell Signal → enter_short
```

Reversal Behavior:

* Spot: With Reverse position ON, opposite signal closes & flips; OFF ignores opposite signals
* Futures Hedge Mode ON: Enable "Reverse position" to flip positions
* Futures Hedge Mode OFF: Bot automatically closes opposite before opening new

Recommendation: For simplicity, we recommend one pair per bot for reversal workflows.
{% endstep %}

{% step %}
### Exit Without Disabling Bot — 🎯 Clean Exit

What it does:

* Closes position cleanly
* Bot stays active for next signal
* No manual re-enabling needed

Best for:

* ✅ Continuous trading
* ✅ Quick re-entry
* ✅ Automated workflow
* ✅ Active strategies

Setup Requirements:

```
Direction: Long or Short
Alerts: 3 total
- Entry: enter_long/enter_short
- Exit: exit_long/exit_short
- Re-entry: enter_long/enter_short
```

Pro Tip: Exit signals use market execution only — limit orders on exits will be rejected
{% endstep %}

{% step %}
### Disable Bot & Close All — ⏹️ Panic Stop

What it does:

* Closes all positions at market
* Disables bot completely
* Requires manual re-enable

Best for:

* ✅ Emergency stops
* ✅ End of session
* ✅ Risk events
* ✅ Manual intervention

Setup Requirements:

```
Action: disable
Sub-action: market_close
Note: Bot must be manually re-enabled
```

Warning: Bot will NOT auto-restart on next signal — you must manually enable it again
{% endstep %}
{% endstepper %}

***

⚙️ Step 1: Configure Signal Bot

{% stepper %}
{% step %}
### Step 1 — Configure Signal Bot (3Commas)

Navigate to 3Commas:

1. Log in → 3Commas.io
2. Bots → Signal Bot → Create Bot
3. Configure with these settings:

Name\
e.g. Infinity Algo BTC

Exchange\
Select your exchange

Pairs\
Single or Multi (up to 200)

Alert Type\
Custom Signal

Direction\
Long / Short / Reversal (both)

TP/SL\
Set here or via webhook

Risk Caps\
Max Investment, Leverage

For multi-pair bots, also set Max active SmartTrades.
{% endstep %}

{% step %}
### Step 2 — Get Webhook Credentials

After saving your bot, find "Message for deal start signal" and copy:

Your Unique Credentials

```
{
  "secret":   "ab12cd34.ef56gh78…",   // Keep this private!
  "bot_uuid": "f1a2b3c4-…-9d0e1f2a",  // Your bot's ID
  "action":   "enter_long",
  "tv_exchange": "{{exchange}}",
  "tv_instrument": "{{ticker}}"
}
```

Security: Never share your `secret` token - it controls your bot! Signal Bots no longer accept old `bot_id`/`email_token` pairs.
{% endstep %}

{% step %}
### Step 3 — Create TradingView Alerts

Alert Configuration

* Condition: Match your Infinity Algo signal exactly
* Options: ✅ Once Per Bar Close (not "Once Per Bar")
* Webhook URL: `https://api.3commas.io/signal_bots/webhooks`
* Message: JSON template with YOUR-SECRET & YOUR-UUID

Important: Alert condition must match your Infinity Algo signal names exactly, including any numeric prefixes
{% endstep %}
{% endstepper %}

***

📝 JSON Templates

Required Fields: All signals must include `secret`, `bot_uuid`, `action`, `tv_exchange`, and `tv_instrument`

enter\_long.json

```
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

Note: For limit entry, add `"price"` or `"price_percent"` with optional `"price_percent_ref_type"`

enter\_short.json

```
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

exit\_long.json

```
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

Note: Exit orders are market-only - don't add `"order_type": "limit"`

exit\_short.json

```
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

disable\_bot.json

```
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

This disables the bot completely — manual re-enable required!

***

⚡ Quick Reference

price\_percent

* Purpose: TP distance from entry
* Values: Integer (1 = 1%, 2 = 2%)

volume\_percent

* Purpose: % of position to close
* Values: Must sum to 100%

trigger\_price\_percent

* Purpose: Stop loss distance
* Values: Integer (1 = 1% loss)

currency\_type

* Purpose: Order size unit
* Values: `quote`, `base`, `margin_percent`, `position_percent`

amount

* Purpose: Position size
* Values: Number based on currency\_type

max\_lag

* Purpose: Reject stale signals
* Values: Seconds (300 = 5 min)

timestamp

* Purpose: Signal freshness
* Values: Always use `{{timenow}}`

price\_percent\_ref\_type

* Purpose: Price reference for limit
* Values: `current_price`, `base_entry_price`, `avg_entry_price`

***

🎯 Which Method Should You Use?

Feature comparison (summary):

* Reversal Bot: Best for trending markets, needs 2 alerts, bot always in position, always active, automatic re-entry. Ideal for active/confident traders.
* Clean Exit: Best for continuous trading, needs 3 alerts (entry/exit/re-entry), flexible gaps in position state, always active, automatic re-entry. Ideal for flexible/cautious traders.
* Panic Stop: Best for emergency stops, needs 1 alert, ends with fully closed positions, bot disabled (manual re-enable required). Ideal for risk-averse traders.

Choose Reversal if you:

* Trade trending pairs
* Trust your signals
* Want set-and-forget

Choose Clean Exit if you:

* Need position control
* Trade multiple pairs
* Want gap periods

***

🚀 Advanced Features

* Multiple TPs, Trailing Stop, Bot Filters
* Up to 8 Take Profit Levels (UI supports up to 4, JSON supports up to 8). Volumes must total 100%. Can mix limit & market orders. Trailing only on last step.

Example: 8-Level TP with Trailing

```
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

Dynamic Stop Loss — Trailing Stop Configuration

```
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

Trails 0.5% behind highest profit

Price Deviation & Deal Close Conditions (set in bot UI, not JSON):

* Price deviation filters: Prevent unfavorable entries
* Minimum profit: May block exits until profit target met

If exits don't close, check your bot's Minimum profit / Deal close conditions.

***

🛠️ Troubleshooting Checklist

* Valid Credentials: JSON must include valid `secret` and `bot_uuid`
* Required Fields: Always include `tv_exchange` and `tv_instrument` in ALL signals
* Correct Webhook URL: Must be exactly `https://api.3commas.io/signal_bots/webhooks`
* Alert Timing: Alerts fire Once Per Bar Close (not "Once Per Bar")
* One Alert Per Action: Never combine entry & exit in one JSON
* Field Names: Use `price_percent` not `price_deviation`
* Volumes Sum to 100: All `volume_percent` must total exactly 100
* Exit Orders: Exit signals use market execution only — no limit orders
* Signal Freshness: Include `max_lag` and `timestamp` to prevent stale signals
* Bot Re-enabling: If using `disable`, must manually re-enable bot
* Exit Not Working: Check bot's Minimum profit / Deal close conditions

***

📖 JSON Field Glossary

`secret` — Private bot token (Required — copy exactly from Step 2)\
`bot_uuid` — Unique Signal Bot ID (Required — copy from Step 2)\
`action` — Bot command (Required — `enter_long`, `enter_short`, `exit_long`, `exit_short`, `disable`)\
`tv_exchange` — TradingView exchange (Required — always `{{exchange}}`)\
`tv_instrument` — TradingView pair (Required — always `{{ticker}}`)\
`positions_sub_action` — When action is `disable` (`market_close` → flatten & disable; `cancel` → cancel only)\
`order.amount` — Position size (based on `currency_type`)\
`order.order_type` — Entry order type (`market` or `limit`; limit needs `price` or `price_percent`)\
`currency_type` — Unit for amount (`quote`, `base`, `margin_percent`, `position_percent`)\
`price` — Exact limit price (for limit orders)\
`price_percent` — TP/limit distance (Integer: 1 = 1%)\
`price_percent_ref_type` — Reference for percent (`current_price`, `base_entry_price`, `avg_entry_price`)\
`volume_percent` — % to close at each TP (1-100; must sum to 100%)\
`trigger_price_percent` — Stop loss trigger (Integer: 1 = 1% loss)\
`max_lag` — Signal age limit (Seconds; 300 = 5 minutes)\
`timestamp` — Current time (Always `{{timenow}}`)

***

📚 Resources

Official 3Commas Documentation:

* Signal Bot Guide: https://help.3commas.io/en/articles/8529406-signal-bot-custom-signal-type
* JSON Format Guide: https://help.3commas.io/en/articles/8894481-signal-bot-json-file-in-custom-signal-type
* Signal Bot FAQ: https://help.3commas.io/en/articles/8637909-signal-bot-faq
* Getting Started: https://help.3commas.io/en/collections/3181386-getting-started

Important Reminders:

* 3Commas is a third-party service with separate subscription costs
* Signal Bots require a paid TradingView plan for webhooks
* Exit orders are market-only (limit orders will be rejected)
* Always test with small amounts or Demo account first
* Manual trading via TradingView is always available as an alternative

***

Last updated 2 months ago

Was this helpful?
