# PRP: Network Discovery MVP (Job 3)

## Goal
Create searchable Norte network directory with one-click intro requests and outcome tracking.

## Why
- **High value:** Network access is top reason founders want VC partners
- **Scales intros:** From memory-based to systematic and trackable
- **Showcases value:** Perks (AWS/NVIDIA/Oracle) and connections visible in one place
- **Success Metric:** 30+ successful intros in Q1

## What
1. **Network Directory:** Searchable contacts (Portfolio, LPs, Advisors, Service Providers)
2. **Intro Requests:** Founder selects contact, adds context, Norte facilitates
3. **Outcome Tracking:** Norte marks status (Intro Made → Meeting Held → Outcome)
4. **Perks Catalog:** Display benefits with claim instructions

## Implementation Blueprint

### Database Schema
```sql
CREATE TABLE network_contacts (
  id, name, company, role, email, linkedin_url,
  contact_type, sectors[], expertise_tags[], willing_to_help_with[],
  is_visible BOOLEAN DEFAULT true
);

CREATE TABLE intro_requests (
  id, company_id, submitted_by_user_id,
  contact_ids[], -- Array: can request multiple intros
  reason TEXT, goal TEXT,
  status, assigned_to_user_id, outcome_details
);

CREATE TABLE perks (
  id, provider, title, description, value_usd, claim_instructions
);

CREATE TABLE perk_claims (
  perk_id, company_id, claimed_at,
  UNIQUE(perk_id, company_id)
);
```

### Implementation Steps (3 days)
1. **Day 1:** Network contacts CRUD, CSV import, seed 50+ contacts
2. **Day 2:** Directory UI with search/filters, intro request form
3. **Day 3:** Norte intro queue, outcome tracking, perks catalog

### Critical Gotchas
- **CRITICAL:** Require context in intro requests ("Why?" and "Goal?")
- **CRITICAL:** Privacy opt-in for non-portfolio contacts
- **GOTCHA:** Outcome tracking relies on Norte updates - make it one-click simple

## Validation Loop
- [ ] Founder searches directory → sees results
- [ ] Founder requests intro → Norte notified
- [ ] Norte marks "Intro Made" → founder sees update
- [ ] Founder claims perk → recorded

## Sign-off
- [ ] Directory with 200+ contacts
- [ ] 10 pilot founders submit intro requests
- [ ] 20+ intros processed
- [ ] 80%+ fulfillment within 1 week
