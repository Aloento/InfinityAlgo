# 🔔 仪表盘告警 (Dashboard Alerts)

Infinity 仪表盘包含 20 个专业级别的告警条件，覆盖所有主要信号类型。这些告警可通过 TradingView 的告警系统触发通知、Webhook 调用或自动交易。

{% columns %}
{% column width="50%" %}

#### 告警分类

- 📦 **订单块告警 (Order Block Alerts)** (6 种)
- 📊 **多时间框架对齐告警 (MTF Alignment Alerts)** (6 种)
- 🧭 **市场结构告警 (Market Structure Alerts)** (4 种)
- ☁️ **云带告警 (Cloud Band Alerts)** (4 种)
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
**专业建议：** 从 2-3 个关键告警开始，避免通知过载。随着策略的完善逐步添加更多告警。
{% endhint %}

---

### 📦 订单块告警 (Order Block Alerts)

#### 区域进出告警 (Zone Entry/Exit Alerts)

| 告警名称                               | 触发条件           | 最佳用途         | 优先级 |
| -------------------------------------- | ------------------ | ---------------- | ------ |
| **进入看涨 OB (Entered Bullish OB)**   | 价格进入需求区     | 潜在做多入场设置 | 高     |
| **进入看跌 OB (Entered Bearish OB)**   | 价格进入供应区     | 潜在做空入场设置 | 高     |
| **离开看涨 OB (Exit from Bullish OB)** | 价格向上离开需求区 | 潜在做多入场设置 | 中     |
| **离开看跌 OB (Exit from Bearish OB)** | 价格向下离开供应区 | 潜在做空入场设置 | 中     |

#### 区域突破告警 (Zone Break Alerts)

| 告警名称                                     | 触发条件          | 最佳用途               | 优先级 |
| -------------------------------------------- | ----------------- | ---------------------- | ------ |
| **看涨 OB 向下突破 (Bullish OB Break Down)** | 需求区被破坏/失效 | 平仓做多，区域翻转警告 | 高     |
| **看跌 OB 向上突破 (Bearish OB Break Up)**   | 供应区被破坏/失效 | 平仓做空，区域翻转警告 | 高     |

{% code title="设置示例" overflow="wrap" %}

```
1. 创建告警 → 条件：Infinity 仪表盘
2. 选择：进入看涨 OB
3. 选项：柱线收盘时触发 (Once Per Bar Close)
4. 操作：通知 + Webhook（可选）
```

{% endcode %}

---

### 📊 多时间框架对齐告警 (MTF Alignment Alerts)

#### 对齐强度告警 (Alignment Strength Alerts)

| 告警名称                                          | 触发条件              | 出现频率 | 强度 | 推荐操作 |
| ------------------------------------------------- | --------------------- | -------- | ---- | -------- |
| **MTF 强看涨 (MTF Strong Bullish)**               | 6+ 个时间框架看涨     | 常见     | 高   | 标准仓位 |
| **MTF 强看跌 (MTF Strong Bearish)**               | 6+ 个时间框架看跌     | 常见     | 高   | 标准仓位 |
| **MTF 完全看涨对齐 (MTF Full Bullish Alignment)** | 全部 8 个时间框架看涨 | 罕见     | 最大 | 加大仓位 |
| **MTF 完全看跌对齐 (MTF Full Bearish Alignment)** | 全部 8 个时间框架看跌 | 罕见     | 最大 | 加大仓位 |

#### 偏向变化告警 (Bias Change Alerts)

| 告警名称                                          | 触发条件           | 最佳用途         | 时机 |
| ------------------------------------------------- | ------------------ | ---------------- | ---- |
| **MTF 偏向翻转 → 看涨 (MTF Bias Flip → Bullish)** | 平均值进入看涨区域 | 趋势变化早期警告 | 提前 |
| **MTF 偏向翻转 → 看跌 (MTF Bias Flip → Bearish)** | 平均值进入看跌区域 | 趋势变化早期警告 | 提前 |

{% hint style="success" %}
**高价值告警：** MTF 完全对齐告警罕见但威力巨大 —— 触发时考虑加大仓位或进行更严密的监控。
{% endhint %}

---

### 🧭 市场结构告警 (Market Structure Alerts)

#### 结构破坏告警 (Structure Break Alerts)

| 告警名称                       | 信号类型       | 重要性  | 操作         | 视觉表示 |
| ------------------------------ | -------------- | ------- | ------------ | -------- |
| **看涨 CHoCH (Bullish CHoCH)** | 趋势反转为看涨 | 🔥 关键 | 重大做多信号 | 虚线     |
| **看跌 CHoCH (Bearish CHoCH)** | 趋势反转为看跌 | 🔥 关键 | 重大做空信号 | 虚线     |
| **看涨 BOS (Bullish BOS)**     | 上升趋势延续   | 📊 中等 | 加仓做多     | 实线     |
| **看跌 BOS (Bearish BOS)**     | 下降趋势延续   | 📊 中等 | 加仓做空     | 实线     |

{% hint style="warning" %}
**告警优先级：** CHoCH > BOS（反转比延续更重要）

- 使用 CHoCH 进行仓位入场
- 使用 BOS 进行仓位管理
  {% endhint %}

---

### ☁️ 云带告警 (Cloud Band Alerts)

#### 突破与穿越告警 (Breakout & Cross Alerts)

| 告警名称                               | 触发条件                      | 市场状态     | 信号强度 |
| -------------------------------------- | ----------------------------- | ------------ | -------- |
| **云带向上突破 (Cloud Breakout Up)**   | 收盘价在上云带上方 + 斜率上升 | 强势动能     | 非常高   |
| **云带向下突破 (Cloud Breakout Down)** | 收盘价在下云带下方 + 斜率下降 | 强势动能     | 非常高   |
| **云带中轴向上穿越 (Cloud Midband ↑)** | 价格穿过中轴线向上            | 看涨偏向转变 | 中等     |
| **云带中轴向下穿越 (Cloud Midband ↓)** | 价格穿过中轴线向下            | 看跌偏向转变 | 中等     |

---

### ⚙️ 告警配置指南 (Alert Configuration Guide)

#### 分步骤设置 (Step-by-Step Setup)

{% stepper %}
{% step %}

#### 打开告警对话框 (Open Alert Dialog)

点击顶部工具栏中的闹钟图标，或按下 **Alt+A**
{% endstep %}

{% step %}

#### 选择条件 (Select Condition)

从条件下拉菜单中选择 **"Infinity 仪表盘"**
{% endstep %}

{% step %}

#### 选择告警类型 (Choose Alert Type)

从上面列出的 20 个可用告警条件中选择
{% endstep %}

{% step %}

#### 配置选项 (Configure Options)

- **频率 (Frequency)：** 柱线收盘时触发 (Once Per Bar Close)（推荐）
- **过期时间 (Expiration)：** 开放式或指定日期
- **告警名称 (Alert name)：** 自定义描述
  {% endstep %}

{% step %}

#### 设置操作 (Set Actions)

- 在应用中通知 (Notify on App)
- 显示弹窗 (Show Popup)
- 发送邮件 (Send Email)
- Webhook URL（用于自动化）
- 播放声音 (Play Sound)
  {% endstep %}
  {% endstepper %}

#### 告警频率选项 (Alert Frequency Options)

| 设置                                  | 行为                     | 最佳用途     | 备注         |
| ------------------------------------- | ------------------------ | ------------ | ------------ |
| **每个柱线一次 (Once Per Bar)**       | 每个满足条件的柱线都触发 | 主动监控     | 可能过于频繁 |
| **柱线收盘一次 (Once Per Bar Close)** | 在确认收盘时触发         | 稳定信号     | ✅ 推荐      |
| **仅一次 (Once)**                     | 触发一次后停用           | 单个事件监控 | 需要手动重置 |

---

### 🎯 告警策略 (Alert Strategies)

{% tabs %}
{% tab title="🛡️ 保守策略 (Conservative)" %}
**关注高概率信号：**

```
1. MTF 强看涨/看跌
2. 看涨/看跌 CHoCH
3. 云带向上/向下突破
```

**总告警数：** 6 个 **最适合：** 初学者、波段交易者 (Swing traders)
{% endtab %}

{% tab title="⚔️ 激进策略 (Aggressive)" %}
**捕捉所有机会：**

```
1. 所有订单块入场/出场
2. 所有 MTF 对齐
3. 所有 BOS 信号
4. 所有云带穿越
```

**总告警数：** 20 个 **最适合：** 活跃交易者、日内交易者 (Scalpers)
{% endtab %}

{% tab title="⚖️ 均衡策略 (Balanced)" %}
**推荐设置：**

```
1. MTF 强对齐（趋势）
2. 仅 CHoCH（反转）
3. 订单块入场（区域）
4. 云带突破（动能）
```

**总告警数：** 10 个 **最适合：** 大多数交易者
{% endtab %}
{% endtabs %}

---

---

### 💡 专业建议 (Pro Tips)

#### 告警优化 (Alert Optimization)

1. **从简开始：** 从 2-3 个告警开始，逐步增加
2. **使用"柱线收盘一次"：** 显著减少虚假信号
3. **组合条件：** 多个确认 = 更高概率
4. **基于时间的过滤：** 避免在低流动性时段触发告警
5. **先测试：** 在实盘交易之前进行模拟纸币交易 (Paper trade)

#### 告警疲劳预防 (Alert Fatigue Prevention)

{% columns %}
{% column width="50%" %}
**组织管理：**

- 将相似告警分组
- 使用不同的通知音
- 按重要性分色标记
- 清晰命名告警
  {% endcolumn %}

{% column %}
**管理维护：**

- 设置静音时段 (Quiet hours)
- 在震荡市场中禁用
- 每周审查和整理
- 使用告警过期日期
  {% endcolumn %}
  {% endcolumns %}

---

### ⚠️ 常见问题 (Common Issues)

<details>

<summary><strong>告警未触发 (Alert not triggering)</strong></summary>

- 验证指标已加载到图表
- 检查告警条件是否与当前版本匹配
- 确保使用"柱线收盘一次"以获得稳定性
- 确认 TradingView 套餐有可用的告警配额
- 检查特定条件是否已满足

</details>

<details>

<summary><strong>告警过多 (Too many alerts)</strong></summary>

- 仅保留核心信号
- 增加时间框架（减少触发次数）
- 使用更强条件（完全对齐 vs 强对齐）
- 设置过期日期
- 将相似告警分组

</details>

<details>

<summary><strong>虚假信号 (False signals)</strong></summary>

- 始终使用"柱线收盘一次"
- 避免在 < 5 分钟时间框架上设置告警
- 组合多个确认
- 检查市场状态（震荡 vs 趋势）
- 定期审查告警逻辑

</details>

<details>

<summary><strong>Webhook 不工作 (Webhook not working)</strong></summary>

- 验证 Webhook URL 是否正确
- 检查 JSON 格式有效性
- 先用简单消息测试
- 确保接收服务在线
- 检查防火墙/安全设置

</details>

---

### 📚 快速参考 (Quick Reference)

#### 告警速查表 (Alert Cheat Sheet)

{% columns %}
{% column width="50%" %}
**订单块 (Order Blocks)：**

- 入场 = 潜在设置
- 出场 = 获利平仓
- 破坏 = 区域失效

**MTF 仪表盘 (MTF Dashboard)：**

- 强 = 6+ 个时间框架
- 完全 = 全部 8 个时间框架
- 翻转 = 趋势变化
  {% endcolumn %}

{% column %}
**市场结构 (Market Structure)：**

- CHoCH = 反转（优先）
- BOS = 延续

**云带 (Cloud Bands)：**

- 突破 = 动能
- 中轴 = 偏向转变
  {% endcolumn %}
  {% endcolumns %}

#### 告警设置检查表 (Alert Setup Checklist)

- [ ] 选择 Infinity 仪表盘条件
- [ ] 选择特定告警类型
- [ ] 设置为"柱线收盘一次"
- [ ] 配置通知方式
- [ ] 使用模拟纸币进行测试
- [ ] 设置适当的过期时间
- [ ] 为告警命名

---

_如需获取更多关于告警的支持，请访问我们的_[_常见问题解答_](https://infinity.aloen.to/faq-and-troubleshoot) _或_ [_联系支持_](https://infinityalgo.com/#contact)
