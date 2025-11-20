# 🔄 通过 Alertatron 自动化 Infinity Algo 警报

{% hint style="danger" %}
**重要提示：Alertatron 有两个不同的系统。不要混合使用：**

- **Signals Lite** - 仅支持 JSON 消息，无脚本
- **Script Bots** - 完整脚本支持，使用 `MyKeys{...} #bot` 标签

**Signals Lite 不使用 `MyKeys{...}` 或 `#bot` 标签！**

选择其中一个系统，并严格按照下方的对应指南操作。
{% endhint %}

---

### 🎯 你应该使用哪个系统？

{% tabs %}
{% tab title="大多数用户 → Signals Lite" %}
**如果您想要以下功能，选择 Signals Lite：**

- ✅ 快速 5 分钟设置
- ✅ 可视化配置（无需编码）
- ✅ 简单的多头/空头自动化
- ✅ 错误风险更低
- ✅ 易于修改设置

**适用于：**

- 自动化新手
- 基本买入/卖出/平仓需求
- 希望快速启动

{% endtab %}

{% tab title="高级用户 → Script Bots" %}
**如果您需要以下功能，选择 Script Bots：**

- ✅ 复杂的订单逻辑
- ✅ 多步骤止盈梯度（Multi-step TP ladders）
- ✅ 条件执行
- ✅ 仓位加仓（Position pyramiding）
- ✅ 自定义 OCO 组
- ✅ 时间延迟

**所需技能：**

- 熟悉代码
- 能够调试脚本
- 需要高级功能

{% endtab %}
{% endtabs %}

---

## 📘 方案 1：Signals Lite（推荐）

基于 JSON 信号的自动化，支持可视化配置。

### ⚙️ 第 1 步：创建 Signals Lite 机器人

1. 导航至 **Signals Lite → Your Bots**
2. 点击 **"Create new automated bot..."**
3. 配置你的机器人：

| 字段         | 需要输入的内容           |
| ------------ | ------------------------ |
| **Bot name** | 例如 `Infinity Algo BTC` |
| **Exchange** | 选择你的交易所           |
| **Symbol**   | 例如 `BTCUSDT` 或 `BTC`  |
| **Access**   | 设置为 Private           |

4. 点击 **Create Bot**

### 🔑 第 2 步：配置机器人设置

创建机器人后：

{% tabs %}
{% tab title="API 密钥" %}

1. 点击你的机器人名称进行展开
2. 找到 **"API Keys"** 部分
3. 添加你的交易所 API 凭证
4. **保存** 配置

{% hint style="warning" %}
切勿为交易机器人启用提现权限
{% endhint %}
{% endtab %}

{% tab title="信号设置" %}
配置默认行为，可以按警报覆盖：

- **Position Size**（仓位大小）：账户余额百分比或固定金额
- **Leverage**（杠杆倍数）：你的首选杠杆
- **Order Type**（订单类型）：市价或限价
- **Take Profit**（止盈）：启用并设置偏移百分比
- **Stop Loss**（止损）：设置风险百分比
- **Hedge Mode**（对冲模式）：如果交易所支持

{% hint style="info" %}
你可以使用 JSON 为每个警报覆盖任何这些字段。参见 [Override signal settings](https://alertatron.com/docs/signals-lite/override-signal-settings)
{% endhint %}
{% endtab %}
{% endtabs %}

### 📩 第 3 步：获取你的 Webhook

{% hint style="warning" %}
**复制机器人页面上显示的确切 webhook。** 不要猜测路径——格式可能会改变。
{% endhint %}

你的机器人页面将显示一个唯一的 webhook URL。完全按照显示的内容复制——你需要它来在 TradingView 中使用。

### 📊 第 4 步：创建 TradingView 警报

#### 可用的 Infinity Algo 警报

{% tabs %}
{% tab title="入场信号（Entry Signals）" %}
**买入信号：**

- `1.0 Buy Signal - Normal`
- `1.1 Buy Signal - Smart`&#x20;
- `1.2 Normal or Smart Buy`&#x20;
- `1.3 Buy Signal - HL Sniper`
- `1.4 Buy Signal - AI`

**卖出信号：**

- `1.5 Sell Signal - Normal`
- `1.6 Sell Signal - Smart`&#x20;
- `1.7 Normal or Smart Sell`
- `1.8 Sell Signal - HL Sniper`
- `1.9 Sell Signal - AI`

{% endtab %}

{% tab title="出场信号（Exit Signals）" %}
**管理：**

- `2.0 Take Profit Long`
- `2.1 Take Profit Short`
- `2.2 Stop Loss Long Hit`
- `2.3 Stop Loss Short Hit`
- `2.4 Possible Long Coming`（仅供参考）
- `2.5 Possible Short Coming`（仅供参考）

{% endtab %}
{% endtabs %}

#### 警报配置

1. 打开你的 Infinity Algo 图表
2. 创建警报（Alt+A）
3. 配置：

| 字段                       | 值                                                      |
| -------------------------- | ------------------------------------------------------- |
| **Condition**（条件）      | 例如 "1.1 Buy Signal - Smart"                           |
| **Options**（选项）        | **Once Per Bar Close**（每根 K 线闭合一次，防止重复！） |
| **Alert name**（警报名称） | 例如 "IA Smart Buy"                                     |
| **Message**（消息）        | JSON 模板（见下方）                                     |
| **Webhook URL**            | 你的机器人 webhook（来自第 3 步）                       |

### 📝 Signals Lite 消息模板

{% hint style="danger" %}
**消息必须是有效的 JSON 格式。** 从简单开始（side + amount），可选择覆盖默认值如 TP/SL、对冲模式或平仓对手方。
{% endhint %}

{% tabs %}
{% tab title="基础 JSON" %}
**最小多头入场：**

```json
{ "side": "long", "amount": "25%" }
```

**最小空头入场：**

```json
{ "side": "short", "amount": "25%" }
```

**平仓：**

```json
{ "side": "close" }
```

{% endtab %}

{% tab title="带覆盖参数" %}
**多头带 TP/SL 覆盖：**

```json
{
  "side": "long",
  "amount": "50%",
  "takeProfit": true,
  "takeProfitOffset": "2%",
  "stopLoss": true,
  "stopLossOffset": "1%",
  "closeExisting": true
}
```

**空头带杠杆：**

```json
{
  "side": "short",
  "amount": "100%",
  "leverage": 10,
  "takeProfit": true,
  "takeProfitOffset": "1.5%"
}
```

{% endtab %}

{% tab title="动态值" %}
**使用 TradingView 占位符：**

```json
{
  "side": "long",
  "amount": "25%",
  "entry": "limit",
  "price": "{{close}}"
}
```

{% hint style="info" %}
不要包含 `symbol` - 它已经在机器人配置中设置
{% endhint %}
{% endtab %}
{% endtabs %}

#### 可用的覆盖字段

完整文档参见：[Override signal settings](https://alertatron.com/docs/signals-lite/override-signal-settings)

| 字段               | 类型    | 描述                          |
| ------------------ | ------- | ----------------------------- |
| `side`             | string  | "long"、"short" 或 "close"    |
| `amount`           | string  | 仓位大小（例如 "50%"、"100"） |
| `takeProfit`       | boolean | 启用止盈                      |
| `takeProfitOffset` | string  | TP 距离（例如 "2%"）          |
| `stopLoss`         | boolean | 启用止损                      |
| `stopLossOffset`   | string  | SL 距离（例如 "1%"）          |
| `closeExisting`    | boolean | 先平仓对手方                  |
| `useHedgeMode`     | boolean | 使用对冲模式（如果可用）      |
| `leverage`         | number  | 覆盖杠杆倍数                  |
| `entry`            | string  | "market" 或 "limit"           |
| `price`            | string  | 限价（如果 entry="limit"）    |

{% hint style="info" %}
对于多交易对机器人，使用**百分比/偏移字段**（例如 `takeProfitOffset`），而不是固定价格。
{% endhint %}

{% hint style="success" %}
**就是这样！** 你的 Signals Lite 机器人已准备好。先用小额测试。
{% endhint %}

---

## 📗 方案 2：Script Bots（高级）

完整的脚本控制，支持复杂订单逻辑和多步骤 TP 梯度。

{% hint style="warning" %}
**先决条件：** 理解基础脚本编程，能够调试语法错误。否则，请使用上方的 Signals Lite。
{% endhint %}

### ⚙️ 第 1 步：配置 Script Bot 基础设施

#### A. 首先添加 API 密钥

1. 转到 **Scripting Signals → Script Bot Config → Script Bot API Keys**
2. 点击 **"Add API Keys"**
3. 配置：
   - **Name**（名称）：例如 `MyKeys`（记住这个确切的名称！）
   - **Exchange**（交易所）：你的交易所
   - **API Key & Secret**：你的凭证
4. **保存** 你的密钥

#### B. 获取你的账户 Webhook

1. 转到 **Account → Webhook Details**
2. **复制显示的确切 webhook**（不要猜测格式）

#### C. 配置机器人组

1. 转到 **Scripting Signals → Trading Bot Settings**
2. 设置一个用于过滤 `#bot` 的组
3. 将此组路由到交易引擎

{% hint style="info" %}
Script Bots 通过你的账户 webhook 使用 `#bot` 标签进行路由，而不是单独的机器人 webhook
{% endhint %}

### 📊 第 2 步：可用的警报条件

与 Signals Lite 相同 - 所有 16 个警报可用：

<details>

<summary>点击查看完整警报列表</summary>

**买入入场：**

- 1.0 至 1.4

**卖出入场：**

- 1.5 至 1.9

**管理：**

- 2.0 至 2.3

</details>

### 📋 第 3 步：创建 TradingView 警报

配置类似，但**消息包含脚本**：

| 字段                  | 值                                                      |
| --------------------- | ------------------------------------------------------- |
| **Condition**（条件） | 你选择的信号                                            |
| **Options**（选项）   | **Once Per Bar Close**（每根 K 线闭合一次，防止重复！） |
| **Message**（消息）   | 你的脚本（见模板）                                      |
| **Webhook URL**       | 你的账户 webhook（不是 Signals Lite！）                 |

### 📝 Script Bot 模板

{% hint style="danger" %}
**每个脚本必须以 `#bot` 结尾，否则不会执行！**
{% endhint %}

{% tabs %}
{% tab title="🟢 多头入场" %}
{% code title="long_entry.txt" overflow="wrap" lineNumbers="true" %}

```
MyKeys({{ticker}}) {
  # 用 100% 可用余额入场多头
  market(side=buy, amount=100%a);

  # 止损设在入场价下方 1%
  stopOrder(side=sell, amount=100%p, stop=e-1%, reduceOnly=true);

  # 带 OCO 的多步骤止盈梯度
  oneCancelsOther(which=all);
    limit(position=75%p, offset=e1%, reduceOnly=true);
    limit(position=50%p, offset=e2%, reduceOnly=true);
    limit(position=25%p, offset=e3%, reduceOnly=true);
    limit(position=0,    offset=e4%, reduceOnly=true);
  oneCancelsOther();
}
#bot
```

{% endcode %}

**这种多步骤止盈梯度仅在 Script Bots 中可用！**
{% endtab %}

{% tab title="🔴 空头入场" %}
{% code title="short_entry.txt" overflow="wrap" lineNumbers="true" %}

```
MyKeys({{ticker}}) {
  # 入场空头
  market(side=sell, amount=100%a);

  # 止损设在入场价上方 1%
  stopOrder(side=buy, amount=100%p, stop=e+1%, reduceOnly=true);

  # 带 OCO 的多步骤止盈梯度（空头用负值）
  oneCancelsOther(which=all);
    limit(position=-75%p, offset=e-1%, reduceOnly=true);
    limit(position=-50%p, offset=e-2%, reduceOnly=true);
    limit(position=-25%p, offset=e-3%, reduceOnly=true);
    limit(position=0,     offset=e-4%, reduceOnly=true);
  oneCancelsOther();
}
#bot
```

{% endcode %}
{% endtab %}

{% tab title="⏹️ 平仓" %}
{% code title="close_position.txt" overflow="wrap" %}

```
MyKeys({{ticker}}) {
  # 平仓任何头寸
  limit(position=0, offset=1, reduceOnly=true);

  # 取消所有订单
  cancel(which=all);
}
#bot
```

{% endcode %}
{% endtab %}

{% tab title="⚡ 乒乓交易" %}
{% code title="flip_position.txt" overflow="wrap" %}

```
MyKeys({{ticker}}) {
  # 取消现有订单
  cancel(which=all);

  # 翻转至多头（如果存在空头则平仓）
  market(position=100%a);

  # 单一止损和止盈
  stopOrder(side=sell, amount=100%p, stop=e-2%, reduceOnly=true);
  limit(side=sell, amount=100%p, offset=e3%, reduceOnly=true);
}
#bot
```

{% endcode %}
{% endtab %}

{% tab title="🔧 高级" %}
{% code title="conditional_pyramid.txt" overflow="wrap" lineNumbers="true" %}

```
MyKeys({{ticker}}) {
  # 仅在仓位 < 10000 时添加
  continue(if=positionLessThan, value=10000);

  # 加仓
  market(side=buy, amount=1000);

  # 尾随止损
  trailingStop(side=sell, amount=100%p, offset=e-1.5%,
               trailingMethod=stepped, stepSize=0.5%, maxSteps=3);
}
#bot
```

{% endcode %}

{% code title="delayed_entry.txt" overflow="wrap" %}

```
MyKeys({{ticker}}) {
  # 等待 5 分钟
  wait(5m);

  # 然后入场
  market(side=buy, amount=50%a);

  # 添加保护
  stopOrder(side=sell, amount=100%p, stop=e-1%, reduceOnly=true);
}
#bot
```

{% endcode %}
{% endtab %}
{% endtabs %}

### 🔤 脚本命令参考

<details>

<summary>点击展开完整命令列表</summary>

| 命令                | 用途                        | 示例                               |
| ------------------- | --------------------------- | ---------------------------------- |
| `market()`          | 市价单                      | `market(side=buy, amount=100%a)`   |
| `limit()`           | 限价单                      | `limit(position=50%p, offset=e2%)` |
| `stopOrder()`       | 止损                        | `stopOrder(side=sell, stop=e-1%)`  |
| `aggressive()`      | 智能限价入场                | `aggressive(position=90%a)`        |
| `wait()`            | 延迟                        | `wait(10m)`                        |
| `cancel()`          | 取消订单                    | `cancel(which=all)`                |
| `oneCancelsOther()` | OCO 组（One Cancels Other） | `oneCancelsOther(which=all)`       |
| `continue()`        | 条件继续                    | `continue(if=positionLong)`        |
| `stop()`            | 条件停止                    | `stop(if=positionShort)`           |
| `trailingStop()`    | 尾随止损                    | `trailingStop(offset=e-1%)`        |

**仓位大小：**

- `100%a` = 100% 可用余额
- `100%p` = 100% 当前仓位
- `100` = 固定金额
- `position=0` = 平仓
- `offset=e2%` = 距入场价 2%

</details>

---

## 🛠️ 故障排除

{% tabs %}
{% tab title="Signals Lite 问题" %}

| 问题         | 解决方案                                         |
| ------------ | ------------------------------------------------ |
| 机器人无响应 | 检查 webhook URL 是否完全复制                    |
| 消息无效     | 必须是有效的 JSON 格式                           |
| 错误的大小   | 验证 JSON 中的 % 对比固定金额                    |
| 无止盈/止损  | 在机器人中设置或使用 JSON 字段覆盖               |
| 重复订单     | 确保在 TradingView 中设置了 "Once Per Bar Close" |

{% endtab %}

{% tab title="Script Bot 问题" %}

| 问题         | 解决方案                             |
| ------------ | ------------------------------------ |
| 脚本被忽略   | 末尾缺少 `#bot` 标签                 |
| 无效密钥     | 检查密钥别名拼写（区分大小写）       |
| 解析错误     | 检查 Alertatron 收件箱中的错误详情   |
| 订单大小为 0 | 缺少大小调整中的 `%`（`%a` 或 `%p`） |
| TP/SL 不取消 | 需要 `oneCancelsOther()` 包装        |

{% endtab %}
{% endtabs %}

---

## 📚 资源

{% hint style="info" %}
**官方文档：**

- **主文档：** [**https://alertatron.com/docs/all/guide**](https://alertatron.com/docs/all/guide)
- **Signals Lite 入门指南**：<https://alertatron.com/docs/getting-started-with-signals-lite>
- **覆盖设置参考**：<https://alertatron.com/docs/signals-lite/override-signal-settings>
- **Script Bots 基础**：<https://alertatron.com/docs/automated-trading/basic-concepts>
- **脚本命令参考**：<https://alertatron.com/docs/automated-trading/market-order>

{% endhint %}

{% hint style="warning" %}
**记住：**

- Alertatron 是第三方服务，有单独的成本
- 始终先用小额测试
- 如果可用，使用交易所模拟交易
- 通过 TradingView 的手动交易始终是一个选项

{% endhint %}
