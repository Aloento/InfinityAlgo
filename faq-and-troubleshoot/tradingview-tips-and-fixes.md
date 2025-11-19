# TradingView Tips & Fixes

[Got ideas?\
Request a feature](https://infinityalgo.canny.io/?utm_source=docs\&utm_medium=banner)

**Note:** These are TradingView platform features. Toggling them doesn't affect Infinity Algo's signals or calculations.

***

<details>

<summary>🔍 Fix: "My Indicator Disappeared"</summary>

When indicators seem to vanish or show no values, it's usually a visibility toggle.

Check the Legend ToggleClick the downward-pointing chevron in the top-left legend to show/hide indicator titles and values.Click the chevron to show indicators.Check Status Line SettingsGo to Settings → Status line and enable:Indicator titlesIndicator arguments (off recommended)Indicator values (off recommended)Note: The "Indicator last value label" is under Settings → Scales (different checkbox).Enable all three options for full visibility.Check Object TreeOpen Object Tree (right toolbar) and click the 👁️ icon to unhide indicators.Toggle visibility with the eye icon.

</details>

<details>

<summary>💾 Save Multiple Trading Setups</summary>

TradingView's "Save as default" only saves ONE configuration. Use these to save multiple named setups (Scalping, Swing, etc.):

* Indicator Templates — Best for quick strategy switching (saves indicators + settings; does NOT save drawings).
* Chart Layouts — Best for complete workspaces (saves everything: symbol, timeframe, drawings, indicators, chart style).

#### Indicator Templates — How to use

Set up your indicators exactly how you want.Click the Templates icon (4 squares) in the top toolbar, then select Save Indicator Template.Name it (e.g., "Scalp 5m", "Swing 4H", "Position Daily") and load any template instantly from the same menu.

![Templates menu](<../.gitbook/assets/image (44)>)

Pro Tip: Create templates for different timeframes and trading styles. Switch between them with 2 clicks!

#### Chart Layouts — How to use

Set up your entire workspace.Click the layout name dropdown in the top bar → Save As, then name your layout.Switch between saved layouts from the dropdown. Quick save: Press Ctrl+S (Windows) or ⌘+S (Mac).

![Layout menu](<../.gitbook/assets/image (45)>)

Use Case: Different layouts for different markets (Crypto, Forex, Stocks) or trading sessions (London, NY, Asia).

</details>

<details>

<summary>🔧 Quick Fixes</summary>

#### Chart looks compressed / squished

An indicator may be plotting values far from price. Solutions:

Hide the problematic indicator temporarily.Right-click the price scale → Reset.Check if an indicator is in a separate pane but scaled wrong.

See TradingView's guide: [The chart looks way too compressed](https://www.tradingview.com/support/solutions/43000502589/)

***

#### Can't see indicator settings gear

Make sure the indicator title is visible (use +/− toggle).Hover over the indicator name in the legend — the ⚙️ settings icon appears on hover.

***

#### Multiple charts not syncing

To sync all charts in a layout:

Click Select Layout → Sync layout.Choose what to sync (Symbol, Interval, Crosshair, Time/date range).For drawings: enable Drawing sync from the left toolbar.\
For selective sync: use the Chart Syncing emoji icon in the Status line to group specific charts (🔴🔵🟢).\
To sync across tabs: use color tags to link specific tabs.

***

#### Compare shows "detached lines"

This happens when using percent comparison mode. To fix:

1. Right-click the price scale
2. Select **Indexed to 100** to align lines from the same starting point

This is normal behavior for the Compare tool's percent mode.

</details>

<details>

<summary>⌨️ Essential Shortcuts</summary>

| Action            |        Windows |       Mac |
| ----------------- | -------------: | --------: |
| Quick Search      |       Ctrl + K |     ⌘ + K |
| Add Indicator     |              / |         / |
| Save Layout       |       Ctrl + S |     ⌘ + S |
| Undo/Redo         |   Ctrl + Z / Y | ⌘ + Z / Y |
| Hide All Drawings | Ctrl + Alt + H | ⌘ + ⌥ + H |

[View all TradingView shortcuts →](https://www.tradingview.com/charting-library-docs/latest/getting_started/Shortcuts/)

</details>

<details>

<summary>🔗 Official TradingView References</summary>

* [Legend visibility and controls](https://www.tradingview.com/charting-library-docs/latest/ui_elements/Legend/)
* [Object Tree for managing indicators](https://www.tradingview.com/support/solutions/43000474684/)
* [Indicator Templates guide](https://www.tradingview.com/support/solutions/43000543048-what-are-indicator-templates/)
* [Chart Layouts documentation](https://www.tradingview.com/charting-library-docs/latest/saving_loading/)
* [Chart looks compressed](https://www.tradingview.com/support/solutions/43000502589/)
* [Chart syncing and groups](https://www.tradingview.com/support/solutions/43000629992-how-to-sync-the-charts-of-my-layout/)
* [Keyboard shortcuts list](https://www.tradingview.com/charting-library-docs/latest/getting_started/Shortcuts/)

</details>

***

**Remember:** These are TradingView platform features. Learning them will improve your experience with ALL indicators, not just Infinity Algo.

Last updated 2 months ago

For privacy details: https://infinityalgo.com/privacy/
