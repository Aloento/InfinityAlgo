# 🔁 连续相同信号切换 (Toggle Same Signal Consecutively)

防止或允许相同信号类型连续重复出现。

![Toggle Setting](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FxUcktpcyHPgm1oG5N6QX%2Fimage.png?alt=media&token=468b781b-8de2-4f9c-943b-9b0c144e0e08)

## 🎯 工作原理

{% tabs %}
{% tab title="✅ 启用 (默认)" %}

### 无连续重复

**阻止:** 相同信号连续出现两次

✅ 图表更清晰 ✅ 噪音更少 ✅ 信号自然轮换 ✅ 信号已过滤

**示例:**

{% code title="enabled-pattern.txt" %}

```
Smart Buy ✅ → Normal Sell ✅ → Smart Buy ✅
              ↑ 需要不同的信号
```

{% endcode %}
{% endtab %}

{% tab title="❌ 禁用" %}

### 允许重复

**允许:** 相同信号多次出现

✅ 显示所有有效信号 ✅ 适合分批建仓 ✅ 更多警报 ⚠️ 可能产生较多噪音

**示例:**

{% code title="disabled-pattern.txt" %}

```
Smart Buy ✅ → Smart Buy ✅ → Smart Buy ✅
              ↑ 允许相同信号
```

{% endcode %}
{% endtab %}
{% endtabs %}

---

### 📊 视觉对比

{% columns %}
{% column width="50%" %}

#### 启用 (清晰)

![Toggle On](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2FfGrui2cM4nd4WCYnaRzx%2Fonm.png?alt=media&token=5f0f64af-3b01-4ea6-9261-35192543cf06) **更少的已过滤信号**
{% endcolumn %}

{% column %}

#### 禁用 (所有信号)

![Toggle Off](https://2387257950-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F5cf3dRpPzq1Qbyc8GksH%2Fuploads%2Fd3MMInqWS3fx09s9shqn%2Fonf.png?alt=media&token=cf000650-a486-4a2f-985c-b58be9968214) **更多信号，可能有重复**
{% endcolumn %}
{% endcolumns %}

---

### ⚡ 快速参考

| 方面           | 启用         | 禁用         |
| -------------- | ------------ | ------------ |
| **信号频率**   | 较低         | 较高         |
| **图表清晰度** | 清晰         | 繁忙         |
| **最适用于**   | 大多数交易者 | 分批建仓策略 |
| **噪音水平**   | 低           | 较高         |
| **建仓方式**   | 单次入场     | 多次入场     |

---

### 🎨 何时使用

{% columns %}
{% column width="50%" %}

#### 保持启用

- 标准交易
- 清晰图表
- 单个头寸
- 噪音减少
- 大多数策略
  {% endcolumn %}

{% column %}

#### 仅在以下情况禁用

- 分批建仓 (Scaling into positions)
- DCA 策略 (Dollar Cost Averaging)
- 需要每个信号
- 激进交易
- 测试目的
  {% endcolumn %}
  {% endcolumns %}

---

### 💡 重要提示

{% hint style="info" %}
**优先级系统:** 如果启用了"Next Signal Must Be Opposite (下一个信号必须相反)"，它将完全覆盖此设置。
{% endhint %}

{% hint style="success" %}
**建议:** 除非您特别需要重复信号，否则保持启用以获得更清晰的交易体验。
{% endhint %}

{% hint style="warning" %}
**记住:** 更多信号 ≠ 更好的性能。质量优于数量！
{% endhint %}
