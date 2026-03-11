# Monthly Competitive Scan

## Schedule
First week of every month

## What It Does
Scans the competitive landscape for changes — new features, pricing moves, positioning shifts, funding rounds, hires — and assesses strategic implications.

## Workflow
1. For each tracked competitor:
   - Check for product updates (changelogs, release notes, Product Hunt)
   - Check for pricing or packaging changes
   - Check for funding, M&A, or leadership changes
   - Check for messaging/positioning shifts (homepage, ads)
2. Run competitive-teardown skill on any major changes
3. Update competitive battlecards
4. Run business-strategist subagent for strategic implications
5. Generate competitive intelligence brief

## Skills Used
- market-research/competitor-analysis
- market-research/competitive-teardown
- go-to-market/competitive-battlecard
- strategy/porters-five-forces
- strategy/swot-analysis

## Subagents
- business-strategist (strategic implications)
- growth-pm (growth tactic assessment)

## Output
Monthly Competitive Brief:
- Competitor activity summary (what changed)
- Updated battlecards for any changed competitors
- Strategic implications (threats and opportunities)
- Recommended responses (react / monitor / ignore)
- Market trend signals

## Trigger
`/competitive-scan` or automated monthly
