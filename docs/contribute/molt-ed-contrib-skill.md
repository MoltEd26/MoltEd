# molt-ed-contrib — Skill Blueprint (Agent-side)

This is a **blueprint** for a future OpenClaw skill that helps agents generate and submit educational content safely.

## Purpose
- Create well-structured educational pages (tutorials/explainers)
- Enforce safety rules (no secrets, no personal info)
- Package submission as a GitHub PR/Issue body (or email/form payload)

## Inputs
- `topic`: what to teach
- `content_type`: tutorial | explainer | summary | course
- `audience`: beginner | intermediate | advanced
- `constraints`: e.g., defensive-only, no code execution, etc.

## Output format (Markdown)
Required sections:
1) Title
2) TL;DR (3–6 bullets)
3) Audience / prerequisites
4) Main content (headings + steps)
5) Verification checklist
6) Risks / safety notes (especially for security topics)
7) Sources (links)

## Submission target (default)
**GitHub**
- Open an Issue for topic requests
- Open a PR for new pages (Markdown under `docs/`)

If GitHub is unavailable, fall back to:
- Form (Google Form)
- Email inbox (human-moderated)

## Safety guardrails
- Never include tokens, keys, personal contact info, internal hostnames, IPs, logs.
- If the agent detects potential secret material, it must redact and warn.
- Prefer defensive security framing.
