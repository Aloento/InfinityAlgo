# FAQ & Troubleshoot

{% hint style="info" %}
**Tip:** For instant assistance try the live-chat widget on our website—it solves \~90 % of questions in under a minute.
{% endhint %}

---

**1 Indicator not showing up — username mismatch**

- The TradingView **username** you entered at checkout must match the one you are logged in with now.
- Find the name on your invoice email or in TradingView **Profile → Settings → Username**.
- If they differ, email **<support@infinityalgo.com>** with the correct username and we'll update your licence.

---

**2 Red lock icon next to the script — script still locked**

- 90 % of the time the username is wrong or the purchase isn't finished.
- Enter the correct username (see Q 1), wait 30 s, then reload the chart.
- When the lock turns **green**, the script is ready to load (see Q 3).

---

**3 How do I unlock the indicator?**

- A **green lock** means the licence is recognised.
- Click the script name under **Invite-only Scripts** to add it to the chart.
- If the lock stays red, go back to Q 2.

---

**4 Indicator timeout error**

- TradingView shows timeout when calculations take too long (usually on lower timeframes or with AI enabled).
- **Quick fix:** Open settings (⚙️) → toggle any input → click OK. This forces a refresh.
- **Alternative:** Remove the indicator (×) and re-add from **Invite-only Scripts**.
- Consider using **Static** mode or higher **Update Frequency** if using AI optimization.

---

**5 Cannot load – "Too many indicators"**

- TradingView limits active indicators per chart:
  - Free = 2 Essential = 5 Plus = 10 Premium = 25 Expert = 30 Ultimate = 50
- Remove unused indicators (× in the legend) and reload, or upgrade your plan/split across multiple charts.

---

**6 Open the indicator settings**

- Click the **gear (⚙️)** icon next to the script name in the legend.
- All inputs, colours and alert toggles are here.
- **Reset to Default** is bottom-left inside that window (see Q 12).

---

**7 "Study Not Auth" error**

- The script could not verify your licence.
- Refresh the page (F5)—fixes \~30 % of cases.
- Re-check username spelling (Q 1).
- Occasionally TradingView's auth server is busy; wait a few minutes and reload.
- Still failing? Send a screenshot and your username to support.

---

**8 "Internal Server Study Error"**

- Temporary TradingView server issue or cached script.
- Hard-refresh (**Ctrl + Shift + R**) or open a new tab / the desktop app.
- Check [**https://status.tradingview.com/**](https://status.tradingview.com/)—if components are red, wait for green.

---

**9 TradingView asks me to pay again**

- It's a quota notice, **not** a payment request.
- You've reached your indicator limit (see Q 5).
- Remove one script or upgrade your TradingView plan; the prompt disappears.

---

**10 Does the indicator repaint?**

- **No.** Once a bar closes, its signals and values never change.
- Values can "breathe" while the current bar is still forming—normal for any real-time calculation.

---

**11 How do I get the latest version?**

- Updates are pushed automatically.
- If you boosted the script you'll receive an email titled **"Infinity Algo – new version."**
- Remove the old copy and re-add it from **Invite-only Scripts** to load the newest build.
- Existing alert templates stay intact unless TradingView flags an input change.

---

**12 Reset settings to factory defaults**

- Open settings (⚙️) → **Reset to Default Inputs** → OK.
- Colours can be reset under the **Style** tab.

---

**13 My alerts don't fire**

**Quick checklist**

1. Alert created on the **correct indicator version**?
2. **Condition** set to **Once per bar close** (recommended).
3. Alert quota: Free = 3 Essential = 20 Plus = 100 Premium = 400 Expert = 600 Ultimate = 1 000
4. Browser tab closed? Use TradingView desktop or server-side alerts (paid plans).
5. Follow the step-by-step alert guide in the docs.

---

**14 No backtest data for futures**

- Futures require a different order size setting in TradingView.
- **Fix:** Open settings (⚙️) → **Properties** → change **Order Size** from "USD" to **"Contracts"** or **"Quantity"**.
- This applies to all futures symbols: ES, MES, NQ, MNQ, YM, RTY, CL, GC, etc.
- Futures trade in contracts/lots, not USD position sizing.

---

**15 Remove the indicator from a chart**

- In the legend click the × next to the script name.
- The licence remains in **Invite-only Scripts**—you can re-add it any time.

---

**16 What are the optimal settings?**

- **Optimal settings** vary by market, timeframe, and trading style. Utilize our **backtesting** to discover what works **best** for you.

---

**17 Can I change my TradingView username after purchase?**

- Yes, email <support@infinityalgo.com> with your new username. One free change per license.

---

**18 Can I share my indicator with others?**

- **No.** The license is tied to your specific **TradingView username** and is non-transferable.

---

**19 Still need help?**

- **Live chat** – bottom-right of our site (fastest).
- **Email** – <support@infinityalgo.com> (responses within 24 h on business days).
