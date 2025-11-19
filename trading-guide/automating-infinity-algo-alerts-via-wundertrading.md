# 🔄 Automating Infinity Algo Alerts via Finandy

---

### 🎯 Integration Method for Indicators

{% tabs %}
{% tab title="📊 Two-Alert Setup" %}
**Separate Buy/Sell Alerts (Required for Indicators)**

**What it does:**

- Two distinct alerts (Buy & Sell)
- Clear signal separation
- Works with any indicator
- No code access needed

**Best for:**

- ✅ All Infinity Algo users
- ✅ Simple setup
- ✅ Clear control
- ✅ Testing & production

{% code title="Alert Requirements" %}

```
Alerts: 2 total (indicators can only send one signal type per alert)
- Buy Signal → side: "buy"
- Sell Signal → side: "sell"
Position Side: Both/Long only/Short only
```

{% endcode %}

{% hint style="info" %}
**Position Side Options:**

- **Both** → Opens Long on buy, Short on sell (reversal in one-way mode)
- **Long only** → Only long trades
- **Short only** → Only short trades
- **Strategy** → For TradingView strategies only (NOT for indicators!)
  {% endhint %}
  {% endtab %}
  {% endtabs %}

{% hint style="warning" %}
**Important:** Since Infinity Algo is an indicator, you MUST create two separate alerts. The `"side"` field must be included with value `"buy"` or `"sell"` (lowercase). Strategy placeholders like `{{strategy.order.action}}` won't work.
{% endhint %}

---

### ⚙️ Step 1: Configure Finandy Webhook

**Navigate to Finandy:**

1. **Log in** → Finandy.com
2. **Algo-trading** → **TradingView Signals**
3. **Create new signal (webhook)**
4. Configure main settings:

| Field             | Value                                    |
| ----------------- | ---------------------------------------- |
| **Name**          | e.g. _Infinity Algo Signals_             |
| **Currency pair** | `{{ticker}}` (one hook for all)          |
| **Position side** | **Both** or **Long only**/**Short only** |
| **Save**          | Shows Signal URL & Message               |

{% hint style="danger" %}
**Do NOT select "Strategy" for Position side** - that's only for TradingView strategies, not indicators
{% endhint %}

---

### 📩 Step 2: Get Webhook Credentials

After saving, Finandy displays your unique webhook details. Copy exactly as shown:

- **Signal URL**: Copy the exact URL displayed for your signal
- **Signal Message**: Copy the template with your secret token

{% hint style="danger" %}
**Security:** Keep your `secret` token private! By default, Finandy only accepts requests from TradingView IPs.
{% endhint %}

---

### 📊 Step 3: Create TWO TradingView Alerts

You MUST create two separate alerts - one for buy signals and one for sell signals.

**Alert Configuration**

| Alert field     | Value                                  |
| --------------- | -------------------------------------- |
| **Condition**   | Infinity Algo → Choose your signal     |
| **Options**     | **Once Per Bar Close**                 |
| **Webhook URL** | Paste the exact Signal URL from Step 2 |
| **Message**     | JSON template (see below)              |

---

### 📝 JSON Templates for Each Alert

{% tabs %}
{% tab title="🟢 Alert #1: Buy Signal" %}
**Create this alert on a Buy condition:**

{% code title="buy\_signal.json" overflow="wrap" %}

```json
{
  "name": "Infinity Algo Signals",
  "secret": "YOUR-SECRET",
  "side": "buy",
  "symbol": "{{ticker}}"
}
```

{% endcode %}

**Required:** `"side": "buy"` (lowercase)
{% endtab %}

{% tab title="🔴 Alert #2: Sell Signal" %}
**Create this alert on a Sell condition:**

{% code title="sell\_signal.json" overflow="wrap" %}

```json
{
  "name": "Infinity Algo Signals",
  "secret": "YOUR-SECRET",
  "side": "sell",
  "symbol": "{{ticker}}"
}
```

{% endcode %}

**Required:** `"side": "sell"` (lowercase)
{% endtab %}

{% tab title="🎯 Advanced: Custom TP" %}
**Override TP settings from alert:**

{% code title="custom\_tp.json" overflow="wrap" lineNumbers="true" %}

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

**Note:** Tick the TP module checkbox in Finandy UI to accept values from signals, and include `"update": true`
{% endtab %}
{% endtabs %}

---

### 🎯 Step 4: Set TP & SL Inside Finandy (Optional)

{% tabs %}
{% tab title="📈 Take Profit" %}

1. Open the webhook you created → **Take Profit (TP)** tab
2. Tick **Enable TP** → choose **Limit** or **Market**
3. **Number of orders** → choose how many levels
4. **Price offset** (%) and **Order distribution** (%) per tier
5. **Level re-ordering** keeps percentages intact when you DCA
6. To accept TP overrides from signals, tick the checkbox to enable

All TP orders sit on the exchange; no extra TradingView alerts required.
{% endtab %}

{% tab title="🛡️ Stop Loss" %}

1. Open webhook → **Stop Loss (SL)** tab
2. Tick **Enable SL**
3. Choose **Market** or **Limit**
4. Set **Price offset** (%)
5. Optional: Enable **Trailing**

SL orders execute on exchange for fastest execution.
{% endtab %}

{% tab title="🔄 Order Types" %}
**Real vs Virtual Orders:**

- **Real** = orders placed on the exchange immediately
- **Virtual** = managed by terminal until trigger conditions are met

Choose based on your exchange and needs.
{% endtab %}
{% endtabs %}

---

### ⚡ Alert Setup Examples

{% columns %}
{% column width="50%" %}
**For "Buy Signal - Smart":**

1. Condition: Infinity Algo → "Buy Signal - Smart"
2. Webhook URL: Your Finandy Signal URL
3. Message: Buy JSON with `"side": "buy"`
   {% endcolumn %}

{% column %}
**For "Sell Signal - Smart":**

1. Condition: Infinity Algo → "Sell Signal - Smart"
2. Webhook URL: Same Finandy Signal URL
3. Message: Sell JSON with `"side": "sell"`
   {% endcolumn %}
   {% endcolumns %}

---

### 🧪 Step 5: Test & Monitor

- **Interface → Signal log** shows every webhook received with "OK" or error code
- Start with tiny sizes to verify setup
- Check that both buy AND sell alerts are working
- Use the Signal Log to see received JSON and actions taken

{% hint style="warning" %}
**Testing Checklist:** ✅ Created TWO separate alerts ✅ Buy alert has `"side": "buy"` (lowercase) ✅ Sell alert has `"side": "sell"` (lowercase) ✅ Both use same webhook URL and secret ✅ Signal Log shows both types of signals
{% endhint %}

---

### 🎯 Position Side Configuration

| Your Trading Style          | Position Side Setting | Result                                            |
| --------------------------- | --------------------- | ------------------------------------------------- |
| **Long & Short (Reversal)** | Both                  | Closes opposite before opening new (one-way mode) |
| **Long Only**               | Long only             | Ignores sell signals                              |
| **Short Only**              | Short only            | Ignores buy signals                               |
| **Strategy Mode**           | Strategy              | Only for TradingView strategies                   |

{% hint style="danger" %}
**Hedge Mode Warning:** In hedge mode, use **Long only** or **Short only** for indicators. Position side "Both" won't close correctly in hedge mode - it's designed for one-way mode reversals.
{% endhint %}

---

### 🛠️ Troubleshooting Checklist

| Issue              | Solution                                               |
| ------------------ | ------------------------------------------------------ |
| **403 error**      | Wrong **secret** or URL missing **https\://**          |
| **"Unknown side"** | `side` must be exactly `"buy"` or `"sell"` (lowercase) |
| **No orders**      | Check Position Side isn't set to "Strategy"            |
| **Only buys work** | Did you create the sell alert?                         |
| **Wrong pair**     | Verify `{{ticker}}` placeholder                        |
| **No reversal**    | Check Position Side = "Both" and one-way mode enabled  |
| **Hedge issues**   | Use Long only/Short only in hedge mode, not "Both"     |

---

### 🔤 JSON Key Reference (Finandy)

| Key             | Meaning                | Details                                       |
| --------------- | ---------------------- | --------------------------------------------- |
| **`name`**      | Webhook identifier     | Any descriptive name                          |
| **`secret`**    | Auth token from signal | Keep private!                                 |
| **`side`**      | Trade direction        | **Required:** `"buy"` or `"sell"` (lowercase) |
| **`symbol`**    | Trading pair           | Usually `{{ticker}}`                          |
| **`tp.orders`** | TP levels array        | Optional override                             |
| **`ofs`**       | % offset from entry    | String: "1.0" = 1%                            |
| **`piece`**     | % of position          | Percentages that sum to intended total        |
| **`update`**    | Apply new settings     | `true` to override TP from signal             |

---

### 📚 Resources

{% hint style="info" %}
**Official Finandy Documentation:**

- **Main Docs:** <https://docs.finandy.com/>
- **TradingView Connection:** <https://docs.finandy.com/algo-trading/signals-tradingview/connection-and-configuration/indicator-strategy-connection>
- **Signal Interface:**[https://docs.finandy.com/algo-trading/signals-tradingview/interface](https://docs.finandy.com/algo-trading/signals-tradingview/interface)
- **Position Management:** <https://docs.finandy.com/algo-trading/signals/interface/open>
  {% endhint %}

{% hint style="warning" %}
**Important Reminders:**

- Finandy is a third-party service with separate costs
- Indicators require TWO alerts (buy and sell separately)
- The `"side"` field is mandatory and must be lowercase
- Test with small amounts first
- Manual trading via TradingView is always available
  {% endhint %}
