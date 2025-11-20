# 🔄 通过 WunderTrading 自动化 Infinity Algo 警报

将 Infinity Algo 信号连接到 WunderTrading，实现自动交易和灵活的仓位管理。

---

### 🎯 两种交易工作流

{% tabs %}
{% tab title="🔄 Swing Trade（摇摆交易）" %}
**自动反向平仓（仅限期货）**

**功能说明：**

- 自动 Long（做多）↔ Short（做空）反向平仓
- 仅需两个警报
- Bot 自动处理仓位反向
- 启用 Swing Trade 时，Enter-Long/Enter-Short 自动反向平仓

**适用场景：**

- ✅ 仅期货交易
- ✅ 趋势市场
- ✅ 警报数量少
- ✅ 始终持仓

{% code title="设置要求" %}

```
Swing Trade: ON（仅限期货！）
警报: 共 2 个
- 买入信号 → Enter-Long
- 卖出信号 → Enter-Short
（Exit-All 仅用于平仓而不开反向仓位）
```

{% endcode %}

{% hint style="warning" %}
**重要提示：** Swing Trade 功能仅适用于期货市场。
{% endhint %}
{% endtab %}

{% tab title="🎯 Explicit Exit（显式平仓）" %}
**手动仓位管制**

**功能说明：**

- 完全控制平仓
- 无仓位重叠
- 适用于现货和期货
- 清晰的开仓/平仓分离

**适用场景：**

- ✅ 现货交易
- ✅ 风险管理
- ✅ 仓位间隔
- ✅ 更多控制

{% code title="设置要求" %}

```
Swing Trade: OFF
警报: 3 个或以上
- 开仓 → Enter-Long/Enter-Short
- 平仓 → Exit-Long/Exit-Short
- 可选重新开仓
```

{% endcode %}

{% hint style="info" %}
完美适合需要完全控制仓位时机的交易者
{% endhint %}
{% endtab %}
{% endtabs %}

---

### ⚙️ 第 1 步：在 WunderTrading 中构建信号 Bot

**访问 WunderTrading：**

1. **登录** → **Bots** → **Signal Bot** → **创建 bot**
2. 配置 **General（常规）** 选项卡设置：

| 字段                                | 值                           |
| ----------------------------------- | ---------------------------- |
| **名称（Name）**                    | 例如 `Infinity Algo BTC`     |
| **交易所/API（Exchange/API）**      | 选择你的交易所 API           |
| **交易对（Pairs）**                 | 在 UI 中选择最多 10 个交易对 |
| **时间框架标签（Timeframe label）** | 任意（仅作为标签）           |
| **多次开仓（Multiple entries）**    | 开启以实现分批进场           |
| **摇摆交易（Swing trade）**         | 开启以实现自动反向（期货）   |

{% hint style="danger" %}
**注意：** 交易对必须在 Bot UI 中选择。JSON 无法覆盖交易对的选择。
{% endhint %}

---

### 📩 第 2 步：配置开仓并获取 Webhook

**开仓（Entries）选项卡配置：**

| 设置                                    | 值                          |
| --------------------------------------- | --------------------------- |
| **Bot 启动条件（Bot start condition）** | _TradingView Alert（警报）_ |
| **Bot 设置格式（Bot settings format）** | **JSON**                    |

保存后，Bot 将显示：

- **Webhook URL：** 从 Bot 的 Alerts（警报）选项卡复制确切的 URL
- **警报注释（Alert comments）：** 按显示的方式精确复制（默认：`Enter-Long`、`Enter-Short`、`Exit-All`）

{% hint style="warning" %}
**关键提示：**

- 从 Bot 复制确切的 webhook URL - 不要猜测格式
- 注释代码区分大小写，如果编辑 Bot 名称/交易所/时间框架/交易对，可能会更改
- 编辑任何 Bot 设置后，更新你的 TradingView 警报以匹配
  {% endhint %}

---

### 📊 第 3 步：创建 TradingView 警报

**标准警报设置**

| 字段                  | 值                                                             |
| --------------------- | -------------------------------------------------------------- |
| **条件（Condition）** | 选择你的 Infinity Algo 信号（例如 "Buy Signal - Smart"）       |
| **选项（Options）**   | **Once Per Bar Close（每根 K 线收盘时一次）** （防止重复订单） |
| **Webhook URL**       | 粘贴从 Bot 的 Alerts（警报）选项卡获得的确切 URL               |
| **消息（Message）**   | JSON 模板（见下文）                                            |

---

### 📝 JSON 模板

{% hint style="info" %}
**重要提示：** 使用 Bot 侧边栏中显示的确切注释代码（例如 `Enter-Long`，而不是 `ENTER-LONG`）
{% endhint %}

{% tabs %}
{% tab title="🟢 做多开仓（Long Entry）" %}
{% code title="enter_long.json" overflow="wrap" lineNumbers="true" %}

```json
{
  "code": "Enter-Long", // 必须与你的 bot 的注释完全匹配
  "orderType": "market",
  "amountPerTradeType": "quote", // 计价货币（例如 BTC/USDT 中的 USDT）
  "amountPerTrade": 150,

  "takeProfits": [
    { "priceDeviation": 0.01, "portfolio": 0.25 },
    { "priceDeviation": 0.02, "portfolio": 0.25 },
    { "priceDeviation": 0.03, "portfolio": 0.25 },
    { "priceDeviation": 0.04, "portfolio": 0.15 },
    { "priceDeviation": 0.05, "portfolio": 0.07 },
    { "priceDeviation": 0.06, "portfolio": 0.03 }
  ],

  "stopLoss": { "priceDeviation": 0.01 },
  "reduceOnly": true, // 防止平仓增加仓位（仅期货）
  "placeConditionalOrdersOnExchange": false
}
```

{% endcode %}

{% hint style="success" %}
**注意：** TP（止盈）投资组合必须正好总和为 1.0（100%）
{% endhint %}
{% endtab %}

{% tab title="🔴 做空开仓（Short Entry）" %}
{% code title="enter_short.json" overflow="wrap" lineNumbers="true" %}

```json
{
  "code": "Enter-Short", // 仅更改此行
  "orderType": "market",
  "amountPerTradeType": "quote", // 计价货币
  "amountPerTrade": 150,

  "takeProfits": [
    { "priceDeviation": 0.01, "portfolio": 0.25 },
    { "priceDeviation": 0.02, "portfolio": 0.25 },
    { "priceDeviation": 0.03, "portfolio": 0.25 },
    { "priceDeviation": 0.04, "portfolio": 0.15 },
    { "priceDeviation": 0.05, "portfolio": 0.07 },
    { "priceDeviation": 0.06, "portfolio": 0.03 }
  ],

  "stopLoss": { "priceDeviation": 0.01 },
  "reduceOnly": true
}
```

{% endcode %}
{% endtab %}

{% tab title="✅ 做多平仓（Exit Long）" %}
{% code title="exit_long.json" overflow="wrap" %}

```json
{
  "code": "Exit-Long",
  "orderType": "market",
  "reduceOnly": true
}
```

{% endcode %}

如使用 Swing Trade ON，则跳过此项
{% endtab %}

{% tab title="❌ 做空平仓（Exit Short）" %}
{% code title="exit_short.json" overflow="wrap" %}

```json
{
  "code": "Exit-Short",
  "orderType": "market",
  "reduceOnly": true
}
```

{% endcode %}

如使用 Swing Trade ON，则跳过此项
{% endtab %}

{% tab title="⏹️ 全部平仓（Exit All）" %}
{% code title="exit_all.json" overflow="wrap" %}

```json
{
  "code": "Exit-All",
  "orderType": "market",
  "reduceOnly": true
}
```

{% endcode %}

市价平仓所有持仓
{% endtab %}
{% endtabs %}

---

### ⚡ 快速对比

| 功能             | Swing Trade ON | Explicit Exit（显式平仓） |
| ---------------- | -------------- | ------------------------- |
| **市场类型**     | ⚠️ 仅期货      | ✅ 现货和期货             |
| **需要的警报数** | 2（最少）      | 3+（开仓/平仓/重新开仓）  |
| **仓位控制**     | 自动反向       | 手动控制                  |
| **仓位间隔**     | 无             | 可能存在                  |
| **复杂度**       | 简单           | 中等                      |

---

### 🎯 选择你的工作流

| 如果你想…                                                                                    | 使用这些警报和 JSON                                                                                                                                                                                                             |
| -------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><strong>A) 乒乓交易（自动反向）</strong><br><em>做多 → 做空 → 做多，仅需两个警报</em></p> | <p><em>在 Bot 中设置 <strong>Swing trade = ON</strong>（仅期货）</em><br>• <strong>买入警报</strong> → `Enter-Long` JSON<br>• <strong>卖出警报</strong> → `Enter-Short` JSON<br>• 仅在想平仓而不开反向仓位时使用 `Exit-All`</p> |
| <p><strong>B) 显式平仓优先</strong><br><em>从不重叠仓位；更多控制</em></p>                   | <p><em>保持 Swing trade = OFF</em><br>• <strong>开仓警报</strong> → `Enter-Long` 或 `Enter-Short` JSON<br>• <strong>平仓警报</strong> → `Exit-Long` 或 `Exit-Short` JSON<br>• <em>（可选）</em>第二个开仓警报来反向交易</p>     |

---

### 🚀 高级功能

{% tabs %}
{% tab title="📈 多个止盈（Multiple TPs）" %}
**0-6 个止盈等级**

- 添加最多 **6 个 TP 步骤**
- 投资组合必须总和为 **1.0**
- 多交易对需要 `priceDeviation`（小数，不是 %）
- 单交易对可以使用 `price`

{% code title="示例：6 级止盈" %}

```json
"takeProfits": [
  { "priceDeviation": 0.01, "portfolio": 0.30 },
  { "priceDeviation": 0.02, "portfolio": 0.25 },
  { "priceDeviation": 0.03, "portfolio": 0.20 },
  { "priceDeviation": 0.04, "portfolio": 0.15 },
  { "priceDeviation": 0.05, "portfolio": 0.07 },
  { "priceDeviation": 0.06, "portfolio": 0.03 }
]
```

{% endcode %}

总和 = 1.0（100%） ✅
{% endtab %}

{% tab title="🔄 分批进场（Scale-In）" %}
**多次开仓**

在 Bot 设置中启用以实现：

- 分批成本（DCA）on 连续信号
- 建立更大的仓位
- 平均开仓价格

适用于两种工作流
{% endtab %}

{% tab title="🛡️ 仓位规模（Position Sizing）" %}
**amountPerTradeType 选项：**

**现货市场：**

- `quote` - 计价货币（例如 USDT）
- `base` - 基础货币（例如 BTC）
- `percents` - 余额百分比

**衍生品/期货：**

- `quote` - 计价货币
- `contracts` - 合约数量
- `percents` - 余额百分比
  {% endtab %}
  {% endtabs %}

---

### 🧠 专业提示

{% hint style="info" %}
**多交易对 Bot：** 使用 `priceDeviation`（小数，如 0.02 表示 2%），而不是 `price` 作为 TP/SL
{% endhint %}

- **priceDeviation 格式** – 使用小数（0.02）而不是百分比（2%）
- **投资组合总和** – TP 投资组合必须准确相加为 1.0（100%）
- **reduceOnly** – 适用于平仓；对现货市场无效
- **注释代码** – 从你的 Bot 精确复制；如果编辑 Bot 设置，它们会改变
- **策略警报** – 使用 `alert()` 函数和 `{{strategy.order.comment}}` 作为策略
- **纸质测试优先** – WunderTrading 日志如果 webhook 解析正确，会显示"Signal executed"

---

### 🛠️ 故障排除清单

| 症状                    | 可能原因/修复                                                     |
| ----------------------- | ----------------------------------------------------------------- |
| **没有成交出现**        | JSON 中的 `code` 与 Bot 的 Alert 注释不完全匹配（检查大小写！）   |
| **Bot 开仓但不平仓**    | Swing trade OFF 且你忘记平仓警报 – 或 `reduceOnly:false` 导致反向 |
| **Webhook 错误 400**    | JSON 语法错误或使用 `%` 代替小数（使用 `0.02`，而不是 `2%`）      |
| **重复成交**            | 警报设置为"Once Per Bar"而不是"Once Per Bar Close"                |
| **多交易对 TP/SL 失败** | 必须使用 `priceDeviation`（小数），而不是 `price`                 |
| **注释已更改**          | Bot 编辑可能会更改注释代码 - 任何 Bot 更改后更新警报              |

---

### 🔤 JSON 键参考

| 键                                     | 作用           | 详情                                                                                                                                             |
| -------------------------------------- | -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| **`code`**                             | 警报注释标识符 | 必须与 Bot 的注释完全匹配（区分大小写！）                                                                                                        |
| **`orderType`**                        | 订单执行类型   | `market`（市价）或 `limit`（限价）                                                                                                               |
| **`amountPerTradeType`**               | 仓位规模单位   | <p>现货: <code>quote</code>/<code>base</code>/<code>percents</code><br>期货: <code>quote</code>/<code>contracts</code>/<code>percents</code></p> |
| **`amountPerTrade`**                   | 仓位规模       | 值取决于上述类型                                                                                                                                 |
| **`takeProfits`**                      | 部分平仓数组   | <p><code>priceDeviation</code>: 小数（0.02 = 2%）<br><code>portfolio</code>: 要平仓的部分（必须总和为 1.0）</p>                                  |
| **`stopLoss`**                         | 止损配置       | `priceDeviation`: 从开仓价的小数距离                                                                                                             |
| **`reduceOnly`**                       | 防止仓位增加   | `true` → 仅平仓减少仓位（仅期货，对现货无效）                                                                                                    |
| **`placeConditionalOrdersOnExchange`** | 订单执行位置   | <p><code>false</code> = 由 Bot 管理<br><code>true</code> = 在交易所执行</p>                                                                      |

---

### 🎯 你应该使用哪种工作流？

{% columns %}
{% column width="50%" %}
**如果你想要以下情况，选择 Swing Trade：**

- 仅交易期货
- 想要最少警报
- 信任你的信号
- 始终持仓
  {% endcolumn %}

{% column %}
**如果你想要以下情况，选择 Explicit Exit：**

- 交易现货市场
- 需要仓位控制
- 想要仓位间隔
- 专注于风险管理
  {% endcolumn %}
  {% endcolumns %}

{% hint style="success" %}
**专业提示：** 从 Explicit Exit 开始学习，然后为期货效率切换到 Swing Trade
{% endhint %}

---

### 📚 资源

{% hint style="info" %}
**WunderTrading 官方文档：**

- **主文档：** [**https://help.wundertrading.com/en/**](https://help.wundertrading.com/en/)
- **Signal Bot 表单指南：** <https://help.wundertrading.com/en/articles/10458409-signal-bot-comprehensive-form-guide>
- **JSON 指南：** <https://help.wundertrading.com/en/articles/10475473-signal-bot-comprehensive-json-guide>
- **TradingView 设置：** <https://help.wundertrading.com/en/articles/5173846-how-to-set-up-a-tradingview-bot-signal-bot-in-wundertrading>
- **故障排除：** <https://help.wundertrading.com/en/articles/5173235-my-signal-bot-does-not-work>
  {% endhint %}

{% hint style="warning" %}
**重要提醒：**

- WunderTrading 是第三方服务，具有单独的订阅成本
- 始终先用小额或模拟交易进行测试
- 注释代码区分大小写，编辑 Bot 设置时可能会改变
- 手动通过 TradingView 交易始终是可用的替代方案
  {% endhint %}
