# 🔄 通过 3Commas 自动化 Infinity Algo 警报

将 Infinity Algo 信号直接连接到 3Commas，实现自动化交易执行。

---

### 🎯 三种集成方法

{% tabs %}
{% tab title="🔄 反向机器人 (Reversal Bot)" %}
**自动交易方向切换**

**功能说明：**

- 自动切换多头 (Long) ↔ 空头 (Short)
- 单个机器人处理双向交易
- 开启新仓位前关闭相反仓位

**最适用于：**

- ✅ 趋势行情
- ✅ 活跃交易
- ✅ 最大化效率
- ✅ 减少警报管理

{% code title="设置需求" %}

```
方向: 反向 (Reversal - 双向)
交易对: 单对或多对 (最多 200 个)
警报: 总共 2 个
- 买入信号 (Buy Signal) → enter_long
- 卖出信号 (Sell Signal) → enter_short
```

{% endcode %}

{% hint style="info" %}
**反向交易行为 (Reversal Behavior)：**

- **现货 (Spot)：** 启用反向仓位 (Reverse position ON) 时，相反信号会关闭并翻转; 禁用时忽略相反信号
- **期货对冲模式开启 (Futures Hedge Mode ON)：** 启用"反向仓位"来翻转交易
- **期货对冲模式关闭 (Futures Hedge Mode OFF)：** 机器人在开启新仓前自动关闭相反仓位
  {% endhint %}

为了简化起见，我们建议对反向交易工作流使用一个交易对配对一个机器人。
{% endtab %}

{% tab title="🎯 清洁退出 (Clean Exit)" %}
**无需禁用机器人直接退出**

**功能说明：**

- 干净地关闭仓位
- 机器人保持活跃状态以接收下一个信号
- 无需手动重新启用

**最适用于：**

- ✅ 连续交易
- ✅ 快速重新进场
- ✅ 自动化工作流
- ✅ 活跃策略

{% code title="设置需求" %}

```
方向: 多头 (Long) 或 空头 (Short)
警报: 总共 3 个
- 入场: enter_long/enter_short
- 出场: exit_long/exit_short
- 重新入场: enter_long/enter_short
```

{% endcode %}

{% hint style="success" %}
**专业建议 (Pro Tip)：** 退出信号仅使用市价执行 (market execution) - 限价出场订单会被拒绝
{% endhint %}
{% endtab %}

{% tab title="⏹️ 紧急停止 (Panic Stop)" %}
**禁用机器人并关闭所有仓位**

**功能说明：**

- 以市价关闭所有仓位
- 完全禁用机器人
- 需要手动重新启用

**最适用于：**

- ✅ 紧急停止
- ✅ 交易日结束
- ✅ 风险事件
- ✅ 手动干预

{% code title="设置需求" %}

```
操作: disable
子操作: market_close
注意: 机器人必须手动重新启用
```

{% endcode %}

{% hint style="danger" %}
**警告：** 机器人不会在下一个信号时自动重启 - 你必须手动重新启用
{% endhint %}
{% endtab %}
{% endtabs %}

---

### ⚙️ 步骤 1：配置信号机器人 (Signal Bot)

**导航至 3Commas：**

1. **登录** → 3Commas.io
2. **机器人 (Bots)** → **信号机器人 (Signal Bot)** → **创建机器人 (Create Bot)**
3. 使用以下设置进行配置：

| 设置 (Setting)            | 值 (Value)                                          |
| ------------------------- | --------------------------------------------------- |
| **名称 (Name)**           | 例如：Infinity Algo BTC                             |
| **交易所 (Exchange)**     | 选择你的交易所                                      |
| **交易对 (Pairs)**        | 单对或多对 (最多 200 个)                            |
| **警报类型 (Alert Type)** | 自定义信号 (Custom Signal)                          |
| **方向 (Direction)**      | 多头 (Long) / 空头 (Short) / 反向 (Reversal - 双向) |
| **止盈/止损 (TP/SL)**     | 在此设置或通过 webhook 设置                         |
| **风险上限 (Risk Caps)**  | 最大投资额、杠杆 (Leverage)                         |

对于多对机器人，还需设置**最大活跃智能交易 (Max active SmartTrades)**。

---

### 📩 步骤 2：获取 Webhook 凭证

保存机器人后，找到**"Message for deal start signal"**并复制：

{% code title="你的唯一凭证 (Your Unique Credentials)" overflow="wrap" %}

```json
{
  "secret": "ab12cd34.ef56gh78…", // 保持私密！
  "bot_uuid": "f1a2b3c4-…-9d0e1f2a", // 你的机器人 ID
  "action": "enter_long",
  "tv_exchange": "{{exchange}}",
  "tv_instrument": "{{ticker}}"
}
```

{% endcode %}

{% hint style="danger" %}
**安全警告：** 不要分享你的 `secret` 令牌 (token) - 它控制着你的机器人！信号机器人不再接受旧的 `bot_id`/`email_token` 配对。
{% endhint %}

---

### 📊 步骤 3：创建 TradingView 警报

**警报配置**

| 字段 (Field)         | 值 (Value)                                                           |
| -------------------- | -------------------------------------------------------------------- |
| **条件 (Condition)** | 精确匹配你的 Infinity Algo 信号                                      |
| **选项 (Options)**   | ✅ **柱子收盘时触发一次 (Once Per Bar Close)** (不是 "Once Per Bar") |
| **Webhook URL**      | `https://api.3commas.io/signal_bots/webhooks`                        |
| **消息 (Message)**   | JSON 模板，包含你的 YOUR-SECRET 和 YOUR-UUID                         |

{% hint style="info" %}
**重要提示：** 警报条件必须精确匹配你的 Infinity Algo 信号名称，包括任何数字前缀
{% endhint %}

---

### 📝 JSON 模板

{% hint style="warning" %}
**必需字段：** 所有信号必须包含 `secret`、`bot_uuid`、`action`、`tv_exchange` 和 `tv_instrument`
{% endhint %}

{% tabs %}
{% tab title="🟢 多头入场 (Long Entry)" %}
{% code title="enter\_long.json" overflow="wrap" lineNumbers="true" %}

```json
{
  "secret": "YOUR-SECRET",
  "bot_uuid": "YOUR-UUID",
  "action": "enter_long",

  "tv_exchange": "{{exchange}}",
  "tv_instrument": "{{ticker}}",

  "order": {
    "amount": 150,
    "currency_type": "quote",
    "order_type": "market"
  },

  "take_profit": {
    "enabled": true,
    "steps": [
      { "order_type": "limit", "price_percent": 1, "volume_percent": 25 },
      { "order_type": "limit", "price_percent": 2, "volume_percent": 25 },
      { "order_type": "limit", "price_percent": 3, "volume_percent": 25 },
      { "order_type": "market", "price_percent": 4, "volume_percent": 25 }
    ]
  },

  "stop_loss": {
    "enabled": true,
    "order_type": "market",
    "trigger_price_percent": 1
  },

  "max_lag": 300,
  "timestamp": "{{timenow}}"
}
```

{% endcode %}

**注意：** 对于限价入场，添加 `"price"` 或 `"price_percent"`，以及可选的 `"price_percent_ref_type"`
{% endtab %}

{% tab title="🔴 空头入场 (Short Entry)" %}
{% code title="enter\_short.json" overflow="wrap" lineNumbers="true" %}

```json
{
  "secret": "YOUR-SECRET",
  "bot_uuid": "YOUR-UUID",
  "action": "enter_short",

  "tv_exchange": "{{exchange}}",
  "tv_instrument": "{{ticker}}",

  "order": {
    "amount": 150,
    "currency_type": "quote",
    "order_type": "market"
  },

  "take_profit": {
    "enabled": true,
    "steps": [
      { "order_type": "limit", "price_percent": 1, "volume_percent": 25 },
      { "order_type": "limit", "price_percent": 2, "volume_percent": 25 },
      { "order_type": "limit", "price_percent": 3, "volume_percent": 25 },
      { "order_type": "market", "price_percent": 4, "volume_percent": 25 }
    ]
  },

  "stop_loss": {
    "enabled": true,
    "order_type": "market",
    "trigger_price_percent": 1
  },

  "max_lag": 300,
  "timestamp": "{{timenow}}"
}
```

{% endcode %}
{% endtab %}

{% tab title="✅ 多头出场 (Exit Long)" %}
{% code title="exit\_long.json" overflow="wrap" %}

```json
{
  "secret": "YOUR-SECRET",
  "bot_uuid": "YOUR-UUID",
  "action": "exit_long",

  "tv_exchange": "{{exchange}}",
  "tv_instrument": "{{ticker}}",

  "order": {
    "amount": 100,
    "currency_type": "position_percent"
  },

  "max_lag": 300,
  "timestamp": "{{timenow}}"
}
```

{% endcode %}

**注意：** 出场订单仅支持市价执行 - 不要添加 `"order_type": "limit"`
{% endtab %}

{% tab title="❌ 空头出场 (Exit Short)" %}
{% code title="exit\_short.json" overflow="wrap" %}

```json
{
  "secret": "YOUR-SECRET",
  "bot_uuid": "YOUR-UUID",
  "action": "exit_short",

  "tv_exchange": "{{exchange}}",
  "tv_instrument": "{{ticker}}",

  "order": {
    "amount": 100,
    "currency_type": "position_percent"
  },

  "max_lag": 300,
  "timestamp": "{{timenow}}"
}
```

{% endcode %}
{% endtab %}

{% tab title="⏹️ 紧急停止 (Panic Stop)" %}
{% code title="disable\_bot.json" overflow="wrap" %}

```json
{
  "secret": "YOUR-SECRET",
  "bot_uuid": "YOUR-UUID",
  "action": "disable",

  "tv_exchange": "{{exchange}}",
  "tv_instrument": "{{ticker}}",

  "positions_sub_action": "market_close",

  "max_lag": 300,
  "timestamp": "{{timenow}}"
}
```

{% endcode %}

{% hint style="danger" %}
这会完全禁用机器人 - 需要手动重新启用！
{% endhint %}
{% endtab %}
{% endtabs %}

---

### ⚡ 快速参考

| 参数 (Parameter)           | 用途 (Purpose)                             | 值和规则 (Values & Rules)                              |
| -------------------------- | ------------------------------------------ | ------------------------------------------------------ |
| **price_percent**          | 止盈距离 (TP distance)                     | 整数：1 = 1%, 2 = 2%                                   |
| **volume_percent**         | 仓位平仓百分比 (% of position to close)    | 总和必须为 100%                                        |
| **trigger_price_percent**  | 止损触发距离 (Stop loss distance)          | 整数：1 = 亏损 1%                                      |
| **currency_type**          | 订单规模单位 (Order size unit)             | `quote`、`base`、`margin_percent`、`position_percent`  |
| **amount**                 | 仓位大小 (Position size)                   | 基于 `currency_type` 设置的数字                        |
| **max_lag**                | 拒绝过期信号 (Reject stale signals)        | 秒数 (300 = 5 分钟)                                    |
| **timestamp**              | 信号新鲜度 (Signal freshness)              | 始终使用 `{{timenow}}`                                 |
| **price_percent_ref_type** | 限价的价格参考 (Price reference for limit) | `current_price`、`base_entry_price`、`avg_entry_price` |

---

### 🎯 应该选择哪种方法？

| 功能特性 (Feature)             | 🔄 反向机器人 (Reversal Bot) | 🎯 清洁退出 (Clean Exit)  | ⏹️ 紧急停止 (Panic Stop) |
| ------------------------------ | ---------------------------- | ------------------------- | ------------------------ |
| **最适用于 (Best For)**        | 趋势行情                     | 连续交易                  | 紧急停止                 |
| **需要的警报 (Alerts Needed)** | 2 个 (最少)                  | 3 个 (入场/出场/重新入场) | 1 个 (停止所有)          |
| **仓位状态 (Position State)**  | 始终在仓                     | 灵活间隔                  | 完全平仓                 |
| **机器人状态 (Bot Status)**    | ✅ 始终活跃                  | ✅ 始终活跃               | ❌ 已禁用                |
| **重新入场 (Re-entry)**        | 自动                         | 自动                      | 手动必需                 |
| **理想交易者 (Ideal Trader)**  | 活跃/自信                    | 灵活/谨慎                 | 风险厌恶                 |

{% columns %}
{% column width="50%" %}
**如果你满足以下条件，选择反向机器人：**

- 交易趋势对
- 相信你的信号
- 想要一劳永逸
  {% endcolumn %}

{% column %}
**如果你满足以下条件，选择清洁退出：**

- 需要仓位控制
- 交易多个对
- 需要间隔期
  {% endcolumn %}
  {% endcolumns %}

---

### 🚀 高级功能

{% tabs %}
{% tab title="📈 多个止盈点 (Multiple TPs)" %}
**最多 8 个止盈级别**

- UI 支持最多 4 个级别
- JSON 支持最多 8 个级别
- 交易量必须总计 **100%**
- 可以混合限价和市价订单
- 尾随平仓仅在最后一步

{% code title="示例：8 级止盈含尾随平仓 (Example: 8-Level TP with Trailing)" %}

```json
"take_profit": {
  "enabled": true,
  "steps": [
    { "order_type": "limit", "price_percent": 1, "volume_percent": 20 },
    { "order_type": "limit", "price_percent": 2, "volume_percent": 20 },
    { "order_type": "limit", "price_percent": 3, "volume_percent": 15 },
    { "order_type": "limit", "price_percent": 4, "volume_percent": 15 },
    { "order_type": "limit", "price_percent": 5, "volume_percent": 10 },
    { "order_type": "limit", "price_percent": 6, "volume_percent": 10 },
    { "order_type": "limit", "price_percent": 7, "volume_percent": 5 },
    { "order_type": "market", "price_percent": 8, "volume_percent": 5,
      "trailing": { "enabled": true, "percent": 0.2 }
    }
  ]
}
```

{% endcode %}
{% endtab %}

{% tab title="🛡️ 尾随止损 (Trailing Stop)" %}
**动态止损**

{% code title="尾随止损配置 (Trailing Stop Configuration)" %}

```json
"stop_loss": {
  "enabled": true,
  "order_type": "market",
  "trigger_price_percent": 2,
  "trailing": {
    "enabled": true,
    "percent": 0.5
  }
}
```

{% endcode %}

在最高利润后跟踪 0.5%
{% endtab %}

{% tab title="🤖 机器人过滤器 (Bot Filters)" %}
**价格偏差和平仓条件**

在机器人配置中（不在 JSON 中）：

- **价格偏差过滤器 (Price deviation filters)：** 防止不利的入场
- **最小利润 (Minimum profit)：** 可能会阻止平仓直到达到利润目标

如果平仓不起作用，检查你的机器人的 **最小利润/平仓条件 (Minimum profit/Deal close conditions)**
{% endtab %}
{% endtabs %}

---

### 🛠️ 故障排查检查清单 (Troubleshooting Checklist)

| ✅ 检查 (Check)                              | 详情 (Details)                                                            |
| -------------------------------------------- | ------------------------------------------------------------------------- |
| **有效的凭证 (Valid Credentials)**           | JSON 必须包含有效的 `secret` 和 `bot_uuid`                                |
| **必需字段 (Required Fields)**               | 始终在所有信号中包含 `tv_exchange` 和 `tv_instrument`                     |
| **正确的 Webhook URL (Correct Webhook URL)** | 必须完全是 `https://api.3commas.io/signal_bots/webhooks`                  |
| **警报时间 (Alert Timing)**                  | 警报在**柱子收盘时触发一次 (Once Per Bar Close)** （不是 "Once Per Bar"） |
| **每个操作一个警报 (One Alert Per Action)**  | 永远不要在一个 JSON 中合并入场和出场                                      |
| **字段名称 (Field Names)**                   | 使用 `price_percent` 而不是 `price_deviation`                             |
| **交易量总计 100% (Volumes Sum to 100)**     | 所有 `volume_percent` 必须精确总计 100                                    |
| **退出订单 (Exit Orders)**                   | 出场信号仅使用市价执行 - 无限价订单                                       |
| **信号新鲜度 (Signal Freshness)**            | 包含 `max_lag` 和 `timestamp` 以防止过期信号                              |
| **机器人重新启用 (Bot Re-enabling)**         | 如果使用 `disable`，必须手动重新启用机器人                                |
| **出场不工作 (Exit Not Working)**            | 检查机器人的最小利润/平仓条件                                             |

---

### 📖 JSON 字段词汇表 (JSON Field Glossary)

| 字段 (Field)                 | 用途 (Purpose)                                   | 值和规则 (Values & Rules)                                                     |
| ---------------------------- | ------------------------------------------------ | ----------------------------------------------------------------------------- |
| **`secret`**                 | 私人机器人令牌 (Private bot token)               | **必需** - 从步骤 2 精确复制                                                  |
| **`bot_uuid`**               | 唯一信号机器人 ID (Unique Signal Bot ID)         | **必需** - 从步骤 2 复制                                                      |
| **`action`**                 | 机器人命令 (Bot command)                         | **必需** - `enter_long`、`enter_short`、`exit_long`、`exit_short`、`disable`  |
| **`tv_exchange`**            | TradingView 交易所 (TradingView exchange)        | **必需** - 始终为 `{{exchange}}`                                              |
| **`tv_instrument`**          | TradingView 交易对 (TradingView pair)            | **必需** - 始终为 `{{ticker}}`                                                |
| **`positions_sub_action`**   | 当操作为 `disable` 时 (When action is `disable`) | <p><code>market_close</code> → 平仓并禁用<br><code>cancel</code> → 仅取消</p> |
| **`order.amount`**           | 仓位大小 (Position size)                         | 基于 `currency_type` 设置                                                     |
| **`order.order_type`**       | 入场订单类型 (Entry order type)                  | `market` 或 `limit` (限价需要 `price` 或 `price_percent`)                     |
| **`currency_type`**          | 金额单位 (Unit for amount)                       | `quote`、`base`、`margin_percent`、`position_percent`                         |
| **`price`**                  | 精确限价 (Exact limit price)                     | 限价订单的精确价格值                                                          |
| **`price_percent`**          | TP/限价距离 (TP/limit distance)                  | 整数：1 = 1%，2 = 2%                                                          |
| **`price_percent_ref_type`** | 百分比参考 (Reference for percent)               | `current_price`、`base_entry_price`、`avg_entry_price`                        |
| **`volume_percent`**         | 每个 TP 的平仓百分比 (% to close at each TP)     | 1-100（必须总计 100%）                                                        |
| **`trigger_price_percent`**  | 止损触发 (Stop loss trigger)                     | 整数：1 = 亏损 1%                                                             |
| **`max_lag`**                | 信号年龄限制 (Signal age limit)                  | 秒数（300 = 5 分钟）                                                          |
| **`timestamp`**              | 当前时间 (Current time)                          | 始终为 `{{timenow}}`                                                          |

---

### 📚 资源 (Resources)

{% hint style="info" %}
**官方 3Commas 文档 (Official 3Commas Documentation)：**

- **信号机器人指南 (Signal Bot Guide)：** [**https://help.3commas.io/en/articles/8529406-signal-bot-custom-signal-type**](https://help.3commas.io/en/articles/8529406-signal-bot-custom-signal-type)
- **JSON 格式指南 (JSON Format Guide)：** <https://help.3commas.io/en/articles/8894481-signal-bot-json-file-in-custom-signal-type>
- **信号机器人常见问题 (Signal Bot FAQ)：** <https://help.3commas.io/en/articles/8637909-signal-bot-faq>
- **入门指南 (Getting Started)：** <https://help.3commas.io/en/collections/3181386-getting-started>
  {% endhint %}

{% hint style="warning" %}
**重要提醒 (Important Reminders)：**

- 3Commas 是一个第三方服务，需要单独的订阅成本
- 信号机器人需要付费的 TradingView 计划才能使用 webhooks
- 退出订单仅支持市价执行（限价订单会被拒绝）
- 始终先用小金额或演示账户进行测试
- 通过 TradingView 手动交易始终可用作替代方案
  {% endhint %}
