# 🔔 提醒 (Alerts) - 回测版本 (Backtest Version)

Infinity Algo V3.0 的**回测版本 (Backtest Version)** 包含**自动提醒生成 (Automatic Alert Generation)** 功能,结构化消息完美适配交易自动化。与标准版本不同,提醒是通过编程方式触发的,无需手动设置。

{% hint style="success" %}
**快速开始:** 在设置中启用提醒 (Enable Alerts) → 创建一个使用 "Any alert() function call" 的提醒 → 接收包含所有止盈/止损 (TP/SL) 水平的自动化信号
{% endhint %}

---

### 🚀 与标准版本的主要区别

{% columns %}
{% column width="50%" %}

#### 📋 标准版本 (Standard Version)

- 每种信号类型需要手动设置
- 用户自定义消息格式
- 仅基础止盈/止损 (TP/SL) 提醒
- 需要文本格式化
- 需要多个提醒
  {% endcolumn %}

{% column %}

#### 🤖 回测版本 (Backtest Version)

- ✅ 通过代码自动化
- ✅ 预格式化结构
- ✅ 包含所有止盈/止损水平
- ✅ 为自动化做好准备
- ✅ 单一统一提醒
  {% endcolumn %}
  {% endcolumns %}

---

### ⚙️ 如何启用自动提醒

{% stepper %}
{% step %}

#### 添加回测指标

从仅限邀请脚本 (Invite-only Scripts) 中加载**回测版本 (Backtest Version)** 到您的图表
{% endstep %}

{% step %}

#### 配置提醒设置

导航到指标设置并启用: `Enable Alerts?(启用提醒?)`
{% endstep %}

{% step %}

#### 创建主提醒 (Master Alert)

1. 右键单击图表 → **Add Alert(添加提醒)**
2. 设置条件: **Infinity Algo Backtest** → **Any alert() function call(任何 alert() 函数调用)**
3. 配置通知方式 (webhook、电子邮件、移动端)

{% hint style="warning" %}
**仅创建一个**提醒 - 所有信号都通过这个单一提醒流转
{% endhint %}
{% endstep %}
{% endstepper %}

---

### 📋 提醒消息格式 (Alert Message Format)

回测版本生成完美适配自动化的结构化消息,可选择显示退出水平的百分比。

{% tabs %}
{% tab title="📊 标准格式" %}
{% code title="standard-output:" overflow="wrap" %}

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

{% tab title="📊 带百分比" %}
{% code title="output-with-percentages:" overflow="wrap" %}

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
**新功能:** 在设置中启用 `📊 Show Exit % in Alerts?(在提醒中显示退出百分比?)` 以在提醒消息中直接包含退出百分比
{% endhint %}
{% endtab %}

{% tab title="🎯 消息组成" %}

#### 核心字段 (Core Fields) (始终存在)

- `Exchange` → 交易平台 (自动检测)
- `Symbol` → 交易对/代码 (Ticker)
- `Side` → 多头 (Long) 或空头 (Short) 仓位
- `Leverage` → 仓位杠杆
- `Entry` → 信号时的入场价格

#### 条件字段 (Conditional Fields)

- `TP1-TP6` → 仅在设置中启用时显示
- `SL` → 仅在启用止损 (Stop Loss) 时显示
- `SignalType` → 用于 HL/AI Sniper 模式

#### 可选百分比 (Optional Percentages)

- 退出百分比 → 当启用 `Show Exit % in Alerts?` 时
- 格式: `Price (XX%)`
- 止损 (SL) 始终显示 `(100%)`
  {% endtab %}
  {% endtabs %}

#### 多重止盈策略 (Multiple Take Profit Strategy)

当启用多个止盈 (TP) 时,提醒包含所有活跃水平以实现复杂的退出策略:

- **部分退出 (Partial exits)** 在每个止盈水平基于您配置的百分比
- **逐步减仓 (Scale out)** 以锁定利润
- **风险降低 (Risk reduction)** 当价格有利移动时
- **可选百分比** 直接显示在提醒中以实现自动化

<details>

<summary><strong>📊 理解退出百分比</strong></summary>

`Show Exit % in Alerts?(在提醒中显示退出百分比?)` 设置为每个水平添加仓位退出百分比,使机器人更容易解析退出大小:

**不带百分比 (默认):**

- 仅显示清晰的价格水平
- 机器人需要单独配置退出大小
- 更简单的格式适合手动交易者

**启用百分比:**

- 每个水平显示 `Price (XX%)`
- 机器人可以直接从提醒中解析退出大小
- 无需额外配置

{% hint style="info" %}
**示例用例:** 您的机器人接收到 `TP1=45700.00 (30%)` 并知道在 45700.00 处退出 30% 的仓位,无需单独的配置文件。
{% endhint %}

</details>

---

### 💡 高级配置

#### 自定义选项

<details>

<summary><strong>🏷️ 自定义商品覆盖 (Custom Symbol Override)</strong></summary>

使用 **Alert Ticker(提醒代码)** 设置可以:

- 为不同的商品发送提醒
- 为您的经纪商规范化命名约定
- 处理交易所特定的格式

示例: 设置 `XBTUSD` 而不是 `BTCUSDT` 以兼容 BitMEX

</details>

<details>

<summary><strong>⚡ 杠杆自定义 (Leverage Customization)</strong></summary>

**Alert Leverage(提醒杠杆)** 设置允许:

- 与显示设置不同的杠杆
- 交易所特定限制 (例如,最大 20 倍)
- 风险管理覆盖
- 仓位规模计算

</details>

---

### 🛠️ 实际设置示例

#### 示例 1: 简单多头入场

{% columns %}
{% column width="50%" %}
**配置:**

- 退出类型 (Exit Type): `Percentage(百分比)`
- 仅止盈 1 (TP1): `2%` 已启用
- 止损 (Stop Loss): `3%` 已启用
- 杠杆 (Leverage): `5x`
- **显示退出百分比 (Show Exit %):** `禁用` ❌
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

#### 示例 2: 复杂多重止盈策略

{% columns %}
{% column width="50%" %}
**配置:**

- 所有 6 个止盈 (TP) 已启用
- 止损 (Stop Loss) 已启用
- 信号模式 (Signal Mode): `AI Sniper`
- 杠杆 (Leverage): `10x`
- **显示退出百分比 (Show Exit %):** `启用` ✅
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

### ⚠️ 关键注意事项

{% hint style="danger" %}
**必须了解的设置规则**

#### 一个提醒统管所有 (One Alert Rules All)

- ✅ **仅创建一个** TradingView 提醒,针对每个交易对和时间框架
- ✅ 使用 `Any alert() function call(任何 alert() 函数调用)` 作为触发器
- ✅ 所有信号 (多头/空头/止盈/止损) 通过这个单一提醒流转

#### 处理与时间 (Processing & Timing)

- ⏱️ 提醒在 **K 线收盘 (Bar Close)** 时触发 (确认的信号)
- ⏱️ 考虑 TradingView 处理延迟 (\~1-3 秒)
- ⏱️ 考虑 webhook 的网络延迟 (Latency)
- ⏱️ 在您的自动化中添加重试逻辑 (Retry Logic)
  {% endhint %}

---

### 🔍 故障排除指南

| 问题                           | 可能原因                     | 解决方案                                                                                                                                                   |
| ------------------------------ | ---------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **没有提醒触发**               | 设置配置错误                 | <p>• 在设置中启用 <code>Enable Alerts(启用提醒)</code><br>• 验证提醒条件为 <code>Any alert() function call</code><br>• 确保使用回测版本 (而非标准版本)</p> |
| **错误的商品 (Symbol)**        | 覆盖 (Override) 处于活动状态 | <p>• 清除 <code>Alert Ticker(提醒代码)</code> 字段以使用当前图表<br>• 检查交易所格式要求</p>                                                               |
| **缺少止盈/止损 (TP/SL) 水平** | 未配置                       | <p>• 在退出设置 (Exit Settings) 中启用所需水平<br>• 将退出类型 (Exit Type) 设置为 <code>Percentage(百分比)</code><br>• 配置止盈百分比</p>                  |
| **Webhook 未接收**             | 连接问题                     | <p>• 使用 webhook.site 测试 webhook URL<br>• 检查消息格式兼容性<br>• 如需要，验证 JSON 格式</p>                                                            |
| **重复的提醒 (Duplicate)**     | 创建了多个提醒               | <p>• 删除所有提醒<br>• 仅创建一个主提醒 (Master Alert)<br>• 检查提醒历史 (Alert History)</p>                                                               |

---

### 🎯 集成方法

根据您的技术技能和需求选择您的集成路径:

{% tabs %}
{% tab title="🚀 无代码 (No-Code) (2 分钟设置)" %}

#### 最快设置 - 无需编程

**选项 1: TradingView → Telegram/Discord 通过 Webhook 桥接**

{% stepper %}
{% step %}

#### 创建 Webhook 桥接

1. 访问 [tradingview.to](https://tradingview.to)
2. 创建免费账户
3. 生成 webhook URL
4. 选择目的地 (Telegram/Discord)
   {% endstep %}

{% step %}

#### 配置 TradingView 提醒

1. 使用 `Any alert() function call` 创建提醒
2. 粘贴从 tradingview\.to 获取的 webhook URL
3. 完成! 消息自动转发到您的频道
   {% endstep %}
   {% endstepper %}

**选项 2: 直接 Discord Webhook**

{% code title="Discord 设置" %}

```
1. 打开 Discord 服务器设置
2. 集成 (Integrations) → Webhooks → 新建 Webhook
3. 复制 webhook URL
4. 粘贴到 TradingView 提醒中
```

{% endcode %}

{% hint style="success" %}
**完美适合:** 只想在 Telegram/Discord 中接收信号而不想编码的交易者
{% endhint %}
{% endtab %}

{% tab title="⚙️ 低代码 (Low-Code) (灵活)" %}

#### 可视化自动化工具

**使用 Pipedream/Make (formerly Integromat)**

**为什么使用这个?**

- 重新格式化消息
- 添加条件逻辑
- 发送到多个目的地
- 添加重试逻辑 (Retry Logic)
- 无需服务器

{% code title="示例流程" %}

```
1. HTTP Webhook 触发器 (从 TradingView 接收)
2. 解析消息
3. 为目的地格式化
4. 发送到:
   - Telegram Bot
   - Discord Webhook
   - Google Sheets
   - Email(电子邮件)
   - Database(数据库)
```

{% endcode %}

**Pipedream 工作流示例**

{% code title="pipedream-parser.js" %}

```javascript
export default defineComponent({
  async run({ steps, $ }) {
    // Parse incoming alert
    const lines = steps.trigger.event.body.split("\n");
    const data = {};

    lines.forEach((line) => {
      const [key, value] = line.split("=");
      data[key] = value;
    });

    // Format for Discord
    return {
      content: `🔔 ${data.Symbol} Signal`,
      embeds: [
        {
          title: `${data.Side} Position`,
          fields: [
            { name: "Entry", value: data.Entry, inline: true },
            { name: "TP1", value: data.TP1, inline: true },
            { name: "SL", value: data.SL, inline: true },
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
**完美适合:** 半技术用户,想要自定义而不需要管理服务器
{% endhint %}
{% endtab %}

{% tab title="🔧 专业级 (Pro) (完全控制)" %}

#### 自定义服务器实现

为了最大控制，运行您自己的 webhook 端点 (Endpoint):

{% code title="webhook-server.py" lineNumbers="true" %}

```python
from fastapi import FastAPI, Request
import hmac
import hashlib

app = FastAPI()

@app.post("/webhook")
async def handle_alert(request: Request):
    # Verify TradingView signature (optional)
    body = await request.body()

    # Parse alert
    data = parse_alert(body.decode())

    # Custom logic
    if data['Symbol'] in WATCHLIST:
        # Execute trade
        execute_trade(data)

        # Log to database
        log_trade(data)

        # Notify multiple channels
        notify_telegram(data)
        notify_discord(data)

    return {"status": "processed"}
```

{% endcode %}

**高级功能:**

- 请求验证 (Request Verification)
- 数据库日志 (Database Logging)
- 多交易所执行 (Multi-exchange Execution)
- 自定义风险管理
- 重试逻辑和错误处理

{% hint style="warning" %}
**完美适合:** 需要自定义逻辑、认证或复杂路由的开发者
{% endhint %}
{% endtab %}
{% endtabs %}

---

### 🤖 流行机器人集成

#### Cornix Bot (自动化交易)

{% columns %}
{% column width="60%" %}
**最简单的自动执行:**

1. 从机器人设置中获取 Cornix webhook URL
2. 粘贴到 TradingView 提醒 webhook 字段
3. Cornix 自动解析并执行交易

**支持:**

- 多个交易所 (Binance、Bybit 等)
- 仓位管理
- 风险设置
- DCA 策略
  {% endcolumn %}

{% column %}
{% hint style="success" %}
**无需编码!** Cornix 直接理解 Infinity Algo 的格式
{% endhint %}
{% endcolumn %}
{% endcolumns %}

#### 其他交易机器人

| 机器人服务        | 设置难度        | 功能              | 最适合       |
| ----------------- | --------------- | ----------------- | ------------ |
| **Cornix**        | ⭐ 最简单       | 完整自动化        | 初学者       |
| **3Commas**       | ⭐⭐ 简单       | DCA、网格机器人   | 中级用户     |
| **TradersPost**   | ⭐⭐ 简单       | 多经纪商 (Broker) | 股票交易者   |
| **PineConnector** | ⭐⭐⭐ 中等     | MT4/MT5 桥接      | 外汇 (Forex) |
| **自定义机器人**  | ⭐⭐⭐⭐⭐ 困难 | 无限              | 开发者       |

---

### ⚠️ 重要限制和注意事项 (Important Limits & Gotchas)

{% hint style="danger" %}
**必须知道:**

- TradingView 需要**付费计划 (Paid Plan)** 才能使用 webhook
- 使用 `Any alert() function call(任何 alert() 函数调用)` 作为条件
- 3 分钟内最多 15 个提醒 (TradingView 限制)
- Discord: 每个 webhook 每分钟约 30 条消息
- Telegram: 总共每秒 30 条消息,每个聊天 1 条/秒
  {% endhint %}

---

### 📚 快速开始建议

<details>

<summary><strong>我只想在 Telegram/Discord 中接收信号</strong></summary>

使用 **tradingview\.to** (路径 A) - 2 分钟设置,无需编码

</details>

<details>

<summary><strong>我想在 Binance/Bybit 上自动交易</strong></summary>

使用 **Cornix Bot** - 粘贴 webhook URL,配置风险设置,完成

</details>

<details>

<summary><strong>我需要自定义格式或多个目的地</strong></summary>

使用 **Pipedream 或 Make** (路径 B) - 可视化工作流构建器

</details>

<details>

<summary><strong>我是开发者,需要完全控制</strong></summary>

构建自定义端点 (Endpoint) (路径 C) - 查看专业级标签页的示例

</details>

---

### ✅ 总结

{% hint style="info" %}
**回测版本提供:**

✅ **零手动设置** - 所有提醒自动处理\
✅ **结构化格式** - 任何平台都可解析\
✅ **完整数据** - 一条消息包含所有止盈/止损水平\
✅ **信号识别** - 确切知道是哪个策略触发\
✅ **直接集成** - 适用于任何 webhook 端点\
✅ **回测准确性** - 用于测试的真实提醒生成
{% endhint %}

完美适用于自动化交易系统、回测验证和无需手动的提醒管理。
