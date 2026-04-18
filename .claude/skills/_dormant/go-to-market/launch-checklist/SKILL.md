---
name: launch-checklist
description: "Create a comprehensive pre-launch checklist with tiered scope (silent, soft, big-bang), covering engineering, design, marketing, support, legal, and operations readiness. Use before releasing features, products, or major updates to ensure nothing is missed."
---

# Launch Checklist

A launch checklist is a comprehensive verification document that ensures all functions are ready before releasing a feature or product. It coordinates across engineering, QA, design, marketing, support, legal, and operations to prevent launch-day surprises.

## When to Use

- 1-2 weeks before any significant launch
- During launch planning kickoff meetings
- When coordinating cross-functional releases
- Before major version releases or feature rollouts
- After incidents to improve launch processes

## Launch Tiers

Default to Tier 1 or 2. Upgrade to Tier 3 only with strong justification. Over-launching creates announcement fatigue.

### Tier 1: Silent Launch

Ship it, turn it on, see what happens. No announcement.

**Use for:** Bug fixes, minor improvements, internal tools, infrastructure changes, experiments.

**Checklist:**
- [ ] Feature is behind a flag or gradually rolled out
- [ ] Monitoring/alerting is in place
- [ ] Rollback plan exists and is tested
- [ ] One person is on point to watch metrics for 24 hours

### Tier 2: Soft Launch

Ship it, tell existing users, collect feedback before going wide.

**Use for:** New features for existing users, significant UX changes, pricing changes, beta programs.

**Checklist:**
- [ ] Changelog entry or in-app notification written
- [ ] Help docs updated (or created)
- [ ] Support team briefed with FAQ
- [ ] Feedback collection mechanism in place (survey, feedback button, Slack channel)
- [ ] Known limitations documented
- [ ] Rollback plan exists and is tested
- [ ] 1-2 week feedback period before going wide

### Tier 3: Big-Bang Launch

Coordinated, public, designed for maximum reach. Maximum 2-3 per year.

**Use for:** New product launch, major pivot, rebrand, entering a new market.

**Product Readiness:**
- [ ] Feature complete and tested at scale
- [ ] Onboarding flow tested with 5+ new users
- [ ] Performance benchmarked under expected load
- [ ] Rollback plan exists and is tested

**Content & Marketing:**
- [ ] Landing page or product page live
- [ ] Blog post / announcement written
- [ ] Demo video or screenshots prepared
- [ ] Social posts drafted for launch day and day +1, +3, +7
- [ ] Email to existing users scheduled
- [ ] Community posts drafted (relevant subreddits, Slack groups, Discord)
- [ ] Product Hunt launch prepared (if applicable)
- [ ] Influencer/partner outreach done 1 week before

**Support & Operations:**
- [ ] Support team briefed and staffed for launch day
- [ ] FAQ and known issues documented
- [ ] Escalation path defined

**Measurement:**
- [ ] Success metrics defined before launch (not after)
- [ ] Analytics tracking verified
- [ ] Daily review scheduled for first week

## Instructions

When asked to create a launch checklist, follow these steps:

1. **Define Launch Context**
   Document what is launching, when, and who the key stakeholders are. Establish the launch tier (Tier 1/2/3) as this determines checklist scope.

2. **Gather Functional Requirements**
   For each function (engineering, QA, marketing, support, legal, ops), identify what must be complete before launch. Distinguish between blockers (must-have) and nice-to-haves.

3. **Assign Owners and Dates**
   Every checklist item needs an owner and a target completion date.

4. **Identify Dependencies and Blockers**
   Flag items that block other work or depend on external factors. Surface these early.

5. **Define Go/No-Go Criteria**
   Establish clear criteria for the launch decision. What conditions must be met? Who makes the final call?

6. **Document Rollback Plan**
   Every launch must have a rollback strategy. Document how to revert if critical issues emerge post-launch.

7. **Schedule Check-in Cadence**
   Establish when the team reviews progress (daily standups, T-2 days review, launch day sync).

## Post-Launch (All Tiers)

1. **Day 1:** Watch metrics. Fix anything broken. Respond to all feedback.
2. **Day 3:** First retro -- what's working, what's not, what surprised you.
3. **Week 1:** Decide whether to iterate, expand, or pull back.
4. **Week 2-4:** Write up learnings. Update the roadmap based on real data.

## Quality Checklist

Before finalizing, verify:

- [ ] Launch tier is explicitly chosen with justification
- [ ] All functional areas are represented
- [ ] Every item has an owner and target date
- [ ] Blockers are clearly distinguished from nice-to-haves
- [ ] Go/No-Go criteria are specific and measurable
- [ ] Rollback plan is documented and tested
- [ ] Check-in cadence is scheduled
- [ ] Success metrics are defined BEFORE launch

## Guidelines

- NEVER launch without a rollback plan. If you can't revert, you're not ready.
- ALWAYS define success metrics BEFORE launch. Post-hoc metrics are storytelling.
- NEVER launch on a Friday. Launch Monday-Wednesday for monitoring time.
- ALWAYS have one person on point for the first 24 hours. Launches without owners drift.
- NEVER do a big-bang launch for features with known bugs. Soft launch first, fix, then go wide.
