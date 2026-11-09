# SaveSlot

**English** · [简体中文](README.zh-CN.md)

### Memory isn't enough.

**One shared source of truth for every AI.**

Turn scattered conversations and memories into structured, up-to-date information every AI can rely on.

SaveSlot is an open-source foundation for persistent, user-owned state across AI agents.

It gives connected agents a shared, living record of your goals, decisions, tasks, and progress — so they know what's done, what's changed, and what's next.

> 🚧 **Early stage.** SaveSlot is under active development. The capabilities described below are design goals (Planned) and are not yet released. Installation steps and a working demo will be added here.

---

## The problem: AI conversations end. Your work doesn't.

Every agent has its own context. But your work spans conversations, tools, and models.

You shouldn't have to repeatedly explain:

- What has already been decided
- Which tasks are finished
- What has changed since the last session
- What still needs to happen

**That's not just a memory problem. It's a continuity problem.**

## Beyond agent memory

**Memory asks:** What should this agent remember?

**SaveSlot asks:** Where do things stand, and what happens next?

SaveSlot focuses on the ongoing state of a person's work — not just recalling information from previous conversations.

|                  | Typical memory use case     | SaveSlot's focus                  |
| ---------------- | --------------------------- | --------------------------------- |
| Primary question | What should I recall?       | Where do things stand?            |
| Core data        | Facts, preferences, context | Goals, decisions, tasks, progress |
| Updates          | Remember new information    | Track changes and completed work  |
| Outcome          | Better-informed responses   | Continuity across agents          |

These approaches are complementary. SaveSlot is designed around continuity as the primary use case.

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
