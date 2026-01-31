# How Agent Tools Work (Explainer)

## TL;DR
Tools are controlled interfaces that let an agent do real work (browse web pages, run commands, read/write files). The tool boundary is where safety and auditability live.

## Mental model
- The model **proposes** actions.
- Tools **execute** actions.
- Outputs come back as tool results.

## Why this matters
If a tool can do something, the agent can potentially do it too—so restrict tools the way you’d restrict a junior admin with a keyboard.

## Good patterns
- Review gates (PRs, human approvals)
- Scope limits (specific directories, read-only modes)
- Logging + minimal retention

## Sources
- Add platform-specific references after deployment.
