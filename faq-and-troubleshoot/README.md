# FAQ & Troubleshoot

[Got ideas? Request a feature](https://infinityalgo.canny.io/?utm_source=docs\&utm_medium=banner)

{% hint style="info" %}
Tip: For instant assistance try the live-chat widget on our website—it solves \~90 % of questions in under a minute.
{% endhint %}

<details>

<summary>Indicator not showing up — username mismatch</summary>

* The TradingView **username** you entered at checkout must match the one you are logged in with now.
* Find the name on your invoice email or in TradingView **Profile → Settings → Username**.
* If they differ, email **support@infinityalgo.com** with the correct username and we'll update your licence.

</details>

<details>

<summary>Red lock icon next to the script — script still locked</summary>

* 90 % of the time the username is wrong or the purchase isn't finished.
* Enter the correct username (see Q 1), wait 30 s, then reload the chart.
* When the lock turns **green**, the script is ready to load (see Q 3).

</details>

<details>

<summary>How do I unlock the indicator?</summary>

* A **green lock** means the licence is recognised.
* Click the script name under **Invite-only Scripts** to add it to the chart.
* If the lock stays red, go back to Q 2.

</details>

<details>

<summary>Indicator timeout error</summary>

* TradingView shows timeout when calculations take too long (usually on lower timeframes or with AI enabled).
* **Quick fix:** Open settings (⚙️) → toggle any input → click OK. This forces a refresh.
* **Alternative:** Remove the indicator (×) and re-add from **Invite-only Scripts**.
* Consider using **Static** mode or higher **Update Frequency** if using AI optimization.

</details>

<details>

<summary>Cannot load – "Too many indicators"</summary>

* TradingView limits active indicators per chart:

| Plan      | Active indicators |
| --------- | ----------------- |
| Free      | 2                 |
| Essential | 5                 |
| Plus      | 10                |
| Premium   | 25                |
| Expert    | 30                |
| Ultimate  | 50                |

* Remove unused indicators (× in the legend) and reload, or upgrade your plan/split across multiple charts.

</details>

<details>

<summary>Open the indicator settings</summary>

* Click the **gear (⚙️)** icon next to the script name in the legend.
* All inputs, colours and alert toggles are here.
* **Reset to Default** is bottom-left inside that window (see Q 12).

</details>

<details>

<summary>"Study Not Auth" error</summary>

* The script could not verify your licence.
* Refresh the page (F5)—fixes \~30 % of cases.
* Re-check username spelling (Q 1).
* Occasionally TradingView's auth server is busy; wait a few minutes and reload.
* Still failing? Send a screenshot and your username to support.

</details>

<details>

<summary>"Internal Server Study Error"</summary>

* Temporary TradingView server issue or cached script.
* Hard-refresh ( **Ctrl + Shift + R**) or open a new tab / the desktop app.
* Check [https://status.tradingview.com/](https://status.tradingview.com/)—if components are red, wait for green.

</details>

<details>

<summary>TradingView asks me to pay again</summary>

* It's a quota notice, **not** a payment request.
* You've reached your indicator limit (see Q 5).
* Remove one script or upgrade your TradingView plan; the prompt disappears.

</details>

<details>

<summary>Does the indicator repaint?</summary>

* **No.** Once a bar closes, its signals and values never change.
* Values can "breathe" while the current bar is still forming—normal for any real-time calculation.

</details>

<details>

<summary>How do I get the latest version?</summary>

* Updates are pushed automatically.
* If you boosted the script you'll receive an email titled **"Infinity Algo – new version."**
* Remove the old copy and re-add it from **Invite-only Scripts** to load the newest build.
* Existing alert templates stay intact unless TradingView flags an input change.

</details>

<details>

<summary>Reset settings to factory defaults</summary>

* Open settings (⚙️) → **Reset to Default Inputs** → OK.
* Colours can be reset under the **Style** tab.

</details>

<details>

<summary>My alerts don't fire</summary>

Quick checklist

1. Alert created on the **correct indicator version**?
2. **Condition** set to **Once per bar close** (recommended).
3. Alert quota:

| Plan      | Alerts |
| --------- | ------ |
| Free      | 3      |
| Essential | 20     |
| Plus      | 100    |
| Premium   | 400    |
| Expert    | 600    |
| Ultimate  | 1 000  |

4. Browser tab closed? Use TradingView desktop or server-side alerts (paid plans).
5. Follow the step-by-step alert guide in the docs.

</details>

<details>

<summary>No backtest data for futures</summary>

* Futures require a different order size setting in TradingView.
* **Fix:** Open settings (⚙️) → **Properties** → change **Order Size** from "USD" to **"Contracts"** or **"Quantity"**.
* This applies to all futures symbols: ES, MES, NQ, MNQ, YM, RTY, CL, GC, etc.
* Futures trade in contracts/lots, not USD position sizing.

</details>

<details>

<summary>Remove the indicator from a chart</summary>

* In the legend click the × next to the script name.
* The licence remains in **Invite-only Scripts**—you can re-add it any time.

</details>

<details>

<summary>What are the optimal settings?</summary>

* **Optimal settings** vary by market, timeframe, and trading style. Utilize our **backtesting** to discover what works **best** for you.

</details>

<details>

<summary>Can I change my TradingView username after purchase?</summary>

* Yes, email support@infinityalgo.com with your new username. One free change per license.

</details>

<details>

<summary>Can I share my indicator with others?</summary>

* **No.** The license is tied to your specific **TradingView username** and is non-transferable.

</details>

<details>

<summary>Still need help?</summary>

* **Live chat** – bottom-right of our site (fastest).
* **Email** – support@infinityalgo.com (responses within 24 h on business days).

</details>

Last updated 2 months ago

[privacy policy](https://infinityalgo.com/privacy/)
