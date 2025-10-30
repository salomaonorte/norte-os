# PRP: Portfolio Health Dashboard (Job 4)

## Goal
Build Norte team dashboard with health scores, red/green flags, and prioritization for all 130 companies.

## Why
- **Shift to proactive:** Catch problems before they become critical
- **Prioritizes effort:** Team knows which 10 companies need attention this week
- **Success Metric:** Norte intervenes on 3+ red flags proactively in Q1

## What
1. **Portfolio Grid:** All companies with health scores (0-100), color-coded (Green 80+, Yellow 50-79, Red <50)
2. **Health Algorithm:** Growth + runway + churn + engagement score, with Z-score analysis
3. **Flag Detection:** Auto-detect red flags (revenue drop >20%, runway <12mo, growth <1.5 SD below mean)
4. **Top 10 List:** Daily prioritization based on flags + last contact + runway urgency

## Implementation Blueprint

### Database Schema
```sql
CREATE TABLE company_health_scores (
  id, company_id, calculation_date,
  health_score INT, health_category VARCHAR(20), -- 'green', 'yellow', 'red'
  growth_score, runway_score, churn_score, engagement_score,
  growth_zscore, arr_zscore, churn_zscore
);

CREATE TABLE company_flags (
  id, company_id,
  flag_type, flag_category, severity,
  title, details,
  is_active BOOLEAN, acknowledged_at, resolved_at
);

CREATE TABLE contact_log (
  id, company_id, norte_user_id,
  contact_type, subject, sentiment, contact_date
);
```

### Implementation Steps (4 days)
1. **Day 1:** Health scoring algorithm, Z-score analysis
2. **Day 2:** Flag detection rules (revenue drop, runway, growth lagging), daily cron
3. **Day 3:** Dashboard UI with company cards, filters, sorting
4. **Day 4:** Company detail view, Top 10 prioritization algorithm

### Critical Gotchas
- **CRITICAL:** Health score must be explainable (show WHY red/yellow/green)
- **CRITICAL:** Internal tool only - don't show founders their health scores
- **GOTCHA:** Min 15 companies per stage for meaningful statistics

## Validation Loop
- [ ] Health scores calculated for all companies
- [ ] Flags detected correctly (validate with Norte team)
- [ ] Dashboard loads <3s with 130 companies
- [ ] Top 10 list is actionable

## Sign-off
- [ ] 100% portfolio has health scores
- [ ] Dashboard used daily for 2 weeks
- [ ] 3+ proactive interventions
- [ ] Team feedback: 9+/10 usefulness
