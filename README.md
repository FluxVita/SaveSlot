<div align="center">

# SaveSlot

### Memory isn't enough.

**Trusted state for every AI.**<br>
Open-source Personal Agent State Layer

![Status](https://img.shields.io/badge/status-early%20design-orange)
![Capabilities](https://img.shields.io/badge/capabilities-planned-lightgrey)

[Website](https://saveslot.ai) · [简体中文](README.zh-CN.md) · [Roadmap](#roadmap)

</div>

---

Long tasks drift. Requirements change, tool calls time out, systems disagree — and an agent may keep acting on what *used to be* true, even within a single session.

SaveSlot maintains a **Trusted State View**: a compact picture of current state, where every item says where it came from and how sure it is.

```yaml
# Trusted State View (illustrative — not yet implemented)
constraints:
  - value: "Only admins may export orders"
    status: confirmed         # by user, latest instruction
    supersedes: "Export orders for everyone"
tasks:
  - value: "Deploy v2"
    status: unknown           # request timed out
    next: verify with the deployment system
  - value: "Checkout feature"
    status: conflicted        # tracker: complete · tests: failing
```

> [!NOTE]
> **Early stage.** This README describes the product direction. Nothing here is implemented yet — see [Status](#status).

## Why

- 🧭 **Context isn't current state.** An agent can still "remember" an instruction after it was changed.
- ⏱️ **A tool call isn't a result.** A timed-out deploy is *unknown*, not *done*.
- ⚖️ **Sources disagree.** Conflicts should surface, not be silently overwritten.

Remembering isn't the same as staying current.

## Trust markers

| | Marker | Meaning |
|---|---|---|
| 🟢 | **Confirmed** | An appropriate authoritative source confirmed it. Not absolute truth. |
| 🔵 | **Inferred** | Derived from evidence. Never silently upgraded. |
| ⚪ | **Unknown** | Missing or unverifiable. Admit it, don't guess. |
| 🟠 | **Conflicted** | Sources disagree. Reconcile, don't pick a side. |

Every item also carries time, version, source, and permission. State is evidence-backed, not guaranteed true.

## Status

| Capability | What it does | Status |
|---|---|---|
| **Track** | Goals, constraints, plans, decisions, progress as explicit objects | 🔜 Planned |
| **Update** | Apply new instructions and tool results, keep versions | 🔜 Planned |
| **Validate** | Assign trust markers, flag stale items | 🔜 Planned |
| **Retrieve** | Return a compact view before each action | 🔜 Planned |
| **API · MCP · SDK** | Integration surfaces | 🔜 Planned |

A status changes only with a reproducible demo.

## What SaveSlot is not

- **Not a runtime, checkpoint, or workflow engine.** It works alongside them.
- **Not a truth arbiter.** Source systems own business facts and write access.
- **Not a permission grant.** Reading state doesn't let an agent change other systems.

## Roadmap

- [ ] **P0** · Single agent, single session — state drift in long tasks and multi-step tool calls
- [ ] **P1** · Across sessions and source systems
- [ ] **P2** · Authorized sharing across agents

---

<div align="center">
<sub><b>SaveSlot</b> · Memory isn't enough. · Trusted state for every AI.</sub>
</div>
