# 🔄 Automating Infinity Algo Alerts via Alertatron

[Got ideas?\
Request a feature](https://infinityalgo.canny.io/?utm_source=docs\&utm_medium=banner)

**CRITICAL: Alertatron has TWO different systems. DO NOT MIX THEM:**

* **Signals Lite** - JSON messages only, no scripts
* **Script Bots** - Full scripting with `MyKeys{...} #bot`

Signals Lite does NOT use `MyKeys{...}` or `#bot` tags!

Choose ONE system and follow ONLY that guide below.

***

🎯 Which System Should You Use?

Most Users → Signals Lite\
Power Users → Script Bots

Choose Signals Lite if you want:

* ✅ Quick 5-minute setup
* ✅ Visual configuration (no coding)
* ✅ Simple long/short automation
* ✅ Lower chance of errors
* ✅ Easy to modify settings

Perfect for:

* New to automation
* Basic buy/sell/close needs
* Want it working fast

Choose Script Bots if you need:

* ✅ Complex order logic
* ✅ Multi-step TP ladders
* ✅ Conditional execution
* ✅ Position pyramiding
* ✅ Custom OCO groups
* ✅ Timing delays

Required skills:

* Comfortable with code
* Can debug scripts
* Need advanced features

***

📘 Option 1: Signals Lite (Recommended)

Simple JSON signal-based automation with visual configuration.

{% stepper %}
{% step %}
### Step: Create Signals Lite Bot

* Navigate to **Signals Lite → Your Bots**
* Click **"Create new automated bot..."**

Configure your bot:

Field / What to enter

* **Bot name** — e.g. `Infinity Algo BTC`
* **Exchange** — Select your exchange
* **Symbol** — e.g. `BTCUSDT` or `BTC`
* **Access** — Set to Private

Click **Create Bot**
{% endstep %}

{% step %}
### Step: Configure Bot Settings

After creating your bot:

* Click on your bot name to expand
* Find **"API Keys"** section
* Add your exchange API credentials
* **Save** configuration

Never enable withdrawal permissions for trading bots.

Configure default behavior that can be overridden per alert:

* **Position Size**: % of balance or fixed amount
* **Leverage**: Your preferred leverage
* **Order Type**: Market or Limit
* **Take Profit**: Enable and set offset %
* **Stop Loss**: Set risk %
* **Hedge Mode**: If supported by exchange

You can override any of these per alert with JSON. See: https://alertatron.com/docs/signals-lite/override-signal-settings
{% endstep %}

{% step %}
### Step: Get Your Webhook

Copy the exact webhook shown on your bot page. Don't guess the path—formats can change.

Your bot page will display a unique webhook URL. Copy it exactly as shown — you'll need it for TradingView.
{% endstep %}

{% step %}
### Step: Create TradingView Alerts

1. Open your Infinity Algo chart
2. Create alert (Alt+A)

Configure the alert:

* **Condition** — e.g. "1.1 Buy Signal - Smart"
* **Options** — **Once Per Bar Close** (prevents duplicates!)
* **Alert name** — e.g. "IA Smart Buy"
* **Message** — JSON template (see below)
* **Webhook URL** — Your bot's webhook from previous step
{% endstep %}
{% endstepper %}

Available Infinity Algo Alerts

Entry Signals — Buy:

* `1.0 Buy Signal - Normal`
* `1.1 Buy Signal - Smart`
* `1.2 Normal or Smart Buy`
* `1.3 Buy Signal - HL Sniper`
* `1.4 Buy Signal - AI`

Sell:

* `1.5 Sell Signal - Normal`
* `1.6 Sell Signal - Smart`
* `1.7 Normal or Smart Sell`
* `1.8 Sell Signal - HL Sniper`
* `1.9 Sell Signal - AI`

Management:

* `2.0 Take Profit Long`
* `2.1 Take Profit Short`
* `2.2 Stop Loss Long Hit`
* `2.3 Stop Loss Short Hit`
* `2.4 Possible Long Coming` (info only)
* `2.5 Possible Short Coming` (info only)

***

📝 Signals Lite Message Templates

Messages MUST be valid JSON. Start simple (side + amount) and optionally override defaults such as TP/SL, hedge mode, or closing the opposite side.

Minimal Long Entry:

```
{"side":"long","amount":"25%"}
```

Minimal Short Entry:

```
{"side":"short","amount":"25%"}
```

Close Position:

```
{"side":"close"}
```

Long with TP/SL override:

```
{
  "side": "long",
  "amount": "50%",
  "takeProfit": true,
  "takeProfitOffset": "2%",
  "stopLoss": true,
  "stopLossOffset": "1%",
  "closeExisting": true
}
```

Short with leverage:

```
{
  "side": "short",
  "amount": "100%",
  "leverage": 10,
  "takeProfit": true,
  "takeProfitOffset": "1.5%"
}
```

Using TradingView placeholders:

```
{
  "side": "long",
  "amount": "25%",
  "entry": "limit",
  "price": "{{close}}"
}
```

Don't include `symbol` — it's already set in your bot configuration.

Available Override Fields (summary)

* `side` (string): "long", "short", or "close"
* `amount` (string): Position size (e.g., "50%", "100")
* `takeProfit` (boolean): Enable take profit
* `takeProfitOffset` (string): TP distance (e.g., "2%")
* `stopLoss` (boolean): Enable stop loss
* `stopLossOffset` (string): SL distance (e.g., "1%")
* `closeExisting` (boolean): Close opposite position first
* `useHedgeMode` (boolean): Use hedge mode if available
* `leverage` (number): Override leverage
* `entry` (string): "market" or "limit"
* `price` (string): Limit price (if entry="limit")

For multi-pair bots, use percent/offset fields (e.g., `takeProfitOffset`), not fixed prices.

That's it! Your Signals Lite bot is ready. Test with small amounts first.

***

📗 Option 2: Script Bots (Advanced)

Full scripting control with complex order logic and multi-step TP ladders.

Prerequisites: Understand basic scripting and can debug syntax errors. If not, use Signals Lite above.

{% stepper %}
{% step %}
### Step: Configure Script Bot Infrastructure — Add API Keys First

1. Go to **Scripting Signals → Script Bot Config → Script Bot API Keys**
2. Click **"Add API Keys"**

Configure:

* **Name**: e.g. `MyKeys` (remember this exactly!)
* **Exchange**: Your exchange
* **API Key & Secret**: Your credentials

4. **Save** your keys
{% endstep %}

{% step %}
### Step: Get Your Account Webhook

1. Go to **Account → Webhook Details**
2. Copy the exact webhook shown (don't guess the format)
{% endstep %}

{% step %}
### Step: Configure Bot Group

1. Go to **Scripting Signals → Trading Bot Settings**
2. Set up a group that filters for `#bot`
3. Route this group to the trading engine

Note: Script Bots route through your account webhook using the `#bot` tag, not a separate bot webhook.
{% endstep %}
{% endstepper %}

📊 Step: Available Alert Conditions

Same as Signals Lite — all 16 alerts available:

* Buy entries: 1.0 through 1.4
* Sell entries: 1.5 through 1.9
* Management: 2.0 through 2.3

📋 Step: Create TradingView Alerts

Configuration is similar but the message contains scripts:

* **Condition** — Your chosen signal
* **Options** — **Once Per Bar Close** (prevents duplicates!)
* **Message** — Your script (see templates)
* **Webhook URL** — Your account webhook (NOT Signals Lite!)

***

📝 Script Bot Templates

Every script MUST end with `#bot` or it won't execute!

long\_entry.txt

```
MyKeys({{ticker}}) {
  # Enter long with 100% of available balance
  market(side=buy, amount=100%a);

  # Stop loss 1% below entry
  stopOrder(side=sell, amount=100%p, stop=e-1%, reduceOnly=true);

  # Multi-step TP ladder with OCO
  oneCancelsOther(which=all);
    limit(position=75%p, offset=e1%, reduceOnly=true);
    limit(position=50%p, offset=e2%, reduceOnly=true);
    limit(position=25%p, offset=e3%, reduceOnly=true);
    limit(position=0,    offset=e4%, reduceOnly=true);
  oneCancelsOther();
}
#bot
```

short\_entry.txt

```
MyKeys({{ticker}}) {
  # Enter short
  market(side=sell, amount=100%a);

  # Stop loss 1% above entry
  stopOrder(side=buy, amount=100%p, stop=e+1%, reduceOnly=true);

  # Multi-step TP ladder (negative values for short)
  oneCancelsOther(which=all);
    limit(position=-75%p, offset=e-1%, reduceOnly=true);
    limit(position=-50%p, offset=e-2%, reduceOnly=true);
    limit(position=-25%p, offset=e-3%, reduceOnly=true);
    limit(position=0,     offset=e-4%, reduceOnly=true);
  oneCancelsOther();
}
#bot
```

close\_position.txt

```
MyKeys({{ticker}}) {
  # Close any position
  limit(position=0, offset=1, reduceOnly=true);

  # Cancel all orders
  cancel(which=all);
}
#bot
```

flip\_position.txt

```
MyKeys({{ticker}}) {
  # Cancel existing orders
  cancel(which=all);

  # Flip to long (closes short if exists)
  market(position=100%a);

  # Single SL and TP
  stopOrder(side=sell, amount=100%p, stop=e-2%, reduceOnly=true);
  limit(side=sell, amount=100%p, offset=e3%, reduceOnly=true);
}
#bot
```

conditional\_pyramid.txt

```
MyKeys({{ticker}}) {
  # Only add if position < 10000
  continue(if=positionLessThan, value=10000);

  # Add to position
  market(side=buy, amount=1000);

  # Trailing stop
  trailingStop(side=sell, amount=100%p, offset=e-1.5%,
               trailingMethod=stepped, stepSize=0.5%, maxSteps=3);
}
#bot
```

delayed\_entry.txt

```
MyKeys({{ticker}}) {
  # Wait 5 minutes
  wait(5m);

  # Then enter
  market(side=buy, amount=50%a);

  # Add protection
  stopOrder(side=sell, amount=100%p, stop=e-1%, reduceOnly=true);
}
#bot
```

This multi-step TP ladder is ONLY possible with Script Bots!

***

🔤 Script Command Reference (summary)

Common commands and examples:

* `market()` — Market order\
  Example: `market(side=buy, amount=100%a)`
* `limit()` — Limit order\
  Example: `limit(position=50%p, offset=e2%)`
* `stopOrder()` — Stop loss\
  Example: `stopOrder(side=sell, stop=e-1%)`
* `aggressive()` — Smart limit entry\
  Example: `aggressive(position=90%a)`
* `wait()` — Delay\
  Example: `wait(10m)`
* `cancel()` — Cancel orders\
  Example: `cancel(which=all)`
* `oneCancelsOther()` — OCO group\
  Example: `oneCancelsOther(which=all)`
* `continue()` — Conditional proceed\
  Example: `continue(if=positionLong)`
* `stop()` — Conditional halt\
  Example: `stop(if=positionShort)`
* `trailingStop()` — Trailing stop\
  Example: `trailingStop(offset=e-1%)`

Position sizing shortcuts:

* `100%a` = 100% available balance
* `100%p` = 100% current position
* `100` = Fixed amount
* `position=0` = Close position
* `offset=e2%` = 2% from entry

***

🛠️ Troubleshooting

<details>

<summary>Signals Lite — Common Problems &#x26; Solutions</summary>

* Bot not responding: Check webhook URL is exactly copied
* Invalid message: Must be valid JSON format
* Wrong size: Verify % vs fixed amount in JSON
* No TP/SL: Set in bot or override with JSON fields
* Duplicate orders: Ensure "Once Per Bar Close" in TradingView

</details>

<details>

<summary>Script Bots — Common Problems &#x26; Solutions</summary>

* Script ignored: Missing `#bot` tag at end
* Invalid keys: Check key alias spelling (case-sensitive)
* Parse error: Check Alertatron inbox for error details
* Orders size 0: Missing `%` on sizing (`%a` or `%p`)
* TP/SL not canceling: Need `oneCancelsOther()` wrapper

</details>

***

📚 Resources

Official Documentation:

* Main: Docs: https://alertatron.com/docs/all/guide
* Signals Lite Getting Started: https://alertatron.com/docs/getting-started-with-signals-lite
* Override Settings Reference: https://alertatron.com/docs/signals-lite/override-signal-settings
* Script Bots Basics: https://alertatron.com/docs/automated-trading/basic-concepts
* Script Command Reference: https://alertatron.com/docs/automated-trading/market-order

Remember:

* Alertatron is a third-party service with separate costs
* Always test with small amounts first
* Use exchange testnet when available
* Manual trading via TradingView is always an option

Last updated 2 months ago

Was this helpful?
