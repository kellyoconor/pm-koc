# Sprint Kickoff Review

## Schedule
Sprint start (every 2 weeks or per sprint cadence)

## What It Does
Reviews upcoming sprint work for completeness, risk, and alignment. Ensures PRDs are solid, stories are sized, and the sprint is achievable.

## Workflow
1. Pull current sprint backlog
2. For each item, check:
   - Does it have a clear PRD or spec? (execution/create-prd)
   - Are acceptance criteria defined? (execution/user-stories)
   - Are edge cases documented? (execution/deliver-edge-cases)
   - Has it been sized? (execution/bet-sizing)
3. Run risk-assessor subagent on the sprint as a whole
4. Run engineering-lead subagent for feasibility check
5. Flag items that need more work before committing
6. Generate sprint summary with confidence score

## Skills Used
- execution/sprint-plan
- execution/create-prd
- execution/user-stories
- execution/deliver-edge-cases
- execution/bet-sizing
- execution/epic-breakdown-advisor
- execution/prioritization-frameworks

## Subagents
- engineering-lead (feasibility + sizing validation)
- risk-assessor (sprint-level risk assessment)

## Output
Sprint Readiness Report:
- Sprint goal and theme
- Item-by-item readiness (green/yellow/red)
- Total capacity vs. committed points
- Top risks and mitigations
- Confidence score (1-10) with reasoning
- Action items to close gaps before sprint starts

## Trigger
`/sprint-kickoff` or automated at sprint start
