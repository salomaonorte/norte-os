# PRP: Founder Self-Service Metrics Dashboard (Job 2)

## Goal
Build monthly metric input system with trend dashboards and anonymous peer benchmarking using Deco framework.

## Why
- **Standardizes data:** All 130 companies report same metrics (ARR, growth, employee count, runway, churn)
- **Enables Job 4 & 5:** Foundation for health scoring and AI extraction
- **Reciprocal value:** Founders get benchmarking insights for sharing data
- **Success Metric:** 30% of companies input metrics monthly after 3 months

## What
1. **Metric Input:** Monthly form for 5 core metrics + optional milestones
2. **Personal Dashboard:** Line charts showing trends, MoM change indicators
3. **Benchmarking:** Quartile positioning per metric, segmented by stage (min 8 companies for privacy)
4. **Monthly Reminders:** Email on 1st of each month

## Implementation Blueprint

### Database Schema
```sql
CREATE TABLE metric_submissions (
  id, company_id, submission_month DATE,
  arr_usd, growth_rate_pct, employee_count, runway_months, churn_rate_pct,
  fundraising_status, key_milestones,
  data_source DEFAULT 'manual', -- 'manual' or 'auto_extracted' for Job 5
  UNIQUE(company_id, submission_month)
);

CREATE TABLE benchmark_cache (
  id, stage, metric_name, calculation_month,
  q1_value, median_value, q3_value, sample_size
);
```

### Implementation Steps (4-5 days)
1. **Day 1:** Metric submission form with validation
2. **Day 2:** Personal dashboard with Recharts line charts
3. **Day 3:** Benchmark calculation (percentile algorithm) + cron job (5th of month)
4. **Day 4:** Benchmark display UI with quartile positioning
5. **Day 5:** CSV import, monthly reminder emails

### Critical Gotchas
- **CRITICAL:** Don't compare Pre-seed to Series A (stage segmentation required)
- **CRITICAL:** Churn rate confusing - provide clear tooltips
- **GOTCHA:** Growth rate misleading at low ARR (<$10k) - add warnings
- **GOTCHA:** Min 8 companies for benchmarking (privacy protection)

## Validation Loop
- [ ] Founder submits metrics → saved to DB
- [ ] Dashboard renders charts correctly
- [ ] Benchmarks calculate accurate quartiles
- [ ] CSV import works for historical data
- [ ] Monthly reminder emails sent

## Sign-off
- [ ] 10 pilot founders submit 2+ months metrics
- [ ] Benchmarks displayed for all stages
- [ ] Founder feedback: 8+/10 on benchmarking usefulness
- [ ] Data completeness >90%
