<div align="center">

# SaveSlot

### 记得住，不代表记得准。

**上下文会腐烂，AI 做事更要心中有数。**<br>
开源 Personal Agent State Layer

![Status](https://img.shields.io/badge/status-early%20design-orange)
![Capabilities](https://img.shields.io/badge/capabilities-planned-lightgrey)

[官网](https://saveslot.ai) · [English](README.md) · [路线图](#路线图)

</div>

---

长任务会“跑偏”：需求改了、工具调用超时、不同系统说法不一致，Agent 却可能继续按**过去成立**的情况行事，哪怕只在一个 Session 里。

SaveSlot 维护一份**可信状态视图（Trusted State View）**：一份紧凑的当前状态，每一项都写明从哪来、有多确定。

```yaml
# Trusted State View（示意，尚未实现）
constraints:
  - value: "只有管理员才能导出订单"
    status: confirmed         # 用户最新指令确认
    supersedes: "所有用户都能导出订单"
tasks:
  - value: "部署 v2"
    status: unknown           # 请求超时
    next: 向部署系统核验
  - value: "结算功能"
    status: conflicted        # 任务系统：已完成 · 测试：未通过
```

> [!NOTE]
> **早期阶段。** 本文描述的是产品方向，目前尚未实现任何能力，详见[能力状态](#能力状态)。

## 为什么需要

- 🧭 **上下文不等于当前状态。** 指令改了，Agent 可能还“记得”旧的那条。
- ⏱️ **调用了不等于完成了。** 部署超时，结果是*未知*，不是*已完成*。
- ⚖️ **来源会冲突。** 冲突应该摆出来，而不是被悄悄覆盖。

记住过去，不等于掌握现在。

## 可信度标记

| | 标记 | 含义 |
|---|---|---|
| 🟢 | **Confirmed** | 适当的权威来源已确认；不代表绝对真理。 |
| 🔵 | **Inferred** | 由证据推断；不会被默默升级为已确认。 |
| ⚪ | **Unknown** | 缺失或无法核验；承认不确定，不自行补全。 |
| 🟠 | **Conflicted** | 来源之间有冲突；先核对，不擅自选边。 |

每一项还记录时间、版本、来源和权限。“心中有数”不等于永远知道事实真相：状态有依据，但不保证一定为真。

## 能力状态

| 能力 | 作用 | 状态 |
|---|---|---|
| **Track 跟踪** | 把目标、约束、计划、决策、进度变成明确对象 | 🔜 规划中 |
| **Update 更新** | 根据新指令和工具结果更新，保留版本 | 🔜 规划中 |
| **Validate 验证** | 打可信度标记，识别过期 | 🔜 规划中 |
| **Retrieve 检索** | 每次行动前返回紧凑的状态视图 | 🔜 规划中 |
| **API · MCP · SDK** | 集成方式 | 🔜 规划中 |

只有附带可复现 Demo，状态才会更新。

## SaveSlot 不是什么

- **不是 Runtime、Checkpoint 或工作流引擎。** 可以和它们配合使用。
- **不是真相裁决者。** 业务事实和写入权归源系统。
- **不授予写入权。** 读到状态，不代表 Agent 能修改其他系统。

## 路线图

- [ ] **P0** · 单 Agent、单 Session：长任务和多步骤工具调用中的状态失真
- [ ] **P1** · 跨 Session、跨多个源系统
- [ ] **P2** · 经授权的跨 Agent 共享

---

<div align="center">
<sub><b>SaveSlot</b> · 记得住，不代表记得准。· 上下文会腐烂，AI 做事更要心中有数。</sub>
</div>
