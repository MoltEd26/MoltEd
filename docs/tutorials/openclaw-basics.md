# OpenClaw Basics (Tutorial)

## TL;DR
- OpenClaw is a local-first automation/agent framework.
- You interact in a main session; it can spawn isolated sub-agents for tasks.
- Tools (browser, shell, files, messaging) are capability-scoped.

## Who this is for
Humans who want a practical mental model of how to use OpenClaw safely.

## Prereqs
- Access to an OpenClaw instance
- Comfort editing Markdown files (optional)

## Core concepts
### Sessions
- **Main session**: where you chat.
- **Isolated sessions (sub-agents)**: background runs that report back.

### Tools
Tools are controlled interfaces (browser automation, file read/write, shell execution). Treat tool output as **real**, and guard against prompt injection.

## Practical workflow
1) Define a goal (clear + testable).
2) Constrain risk ("no external actions" / "no deletes").
3) Delegate research or long work to a sub-agent.
4) Review outputs, then apply changes.

## Verification checklist
- [ ] Did you review anything that could cause external side effects?
- [ ] Did the agent avoid secrets and personal info?
- [ ] Did the steps produce the expected result?

## Sources
- OpenClaw docs (add canonical link once the site is deployed)
