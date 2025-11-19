# 🔔 Alerts - Backtest Version

[Got ideas? Request a feature](https://infinityalgo.canny.io/?utm_source=docs\&utm_medium=banner)

The **Backtest Version** of Infinity Algo V3.0 includes **automatic alert generation** with structured messages perfect for trading automation. Unlike the standard version, alerts are triggered programmatically without manual setup.

Quick Start: Enable Alerts in settings → Create ONE alert with "Any alert() function call" → Receive automated signals with all TP/SL levels

***

🚀 Key Differences from Standard Version

#### Standard Version

* Manual setup for each signal type
* User-defined message format
* Basic TP/SL alerts only
* Requires text formatting
* Multiple alerts needed

#### Backtest Version

* ✅ Automatic via code
* ✅ Pre-formatted structure
* ✅ All TP/SL levels included
* ✅ Ready for automation
* ✅ Single unified alert

***

⚙️ How to Enable Automatic Alerts

{% stepper %}
{% step %}
### Add Backtest Indicator

Load the **Backtest Version** to your chart from Invite-only Scripts.
{% endstep %}

{% step %}
### Configure Alert Settings

Navigate to indicator settings and enable: `Enable Alerts?`.
{% endstep %}

{% step %}
### Create Master Alert

* Right-click chart → **Add Alert**
* Set condition: **Infinity Algo Backtest** → **Any alert() function call**
* Configure notifications (webhook, email, mobile)

Create **ONLY ONE** alert - all signals flow through this single alert.
{% endstep %}
{% endstepper %}

***

📋 Alert Message Format

The backtest version generates structured messages perfect for automation, with optional percentage display for exit levels.

Standard Format (example):

{% code title="standard-output" %}
```
Exchange=BINANCE
Symbol=BTCUSDT
Side=Long
Leverage=10x
Entry=45250.50
TP1=45700.00
TP2=46150.00
TP3=46600.00
TP4=47050.00
TP5=47500.00
TP6=47950.00
SL=43250.00
SignalType=AI Sniper Buy
```
{% endcode %}

With Percentages (example):

{% code title="output-with-percentages" %}
```
Exchange=BINANCE
Symbol=BTCUSDT
Side=Long
Leverage=10x
Entry=45250.50
TP1=45700.00 (30%)
TP2=46150.00 (25%)
TP3=46600.00 (20%)
TP4=47050.00 (15%)
TP5=47500.00 (7%)
TP6=47950.00 (3%)
SL=43250.00 (100%)
SignalType=AI Sniper Buy
```
{% endcode %}

New Feature: Enable `📊 Show Exit % in Alerts?` in settings to include exit percentages directly in alert messages.

Core Fields (Always Present)

* `Exchange` → Trading venue (auto-detected)
* `Symbol` → Trading pair/ticker
* `Side` → Long or Short position
* `Leverage` → Position leverage
* `Entry` → Entry price at signal

Conditional Fields

* `TP1-TP6` → Only if enabled in settings
* `SL` → Only if Stop Loss enabled
* `SignalType` → For HL/AI Sniper modes

Optional Percentages

* Exit percentages → When `Show Exit % in Alerts?` enabled
* Format: `Price (XX%)`
* SL always shows `(100%)`

Multiple Take Profit Strategy

* When multiple TPs are enabled, the alert includes all active levels for sophisticated exit strategies:
  * Partial exits at each TP level based on your configured percentages
  * Scale out of positions gradually to lock in profits
  * Risk reduction as price moves favorably
  * Optional percentages displayed directly in alerts for automation

Understanding Exit Percentages

Without Percentages (Default):

* Clean price levels only
* Bot needs separate configuration for exit sizes
* Simpler format for manual traders

With Percentages Enabled:

* Each level shows `Price (XX%)`
* Bot can parse exit sizes directly from alert
* No additional configuration needed

Example Use Case: Your bot receives `TP1=45700.00 (30%)` and knows to exit 30% of the position at 45700.00 without needing a separate configuration file.

***

💡 Advanced Configuration

Customization Options

Custom Symbol Override

* Use the **Alert Ticker** setting to: send alerts for a different symbol, normalize naming conventions for your broker, handle exchange-specific formatting.
* Example: Set `XBTUSD` instead of `BTCUSDT` for BitMEX compatibility

Leverage Customization

* The **Alert Leverage** setting allows different leverage from display settings, exchange-specific limits (e.g., max 20x), risk management overrides, and position sizing calculations.

***

🛠️ Real-World Setup Examples

#### Example 1: Simple Long Entry

Configuration:

* Exit Type: `Percentage`
* Only TP1: `2%` enabled
* Stop Loss: `3%` enabled
* Leverage: `5x`
* **Show Exit %:** Disabled ❌

Output:

```
Exchange=BINANCE
Symbol=ETHUSDT
Side=Long
Leverage=5x
Entry=2250.75
TP1=2295.77
SL=2183.23
```

#### Example 2: Complex Multi-TP Strategy

Configuration:

* All 6 TPs enabled
* Stop Loss enabled
* Signal Mode: `AI Sniper`
* Leverage: `10x`
* **Show Exit %:** Enabled ✅

Output with Percentages:

```
Exchange=BINANCE
Symbol=BTCUSDT
Side=Short
Leverage=10x
Entry=45000.00
TP1=44550.00 (30%)
TP2=44100.00 (25%)
TP3=43650.00 (20%)
TP4=43200.00 (15%)
TP5=42750.00 (7%)
TP6=42300.00 (3%)
SL=46350.00 (100%)
SignalType=AI Sniper Sell
```

***

⚠️ Critical Considerations

Must-Know Setup Rules

One Alert Rules All

* ✅ Create **ONLY ONE** TradingView alert for each pair and timeframe
* ✅ Use `Any alert() function call` as trigger
* ✅ All signals (Long/Short/TP/SL) flow through this single alert

Processing & Timing

* ⏱️ Alerts fire on **bar close** (confirmed signals)
* ⏱️ Account for TradingView processing delay (\~1-3 seconds)
* ⏱️ Consider network latency for webhooks
* ⏱️ Add retry logic in your automation

***

🔍 Troubleshooting Guide

<details>

<summary>No alerts firing</summary>

Possible Causes

* Settings misconfigured

Solution

* Enable `Enable Alerts` in settings
* Verify alert condition is `Any alert() function call`
* Ensure using Backtest version (not standard)

</details>

<details>

<summary>Wrong symbol</summary>

Possible Causes

* Override active

Solution

* Clear `Alert Ticker` field to use current chart
* Check exchange formatting requirements

</details>

<details>

<summary>Missing TP/SL levels</summary>

Possible Causes

* Not configured

Solution

* Enable desired levels in Exit Settings
* Set Exit Type to `Percentage`
* Configure TP percentages

</details>

<details>

<summary>Webhook not receiving</summary>

Possible Causes

* Connection issue

Solution

* Test webhook URL with webhook.site
* Check message format compatibility
* Verify JSON formatting if needed

</details>

<details>

<summary>Duplicate alerts</summary>

Possible Causes

* Multiple alerts created

Solution

* Delete all alerts
* Create only ONE master alert
* Check alert history

</details>

***

🎯 Integration Methods

Choose your integration path based on your technical skills and needs:

* 🚀 No-Code (2 min setup)
* ⚙️ Low-Code (Flexible)
* 🔧 Pro (Full Control)

Fastest Setup - Zero Programming Required

Option 1: TradingView → Telegram/Discord via Webhook Bridge

{% stepper %}
{% step %}
### Create Webhook Bridge

1. Go to [tradingview.to](https://tradingview.to/)
2. Create free account
3. Generate webhook URL
4. Select destination (Telegram/Discord)
{% endstep %}

{% step %}
### Configure TradingView Alert

1. Create alert with `Any alert() function call`
2. Paste webhook URL from tradingview.to
3. Done! Messages auto-forward to your channel
{% endstep %}
{% endstepper %}

Option 2: Direct Discord Webhook

```
1. Open Discord Server Settings
2. Integrations → Webhooks → New Webhook
3. Copy webhook URL
4. Paste in TradingView alert
```

Perfect for: Traders who just want signals in Telegram/Discord without any coding

Visual Automation Tools

Using Pipedream/Make (formerly Integromat)

Why use this?

* Reformat messages
* Add conditional logic
* Send to multiple destinations
* Add retry logic
* No server needed

Example Flow

```
1. HTTP Webhook trigger (receives from TradingView)
2. Parse the message
3. Format for destination
4. Send to:
   - Telegram Bot
   - Discord Webhook
   - Google Sheets
   - Email
   - Database
```

Sample Pipedream Workflow (parser example)

{% code title="pipedream-parser.js" %}
```javascript
export default defineComponent({
  async run({ steps, $ }) {
    // Parse incoming alert
    const lines = steps.trigger.event.body.split('\n');
    const data = {};

    lines.forEach(line => {
      const [key, value] = line.split('=');
      data[key] = value;
    });

    // Format for Discord
    return {
      content: `🔔 ${data.Symbol} Signal`,
      embeds: [{\
        title: `${data.Side} Position`,\
        fields: [\
          { name: "Entry", value: data.Entry, inline: true },\
          { name: "TP1", value: data.TP1, inline: true },\
          { name: "SL", value: data.SL, inline: true }\
        ],\
        color: data.Side === "Long" ? 0x00ff00 : 0xff0000\
      }]
    };
  }
});
```
{% endcode %}

Perfect for: Semi-technical users who want customization without managing servers

Custom Server Implementation

For maximum control, run your own webhook endpoint:

{% code title="webhook-server.py" %}
```python
from fastapi import FastAPI, Request
import hmac
import hashlib

app = FastAPI()

@app.post("/webhook")
async def handle_alert(request: Request):
    # Verify TradingView signature (optional)
    body = await request.body()

    # Parse alert
    data = parse_alert(body.decode())

    # Custom logic
    if data['Symbol'] in WATCHLIST:
        # Execute trade
        execute_trade(data)

        # Log to database
        log_trade(data)

        # Notify multiple channels
        notify_telegram(data)
        notify_discord(data)

    return {"status": "processed"}
```
{% endcode %}

Advanced Features:

* Request verification
* Database logging
* Multi-exchange execution
* Custom risk management
* Retry logic & error handling

Perfect for: Developers who need custom logic, authentication, or complex routing

***

🤖 Popular Bot Integrations

Cornix Bot (Automated Trading)

* Easiest automated execution:
  1. Get Cornix webhook URL from bot settings
  2. Paste in TradingView alert webhook field
  3. Cornix auto-parses and executes trades

Supports:

* Multiple exchanges (Binance, Bybit, etc.)
* Position management
* Risk settings
* DCA strategies

No coding required! Cornix understands Infinity Algo's format directly

Other Trading Bots (comparison)

| Bot Service   | Setup Difficulty | Features        | Best For      |
| ------------- | ---------------: | --------------- | ------------- |
| Cornix        |        ⭐ Easiest | Full automation | Beginners     |
| 3Commas       |          ⭐⭐ Easy | DCA, Grid bots  | Intermediate  |
| TradersPost   |          ⭐⭐ Easy | Multi-broker    | Stock traders |
| PineConnector |       ⭐⭐⭐ Medium | MT4/MT5 bridge  | Forex         |
| Custom Bot    |       ⭐⭐⭐⭐⭐ Hard | Unlimited       | Developers    |

***

⚠️ Important Limits & Gotchas

* TradingView requires **paid plan** for webhooks
* Use `Any alert() function call` as condition
* Max 15 alerts in 3 minutes (TradingView limit)
* Discord: \~30 messages/minute per webhook
* Telegram: \~30 messages/second total, 1/second per chat

***

📚 Quick Start Recommendations

* I just want signals in Telegram/Discord\
  Use **tradingview.to** (Track A) - 2 minute setup, no coding needed
* I want to auto-trade on Binance/Bybit\
  Use **Cornix Bot** - Paste webhook URL, configure risk settings, done
* I need custom formatting or multiple destinations\
  Use **Pipedream or Make** (Track B) - Visual workflow builders
* I'm a developer and need full control\
  Build custom endpoint (Track C) - See Pro tab for examples

***

✅ Summary

The Backtest Version provides:

* ✅ Zero manual setup - All alerts handled automatically
* ✅ Structured format - Parse-ready for any platform
* ✅ Complete data - All TP/SL levels in one message
* ✅ Signal identification - Know exactly which strategy triggered
* ✅ Direct integration - Works with any webhook endpoint
* ✅ Backtesting accuracy - Realistic alert generation for testing

Perfect for automated trading systems, backtesting validation, and hands-free alert management.

[Previous📋 Settings Spreadsheet](settings-spreadsheet.md) [NextInfinity Dashboard](../infinity-dashboard/)

Last updated 2 months ago

[privacy policy](https://infinityalgo.com/privacy/)
