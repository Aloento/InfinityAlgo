# 🔔 仪表盘告警 (Dashboard Alerts)

Infinity 仪表盘包含 20 个专业的告警条件，涵盖所有主要信号类型。这些告警可以通过 TradingView 的告警系统触发通知、webhooks 或自动交易。

{% columns %}
{% column width="50%" %}

#### 告警类别

- 📦 **订单块告警** (Order Block Alerts) (6 种)
- 📊 **多时间框架对齐告警** (MTF Alignment Alerts) (6 种)
- 🧭 **市场结构告警** (Market Structure Alerts) (4 种)
- ☁️ **云带告警** (Cloud Band Alerts) (4 种)
  {% endcolumn %}

{% column %}

#### 告警优势

- 实时信号通知
- Webhook 自动化支持
- 多平台集成
- 可自定义条件
  {% endcolumn %}
  {% endcolumns %}

{% hint style="info" %}
**专业提示：** 从 2-3 个关键告警开始，避免通知过载。随着策略优化逐步添加更多告警。
{% endhint %}

---

### 📦 订单块告警 (Order Block Alerts)

#### 区域进入/退出告警 (Zone Entry/Exit Alerts)

| 告警名称 (Alert Name)                     | 触发条件 (Trigger Condition) | 最佳用途 (Best Use) | 优先级 (Priority) |
| ----------------------------------------- | ---------------------------- | ------------------- | ----------------- |
| **进入看涨订单块** (Entered Bullish OB)   | 价格进入需求区 (demand zone) | 潜在长仓进场设置    | 高                |
| **进入看跌订单块** (Entered Bearish OB)   | 价格进入供给区 (supply zone) | 潜在短仓进场设置    | 高                |
| **退出看涨订单块** (Exit from Bullish OB) | 价格向上离开需求区           | 潜在长仓进场设置    | 中                |
| **退出看跌订单块** (Exit from Bearish OB) | 价格向下离开供给区           | 潜在短仓进场设置    | 中                |

#### 区域突破告警 (Zone Break Alerts)

| 告警名称 (Alert Name)                          | 触发条件 (Trigger Condition) | 最佳用途 (Best Use)    | 优先级 (Priority) |
| ---------------------------------------------- | ---------------------------- | ---------------------- | ----------------- |
| **看涨订单块向下破裂** (Bullish OB Break Down) | 需求区被破裂/失效            | 平仓多头，区域反转警告 | 高                |
| **看跌订单块向上破裂** (Bearish OB Break Up)   | 供给区被破裂/失效            | 平仓空头，区域反转警告 | 高                |

{% code title="设置示例 (Setup Example)" overflow="wrap" %}

```
1. 创建告警 (Create Alert) → 条件: Infinity 仪表盘 (Condition: Infinity Dashboard)
2. 选择: "进入看涨订单块" (Select: "Entered Bullish OB")
3. 选项: 每根柱线收盘时触发一次 (Once Per Bar Close)
4. 操作: 通知 + Webhook (可选) (Actions: Notification + Webhook)
```

{% endcode %}

---

### 📊 多时间框架对齐告警 (MTF Alignment Alerts)

#### 对齐强度告警 (Alignment Strength Alerts)

| 告警名称 (Alert Name)                                   | 触发条件 (Trigger Condition) | 稀有度 (Rarity) | 威力 (Power) | 推荐操作 (Recommended Action) |
| ------------------------------------------------------- | ---------------------------- | --------------- | ------------ | ----------------------------- |
| **多时间框架强看涨** (MTF Strong Bullish)               | 6 个以上时间框架看涨         | 常见            | 高           | 标准仓位                      |
| **多时间框架强看跌** (MTF Strong Bearish)               | 6 个以上时间框架看跌         | 常见            | 高           | 标准仓位                      |
| **多时间框架完全看涨对齐** (MTF Full Bullish Alignment) | 全部 8 个时间框架看涨        | 罕见            | 最大         | 更大仓位                      |
| **多时间框架完全看跌对齐** (MTF Full Bearish Alignment) | 全部 8 个时间框架看跌        | 罕见            | 最大         | 更大仓位                      |

#### 偏向变化告警 (Bias Change Alerts)

| 告警名称 (Alert Name)                                   | 触发条件 (Trigger Condition) | 最佳用途 (Best Use) | 时机 (Timing) |
| ------------------------------------------------------- | ---------------------------- | ------------------- | ------------- |
| **多时间框架偏向反转 → 看涨** (MTF Bias Flip → Bullish) | 平均值进入看涨区间           | 趋势变化早期预警    | 早期          |
| **多时间框架偏向反转 → 看跌** (MTF Bias Flip → Bearish) | 平均值进入看跌区间           | 趋势变化早期预警    | 早期          |

{% hint style="success" %}
**高价值告警：** 多时间框架完全对齐告警极其罕见但威力强大 —— 当这些告警触发时，考虑增加仓位或紧密监控。
{% endhint %}

---

### 🧭 市场结构告警 (Market Structure Alerts)

#### 结构突破告警 (Structure Break Alerts)

| 告警名称 (Alert Name)          | 信号类型 (Signal Type) | 重要性 (Importance) | 操作 (Action) | 视觉显示 (Visual) |
| ------------------------------ | ---------------------- | ------------------- | ------------- | ----------------- |
| **看涨 CHoCH** (Bullish CHoCH) | 趋势反转至看涨         | 🔥 关键             | 重大长仓信号  | 虚线              |
| **看跌 CHoCH** (Bearish CHoCH) | 趋势反转至看跌         | 🔥 关键             | 重大短仓信号  | 虚线              |
| **看涨 BOS** (Bullish BOS)     | 上升趋势延续           | 📊 中等             | 加仓多头      | 实线              |
| **看跌 BOS** (Bearish BOS)     | 下降趋势延续           | 📊 中等             | 加仓空头      | 实线              |

{% hint style="warning" %}
**告警优先级：** CHoCH (Change of Character) > BOS (Break of Structure) (反转比延续更重要)

- 使用 CHoCH 进场
- 使用 BOS 管理仓位
  {% endhint %}

---

### ☁️ 云带告警 (Cloud Band Alerts)

#### 突破与交叉告警 (Breakout & Cross Alerts)

| 告警名称 (Alert Name)                  | 触发条件 (Trigger Condition)  | 市场状态 (Market State) | 信号强度 (Signal Strength) |
| -------------------------------------- | ----------------------------- | ----------------------- | -------------------------- |
| **云带向上突破** (Cloud Breakout Up)   | 收盘价在上云带上方 + 斜率上升 | 强势动能                | 非常高                     |
| **云带向下突破** (Cloud Breakout Down) | 收盘价在下云带下方 + 斜率下降 | 强势动能                | 非常高                     |
| **云带中位线 ↑** (Cloud Midband ↑)     | 价格向上穿过中位线            | 偏向转为看涨            | 中等                       |
| **云带中位线 ↓** (Cloud Midband ↓)     | 价格向下穿过中位线            | 偏向转为看跌            | 中等                       |

---

### ⚙️ 告警配置指南 (Alert Configuration Guide)

#### 分步设置 (Step-by-Step Setup)

{% stepper %}
{% step %}

#### 打开告警对话框 (Open Alert Dialog)

点击顶部工具栏中的闹钟图标，或按 **Alt+A**
{% endstep %}

{% step %}

#### 选择条件 (Select Condition)

从条件下拉菜单中选择 **"Infinity 仪表盘"** (Infinity Dashboard)
{% endstep %}

{% step %}

#### 选择告警类型 (Choose Alert Type)

从上面列出的 20 个告警条件中选择一个
{% endstep %}

{% step %}

#### 配置选项 (Configure Options)

- **频率 (Frequency)：** 每根柱线收盘时触发一次 (Once Per Bar Close) - 推荐
- **过期时间 (Expiration)：** 开放式或特定日期
- **告警名称 (Alert name)：** 自定义描述
  {% endstep %}

{% step %}

#### 设置操作 (Set Actions)

- 应用内通知 (Notify on App)
- 显示弹窗 (Show Popup)
- 发送邮件 (Send Email)
- Webhook 网址 (Webhook URL) - 用于自动化
- 播放声音 (Play Sound)
  {% endstep %}
  {% endstepper %}

#### 告警频率选项 (Alert Frequency Options)

| 设置 (Setting)                          | 行为 (Behavior)        | 最佳用途 (Best For) | 备注 (Notes)   |
| --------------------------------------- | ---------------------- | ------------------- | -------------- |
| **每根柱线** (Once Per Bar)             | 每根符合条件的柱线触发 | 主动监控            | 可能通知较频繁 |
| **每根柱线收盘时** (Once Per Bar Close) | 在确认收盘时触发       | 稳定信号            | ✅ 推荐        |
| **仅一次** (Once)                       | 触发一次后停用         | 单次事件监控        | 需手动重置     |

---

### 🎯 告警策略 (Alert Strategies)

{% tabs %}
{% tab title="🛡️ 保守型 (Conservative)" %}
**专注于高概率信号：**

```
1. 多时间框架强看涨/强看跌
2. 看涨/看跌 CHoCH
3. 云带向上/向下突破
```

**总告警数：** 6 个 **最适合：** 初学者、波段交易者
{% endtab %}

{% tab title="⚔️ 激进型 (Aggressive)" %}
**捕捉每个机会：**

```
1. 所有订单块进场/退场
2. 所有多时间框架对齐
3. 所有 BOS 信号
4. 所有云带交叉
```

**总告警数：** 20 个 **最适合：** 活跃交易者、日内交易者
{% endtab %}

{% tab title="⚖️ 平衡型 (Balanced)" %}
**推荐设置：**

```
1. 多时间框架强对齐 (趋势)
2. 仅 CHoCH (反转)
3. 订单块进场 (区域)
4. 云带突破 (动能)
```

**总告警数：** 10 个 **最适合：** 大多数交易者
{% endtab %}
{% endtabs %}

---

---

### 💡 专业建议 (Pro Tips)

#### 告警优化 (Alert Optimization)

1. **从简单开始：** 先使用 2-3 个告警，逐步添加更多
2. **使用"每根柱线收盘时"：** 显著减少虚假信号
3. **组合条件：** 多重确认 = 更高概率
4. **基于时间的过滤：** 避免在低流动性时段触发告警
5. **先测试：** 在真实交易前进行模拟交易测试

#### 告警疲劳防止 (Alert Fatigue Prevention)

{% columns %}
{% column width="50%" %}
**组织 (Organization)：**

- 分组相似告警
- 使用不同通知声音
- 按重要性进行颜色编码
- 清晰命名告警
  {% endcolumn %}

{% column %}
**管理 (Management)：**

- 设置静音时段
- 在震荡市场中禁用
- 每周审查和修剪
- 使用告警过期日期
  {% endcolumn %}
  {% endcolumns %}

---

### ⚠️ 常见问题 (Common Issues)

<details>

<summary><strong>告警未触发 (Alert not triggering)</strong></summary>

- 验证指标已加载到图表上
- 检查告警条件是否与当前版本匹配
- 确保使用"每根柱线收盘时"以获得稳定性
- 确认 TradingView 账户还有可用告警配额
- 检查特定条件是否满足

</details>

<details>

<summary><strong>告警过多 (Too many alerts)</strong></summary>

- 减少至核心信号
- 增加时间框架 (减少触发次数)
- 使用更强的条件 (完全对齐 vs 强对齐)
- 设置过期日期
- 将相似告警分组

</details>

<details>

<summary><strong>虚假信号 (False signals)</strong></summary>

- 始终使用"每根柱线收盘时"
- 避免在小于 5 分钟的时间框架上设置告警
- 组合多个确认条件
- 检查市场状况 (震荡市 vs 趋势市)
- 定期审查告警逻辑

</details>

<details>

<summary><strong>Webhook 不工作 (Webhook not working)</strong></summary>

- 验证 Webhook 网址正确
- 检查 JSON 格式的有效性
- 先用简单信息进行测试
- 确保接收服务在线
- 检查防火墙/安全设置

</details>

---

### 📚 快速参考 (Quick Reference)

#### 告警速查表 (Alert Cheat Sheet)

{% columns %}
{% column width="50%" %}
**订单块 (Order Blocks)：**

- 进场 (Entry) = 潜在设置
- 退场 (Exit) = 止盈
- 破裂 (Break) = 区域失效

**多时间框架仪表盘 (MTF Dashboard)：**

- 强 (Strong) = 6+ 时间框架
- 完全 (Full) = 全部 8 个时间框架
- 反转 (Flip) = 趋势变化
  {% endcolumn %}

{% column %}
**市场结构 (Market Structure)：**

- CHoCH = 反转 (优先级更高)
- BOS = 延续

**云带 (Cloud Bands)：**

- 突破 (Breakout) = 动能
- 中位线 (Midband) = 偏向转变
  {% endcolumn %}
  {% endcolumns %}

#### 告警设置检查清单 (Alert Setup Checklist)

- [ ] 选择 Infinity 仪表盘条件
- [ ] 选择特定告警类型
- [ ] 设置为"每根柱线收盘时"
- [ ] 配置通知方法
- [ ] 进行模拟交易测试
- [ ] 设置适当的过期时间
- [ ] 清晰描述告警名称

---

_如需告警方面的额外支持，请访问_[_常见问题_](https://infinity.aloen.to/faq-and-troubleshoot) _或_ [_联系支持。_](https://infinityalgo.com/#contact)
