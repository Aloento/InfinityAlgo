# TradingView Tips & Fixes

{% hint style="info" %}
**Note:** These are TradingView platform features. Toggling them doesn't affect Infinity Algo's signals or calculations.
{% endhint %}

---

#### 🔍 Fix: "My Indicator Disappeared"

When indicators seem to vanish or show no values, it's usually a visibility toggle.

{% stepper %}
{% step %}
**Check the Legend Toggle**

Click the downward-pointing chevron in the top-left legend to show/hide indicator titles and values.

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2Fd8GtEBBTQCRmNMQrJac4%2F0823-ezgif.com-video-to-gif-converter.gif?alt=media&#x26;token=e5441a6d-d5c3-4568-9dde-c9251658271e" alt="Legend toggle button"><figcaption><p>Click chevron to show indicators</p></figcaption></figure>
{% endstep %}

{% step %}
**Check Status Line Settings**

Go to **Settings → Status line** and enable:

- Indicator titles
- Indicator arguments (off recommended)
- Indicator values (off recommended)

**Note:** The "Indicator last value label" is under **Settings → Scales** (different checkbox).

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FKEyS7FP8uny3KXbsrqYf%2F08231-ezgif.com-video-to-gif-converter.gif?alt=media&#x26;token=635fc3fd-37dd-441d-b88a-88651f86ff38" alt="Status line settings"><figcaption><p>Enable all three options for full visibility</p></figcaption></figure>
{% endstep %}

{% step %}
**Check Object Tree**

Open **Object Tree** (right toolbar) and click the 👁️ icon to unhide indicators.

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FbMVhgzkVA0Aw7IHL7mMF%2F08233-ezgif.com-video-to-gif-converter.gif?alt=media&#x26;token=06218e5f-137c-4b54-9b8e-2e6c1fd04f33" alt="Object tree panel"><figcaption><p>Toggle visibility with the eye icon</p></figcaption></figure>
{% endstep %}
{% endstepper %}

---

#### 💾 Save Multiple Trading Setups

TradingView's "Save as default" only saves ONE configuration. Here's how to save multiple named setups (Scalping, Swing, etc.):

{% tabs %}
{% tab title="⭐ Indicator Templates" %}
**Best for Quick Strategy Switching**

**What it saves:** All indicators + their settings as a reusable preset

**Important:** Templates replace current indicators and do NOT save drawings.

**How to use:**

1. Set up your indicators exactly how you want
2. Click **Templates** icon (4 squares) in top toolbar
3. Select **Save Indicator Template**
4. Name it (e.g., "Scalp 5m", "Swing 4H", "Position Daily")
5. Load any template instantly from the same menu

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FfoGfBaUYz3Gv2Jwu9Jdy%2F08234-ezgif.com-video-to-gif-converter.gif?alt=media&#x26;token=81edf531-d419-448a-bbe7-0942aea4d16e" alt="Templates menu"><figcaption><p>Save and load indicator templates from this menu</p></figcaption></figure>

{% hint style="success" %}
**Pro Tip:** Create templates for different timeframes and trading styles. Switch between them with 2 clicks!
{% endhint %}
{% endtab %}

{% tab title="📊 Chart Layouts" %}
**Best for Complete Workspaces**

**What it saves:** EVERYTHING - symbol, timeframe, drawings, indicators, chart style

**How to use:**

1. Set up your entire workspace
2. Click the **layout name dropdown** in top bar → **Save As**
3. Name your layout
4. Switch between saved layouts from the dropdown

**Quick save:** Press **Ctrl+S** (Windows) or **⌘+S** (Mac)

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FCnUpWf5QoHDfBc13ozkT%2F08235-ezgif.com-video-to-gif-converter.gif?alt=media&#x26;token=5a242486-2445-4211-8a2a-e3c4732e7200" alt="Layout menu"><figcaption><p>Save complete workspaces as layouts</p></figcaption></figure>

{% hint style="info" %}
**Use Case:** Different layouts for different markets (Crypto, Forex, Stocks) or trading sessions (London, NY, Asia)
{% endhint %}
{% endtab %}
{% endtabs %}

---

#### 🔧 Quick Fixes

<details>

<summary><strong>Chart looks compressed/squished</strong></summary>

An indicator may be plotting values far from price. Solutions:

1. **Hide** the problematic indicator temporarily
2. **Right-click** the price scale → **Reset**
3. **Check** if an indicator is in a separate pane but scaled wrong

See TradingView's guide: [The chart looks way too compressed](https://www.tradingview.com/support/solutions/43000502589/)

</details>

<details>

<summary><strong>Can't see indicator settings gear</strong></summary>

1. Make sure the indicator title is visible (use +/− toggle)
2. **Hover** over the indicator name in the legend
3. The ⚙️ settings icon appears on hover

</details>

<details>

<summary><strong>Multiple charts not syncing</strong></summary>

**To sync all charts in layout:**

1. Click **Select Layout** → **Sync layout**
2. Choose what to sync:
   - Symbol
   - Interval (timeframe)
   - Crosshair
   - Time (date range)

**For drawings:** Enable **Drawing sync** from the **left toolbar**

**For selective sync:** Use the **Chart Syncing** emoji icon in the **Status line** to group specific charts (🔴🔵🟢)

**To sync across tabs:** Use **color tags** to link specific tabs

</details>

<details>

<summary><strong>Compare shows "detached lines"</strong></summary>

This happens when using percent comparison mode. To fix:

1. Right-click the price scale
2. Select **Indexed to 100** to align lines from the same starting point

This is normal behavior for the Compare tool's percent mode.

</details>

---

#### ⌨️ Essential Shortcuts

| Action                | Windows        | Mac       |
| --------------------- | -------------- | --------- |
| **Quick Search**      | Ctrl + K       | ⌘ + K     |
| **Add Indicator**     | /              | /         |
| **Save Layout**       | Ctrl + S       | ⌘ + S     |
| **Undo/Redo**         | Ctrl + Z/Y     | ⌘ + Z/Y   |
| **Hide All Drawings** | Ctrl + Alt + H | ⌘ + ⌥ + H |

[View all TradingView shortcuts →](https://www.tradingview.com/charting-library-docs/latest/getting_started/Shortcuts/)

---

#### 🔗 Official TradingView References

- [Legend visibility and controls](https://www.tradingview.com/charting-library-docs/latest/ui_elements/Legend/)
- [Object Tree for managing indicators](https://www.tradingview.com/support/solutions/43000474684/)
- [Indicator Templates guide](https://www.tradingview.com/support/solutions/43000543048-what-are-indicator-templates/)
- [Chart Layouts documentation](https://www.tradingview.com/charting-library-docs/latest/saving_loading/)
- [Chart looks compressed](https://www.tradingview.com/support/solutions/43000502589/)
- [Chart syncing and groups](https://www.tradingview.com/support/solutions/43000629992-how-to-sync-the-charts-of-my-layout/)
- [Keyboard shortcuts list](https://www.tradingview.com/charting-library-docs/latest/getting_started/Shortcuts/)

{% hint style="success" %}
**Remember:** These are TradingView platform features. Learning them will improve your experience with ALL indicators, not just Infinity Algo.
{% endhint %}
