# TradingView 使用技巧与问题修复

{% hint style="info" %}
**注意：** 这些是 TradingView 平台功能。切换这些设置不会影响 Infinity Algo 的信号或计算结果。
{% endhint %}

---

#### 🔍 修复：指标消失了

当指标似乎消失或不显示数值时，通常是由于可见性切换设置。

{% stepper %}
{% step %}
**检查图例切换**

点击左上角图例的向下箭头来显示/隐藏指标标题和数值。

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2Fd8GtEBBTQCRmNMQrJac4%2F0823-ezgif.com-video-to-gif-converter.gif?alt=media&#x26;token=e5441a6d-d5c3-4568-9dde-c9251658271e" alt="Legend toggle button"><figcaption><p>点击箭头显示指标</p></figcaption></figure>
{% endstep %}

{% step %}
**检查状态行设置**

进入 **Settings（设置）→ Status line（状态行）** 并启用：

- Indicator titles（指标名称）
- Indicator arguments（指标参数，建议关闭）
- Indicator values（指标数值，建议关闭）

**注意：** "Indicator last value label（指标最新数值标签）" 位于 **Settings（设置）→ Scales（比例）**（不同的复选框）。

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FKEyS7FP8uny3KXbsrqYf%2F08231-ezgif.com-video-to-gif-converter.gif?alt=media&#x26;token=635fc3fd-37dd-441d-b88a-88651f86ff38" alt="Status line settings"><figcaption><p>启用所有三个选项以获得完整可见性</p></figcaption></figure>
{% endstep %}

{% step %}
**检查对象树**

打开 **Object Tree（对象树）**（右侧工具栏）并点击 👁️ 图标来显示隐藏的指标。

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FbMVhgzkVA0Aw7IHL7mMF%2F08233-ezgif.com-video-to-gif-converter.gif?alt=media&#x26;token=06218e5f-137c-4b54-9b8e-2e6c1fd04f33" alt="Object tree panel"><figcaption><p>用眼睛图标切换可见性</p></figcaption></figure>
{% endstep %}
{% endstepper %}

---

#### 💾 保存多个交易设置

TradingView 的 "Save as default（保存为默认值）" 只能保存一个配置。以下是如何保存多个命名设置（如剥头皮交易 Scalping、波段交易 Swing 等）的方法：

{% tabs %}
{% tab title="⭐ 指标模板" %}
**最适合快速切换策略**

**保存内容：** 所有指标 + 它们的设置作为可重用的预设

**重要提示：** 模板会替换当前指标，且不保存绘图（Drawing）。

**使用方法：**

1. 按照需要设置您的指标
2. 点击顶部工具栏中的 **Templates（模板）** 图标（4 个方块）
3. 选择 **Save Indicator Template（保存指标模板）**
4. 命名（例如："Scalp 5m"、"Swing 4H"、"Position Daily"）
5. 从同一菜单中即时加载任何模板

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FfoGfBaUYz3Gv2Jwu9Jdy%2F08234-ezgif.com-video-to-gif-converter.gif?alt=media&#x26;token=81edf531-d419-448a-bbe7-0942aea4d16e" alt="Templates menu"><figcaption><p>从此菜单保存和加载指标模板</p></figcaption></figure>

{% hint style="success" %}
**专业提示：** 为不同的时间周期和交易风格创建模板。只需 2 次点击即可在它们之间切换！
{% endhint %}
{% endtab %}

{% tab title="📊 图表布局" %}
**最适合完整的工作区**

**保存内容：** 一切 - 交易对符号、时间周期、绘图、指标、图表样式

**使用方法：**

1. 设置整个工作区
2. 点击顶部栏中的 **布局名称下拉菜单** → **Save As（另存为）**
3. 为布局命名
4. 从下拉菜单中在已保存的布局之间切换

**快速保存：** 按 **Ctrl+S**（Windows）或 **⌘+S**（Mac）

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FCnUpWf5QoHDfBc13ozkT%2F08235-ezgif.com-video-to-gif-converter.gif?alt=media&#x26;token=5a242486-2445-4211-8a2a-e3c4732e7200" alt="Layout menu"><figcaption><p>将完整工作区保存为布局</p></figcaption></figure>

{% hint style="info" %}
**用途：** 为不同市场（加密货币、外汇、股票）或交易时段（伦敦、纽约、亚洲）设置不同的布局
{% endhint %}
{% endtab %}
{% endtabs %}

---

#### 🔧 快速修复

<details>

<summary><strong>图表看起来被压缩/挤压了</strong></summary>

一个指标可能正在绘制远离价格的数值。解决方案：

1. **隐藏** 有问题的指标（暂时）
2. **右键点击** 价格比例 → **Reset（重置）**
3. **检查** 指标是否在单独的窗格中但比例设置不正确

查看 TradingView 指南：[The chart looks way too compressed](https://www.tradingview.com/support/solutions/43000502589/)

</details>

<details>

<summary><strong>看不到指标设置齿轮图标</strong></summary>

1. 确保指标标题可见（使用 +/− 切换）
2. **悬停** 在图例中的指标名称上方
3. ⚙️ 设置图标会在悬停时出现

</details>

<details>

<summary><strong>多个图表不同步</strong></summary>

**要同步布局中的所有图表：**

1. 点击 **Select Layout（选择布局）** → **Sync layout（同步布局）**
2. 选择要同步的内容：
   - Symbol（交易对符号）
   - Interval（时间周期）
   - Crosshair（十字光标）
   - Time（时间/日期范围）

**对于绘图：** 从 **左侧工具栏** 启用 **Drawing sync（绘图同步）**

**用于选择性同步：** 使用 **Status line（状态行）** 中的 **Chart Syncing（图表同步）** 表情图标来分组特定图表（🔴🔵🟢）

**跨标签页同步：** 使用 **色标标签** 链接特定标签页

</details>

<details>

<summary><strong>Compare（对比）显示"分离的线"</strong></summary>

当使用百分比对比模式时会发生这种情况。要修复：

1. 右键点击价格比例
2. 选择 **Indexed to 100（按 100 索引）** 以从同一起点对齐线条

这是 Compare 工具百分比模式的正常行为。

</details>

---

#### ⌨️ 必须掌握的快捷键

| 操作             | Windows        | Mac       |
| ---------------- | -------------- | --------- |
| **快速搜索**     | Ctrl + K       | ⌘ + K     |
| **添加指标**     | /              | /         |
| **保存布局**     | Ctrl + S       | ⌘ + S     |
| **撤销/重做**    | Ctrl + Z/Y     | ⌘ + Z/Y   |
| **隐藏所有绘图** | Ctrl + Alt + H | ⌘ + ⌥ + H |

[查看所有 TradingView 快捷键 →](https://www.tradingview.com/charting-library-docs/latest/getting_started/Shortcuts/)

---

#### 🔗 官方 TradingView 参考资源

- [图例可见性和控制](https://www.tradingview.com/charting-library-docs/latest/ui_elements/Legend/)
- [用于管理指标的对象树](https://www.tradingview.com/support/solutions/43000474684/)
- [指标模板指南](https://www.tradingview.com/support/solutions/43000543048-what-are-indicator-templates/)
- [图表布局文档](https://www.tradingview.com/charting-library-docs/latest/saving_loading/)
- [图表被压缩](https://www.tradingview.com/support/solutions/43000502589/)
- [图表同步和分组](https://www.tradingview.com/support/solutions/43000629992-how-to-sync-the-charts-of-my-layout/)
- [键盘快捷键列表](https://www.tradingview.com/charting-library-docs/latest/getting_started/Shortcuts/)

{% hint style="success" %}
**记住：** 这些是 TradingView 平台功能。学习它们将改进您对所有指标的体验，不仅仅是 Infinity Algo。
{% endhint %}
