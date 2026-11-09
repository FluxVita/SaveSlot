# SaveSlot

**English** · [简体中文](README.zh-CN.md)

### Memory isn't enough.

**One shared source of truth for every AI.**

Keep important facts, decisions, and progress structured and up to date.

SaveSlot is an open-source foundation for persistent, user-owned state across AI agents.

It gives connected agents a shared, living record of your goals, decisions, tasks, and progress — so they know what's done, what's changed, and what's next.

> 🚧 **Early stage.** SaveSlot is under active development. The capabilities described below are design goals (Planned) and are not yet released. Installation steps and a working demo will be added here.

---

## Your AI remembers the conversation. But does it know what's current?

| | What you said | Scattered memory | SaveSlot |
|---|---|---|---|
| **The plan changed** | Earlier: "Launch is set for Friday."<br>Later: "Launch moved to next Tuesday." | 🤔 Friday? Or next Tuesday? | **Launch date: next Tuesday**<br>Friday · changed |
| **The work got done** | Yesterday: "Landing page is done. Payments still to go."<br>Today: "Payments are live too." | ❌ "Next, let's hook up payments." | ✅ Landing page<br>✅ Payments |
| **The decision changed** | Last week: "We're going with Plan A."<br>This week: "After review, we're switching to Plan B." | 🤔 Plan A and Plan B are both still in memory. | **Current decision: Plan B**<br>Plan A · superseded |

State changes. Tasks get done. Decisions get replaced. Saving more memories doesn't guarantee your AI uses what's current.

<sub>Illustrates the planned experience. The middle column shows what can go wrong when an AI relies on scattered history — not every memory product makes these mistakes.</sub>

## The problem: AI remembers you. It still can't pick up where you left off.

- You settle a plan in ChatGPT yesterday, then re-explain it to Claude today.
- One agent finishes a task; another still thinks it hasn't started.
- Your AI knows your goal, but not how far along you are, which decision changed, or what's next.
- Your projects, health, finances, and daily life are scattered across apps and chat logs.

**That's not a memory problem. It's a continuity problem.**

## Memory → State → Continuity

- **Memory** — what an AI remembers about you.
- **State** — where things actually stand: goals, decisions, tasks, and records, kept correct and current.
- **Continuity** — every AI working from that same state, with nothing to re-explain.

Many memory tools now persist across sessions and agents. SaveSlot differs in its core object: not memories or context, but your state, maintained as data.

|             | Memory layers            | SaveSlot                                     |
| ----------- | ------------------------ | -------------------------------------------- |
| Core object | Memories and context     | Your state: goals, decisions, tasks, records |
| On change   | Add or update a memory   | Update the record, keep its history and source |
| Goal        | Recall the right context | Keep every AI working from the same facts    |

## One shared state. Different agents.

**Agent A**

> "We've approved the design and completed the landing page. The launch email is still pending."

**SaveSlot**

> Project: Product launch<br>
> Design: Approved<br>
> Landing page: Complete<br>
> Launch email: Pending

**Agent B**

> "The design and landing page are done. Let's work on the launch email."

No repeated briefings. No losing track of progress.

## Built around the user's state

SaveSlot's design centers on:

- **Persistent state** — Ongoing work outlives individual agent sessions.
- **Shared access** — Authorized agents work with the same current state.
- **Structured progress** — Goals, decisions, tasks, and next steps are first-class concepts.
- **Traceable changes** — State evolves with clear updates and history.
- **User ownership** — Personal state stays independent of any single agent provider.

---

### Agents are replaceable. Your progress isn't.

**SaveSlot — Keep the state. Change the agent.**
