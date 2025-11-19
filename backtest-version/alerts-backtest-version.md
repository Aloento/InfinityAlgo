# 🔔 Alerts - Backtest Version

The **Backtest Version** of Infinity Algo V3.0 includes **automatic alert generation** with structured messages perfect for trading automation. Unlike the standard version, alerts are triggered programmatically without manual setup.

{% hint style="success" %}
**Quick Start:** Enable Alerts in settings → Create ONE alert with "Any alert() function call" → Receive automated signals with all TP/SL levels
{% endhint %}

---

### 🚀 Key Differences from Standard Version

{% columns %}
{% column width="50%" %}

#### 📋 Standard Version

- Manual setup for each signal type
- User-defined message format
- Basic TP/SL alerts only
- Requires text formatting
- Multiple alerts needed
  {% endcolumn %}

{% column %}

#### 🤖 Backtest Version

- ✅ Automatic via code
- ✅ Pre-formatted structure
- ✅ All TP/SL levels included
- ✅ Ready for automation
- ✅ Single unified alert
  {% endcolumn %}
  {% endcolumns %}

---

### ⚙️ How to Enable Automatic Alerts

{% stepper %}
{% step %}

#### Add Backtest Indicator

Load the **Backtest Version** to your chart from Invite-only Scripts
{% endstep %}

{% step %}

#### Configure Alert Settings

Navigate to indicator settings and enable: `Enable Alerts?`
{% endstep %}

{% step %}

#### Create Master Alert

1. Right-click chart → **Add Alert**
2. Set condition: **Infinity Algo Backtest** → **Any alert() function call**
3. Configure notifications (webhook, email, mobile)

{% hint style="warning" %}
Create **ONLY ONE** alert - all signals flow through this single alert
{% endhint %}
{% endstep %}
{% endstepper %}

---

### 📋 Alert Message Format

The backtest version generates structured messages perfect for automation, with optional percentage display for exit levels.

{% tabs %}
{% tab title="📊 Standard Format" %}
{% code title="standard-output:" overflow="wrap" %}

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
{% endtab %}

{% tab title="📊 With Percentages" %}
{% code title="output-with-percentages:" overflow="wrap" %}

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

{% hint style="success" %}
**New Feature:** Enable `📊 Show Exit % in Alerts?` in settings to include exit percentages directly in alert messages
{% endhint %}
{% endtab %}

{% tab title="🎯 Message Components" %}

#### Core Fields (Always Present)

- `Exchange` → Trading venue (auto-detected)
- `Symbol` → Trading pair/ticker
- `Side` → Long or Short position
- `Leverage` → Position leverage
- `Entry` → Entry price at signal

#### Conditional Fields

- `TP1-TP6` → Only if enabled in settings
- `SL` → Only if Stop Loss enabled
- `SignalType` → For HL/AI Sniper modes

#### Optional Percentages

- Exit percentages → When `Show Exit % in Alerts?` enabled
- Format: `Price (XX%)`
- SL always shows `(100%)`
  {% endtab %}
  {% endtabs %}

#### Multiple Take Profit Strategy

When multiple TPs are enabled, the alert includes all active levels for sophisticated exit strategies:

- **Partial exits** at each TP level based on your configured percentages
- **Scale out** of positions gradually to lock in profits
- **Risk reduction** as price moves favorably
- **Optional percentages** displayed directly in alerts for automation

<details>

<summary><strong>📊 Understanding Exit Percentages</strong></summary>

The `Show Exit % in Alerts?` setting adds position exit percentages to each level, making it easier for bots to parse exit sizes:

**Without Percentages (Default):**

- Clean price levels only
- Bot needs separate configuration for exit sizes
- Simpler format for manual traders

**With Percentages Enabled:**

- Each level shows `Price (XX%)`
- Bot can parse exit sizes directly from alert
- No additional configuration needed

{% hint style="info" %}
**Example Use Case:** Your bot receives `TP1=45700.00 (30%)` and knows to exit 30% of the position at 45700.00 without needing a separate configuration file.
{% endhint %}

</details>

---

### 💡 Advanced Configuration

#### Customization Options

<details>

<summary><strong>🏷️ Custom Symbol Override</strong></summary>

Use the **Alert Ticker** setting to:

- Send alerts for a different symbol
- Normalize naming conventions for your broker
- Handle exchange-specific formatting

Example: Set `XBTUSD` instead of `BTCUSDT` for BitMEX compatibility

</details>

<details>

<summary><strong>⚡ Leverage Customization</strong></summary>

The **Alert Leverage** setting allows:

- Different leverage from display settings
- Exchange-specific limits (e.g., max 20x)
- Risk management overrides
- Position sizing calculations

</details>

---

### 🛠️ Real-World Setup Examples

#### Example 1: Simple Long Entry

{% columns %}
{% column width="50%" %}
**Configuration:**

- Exit Type: `Percentage`
- Only TP1: `2%` enabled
- Stop Loss: `3%` enabled
- Leverage: `5x`
- **Show Exit %:** `Disabled` ❌
  {% endcolumn %}

{% column %}
{% code title="Output" %}

```
Exchange=BINANCE
Symbol=ETHUSDT
Side=Long
Leverage=5x
Entry=2250.75
TP1=2295.77
SL=2183.23
```

{% endcode %}
{% endcolumn %}
{% endcolumns %}

#### Example 2: Complex Multi-TP Strategy

{% columns %}
{% column width="50%" %}
**Configuration:**

- All 6 TPs enabled
- Stop Loss enabled
- Signal Mode: `AI Sniper`
- Leverage: `10x`
- **Show Exit %:** `Enabled` ✅
  {% endcolumn %}

{% column %}
{% code title="Output with Percentages" %}

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

{% endcode %}
{% endcolumn %}
{% endcolumns %}

---

### ⚠️ Critical Considerations

{% hint style="danger" %}
**Must-Know Setup Rules**

#### One Alert Rules All

- ✅ Create **ONLY ONE** TradingView alert for each pair and timeframe
- ✅ Use `Any alert() function call` as trigger
- ✅ All signals (Long/Short/TP/SL) flow through this single alert

#### Processing & Timing

- ⏱️ Alerts fire on **bar close** (confirmed signals)
- ⏱️ Account for TradingView processing delay (\~1-3 seconds)
- ⏱️ Consider network latency for webhooks
- ⏱️ Add retry logic in your automation
  {% endhint %}

---

### 🔍 Troubleshooting Guide

| Issue                     | Possible Causes         | Solution                                                                                                                                                                       |
| ------------------------- | ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **No alerts firing**      | Settings misconfigured  | <p>• Enable <code>Enable Alerts</code> in settings<br>• Verify alert condition is <code>Any alert() function call</code><br>• Ensure using Backtest version (not standard)</p> |
| **Wrong symbol**          | Override active         | <p>• Clear <code>Alert Ticker</code> field to use current chart<br>• Check exchange formatting requirements</p>                                                                |
| **Missing TP/SL levels**  | Not configured          | <p>• Enable desired levels in Exit Settings<br>• Set Exit Type to <code>Percentage</code><br>• Configure TP percentages</p>                                                    |
| **Webhook not receiving** | Connection issue        | <p>• Test webhook URL with webhook.site<br>• Check message format compatibility<br>• Verify JSON formatting if needed</p>                                                      |
| **Duplicate alerts**      | Multiple alerts created | <p>• Delete all alerts<br>• Create only ONE master alert<br>• Check alert history</p>                                                                                          |

---

### 🎯 Integration Methods

Choose your integration path based on your technical skills and needs:

{% tabs %}
{% tab title="🚀 No-Code (2 min setup)" %}

#### Fastest Setup - Zero Programming Required

**Option 1: TradingView → Telegram/Discord via Webhook Bridge**

{% stepper %}
{% step %}

#### Create Webhook Bridge

1. Go to [tradingview.to](https://tradingview.to)
2. Create free account
3. Generate webhook URL
4. Select destination (Telegram/Discord)
   {% endstep %}

{% step %}

#### Configure TradingView Alert

1. Create alert with `Any alert() function call`
2. Paste webhook URL from tradingview\.to
3. Done! Messages auto-forward to your channel
   {% endstep %}
   {% endstepper %}

**Option 2: Direct Discord Webhook**

{% code title="Discord Setup" %}

```
1. Open Discord Server Settings
2. Integrations → Webhooks → New Webhook
3. Copy webhook URL
4. Paste in TradingView alert
```

{% endcode %}

{% hint style="success" %}
**Perfect for:** Traders who just want signals in Telegram/Discord without any coding
{% endhint %}
{% endtab %}

{% tab title="⚙️ Low-Code (Flexible)" %}

#### Visual Automation Tools

**Using Pipedream/Make (formerly Integromat)**

**Why use this?**

- Reformat messages
- Add conditional logic
- Send to multiple destinations
- Add retry logic
- No server needed

{% code title="Example Flow" %}

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

{% endcode %}

**Sample Pipedream Workflow**

{% code title="pipedream-parser.js" %}

```javascript
export default defineComponent({
  async run({ steps, $ }) {
    // Parse incoming alert
    const lines = steps.trigger.event.body.split("\n");
    const data = {};

    lines.forEach((line) => {
      const [key, value] = line.split("=");
      data[key] = value;
    });

    // Format for Discord
    return {
      content: `🔔 ${data.Symbol} Signal`,
      embeds: [
        {
          title: `${data.Side} Position`,
          fields: [
            { name: "Entry", value: data.Entry, inline: true },
            { name: "TP1", value: data.TP1, inline: true },
            { name: "SL", value: data.SL, inline: true },
          ],
          color: data.Side === "Long" ? 0x00ff00 : 0xff0000,
        },
      ],
    };
  },
});
```

{% endcode %}

{% hint style="info" %}
**Perfect for:** Semi-technical users who want customization without managing servers
{% endhint %}
{% endtab %}

{% tab title="🔧 Pro (Full Control)" %}

#### Custom Server Implementation

For maximum control, run your own webhook endpoint:

{% code title="webhook-server.py" lineNumbers="true" %}

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

**Advanced Features:**

- Request verification
- Database logging
- Multi-exchange execution
- Custom risk management
- Retry logic & error handling

{% hint style="warning" %}
**Perfect for:** Developers who need custom logic, authentication, or complex routing
{% endhint %}
{% endtab %}
{% endtabs %}

---

### 🤖 Popular Bot Integrations

#### Cornix Bot (Automated Trading)

{% columns %}
{% column width="60%" %}
**Easiest automated execution:**

1. Get Cornix webhook URL from bot settings
2. Paste in TradingView alert webhook field
3. Cornix auto-parses and executes trades

**Supports:**

- Multiple exchanges (Binance, Bybit, etc.)
- Position management
- Risk settings
- DCA strategies
  {% endcolumn %}

{% column %}
{% hint style="success" %}
**No coding required!** Cornix understands Infinity Algo's format directly
{% endhint %}
{% endcolumn %}
{% endcolumns %}

#### Other Trading Bots

| Bot Service       | Setup Difficulty | Features        | Best For      |
| ----------------- | ---------------- | --------------- | ------------- |
| **Cornix**        | ⭐ Easiest       | Full automation | Beginners     |
| **3Commas**       | ⭐⭐ Easy        | DCA, Grid bots  | Intermediate  |
| **TradersPost**   | ⭐⭐ Easy        | Multi-broker    | Stock traders |
| **PineConnector** | ⭐⭐⭐ Medium    | MT4/MT5 bridge  | Forex         |
| **Custom Bot**    | ⭐⭐⭐⭐⭐ Hard  | Unlimited       | Developers    |

---

### ⚠️ Important Limits & Gotchas

{% hint style="danger" %}
**Must Know:**

- TradingView requires **paid plan** for webhooks
- Use `Any alert() function call` as condition
- Max 15 alerts in 3 minutes (TradingView limit)
- Discord: \~30 messages/minute per webhook
- Telegram: \~30 messages/second total, 1/second per chat
  {% endhint %}

---

### 📚 Quick Start Recommendations

<details>

<summary><strong>I just want signals in Telegram/Discord</strong></summary>

Use **tradingview\.to** (Track A) - 2 minute setup, no coding needed

</details>

<details>

<summary><strong>I want to auto-trade on Binance/Bybit</strong></summary>

Use **Cornix Bot** - Paste webhook URL, configure risk settings, done

</details>

<details>

<summary><strong>I need custom formatting or multiple destinations</strong></summary>

Use **Pipedream or Make** (Track B) - Visual workflow builders

</details>

<details>

<summary><strong>I'm a developer and need full control</strong></summary>

Build custom endpoint (Track C) - See Pro tab for examples

</details>

---

### ✅ Summary

{% hint style="info" %}
**The Backtest Version provides:**

✅ **Zero manual setup** - All alerts handled automatically\
✅ **Structured format** - Parse-ready for any platform\
✅ **Complete data** - All TP/SL levels in one message\
✅ **Signal identification** - Know exactly which strategy triggered\
✅ **Direct integration** - Works with any webhook endpoint\
✅ **Backtesting accuracy** - Realistic alert generation for testing
{% endhint %}

Perfect for automated trading systems, backtesting validation, and hands-free alert management.
