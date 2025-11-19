# 🎯 Entry, Take Profit and Stop Loss

![Settings Panel](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2Fs4Vdtl8fxs226HhSzqpQ%2F2025-08-24_22-58-59.jpg?alt=media&token=2f8b4916-5873-46a0-90df-456cf7d0a5ff)

---

#### 📊 Settings Overview

{% tabs %}
{% tab title="📍 Entry Price" %}
**Entry Level Display**

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FbmAV4XD5r3SZfSR0HzMk%2Fimage.png?alt=media&#x26;token=7594ac6b-efc6-4f88-abf2-3fd9e6b255d1" alt=""><figcaption></figcaption></figure>

**Purpose:** Shows your position entry with dotted line

**Enabled**

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FXzpeeNRhn2frhR8NQGz7%2Fimage.png?alt=media&#x26;token=1594f3f0-fcfe-4af0-b95c-e88696b55034" alt=""><figcaption><p>Line visualization Entry Price enabled</p></figcaption></figure>
{% endtab %}

{% tab title="💰 Take Profit" %}
**TP Levels Configuration**

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FGvI8D8QS2rcwWiFgv07e%2Fimage.png?alt=media&#x26;token=a13943f3-a1ad-443b-988b-ace733f1fb0d" alt="" width="375"><figcaption></figcaption></figure>

{% hint style="warning" %}
**Important:** TP levels only work with "Percentage" exit type
{% endhint %}

**Setup Process:**

{% stepper %}
{% step %}
**Enable TP Level**

Toggle ON the TP levels you want
{% endstep %}

{% step %}
**Set Percentage**

Define profit % for each level
{% endstep %}

{% step %}
**Assign Position %**

Set how much to exit at each TP
{% endstep %}

{% step %}
**Verify Total = 100%**

Sum of all exit % must equal 100
{% endstep %}
{% endstepper %}

**Configuration Examples:**

{% code title="single-tp:" %}

```
Single TP:
TP1: 2% profit, exit 100%
```

{% endcode %}

{% code title="multiple-tp:" %}

```
Multiple TPs:
TP1: 1% profit, exit 50%
TP2: 2% profit, exit 30%
TP3: 3% profit, exit 20%
Total: 100% ✅
```

{% endcode %}

**Visual Display:** Enable "Show TP Prices" for dotted lines on chart

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2Fk20MvZWwDaYvnaK6fyKc%2Fimage.png?alt=media&#x26;token=cd6e1825-394e-41d5-926f-46805c860242" alt=""><figcaption><p>Line visualization with all 6 TPs enabled</p></figcaption></figure>
{% endtab %}

{% tab title="🛑 Stop Loss" %}
**Stop Loss Setup**

**Configure separately for Long and Short positions**

![SL Settings](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FhosipOwLOCvCoE8GSggs%2F2025-08-20_16-21-08.jpg?alt=media&token=19c589ba-ca12-45bc-bbc7-f063c9f41d0e)

**Long Position SL**

Set % below entry for longs

- Example: 2% = Exit if -2%

**Short Position SL**

Set % above entry for shorts

- Example: 2% = Exit if -2%

**Visual Display:** Enable "Show SL Price" for dotted line on chart

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FecvM4PErLl9QtSM4um9n%2Fimage.png?alt=media&#x26;token=953f389b-5bfb-48d7-8704-39df5a955e3d" alt=""><figcaption><p>Line visualization SL enabled</p></figcaption></figure>
{% endtab %}

{% tab title="🔄 Trailing Stop Loss" %}
**Advanced SL Management**

**Three Trailing Modes Available:**

<figure><img src="https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FFh3VQlluQErei97fRKJQ%2Fimage.png?alt=media&#x26;token=6f5839e1-749d-4a3f-846f-6496c8486abc" alt=""><figcaption></figcaption></figure>

| Mode              | Description      | How It Works                          |
| ----------------- | ---------------- | ------------------------------------- |
| **None**          | Static stop loss | SL stays at initial level             |
| **Breakeven**     | Move to entry    | SL moves to entry price after trigger |
| **Moving Target** | Follow TP levels | SL trails up to previous TP levels    |

**Setup Process:**

{% stepper %}
{% step %}
**Select Trailing Mode**

Choose from None, Breakeven, or Moving Target
{% endstep %}

{% step %}
**Set Trigger Point**

Select which TP triggers the trailing (TP1-TP6)
{% endstep %}

{% step %}
**Monitor Status**

Chart shows (BE) or (TP1), (TP2) etc. next to SL
{% endstep %}
{% endstepper %}

**Example Configurations:**

{% code title="breakeven-setup:" %}

```
Breakeven Mode:
- Mode: Breakeven
- Trigger: After TP1
- Result: SL moves to entry when TP1 hits
- Display: "Stop loss (BE)"
```

{% endcode %}

{% code title="moving-target-setup:" %}

```
Moving Target Mode:
- Mode: Moving Target
- Trigger: After TP2
- Result:
  * After TP2: SL → Entry
  * After TP3: SL → TP1
  * After TP4: SL → TP2
- Display: "Stop loss (TP1)", etc.
```

{% endcode %}

{% hint style="success" %}
**Pro Tip:** Moving Target mode locks in profits progressively as each TP level is reached
{% endhint %}

**Visual Indicators:**

| SL Status        | Label Display               | Meaning           |
| ---------------- | --------------------------- | ----------------- |
| **Normal**       | "Stop loss: \[price]"       | Static SL active  |
| **Breakeven**    | "Stop loss (BE): \[price]"  | SL moved to entry |
| **Trailing TP1** | "Stop loss (TP1): \[price]" | SL at TP1 level   |
| **Trailing TP2** | "Stop loss (TP2): \[price]" | SL at TP2 level   |

{% hint style="info" %}
**Entry Line Behavior:** When SL is at breakeven, the entry line dims to avoid visual overlap
{% endhint %}
{% endtab %}
{% endtabs %}

---

#### 📈 Visual Display & Behavior

**What Shows on Chart:**

| Level         | Display     | Line Style    | When Visible         | Special Notes             |
| ------------- | ----------- | ------------- | -------------------- | ------------------------- |
| **Entry**     | Dotted line | `···········` | When enabled         | Dims when SL at BE        |
| **TP Levels** | Dotted line | `···········` | Percentage mode only | Replaced by dots when hit |
| **Stop Loss** | Dotted line | `···········` | When enabled         | Shows trailing status     |

{% hint style="info" %}
**Dynamic Display:**

- TP lines disappear and become dot markers when hit
- SL label updates to show current mode (BE, TP1, TP2, etc.)
- Entry line dims when SL is at breakeven to reduce clutter
  {% endhint %}

**Chart Examples:**

{% columns %}
{% column width="50%" %}
**Active TP Lines**

![Before TP Hit](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FbWGbiHuheTXVKJHpX4KW%2F2025-08-20_16-58-38.jpg?alt=media&token=129a1cd9-330d-463c-aaf2-7c35640196a7) **Lines show pending TP levels**
{% endcolumn %}

{% column %}
**TP Hit Markers**

![After TP Hit](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FDzZ7kGlWG30skuBIDGZG%2F2025-08-20_17-00-02.jpg?alt=media&token=7c845ba8-dcab-4cc0-a990-7e14324a9067) **Dots mark executed TPs**
{% endcolumn %}
{% endcolumns %}

---

#### 🎨 Visual Indicators Guide

**TP Level Status:**

| Status                 | Visual         | Description      | Chart State        |
| ---------------------- | -------------- | ---------------- | ------------------ |
| **📊 Pending TP**      | Dotted line    | Ready to trigger | Label shows target |
| **✅ TP Hit**          | Dot marker (●) | Level executed   | Line disappears    |
| **🔄 Position Closed** | Dots remain    | Trade complete   | All lines cleared  |

**SL Trailing Status:**

| Status           | Visual                      | Description         | Notes           |
| ---------------- | --------------------------- | ------------------- | --------------- |
| **📍 Static**    | "Stop loss: \[price]"       | Fixed SL position   | Initial state   |
| **🟢 Breakeven** | "Stop loss (BE): \[price]"  | Moved to entry      | Risk-free trade |
| **📈 Trailing**  | "Stop loss (TP#): \[price]" | Following TP levels | Profits locked  |

---

#### 🎯 Quick Setup Templates

**Conservative (Single TP + Breakeven)**

{% code title="conservative:" %}

```
TP1: 2% profit, exit 100%
SL: 1% loss
Trailing: Breakeven after TP1
Risk/Reward: 2:1 → Risk-free after TP
```

{% endcode %}

**Scaled Exit (Multiple TP + Moving Target)**

{% code title="scaled:" %}

```
TP1: 1% profit, exit 50%
TP2: 2% profit, exit 30%
TP3: 3% profit, exit 20%
SL: 2% loss
Trailing: Moving Target after TP1
Result: Progressive profit locking
```

{% endcode %}

**Aggressive (Wide Targets + Late Trailing)**

{% code title="aggressive:" %}

```
TP1: 3% profit, exit 40%
TP2: 5% profit, exit 30%
TP3: 8% profit, exit 30%
SL: 3% loss
Trailing: Moving Target after TP2
Result: Maximum profit potential
```

{% endcode %}

---

#### 💡 Pro Tips

{% hint style="success" %}
**Best Practices:**

- Always verify TP percentages = 100%
- Use Breakeven mode for conservative trading
- Use Moving Target to lock in progressive profits
- Set trailing trigger based on your confidence level
- Monitor the SL label for current protection status
  {% endhint %}

{% hint style="info" %}
**Trailing Tips:**

- **Breakeven after TP1** = Quick risk elimination
- **Moving Target after TP2** = Balance between profit and protection
- **No trailing** = Maximum profit potential but constant risk
  {% endhint %}

{% hint style="warning" %}
**Remember:**

- TP lines only show in "Percentage" exit mode
- Trailing SL requires at least one TP to be enabled
- Moving Target mode requires multiple TPs for best results
  {% endhint %}
