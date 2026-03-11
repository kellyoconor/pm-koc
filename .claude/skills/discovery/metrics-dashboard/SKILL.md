---
name: metrics-dashboard
description: "Define and design a product metrics dashboard with key metrics, data sources, visualization types, alert thresholds, and review cadences. Use when creating a metrics dashboard, defining KPIs, setting up product analytics, building a data monitoring plan, or auditing existing metrics for quality."
---

## Product Metrics Dashboard

Design a comprehensive product metrics dashboard with the right metrics, visualizations, alert thresholds, and review cadences.

### Context

You are designing a metrics dashboard for **$ARGUMENTS**.

If the user provides files (existing dashboards, analytics data, OKRs, or strategy docs), read them first.

### Domain Context

**Metrics vs KPIs vs NSM**: Metrics = all measurable things. KPIs = a few key quantitative metrics tracked over a longer period. North Star Metric = a single customer-centric KPI that is a leading indicator of business success.

**4 criteria for a good metric** (Ben Yoskovitz, *Lean Analytics*):
1. **Understandable** -- creates a common language
2. **Comparative** -- over time, not a snapshot
3. **Ratio or Rate** -- more revealing than whole numbers
4. **Behavior-changing** -- the Golden Rule: "If a metric won't change how you behave, it's a bad metric"

**8 metric types**: Vanity vs Actionable (only actionable metrics change behavior), Qualitative vs Quantitative (WHAT vs WHY -- you need both; never stop talking to customers), Exploratory vs Reporting (explore data to uncover unexpected insights), Lagging vs Leading (leading indicators enable faster learning cycles, e.g. customer complaints predict churn).

**Counter-metrics**: EVERY tracked metric should have a counter-metric to prevent gaming. If the metric improves but the counter-metric degrades, you've optimized the wrong thing.

For case studies and more detail: [Are You Tracking the Right Metrics?](https://www.productcompass.pm/p/are-you-tracking-the-right-metrics)

### Instructions

1. **Audit existing metrics** (if any) against the 4 good-metric criteria:
   - Remove vanity metrics or flag them with appropriate caveats
   - Classify leading vs lagging indicators
   - Identify gaps in coverage

2. **Identify the metrics framework** -- organize metrics into layers:

   **North Star Metric**: The single metric that best captures core value delivery

   **Input Metrics** (3-5): The levers that drive the North Star

   **Health Metrics**: Guardrails that ensure overall product health

   **Business Metrics**: Revenue, cost, and unit economics

3. **For each metric, define**:

   | Metric | Definition | Data Source | Visualization | Target | Alert Threshold | Counter-Metric |
   |---|---|---|---|---|---|---|
   | [Name] | [Exact calculation: numerator/denominator, time window] | [Where the data comes from] | [Line chart / Bar / Number / Funnel] | [Goal value] | [When to trigger an alert] | [What to watch for gaming] |

   Exact formulas matter. "Activation rate" means nothing. "Percentage of new signups who invite at least one teammate within 7 days of account creation" is a metric.

4. **Design the dashboard layout**:

   ```
   +---------------------------------------------+
   |  NORTH STAR: [Metric] -- [Current Value]     |
   |  Trend: [up/down X% vs last period]          |
   +----------------------+-----------------------+
   |  Input Metric 1      |  Input Metric 2       |
   |  [Sparkline]         |  [Sparkline]          |
   +----------------------+-----------------------+
   |  Input Metric 3      |  Input Metric 4       |
   |  [Sparkline]         |  [Sparkline]          |
   +----------------------+-----------------------+
   |  HEALTH: [Latency] [Error Rate] [NPS]        |
   +----------------------------------------------+
   |  BUSINESS: [MRR] [CAC] [LTV] [Churn]         |
   +----------------------------------------------+
   ```

5. **Set review cadence**:
   - **Daily**: Operational health (errors, latency, critical flows)
   - **Weekly**: Input metrics and engagement trends
   - **Monthly**: North Star, business metrics, OKR progress
   - **Quarterly**: Strategic review and metric recalibration

6. **Define alerts**:
   - What thresholds trigger investigation?
   - Who gets alerted and through what channel?
   - What's the expected response time?

7. **Recommend tools** based on the user's context:
   - Amplitude, Mixpanel, PostHog for product analytics
   - Looker, Metabase, Mode for SQL-based dashboards
   - Datadog, Grafana for operational health

### 5 Action Steps for Metric Hygiene

1. Audit metrics against the 4 good-metric criteria
2. Update dashboards -- ensure all key metrics are good ones
3. Identify vanity metrics -- be careful how you use them
4. Classify leading vs lagging indicators
5. Pick one problem and dig deep into the data

### Guidelines

- NEVER track more than 5-7 metrics actively. If your dashboard has 20 charts, nobody looks at any of them.
- ALWAYS pair every metric with a counter-metric.
- ALWAYS define metrics with exact formulas.
- ALWAYS set a baseline before setting a target.
- NEVER use vanity metrics (total signups, page views, total users) as primary dashboard items.
- ALWAYS measure outcomes (user behavior) over outputs (features shipped).

Think step by step. Save the dashboard specification as a markdown document.

---

### Further Reading

- [The Ultimate List of Product Metrics](https://www.productcompass.pm/p/the-ultimate-list-of-product-metrics)
- [The North Star Framework 101](https://www.productcompass.pm/p/the-north-star-framework-101)
- [The Product Analytics Playbook: AARRR, HEART, Cohorts & Funnels for PMs](https://www.productcompass.pm/p/the-product-analytics-playbook-aarrr)
- [AARRR (Pirate) Metrics: The 5-Stage Framework for Growth](https://www.productcompass.pm/p/aarrr-pirate-metrics)
- [The Google HEART Framework: Your Guide to Measuring User-Centric Success](https://www.productcompass.pm/p/the-google-heart-framework)
- [Funnel Analysis 101: How to Track and Optimize Your User Journey](https://www.productcompass.pm/p/funnel-analysis)
- [Are You Tracking the Right Metrics?](https://www.productcompass.pm/p/are-you-tracking-the-right-metrics)
