# SaveSlot

**English** · [简体中文](README.zh-CN.md)

### Memory isn't enough.

**Trusted state for every AI.** · Open-source Personal Agent State Layer.

Context rot can hide important changes in long tasks. Requirements change, tool results stay uncertain, and agents may act on stale assumptions—even within one session.

SaveSlot is designed to track, update, validate, and retrieve concise current state — with source, evidence, time, version, permission, and an explicit trust marker — throughout an agent's execution.

> 🚧 **Early stage.** Everything below describes the product direction. All capabilities are **Planned**; see the [feature matrix](#feature-matrix) for verified availability.

---

## State drift happens within a session

One agent, one long-running session. Three things that go wrong without a trusted state view:

| | What happened | Trusted State View (target) |
|---|---|---|
| **Constraint changed** | Earlier: "Export orders for everyone."<br>Later: "Only admins may export orders." | **Confirmed** (by user): admin-only export.<br>Previous constraint kept as *superseded*, with time and version. |
| **Tool result uncertain** | "Deploy version 2."<br>Tool: request timed out, no success confirmation. | **Unknown**: deployment outcome.<br>Next step: verify with the deployment system. Not marked complete. |
| **Evidence conflicts** | Project tracker: "Task complete."<br>Test system: "Required tests still failing." | **Conflicted**: both sources and timestamps kept.<br>No silent overwrite; asks for reconciliation. |

<sub>Illustrative target experience. Not a claim that every memory product makes these mistakes.</sub>

**Remembering isn't the same as staying current.**

## Trusted State View

Know what is current, confirmed, inferred, unknown, or conflicted before the next action. A compact view of current state, returned before an agent decides. Each item carries one trust marker:

| Marker | Meaning |
|---|---|
| **Confirmed** | An appropriate authoritative source confirmed it — who, where, when. Not a claim of absolute truth. |
| **Inferred** | Derived from conversation or tool evidence, not yet confirmed. Never silently upgraded. |
| **Unknown** | Missing or unverifiable. The agent should admit uncertainty, not fill the gap. |
| **Conflicted** | Sources disagree. Resolved by permission, source priority, and confirmation — not by guessing. |

Every item also records time, validity, version, source/evidence, and permission. *Stale* can apply alongside any marker.

**State is evidence-backed, not guaranteed true.**

## Feature matrix

| Capability | What it does | Status |
|---|---|---|
| State Tracking | Goals, constraints, plans, decisions, commitments, and key progress as explicit objects | Planned |
| State Updates | Update from new instructions, tool results, and external changes; keep versions and superseded / effective relations | Planned |
| State Validation | Assign Confirmed / Inferred / Unknown / Conflicted; flag stale items; show evidence | Planned |
| State Retrieval | Return a compact, relevant Trusted State View before a decision | Planned |
| Trust markers | Confirmed · Inferred · Unknown · Conflicted | Planned |
| API · MCP · SDK | Integration surfaces | Planned |

Statuses will move to *Partial* or *Implemented & verified* only with a reproducible demo.

## What SaveSlot is not

- **Not a runtime, checkpoint, or workflow engine.** It does not save or restore execution stacks, processes, or scheduling. Those tools can work alongside it.
- **Not a truth arbiter.** Source systems own business facts, rules, and write access. SaveSlot does not replace them.
- **Not a write-access grant.** Reading state does not give an agent permission to change other systems.

## Roadmap

- **P0** — Single agent, single session: state drift in long tasks and multi-step tool calls.
- **P1** — Single agent across sessions; changes and conflicts across source systems.
- **P2** — Authorized sharing across agents, with versioned conflict handling.

---

**SaveSlot — Help agents act on trusted, traceable state, not stale context.**
