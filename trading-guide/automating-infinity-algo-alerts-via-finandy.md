# 🔄 Automating Infinity Algo Alerts via Finandy

[Got ideas? Request a feature](https://infinityalgo.canny.io/?utm_source=docs\&utm_medium=banner)

***

#### 🎯 Integration Method for Indicators

**📊 Two-Alert Setup**

Separate Buy/Sell Alerts (Required for Indicators)

What it does:

* Two distinct alerts (Buy & Sell)
* Clear signal separation
* Works with any indicator
* No code access needed

Best for:

* ✅ All Infinity Algo users
* ✅ Simple setup
* ✅ Clear control
* ✅ Testing & production

Alert Requirements

```
Alerts: 2 total (indicators can only send one signal type per alert)
- Buy Signal → side: "buy"
- Sell Signal → side: "sell"
Position Side: Both/Long only/Short only
```

Position Side Options:

* Both → Opens Long on buy, Short on sell (reversal in one-way mode)
* Long only → Only long trades
* Short only → Only short trades
* Strategy → For TradingView strategies only (NOT for indicators!)

Important: Since Infinity Algo is an indicator, you MUST create two separate alerts. The "side" field must be included with value "buy" or "sell" (lowercase). Strategy placeholders like `{{strategy.order.action}}` won't work.

***

#### ⚙️ Configure Finandy Webhook (Step 1–5)

{% stepper %}
{% step %}
### Step 1: Configure Finandy Webhook

Navigate to Finandy:

1. Log in → Finandy.com
2. Algo-trading → TradingView Signals
3. Create new signal (webhook)
4. Configure main settings:

Field — Value

* Name — e.g. _Infinity Algo Signals_
* Currency pair — `{{ticker}}` (one hook for all)
* Position side — Both or Long only / Short only
* Save — Shows Signal URL & Message

Do NOT select "Strategy" for Position side — that's only for TradingView strategies, not indicators.
{% endstep %}

{% step %}
### Step 2: Get Webhook Credentials

After saving, Finandy displays your unique webhook details. Copy exactly as shown:

* Signal URL: Copy the exact URL displayed for your signal
* Signal Message: Copy the template with your secret token

Security: Keep your `secret` token private! By default, Finandy only accepts requests from TradingView IPs.
{% endstep %}

{% step %}
### Step 3: Create TWO TradingView Alerts

You MUST create two separate alerts - one for buy signals and one for sell signals.

Alert Configuration:

* Condition — Infinity Algo → Choose your signal
* Options — Once Per Bar Close
* Webhook URL — Paste the exact Signal URL from Step 2
* Message — JSON template (see below)
{% endstep %}

{% step %}
### JSON Templates for Each Alert

Create this alert on a Buy condition (buy\_signal.json):

{% code title="buy_signal.json" %}
```json
{
  "name": "Infinity Algo Signals",
  "secret": "YOUR-SECRET",
  "side": "buy",
  "symbol": "{{ticker}}"
}
```
{% endcode %}

Required: `"side": "buy"` (lowercase)

Create this alert on a Sell condition (sell\_signal.json):

{% code title="sell_signal.json" %}
```json
{
  "name": "Infinity Algo Signals",
  "secret": "YOUR-SECRET",
  "side": "sell",
  "symbol": "{{ticker}}"
}
```
{% endcode %}

Required: `"side": "sell"` (lowercase)

Advanced — Override TP settings from alert (custom\_tp.json):

{% code title="custom_tp.json" %}
```json
{
  "name": "Infinity Algo Signals",
  "secret": "YOUR-SECRET",
  "side": "buy",
  "symbol": "{{ticker}}",
  "tp": {
    "orders": [
      { "ofs": "1.0", "price": "", "piece": "25" },
      { "ofs": "2.0", "price": "", "piece": "25" },
      { "ofs": "3.0", "price": "", "piece": "25" },
      { "ofs": "4.0", "price": "", "piece": "25" }
    ],
    "update": true
  }
}
```
{% endcode %}

Note: Tick the TP module checkbox in Finandy UI to accept values from signals, and include `"update": true`.
{% endstep %}

{% step %}
### Step 4: Set TP & SL Inside Finandy (Optional)

Take Profit (TP)

1. Open the webhook you created → Take Profit (TP) tab
2. Tick Enable TP → choose Limit or Market
3. Number of orders → choose how many levels
4. Price offset (%) and Order distribution (%) per tier
5. Level re-ordering keeps percentages intact when you DCA
6. To accept TP overrides from signals, tick the checkbox to enable

All TP orders sit on the exchange; no extra TradingView alerts required.

Stop Loss (SL)

1. Open webhook → Stop Loss (SL) tab
2. Tick Enable SL
3. Choose Market or Limit
4. Set Price offset (%)
5. Optional: Enable Trailing

SL orders execute on exchange for fastest execution.

Real vs Virtual Orders:

* Real = orders placed on the exchange immediately
* Virtual = managed by terminal until trigger conditions are met

Choose based on your exchange and needs.
{% endstep %}

{% step %}
### Step 5: Test & Monitor

* Interface → Signal log shows every webhook received with "OK" or error code
* Start with tiny sizes to verify setup
* Check that both buy AND sell alerts are working
* Use the Signal Log to see received JSON and actions taken

Testing Checklist:

* ✅ Created TWO separate alerts
* ✅ Buy alert has `"side": "buy"` (lowercase)
* ✅ Sell alert has `"side": "sell"` (lowercase)
* ✅ Both use same webhook URL and secret
* ✅ Signal Log shows both types of signals
{% endstep %}
{% endstepper %}

***

#### ⚡ Alert Setup Examples

For "Buy Signal - Smart":

1. Condition: Infinity Algo → "Buy Signal - Smart"
2. Webhook URL: Your Finandy Signal URL
3. Message: Buy JSON with `"side": "buy"`

For "Sell Signal - Smart":

1. Condition: Infinity Algo → "Sell Signal - Smart"
2. Webhook URL: Same Finandy Signal URL
3. Message: Sell JSON with `"side": "sell"`

***

#### 🎯 Position Side Configuration

Your Trading Style — Position Side Setting — Result

* Long & Short (Reversal) — Both — Closes opposite before opening new (one-way mode)
* Long Only — Long only — Ignores sell signals
* Short Only — Short only — Ignores buy signals
* Strategy Mode — Strategy — Only for TradingView strategies

Hedge Mode Warning: In hedge mode, use Long only or Short only for indicators. Position side "Both" won't close correctly in hedge mode - it's designed for one-way mode reversals.

***

<details>

<summary>🛠️ Troubleshooting Checklist</summary>

Issue — Solution

* 403 error — Wrong **secret** or URL missing **https://**
* "Unknown side" — `side` must be exactly `"buy"` or `"sell"` (lowercase)
* No orders — Check Position Side isn't set to "Strategy"
* Only buys work — Did you create the sell alert?
* Wrong pair — Verify `{{ticker}}` placeholder
* No reversal — Check Position Side = "Both" and one-way mode enabled
* Hedge issues — Use Long only/Short only in hedge mode, not "Both"

</details>

<details>

<summary>🔤 JSON Key Reference (Finandy)</summary>

Key — Meaning — Details

* `name` — Webhook identifier — Any descriptive name
* `secret` — Auth token from signal — Keep private!
* `side` — Trade direction — Required: `"buy"` or `"sell"` (lowercase)
* `symbol` — Trading pair — Usually `{{ticker}}`
* `tp.orders` — TP levels array — Optional override
* `ofs` — % offset from entry — String: "1.0" = 1%
* `piece` — % of position — Percentages that sum to intended total
* `update` — Apply new settings — `true` to override TP from signal

</details>

<details>

<summary>📚 Resources</summary>

Official Finandy Documentation:

* Main Docs: https://docs.finandy.com/
* TradingView Connection: https://docs.finandy.com/algo-trading/signals-tradingview/connection-and-configuration/indicator-strategy-connection
* Signal Interface: https://docs.finandy.com/algo-trading/signals-tradingview/interface
* Position Management: https://docs.finandy.com/algo-trading/signals/interface/open

Important Reminders:

* Finandy is a third-party service with separate costs
* Indicators require TWO alerts (buy and sell separately)
* The `"side"` field is mandatory and must be lowercase
* Test with small amounts first
* Manual trading via TradingView is always available

</details>

***

Last updated 2 months ago

This site uses cookies to deliver its service and to analyze traffic. By browsing this site, you accept the [privacy policy](https://infinityalgo.com/privacy/).
