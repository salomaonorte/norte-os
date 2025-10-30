# PRP: Centralized Communication Hub (Job 1)

## Goal
Build a founder portal with request submission, status tracking, and company profiles using Deco framework.

## Why
- **Streamlines communication:** Single source of truth for all Norte-founder interactions
- **Eliminates lost requests:** 100% tracking of founder asks (intros, GTM, hiring, fundraising)
- **Scales Norte's approach:** 5-person team can manage 130+ companies systematically
- **Success Metric:** 35% of portfolio submits request in first month

## What
1. **Authentication:** Passwordless email login (magic links)
2. **Founder Dashboard:** Overview of requests, available opportunities (perks), and network highlights
3. **Request System:** Submit requests (5 types), track status (Submitted → In Progress → Completed/Declined), email notifications
4. **Opportunities & Network:** Display available perks (AWS/NVIDIA/Oracle), showcase key LPs and connections
5. **Company Profiles:** Basic info (name, sector, stage, assigned Norte partner)

## Implementation Blueprint

### Database Schema
```sql
CREATE TABLE users (id, email, name, role);
CREATE TABLE companies (id, name, sector, stage, norte_partner_id);
CREATE TABLE user_companies (user_id, company_id);
CREATE TABLE requests (id, company_id, type, title, details, priority, status, assigned_to_user_id, norte_notes);
CREATE TABLE request_attachments (id, request_id, filename, file_url);

-- Opportunities & Network (basic for Job 1, full version in Job 3)
CREATE TABLE perks (id, provider, title, description, value_usd, is_featured BOOLEAN);
CREATE TABLE network_contacts (id, name, company, role, contact_type, is_featured BOOLEAN);
```

### Deco App Structure
```
src/
  routes/
    login.tsx, dashboard.tsx (with perks & network widgets), request-new.tsx, request-detail.tsx
    admin/requests-queue.tsx, admin/companies-list.tsx, admin/perks-manage.tsx
  tools/
    sendMagicLink.ts, submitRequest.ts, updateRequestStatus.ts
  components/
    PerksWidget.tsx (shows top 3-5 available perks), NetworkWidget.tsx (featured LPs/connections)
```

### Implementation Steps (3-4 days)
1. **Day 1:** Auth setup, magic links, users/companies tables
2. **Day 2:** Request submission form, founder dashboard with perks/network widgets
3. **Day 3:** Norte admin queue, status updates, email notifications, seed perks/featured contacts
4. **Day 4:** Polish UI, onboarding flow, pilot with 10 founders

**Dashboard Widgets:**
- **Perks Widget:** Show 3-5 featured opportunities (NVIDIA GPU credits, AWS $100k, Oracle Cloud)
- **Network Widget:** Showcase 5-10 key LPs, advisors, or connections available for intros
- Click "View All" links to full Job 3 directory (implemented later)

### Critical Gotchas
- **CRITICAL:** Use magic links, NOT passwords (low friction)
- **CRITICAL:** Email notifications required (can't rely on portal checks)
- **GOTCHA:** File attachments max 10MB, use S3 not DB

## Validation Loop
- [ ] Founder logs in via magic link
- [ ] Founder submits request → Norte receives email
- [ ] Norte updates status → founder receives email
- [ ] All requests visible in admin queue

## Sign-off
- [ ] 10 pilot founders onboarded
- [ ] 20+ requests submitted
- [ ] Zero lost requests
- [ ] Founder feedback: 8+/10 ease of use
