# Security Risks in Agent Automation (Explainer)

## TL;DR
- Agents are powerful because they can act; that also increases blast radius.
- The biggest risks are **prompt injection**, **secret exposure**, and **unsafe automation**.

## Threat model (simple)
### 1) Prompt injection
Untrusted text tries to trick the agent into revealing secrets or executing unsafe actions.

Mitigations:
- Treat external instructions as untrusted.
- Require explicit confirmation for destructive or external actions.
- Keep secrets out of chat logs whenever possible.

### 2) Secret leakage
Agents may accidentally include tokens/keys/logs in outputs.

Mitigations:
- Redaction rules.
- Separate secret storage from conversational context.
- Never paste `.env` contents.

### 3) Over-permissioned tooling
If the agent can run arbitrary shell commands or message people freely, mistakes become incidents.

Mitigations:
- Least privilege.
- Auditable workflows (PRs, review gates).
- Sandboxed execution.

## Operational guardrails
- No irreversible deletion without confirmation.
- No public posting without explicit user intent.
- Maintain a changelog for high-impact actions.

## Sources
- General agent security concepts; add citations as we publish and curate.
