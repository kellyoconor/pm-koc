# Weekly Feedback Analysis

## Schedule
Every Monday morning

## What It Does
Analyzes the past week's user feedback (support tickets, reviews, NPS responses, Slack mentions) and surfaces patterns, sentiment shifts, and actionable insights.

## Workflow
1. Ingest new feedback data (CSV, API export, or pasted text)
2. Run sentiment-analysis skill on all new entries
3. Cluster feedback by theme and JTBD
4. Compare to previous week's themes — flag new patterns or escalations
5. Prioritize top 3 insights with recommended actions
6. Run through customer-advocate subagent for interpretation

## Skills Used
- market-research/sentiment-analysis
- market-research/user-segmentation
- discovery/analyze-feature-requests
- discovery/designing-surveys (if follow-up needed)

## Subagents
- customer-advocate (interpret what customers are really saying)
- data-analyst (validate patterns with numbers)

## Output
Weekly Feedback Report:
- Sentiment trend (up/down/stable vs. last week)
- Top 3 themes with volume and severity
- New emerging issues (first-time this week)
- Recommended actions with priority
- Suggested follow-up questions for user research

## Trigger
`/weekly-feedback` or automated Monday AM
