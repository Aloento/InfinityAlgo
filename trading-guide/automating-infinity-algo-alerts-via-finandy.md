# 🔄 通过 Finandy 自动化 Infinity Algo 警报

---

### 🎯 指标集成方法

{% tabs %}
{% tab title="📊 双警报设置" %}
**分开的买入/卖出警报（指标必需）**

**功能说明：**

- 两个独立警报（买入和卖出）
- 清晰的信号分离
- 适用于任何指标
- 无需代码访问权限

**最适合：**

- ✅ 所有 Infinity Algo 用户
- ✅ 简单设置
- ✅ 清晰的控制
- ✅ 测试和生产环境

{% code title="警报要求" %}

```
警报：共 2 个（指标每个警报只能发送一种信号类型）
- 买入信号 → side: "buy"
- 卖出信号 → side: "sell"
头寸方向：双向/仅做多/仅做空
```

{% endcode %}

{% hint style="info" %}
**头寸方向选项：**

- **双向（Both）** → 买入时开多头（Long），卖出时开空头（Short）（单向模式下的反向平仓）
- **仅做多（Long only）** → 仅做多头交易
- **仅做空（Short only）** → 仅做空头交易
- **策略（Strategy）** → 仅限 TradingView 策略使用（不适用于指标！）
  {% endhint %}
  {% endtab %}
  {% endtabs %}

{% hint style="warning" %}
**重要提示：** 由于 Infinity Algo 是一个指标，您必须创建两个单独的警报。`"side"` 字段必须包含值 `"buy"` 或 `"sell"`（小写）。策略占位符如 `{{strategy.order.action}}` 不支持使用。
{% endhint %}

---

### ⚙️ 第一步：配置 Finandy Webhook

**访问 Finandy：**

1. **登录** → Finandy.com
2. **Algo-trading** → **TradingView Signals**
3. **创建新信号（webhook）**
4. 配置主要设置：

| 字段         | 值                                 |
| ------------ | ---------------------------------- |
| **名称**     | 例如 _Infinity Algo 信号_          |
| **货币对**   | `{{ticker}}`（一个钩子适用于所有） |
| **头寸方向** | **双向** 或 **仅做多**/**仅做空**  |
| **保存**     | 显示信号 URL 和消息                |

{% hint style="danger" %}
**不要选择"策略"作为头寸方向** - 这仅适用于 TradingView 策略，不适用于指标
{% endhint %}

---

### 📩 第二步：获取 Webhook 凭证

保存后，Finandy 显示您的唯一 webhook 详细信息。按显示方式精确复制：

- **信号 URL**：复制为您的信号显示的精确 URL
- **信号消息**：复制包含您的密钥令牌的模板

{% hint style="danger" %}
**安全性：** 保护您的 `secret` 令牌安全！默认情况下，Finandy 仅接受来自 TradingView IP 的请求。
{% endhint %}

---

### 📊 第三步：创建两个 TradingView 警报

您必须创建两个单独的警报 - 一个用于买入信号，一个用于卖出信号。

**警报配置**

| 警报字段        | 值                                       |
| --------------- | ---------------------------------------- |
| **条件**        | Infinity Algo → 选择您的信号             |
| **选项**        | **Once Per Bar Close**（K 线收盘时触发） |
| **Webhook URL** | 粘贴第二步中的精确信号 URL               |
| **消息**        | JSON 模板（见下文）                      |

---

### 📝 每个警报的 JSON 模板

{% tabs %}
{% tab title="🟢 警报 #1：买入信号" %}
**在买入条件上创建此警报：**

{% code title="buy_signal.json" overflow="wrap" %}

```json
{
  "name": "Infinity Algo Signals",
  "secret": "YOUR-SECRET",
  "side": "buy",
  "symbol": "{{ticker}}"
}
```

{% endcode %}

**必需：** `"side": "buy"`（小写）
{% endtab %}

{% tab title="🔴 警报 #2：卖出信号" %}
**在卖出条件上创建此警报：**

{% code title="sell_signal.json" overflow="wrap" %}

```json
{
  "name": "Infinity Algo Signals",
  "secret": "YOUR-SECRET",
  "side": "sell",
  "symbol": "{{ticker}}"
}
```

{% endcode %}

**必需：** `"side": "sell"`（小写）
{% endtab %}

{% tab title="🎯 高级：自定义止盈（TP）" %}
**从警报中覆盖止盈设置：**

{% code title="custom_tp.json" overflow="wrap" lineNumbers="true" %}

```json
{
  "name": "Infinity Algo Signals",
  "secret": "YOUR-SECRET",
  "side": "buy",
  "symbol": "{{ticker}}",
  "tp": {
    "orders": [
      { "ofs": "1.0", "price": "", "piece": "25" },
      { "ofs": "2.0", "price": "", "piece": "25" },
      { "ofs": "3.0", "price": "", "piece": "25" },
      { "ofs": "4.0", "price": "", "piece": "25" }
    ],
    "update": true
  }
}
```

{% endcode %}

**注意：** 在 Finandy UI 中勾选"止盈（TP）"模块复选框以接受来自信号的值，并包含 `"update": true`
{% endtab %}
{% endtabs %}

---

### 🎯 第四步：在 Finandy 中设置止盈和止损（可选）

{% tabs %}
{% tab title="📈 止盈（Take Profit）" %}

1. 打开您创建的 webhook → **止盈（Take Profit, TP）** 选项卡
2. 勾选 **启用止盈** → 选择 **限价单** 或 **市价单**
3. **订单数量** → 选择有多少个层级
4. **价格偏移** (%) 和每个层级的 **订单分配** (%)
5. **级别重新排序** 在您分批建仓（DCA）时保持百分比不变
6. 要接受来自信号的止盈覆盖，勾选复选框以启用

所有止盈订单都在交易所挂单；无需额外的 TradingView 警报。
{% endtab %}

{% tab title="🛡️ 止损（Stop Loss）" %}

1. 打开 webhook → **止损（Stop Loss, SL）** 选项卡
2. 勾选 **启用止损**
3. 选择 **市价单** 或 **限价单**
4. 设置 **价格偏移** (%)
5. 可选：启用 **跟踪止损（Trailing）**

止损订单在交易所执行以实现最快执行速度。
{% endtab %}

{% tab title="🔄 订单类型" %}
**真实订单（Real）与虚拟订单（Virtual）：**

- **真实（Real）** = 立即在交易所下单
- **虚拟（Virtual）** = 由终端（Terminal）管理，直到触发条件满足

根据您的交易所和需求选择。
{% endtab %}
{% endtabs %}

---

### ⚡ 警报设置示例

{% columns %}
{% column width="50%" %}
**对于"买入信号 - Smart"：**

1. 条件：Infinity Algo → "Buy Signal - Smart"
2. Webhook URL：您的 Finandy 信号 URL
3. 消息：买入 JSON，包含 `"side": "buy"`
   {% endcolumn %}

{% column %}
**对于"卖出信号 - Smart"：**

1. 条件：Infinity Algo → "Sell Signal - Smart"
2. Webhook URL：相同的 Finandy 信号 URL
3. 消息：卖出 JSON，包含 `"side": "sell"`
   {% endcolumn %}
   {% endcolumns %}

---

### 🧪 第五步：测试和监控

- **界面 → 信号日志** 显示每个接收到的 webhook，其中包含 "OK" 或错误代码
- 从很小的仓位开始以验证设置
- 检查买入和卖出警报是否都正常工作
- 使用信号日志查看接收到的 JSON 和采取的操作

{% hint style="warning" %}
**测试清单：** ✅ 已创建两个单独的警报 ✅ 买入警报包含 `"side": "buy"`（小写）✅ 卖出警报包含 `"side": "sell"`（小写）✅ 两者使用相同的 webhook URL 和密钥 ✅ 信号日志显示两种类型的信号
{% endhint %}

---

### 🎯 头寸方向配置

| 您的交易风格           | 头寸方向设置         | 结果                               |
| ---------------------- | -------------------- | ---------------------------------- |
| **做多和做空（反向）** | 双向（Both）         | 在开新单前关闭相反头寸（单向模式） |
| **仅做多**             | 仅做多（Long only）  | 忽略卖出信号                       |
| **仅做空**             | 仅做空（Short only） | 忽略买入信号                       |
| **策略模式**           | 策略（Strategy）     | 仅限 TradingView 策略              |

{% hint style="danger" %}
**套期保值模式警告：** 在套期保值（Hedge）模式中，对于指标使用 **仅做多** 或 **仅做空**。头寸方向"双向"在套期保值模式中无法正确关闭 - 它旨在用于单向模式反向平仓。
{% endhint %}

---

### 🛠️ 故障排除检查清单

| 问题               | 解决方案                                          |
| ------------------ | ------------------------------------------------- |
| **403 错误**       | 错误的 **密钥** 或 URL 缺少 **https://**          |
| **"Unknown side"** | `side` 必须精确为 `"buy"` 或 `"sell"`（小写）     |
| **无订单**         | 检查头寸方向是否未设置为"策略"                    |
| **仅买入有效**     | 您是否创建了卖出警报？                            |
| **错误的交易对**   | 验证 `{{ticker}}` 占位符                          |
| **无反向平仓**     | 检查头寸方向 = "双向" 且启用了单向模式            |
| **套期保值问题**   | 在套期保值模式中使用仅做多/仅做空，不要使用"双向" |

---

### 🔤 JSON 键参考（Finandy）

| 键              | 含义                | 详情                                   |
| --------------- | ------------------- | -------------------------------------- |
| **`name`**      | Webhook 标识符      | 任何描述性名称                         |
| **`secret`**    | 来自信号的授权令牌  | 保护好！                               |
| **`side`**      | 交易方向            | **必需：** `"buy"` 或 `"sell"`（小写） |
| **`symbol`**    | 交易对              | 通常是 `{{ticker}}`                    |
| **`tp.orders`** | 止盈水平数组        | 可选覆盖                               |
| **`ofs`**       | 距离入场价的 % 偏移 | 字符串："1.0" = 1%                     |
| **`piece`**     | 头寸的 %            | 百分比总和等于预期总额                 |
| **`update`**    | 应用新设置          | `true` 从信号覆盖止盈                  |

---

### 📚 资源

{% hint style="info" %}
**Finandy 官方文档：**

- **主文档：** <https://docs.finandy.com/>
- **TradingView 连接：** <https://docs.finandy.com/algo-trading/signals-tradingview/connection-and-configuration/indicator-strategy-connection>
- **信号界面：** <https://docs.finandy.com/algo-trading/signals-tradingview/interface>
- **头寸管理：** <https://docs.finandy.com/algo-trading/signals/interface/open>
  {% endhint %}

{% hint style="warning" %}
**重要提醒：**

- Finandy 是第三方服务，需要单独付费
- 指标需要两个警报（分别购买和出售）
- `"side"` 字段是必需的，必须为小写
- 首先用小额进行测试
- 通过 TradingView 手动交易始终可用
  {% endhint %}
