# 🔔 警报 - Backtest 版本

Infinity Algo V3.0 的 **Backtest 版本**包括**自动警报生成**功能，具有结构化消息，非常适合交易自动化。与标准版本不同，警报通过编程方式触发，无需手动设置。

{% hint style="success" %}
**快速开始：** 在设置中启用警报 → 创建一个 "Any alert() function call" 警报 → 接收包含所有止盈(TP)/止损(SL)水平的自动化信号
{% endhint %}

---

## 🚀 与标准版本的主要区别

{% columns %}
{% column width="50%" %}

#### 📋 标准版本

- 每种信号类型手动设置
- 用户定义的消息格式
- 仅基本止盈(TP)/止损(SL)警报
- 需要文本格式化
- 需要多个警报
  {% endcolumn %}

{% column %}

#### 🤖 Backtest 版本

- ✅ 通过代码自动生成
- ✅ 预格式化结构
- ✅ 包含所有止盈(TP)/止损(SL)水平
- ✅ 准备就绪用于自动化
- ✅ 单一统一警报
  {% endcolumn %}
  {% endcolumns %}

---

## ⚙️ 如何启用自动警报

{% stepper %}
{% step %}

#### 添加 Backtest 指标

从 Invite-only Scripts 将 **Backtest 版本**加载到图表
{% endstep %}

{% step %}

#### 配置警报设置

导航到指标设置并启用：`Enable Alerts?` （启用警报？）
{% endstep %}

{% step %}

#### 创建主警报

1. 右键点击图表 → **Add Alert** （添加警报）
2. 设置条件：**Infinity Algo Backtest** → **Any alert() function call**
3. 配置通知（webhook、电子邮件、移动通知）

{% hint style="warning" %}
仅创建**一个**警报 - 所有信号通过此单个警报流转
{% endhint %}
{% endstep %}
{% endstepper %}

---

## 📋 警报消息格式

Backtest 版本生成结构化消息，非常适合自动化，支持可选的百分比显示退出水平。

{% tabs %}
{% tab title="📊 标准格式" %}
{% code title="标准输出:" overflow="wrap" %}

```
Exchange=BINANCE
Symbol=BTCUSDT
Side=Long
Leverage=10x
Entry=45250.50
TP1=45700.00
TP2=46150.00
TP3=46600.00
TP4=47050.00
TP5=47500.00
TP6=47950.00
SL=43250.00
SignalType=AI Sniper Buy
```

{% endcode %}
{% endtab %}

{% tab title="📊 带百分比格式" %}
{% code title="带百分比输出:" overflow="wrap" %}

```
Exchange=BINANCE
Symbol=BTCUSDT
Side=Long
Leverage=10x
Entry=45250.50
TP1=45700.00 (30%)
TP2=46150.00 (25%)
TP3=46600.00 (20%)
TP4=47050.00 (15%)
TP5=47500.00 (7%)
TP6=47950.00 (3%)
SL=43250.00 (100%)
SignalType=AI Sniper Buy
```

{% endcode %}

{% hint style="success" %}
**新功能：** 在设置中启用 `📊 Show Exit % in Alerts?` （在警报中显示退出百分比？）可将退出百分比直接包含在警报消息中
{% endhint %}
{% endtab %}

{% tab title="🎯 消息组件" %}

#### 核心字段（始终存在）

- `Exchange` → 交易场所（自动检测）
- `Symbol` → 交易对/代码
- `Side` → 多头(Long)或空头(Short)头寸
- `Leverage` → 头寸杠杆
- `Entry` → 信号时的进场价格

#### 条件字段

- `TP1-TP6` → 仅在设置中启用时
- `SL` → 仅在启用止损时
- `SignalType` → 用于 HL/AI Sniper 模式

#### 可选百分比

- 退出百分比 → 启用 `Show Exit % in Alerts?` 时
- 格式：`Price (XX%)`
- 止损始终显示 `(100%)`
  {% endtab %}
  {% endtabs %}

#### 多重止盈策略

启用多个止盈时，警报包含所有激活水平，可用于复杂的退出策略：

- **部分平仓** 在每个止盈水平，基于配置的百分比
- **逐步退出** 头寸以逐步锁定利润
- **风险降低** 随着价格有利移动
- **可选百分比** 直接在警报中显示，便于自动化

<details>

<summary><strong>📊 理解退出百分比</strong></summary>

`Show Exit % in Alerts?` 设置将头寸退出百分比添加到每个水平，使 bot 更容易解析退出大小：

**无百分比（默认）：**

- 仅清晰的价格水平
- Bot 需要单独的退出大小配置
- 对手动交易者更简洁

**启用百分比：**

- 每个水平显示 `Price (XX%)`
- Bot 可直接从警报解析退出大小
- 不需要额外配置

{% hint style="info" %}
**使用示例：** 你的 bot 收到 `TP1=45700.00 (30%)` 并知道在 45700.00 处平仓 30% 的头寸，无需单独的配置文件。
{% endhint %}

</details>

---

## 💡 高级配置

#### 自定义选项

<details>

<summary><strong>🏷️ 自定义代码覆盖（Custom Symbol Override）</strong></summary>

使用 **Alert Ticker** 设置来：

- 为不同的代码发送警报
- 规范化经纪商的命名约定
- 处理交易所特定的格式化

示例：为 BitMEX 兼容性设置 `XBTUSD` 而不是 `BTCUSDT`

</details>

<details>

<summary><strong>⚡ 杠杆自定义（Leverage Customization）</strong></summary>

**Alert Leverage** 设置允许：

- 与显示设置不同的杠杆
- 交易所特定限制（例如最大 20x）
- 风险管理覆盖
- 头寸规模计算

</details>

---

## 🛠️ 真实世界设置示例

### 示例 1：简单多头进场

{% columns %}
{% column width="50%" %}
**配置：**

- 退出类型：`Percentage` （百分比）
- 仅启用 TP1：`2%`
- 止损：`3%` 已启用
- 杠杆：`5x`
- **Show Exit %:** `Disabled` ❌
  {% endcolumn %}

{% column %}
{% code title="输出" %}

```
Exchange=BINANCE
Symbol=ETHUSDT
Side=Long
Leverage=5x
Entry=2250.75
TP1=2295.77
SL=2183.23
```

{% endcode %}
{% endcolumn %}
{% endcolumns %}

### 示例 2：复杂多止盈策略

{% columns %}
{% column width="50%" %}
**配置：**

- 所有 6 个止盈已启用
- 止损已启用
- 信号模式：`AI Sniper`
- 杠杆：`10x`
- **Show Exit %:** `Enabled` ✅
  {% endcolumn %}

{% column %}
{% code title="带百分比的输出" %}

```
Exchange=BINANCE
Symbol=BTCUSDT
Side=Short
Leverage=10x
Entry=45000.00
TP1=44550.00 (30%)
TP2=44100.00 (25%)
TP3=43650.00 (20%)
TP4=43200.00 (15%)
TP5=42750.00 (7%)
TP6=42300.00 (3%)
SL=46350.00 (100%)
SignalType=AI Sniper Sell
```

{% endcode %}
{% endcolumn %}
{% endcolumns %}

---

## ⚠️ 关键考虑事项

{% hint style="danger" %}
**必须了解的设置规则**

#### 一个警报规则全部

- ✅ 为每个交易对和时间框架创建**仅一个** TradingView 警报
- ✅ 使用 `Any alert() function call` 作为触发条件
- ✅ 所有信号（多头/空头/止盈/止损）通过此单一警报流转

#### 处理与计时

- ⏱️ 警报在**收盘时**触发（已确认的信号）
- ⏱️ 考虑 TradingView 处理延迟（约 1-3 秒）
- ⏱️ 考虑 webhook 的网络延迟
- ⏱️ 在自动化中添加重试逻辑
  {% endhint %}

---

## 🔍 故障排除指南

| 问题                  | 可能的原因     | 解决方案                                                                                                                                       |
| --------------------- | -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| **没有警报触发**      | 设置配置错误   | <p>• 在设置中启用 `Enable Alerts` （启用警报）<br>• 验证警报条件是 `Any alert() function call`<br>• 确保使用 Backtest 版本（不是标准版本）</p> |
| **错误的代码**        | 启用了覆盖     | <p>• 清除 `Alert Ticker` 字段以使用当前图表<br>• 检查交易所格式化要求</p>                                                                      |
| **缺少止盈/止损水平** | 未配置         | <p>• 在退出设置中启用所需水平<br>• 将退出类型设置为 `Percentage` （百分比）<br>• 配置止盈百分比</p>                                            |
| **Webhook 未接收**    | 连接问题       | <p>• 使用 webhook.site 测试 webhook URL<br>• 检查消息格式兼容性<br>• 验证 JSON 格式化（如需要）</p>                                            |
| **重复警报**          | 创建了多个警报 | <p>• 删除所有警报<br>• 仅创建一个主警报<br>• 检查警报历史</p>                                                                                  |

---

## 🎯 集成方法

根据你的技术技能和需求选择集成路径：

{% tabs %}
{% tab title="🚀 无代码（2 分钟设置）" %}

#### 最快的设置 - 无需编程

**选项 1：TradingView → Telegram/Discord（通过 Webhook 桥接）**

{% stepper %}
{% step %}

#### 创建 Webhook 桥接

1. 访问 [tradingview.to](https://tradingview.to)
2. 创建免费账户
3. 生成 webhook URL
4. 选择目标（Telegram/Discord）
   {% endstep %}

{% step %}

#### 配置 TradingView 警报

1. 创建 `Any alert() function call` 警报
2. 从 tradingview\.to 粘贴 webhook URL
3. 完成！消息会自动转发到你的频道
   {% endstep %}
   {% endstepper %}

**选项 2：直接 Discord Webhook**

{% code title="Discord 设置" %}

```
1. 打开 Discord 服务器设置
2. 集成(Integrations) → Webhooks → 新 Webhook
3. 复制 webhook URL
4. 粘贴到 TradingView 警报
```

{% endcode %}

{% hint style="success" %}
**适用于：** 只想在 Telegram/Discord 中接收信号的交易者，无需任何编码
{% endhint %}
{% endtab %}

{% tab title="⚙️ 低代码（灵活）" %}

#### 视觉自动化工具

**使用 Pipedream/Make（原名 Integromat）**

**为什么使用这个？**

- 重新格式化消息
- 添加条件逻辑
- 发送到多个目标
- 添加重试逻辑
- 无需服务器

{% code title="示例工作流" %}

```
1. HTTP Webhook 触发（从 TradingView 接收）
2. 解析消息
3. 格式化为目标格式
4. 发送到：
   - Telegram Bot
   - Discord Webhook
   - Google Sheets
   - 电子邮件
   - 数据库
```

{% endcode %}

**Pipedream 工作流示例**

{% code title="pipedream-parser.js" %}

```javascript
export default defineComponent({
  async run({ steps, $ }) {
    // 解析传入的警报
    const lines = steps.trigger.event.body.split("\n");
    const data = {};

    lines.forEach((line) => {
      const [key, value] = line.split("=");
      data[key] = value;
    });

    // 格式化为 Discord
    return {
      content: `🔔 ${data.Symbol} 信号`,
      embeds: [
        {
          title: `${data.Side} 头寸`,
          fields: [
            { name: "进场价", value: data.Entry, inline: true },
            { name: "止盈1", value: data.TP1, inline: true },
            { name: "止损", value: data.SL, inline: true },
          ],
          color: data.Side === "Long" ? 0x00ff00 : 0xff0000,
        },
      ],
    };
  },
});
```

{% endcode %}

{% hint style="info" %}
**适用于：** 需要自定义但不想管理服务器的半技术用户
{% endhint %}
{% endtab %}

{% tab title="🔧 专业（完全控制）" %}

#### 自定义服务器实现

为获得最大控制，运行你自己的 webhook 端点：

{% code title="webhook-server.py" lineNumbers="true" %}

```python
from fastapi import FastAPI, Request
import hmac
import hashlib

app = FastAPI()

@app.post("/webhook")
async def handle_alert(request: Request):
    # 验证 TradingView 签名（可选）
    body = await request.body()

    # 解析警报
    data = parse_alert(body.decode())

    # 自定义逻辑
    if data['Symbol'] in WATCHLIST:
        # 执行交易
        execute_trade(data)

        # 记录到数据库
        log_trade(data)

        # 通知多个频道
        notify_telegram(data)
        notify_discord(data)

    return {"status": "processed"}
```

{% endcode %}

**高级功能：**

- 请求验证
- 数据库日志
- 多交易所执行
- 自定义风险管理
- 重试逻辑和错误处理

{% hint style="warning" %}
**适用于：** 需要自定义逻辑、身份验证或复杂路由的开发者
{% endhint %}
{% endtab %}
{% endtabs %}

---

## 🤖 流行的 Bot 集成

### Cornix Bot（自动交易）

{% columns %}
{% column width="60%" %}
**最简单的自动执行：**

1. 从 bot 设置获取 Cornix webhook URL
2. 粘贴到 TradingView 警报 webhook 字段
3. Cornix 自动解析并执行交易

**支持：**

- 多个交易所（Binance、Bybit 等）
- 头寸管理
- 风险设置
- DCA 策略
  {% endcolumn %}

{% column %}
{% hint style="success" %}
**无需编码！** Cornix 直接理解 Infinity Algo 的格式
{% endhint %}
{% endcolumn %}
{% endcolumns %}

### 其他交易 Bot

| Bot 服务          | 设置难度        | 功能          | 最适合     |
| ----------------- | --------------- | ------------- | ---------- |
| **Cornix**        | ⭐ 最简单       | 完全自动化    | 初学者     |
| **3Commas**       | ⭐⭐ 简单       | DCA、网格 bot | 中级       |
| **TradersPost**   | ⭐⭐ 简单       | 多 broker     | 股票交易者 |
| **PineConnector** | ⭐⭐⭐ 中等     | MT4/MT5 桥接  | 外汇       |
| **自定义 Bot**    | ⭐⭐⭐⭐⭐ 困难 | 无限制        | 开发者     |

---

## ⚠️ 重要限制和陷阱

{% hint style="danger" %}
**必须了解：**

- TradingView 需要**付费计划**才能使用 webhook
- 使用 `Any alert() function call` 作为条件
- 最多 15 个警报/3 分钟（TradingView 限制）
- Discord：每个 webhook 约 30 条消息/分钟
- Telegram：总共约 30 条消息/秒，每个聊天 1 条/秒
  {% endhint %}

---

## 📚 快速开始建议

<details>

<summary><strong>我只想在 Telegram/Discord 中获取信号</strong></summary>

使用 **tradingview\.to**（方案 A）- 2 分钟设置，无需编码

</details>

<details>

<summary><strong>我想在 Binance/Bybit 上自动交易</strong></summary>

使用 **Cornix Bot** - 粘贴 webhook URL，配置风险设置，完成

</details>

<details>

<summary><strong>我需要自定义格式或多个目标</strong></summary>

使用 **Pipedream 或 Make**（方案 B）- 视觉工作流构建器

</details>

<details>

<summary><strong>我是开发者，需要完全控制</strong></summary>

构建自定义端点（方案 C）- 参看专业选项卡中的示例

</details>

---

## ✅ 总结

{% hint style="info" %}
**Backtest 版本提供：**

✅ **零手动设置** - 所有警报自动处理\
✅ **结构化格式** - 为任何平台做好准备解析\
✅ **完整数据** - 一条消息中的所有止盈/止损水平\
✅ **信号识别** - 准确了解哪个策略触发\
✅ **直接集成** - 与任何 webhook 端点兼容\
✅ **回测准确性** - 现实的警报生成用于测试
{% endhint %}

非常适合自动交易系统、回测验证和免提警报管理。
