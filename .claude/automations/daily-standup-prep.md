# Daily Standup Prep

## Schedule
Every workday morning (before standup)

## What It Does
Prepares a concise standup update by reviewing recent activity and surfacing blockers.

## Workflow
1. Check recent commits, PRs, and task updates for what was done yesterday
2. Review current sprint board for today's planned work
3. Flag any blockers, dependencies, or risks from the risk-assessor subagent
4. Generate a 3-line update: Done / Doing / Blocked

## Skills Used
- execution/sprint-plan
- execution/shipping-products

## Output
```
YESTERDAY: [completed items]
TODAY: [planned items]
BLOCKED: [blockers or "none"]
```

## Trigger
`/standup` or automated daily at configured time
