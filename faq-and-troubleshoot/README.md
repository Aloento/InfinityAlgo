# 常见问题 & 故障排除 (FAQ & Troubleshoot)

{% hint style="info" %}
**提示：** 需要即时帮助？请尝试我们网站上的在线客服小组件 (live-chat widget)——可以在一分钟内解决约 90% 的问题。
{% endhint %}

---

## 1 指标不显示 — 用户名不匹配

- 结账时输入的 TradingView **用户名** 必须与当前登录的用户名相同。
- 在发票邮件或 TradingView **个人资料 (Profile) → 设置 (Settings) → 用户名 (Username)** 中查找。
- 如果不匹配，请发送邮件至 **<support@infinityalgo.com>**，附上正确的用户名，我们将更新您的许可证 (licence)。

---

## 2 脚本旁出现红色锁定图标 — 脚本仍然被锁定

- 90% 的情况下是用户名错误或购买未完成。
- 输入正确的用户名（参见问题 1），等待 30 秒，然后重新加载图表。
- 当锁定变为 **绿色** 时，脚本已准备好加载（参见问题 3）。

---

## 3 如何解锁指标？

- **绿色锁** 表示许可证 (licence) 已被识别。
- 点击 **仅限邀请脚本 (Invite-only Scripts)** 下的脚本名称，将其添加到图表。
- 如果锁定仍为红色，返回查看问题 2。

---

## 4 指标超时错误 (Indicator timeout error)

- 当计算耗时过长时，TradingView 会显示超时错误（通常在较低时间框架或启用 AI 时出现）。
- **快速修复：** 打开设置 (⚙️) → 切换任何输入 → 点击确定。这将强制刷新。
- **替代方案：** 删除指标 (×)，然后从 **仅限邀请脚本 (Invite-only Scripts)** 重新添加。
- 如果使用 AI 优化 (AI optimization)，请考虑使用 **静态 (Static)** 模式或更高的 **更新频率 (Update Frequency)**。

---

## 5 无法加载 – "指标过多" (Too many indicators)

- TradingView 限制每个图表上的活跃指标数量：
  - 免费 (Free) = 2 基础 (Essential) = 5 加强 (Plus) = 10 专业 (Premium) = 25 专家 (Expert) = 30 终极 (Ultimate) = 50
- 删除未使用的指标（图例中的 ×）并重新加载，或升级您的计划/在多个图表上分散使用。

---

## 6 打开指标设置

- 点击图例中脚本名称旁边的 **齿轮 (gear)** 图标 (⚙️)。
- 所有输入、颜色和告警切换 (alert toggles) 都在这里。
- **重置为默认值 (Reset to Default)** 位于该窗口的左下角（参见问题 12）。

---

## 7 "研究未授权" (Study Not Auth) 错误

- 脚本无法验证您的许可证 (licence)。
- 刷新页面 (F5)——可以解决约 30% 的情况。
- 重新检查用户名拼写（问题 1）。
- 有时 TradingView 的认证服务器繁忙；请等待几分钟后重新加载。
- 仍然失败？请发送屏幕截图和用户名至支持团队。

---

## 8 "内部服务器研究错误" (Internal Server Study Error)

- TradingView 服务器临时故障或脚本缓存问题。
- 强制刷新（**Ctrl + Shift + R**）或打开新标签页/桌面应用程序。
- 查看 [**https://status.tradingview.com/**](https://status.tradingview.com/)——如果组件显示为红色，请等待变为绿色。

---

## 9 TradingView 要求我再次支付

- 这是配额通知 (quota notice)，**不是** 付款请求。
- 您已达到指标限制（参见问题 5）。
- 删除一个脚本或升级您的 TradingView 计划；提示将消失。

---

## 10 指标会重绘吗？(Does the indicator repaint?)

- **否。** 一旦 K 线柱 (bar) 关闭，其信号和数值永远不会改变。
- 当前 K 线柱仍在形成时，数值可能会"呼吸" (breathe)——这对任何实时计算都是正常的。

---

## 11 如何获取最新版本？

- 更新会自动推送。
- 如果您已订阅脚本，您将收到标题为 **"Infinity Algo – 新版本"** 的邮件。
- 删除旧副本，然后从 **仅限邀请脚本 (Invite-only Scripts)** 重新添加以加载最新版本。
- 除非 TradingView 标记输入 (input) 有变化，否则现有告警模板 (alert templates) 保持不变。

---

## 12 将设置重置为出厂默认值

- 打开设置 (⚙️) → **重置为默认输入 (Reset to Default Inputs)** → 确定。
- 颜色可在 **样式 (Style)** 标签中重置。

---

## 13 我的告警没有触发

### 快速检查清单

1. 告警是在 **正确的指标版本** 上创建的吗？
2. **条件 (Condition)** 是否设置为 **K 线柱关闭时一次 (Once per bar close)**（推荐）？
3. 告警配额 (Alert quota)：免费 (Free) = 3 基础 (Essential) = 20 加强 (Plus) = 100 专业 (Premium) = 400 专家 (Expert) = 600 终极 (Ultimate) = 1,000
4. 浏览器标签页关闭？使用 TradingView 桌面版或服务器端告警 (server-side alerts)（付费计划）。
5. 遵循文档中的分步告警指南。

---

## 14 期货没有回测数据 (No backtest data for futures)

- 期货 (Futures) 需要在 TradingView 中设置不同的订单大小 (order size)。
- **修复：** 打开设置 (⚙️) → **属性 (Properties)** → 将 **订单大小 (Order Size)** 从"美元 (USD)"更改为 **"合约 (Contracts)"** 或 **"数量 (Quantity)"**。
- 这适用于所有期货合约代码：ES、MES、NQ、MNQ、YM、RTY、CL、GC 等。
- 期货以合约/手数 (contracts/lots) 交易，而不是美元头寸规模 (USD position sizing)。

---

## 15 从图表中删除指标

- 在图例中点击脚本名称旁的 ×。
- 许可证 (licence) 仍保留在 **仅限邀请脚本 (Invite-only Scripts)** 中——您可以随时重新添加。

---

## 16 最优设置是什么？

- **最优设置** 因市场、时间框架 (timeframe) 和交易风格而异。利用我们的 **回测 (backtesting)** 功能来发现最适合您的设置。

---

## 17 购买后可以更改 TradingView 用户名吗？

- 可以，发送邮件至 <support@infinityalgo.com>，附上您的新用户名。每个许可证可免费更改一次。

---

## 18 我可以与他人共享我的指标吗？

- **不可以。** 许可证 (license) 与您特定的 **TradingView 用户名** 绑定，不可转让。

---

## 19 仍需要帮助？

- **在线客服 (Live chat)** – 我们网站右下角（最快）。
- **邮件 (Email)** – <support@infinityalgo.com>（工作日内 24 小时内回复）。
