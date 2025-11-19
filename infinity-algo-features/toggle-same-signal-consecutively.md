# 🔁 Toggle Same Signal Consecutively

<a href="https://infinityalgo.canny.io/?utm_source=docs&#x26;utm_medium=banner" class="button primary">Got ideas? Request a feature</a>

## Toggle: Same Signal Consecutively

Prevent or allow the same signal type from repeating consecutively.

![](<../.gitbook/assets/image (10)>)

***

### How it works

Toggle controls whether the same signal type (e.g., "Smart Buy") can appear twice (or more) in a row.

* ✅ Enabled (Default) — prevents consecutive identical signals.
* ❌ Disabled — allows repeated identical signals.

***

### No Consecutive Repeats (Enabled)

Blocks: Same signal appearing twice in a row

Benefits:

* ✅ Cleaner charts
* ✅ Less noise
* ✅ Natural rotation
* ✅ Filtered signals

Example:

{% code title="enabled-pattern.txt" %}
```
Smart Buy ✅ → Normal Sell ✅ → Smart Buy ✅
              ↑ Different signal required
```
{% endcode %}

***

### Allows Repeats (Disabled)

Allows the same signal multiple times

Benefits / tradeoffs:

* ✅ All valid signals shown
* ✅ Good for scaling in
* ✅ More alerts
* ⚠️ Can be noisy

Example:

{% code title="disabled-pattern.txt" %}
```
Smart Buy ✅ → Smart Buy ✅ → Smart Buy ✅
              ↑ Same signal allowed
```
{% endcode %}

***

### Visual Comparison

#### Enabled (Clean)

![Toggle On](<../.gitbook/assets/image (11)>) Fewer, filtered signals

#### Disabled (All Signals)

![Toggle Off](<../.gitbook/assets/image (12)>) More signals, possible repeats

***

### Quick Reference

| Aspect            |      Enabled |           Disabled |
| ----------------- | -----------: | -----------------: |
| Signal Frequency  |        Lower |             Higher |
| Chart Clarity     |      Cleaner |             Busier |
| Best For          | Most traders | Scaling strategies |
| Noise Level       |          Low |             Higher |
| Position Building | Single entry |   Multiple entries |

***

### When to use

#### Keep Enabled For

* Standard trading
* Clean charts
* Single positions
* Reduced noise
* Most strategies

#### Disable Only For

* Scaling into positions
* DCA strategies
* Need every signal
* Aggressive trading
* Testing purposes

***

{% hint style="info" %}
Priority System: If "Next Signal Must Be Opposite" is enabled, it overrides this setting completely.

Recommendation: Keep enabled for a cleaner trading experience unless you specifically need repeated signals.

Remember: More signals ≠ better performance. Quality over quantity!
{% endhint %}

***

Last updated 3 months ago

Was this helpful?
