# Norte OS - Product Requirements Document

## Executive Summary

**Product Name:** Norte OS - Portfolio Operating System  
**Version:** 1.0 (POC)  
**Target Launch:** Q1 2025 (4-week POC)  
**Owner:** Norte Ventures

Norte OS is an integrated digital platform that transforms how Norte Ventures manages its 130-company portfolio. Built on the Deco framework with Nekt integration for analytics, Norte OS replaces fragmented, manual processes with a centralized, data-driven system that enables proactive portfolio management and delivers immediate value to founders.

**Vision:** Become the industry benchmark for VC portfolio management, turning Norte from a reactive follower fund into a proactive, high-touch partner at scale.

## Problem Statement

### Current Pain Points

**For Norte Team (5 people, 130+ companies):**
- **Reactive Management:** Portfolio health issues discovered too late; no systematic way to identify companies needing attention
- **Fragmented Communication:** Requests scattered across WhatsApp, email, meetings; information falls through cracks
- **Manual Data Collection:** Monthly metrics requested ad-hoc via email/calls; inconsistent tracking
- **Lost Opportunities:** Network connections and intros rely on memory; synergies between portfolio companies missed
- **Time-Intensive Operations:** Team spends 10+ hours/week on manual tracking and admin work instead of value-add support

**For Portfolio Founders:**
- **Hidden Value:** Unaware of full Norte network, perks (AWS/NVIDIA/Oracle credits), and available resources
- **Request Friction:** No clear system to ask for intros, GTM help, hiring support, or fundraising assistance
- **No Benchmarking:** Flying blind on performance vs. peers; no reference points for metrics

### Business Impact
- Norte's high-touch value proposition doesn't scale beyond current portfolio size
- Founder satisfaction and engagement lower than potential
- Norte differentiation as a fund limited by operational constraints
- Missed opportunities for cross-portfolio synergies and timely interventions

## Solution Overview

Norte OS is a web-based platform built on **Deco** (TypeScript, self-hosted admin) with **Nekt** integration (Phase 2) that provides:

1. **Centralized Communication Hub** - Single place for founders to request help and access Norte resources
2. **Self-Service Metrics Dashboard** - Founders input metrics, see trends, get anonymous benchmarking
3. **Network Discovery Engine** - Searchable directory of Norte's network with one-click intro requests
4. **Portfolio Health Dashboard** - Norte team view with health scores, red/green flags, prioritization
5. **Automated Meeting Intelligence** - AI extraction from Fireflies transcripts to auto-populate metrics and insights

### Key Differentiators
- **Reciprocal Value:** Founders get immediate benefits (benchmarking, network access) in exchange for data sharing
- **Proactive Management:** Shift from reactive to predictive portfolio oversight
- **Composable Architecture:** Deco's MCP-native design enables progressive enhancement and tool stacking
- **Self-Hosted & Secure:** Full data control with Norte's infrastructure

## Functional Requirements

### Phase 1: Foundation (Weeks 1-2) - Deco Only

#### Job 1: Centralized Communication Hub

**User Story:** When I need to interact with Norte or request something, I want one place to make requests and see my company info, so that communication is streamlined and nothing falls through cracks.

**Features:**
- Founder portal with authentication (email-based, passwordless)
- Request submission system:
  - Request types: Introductions, GTM Help, Hiring Support, Fundraising Assistance
  - Rich text descriptions
  - Priority levels (Normal, Urgent)
  - File attachments support
- Request status tracking:
  - States: Submitted, In Progress, Completed, Declined
  - Norte team notes visible to founders
  - Email notifications on status changes
- Basic company profile page:
  - Company name, logo, founding date
  - Founder contact info
  - Sector, stage, investment date
  - Norte contact (assigned partner)

**Success Criteria:**
- 50% of portfolio companies submit at least one request in first month
- Response time to requests drops from days to hours
- 100% request tracking (nothing lost)

#### Job 2: Founder Self-Service Metrics

**User Story:** When I want to report my metrics, I want to input them in a standard format and see basic comparisons, so that I get standardized data and Norte gets insights.

**Features:**
- Monthly metric input form:
  - Core metrics: ARR (or MRR), Growth % (MoM), Employee Count, Runway (months), Churn Rate %
  - Optional: Fundraising status, key milestones
  - Historical data import capability
- Personal dashboard:
  - Metric trends over time (line charts)
  - Month-over-month change indicators
  - Data export (CSV)
- Anonymous benchmarking:
  - Quartile positioning per metric ("You're in top 25% for growth")
  - Segmented by stage (Pre-seed, Seed, Series A)
  - No company names visible
- Optional: Auto-generate investor update template
  - Pre-filled with metric data
  - Editable narrative sections
  - PDF export

**Success Criteria:**
- 60% of companies input metrics monthly
- Founders rate benchmarking feature 8+/10 usefulness
- Data completeness >90% for submitted metrics

#### Job 3: Network Discovery MVP

**User Story:** When I need a customer, hire, or investor connection, I want to see relevant Norte connections and request intros, so that I leverage Norte's network effectively.

**Features:**
- Network directory (manually curated):
  - Contact types: Portfolio Companies, LPs, Advisors, Service Providers
  - Profile fields: Name, company, role, expertise, sectors, willing to help with
  - Tag-based categorization
- Search and filter:
  - Text search (name, company, expertise)
  - Filters: Contact type, sector, help category
  - Results sorted by relevance
- One-click intro request:
  - Select contact(s) from directory
  - Add context (why this intro, what you hope to achieve)
  - Routes to Norte team for review
- Intro outcome tracking:
  - Norte marks: Intro Made, Meeting Held, Deal Closed, Hire Made, No Outcome
  - Visible to founders
- Perks & benefits catalog:
  - AWS, NVIDIA, Oracle credits
  - Partner discounts
  - Application/claim instructions

**Success Criteria:**
- 50+ successful intros made through platform in Q1
- 80%+ intro requests fulfilled within 1 week
- Founders discover perks they didn't know existed

### Phase 2: Intelligence Layer (Weeks 3-4) - Deco + Nekt

#### Job 4: Portfolio Health Dashboard

**User Story:** When I'm planning my week, I want to see which companies need attention, so that I prioritize outreach strategically.

**Features:**
- Portfolio overview grid:
  - All 130 companies displayed
  - Health score (1-100) with color coding (Green 80+, Yellow 50-79, Red <50)
  - Key metrics at a glance (latest ARR, growth, runway)
  - Last contact date
- Health scoring algorithm:
  - Inputs: Growth rate, runway, churn, metric submission consistency, sentiment from meetings
  - Statistical analysis: Compare to portfolio mean and standard deviation
  - Weights adjustable by Norte team
- Red flag detection:
  - Automatic triggers: Revenue drop >20%, Churn spike >2x, Runway <12 months, Growth <1.5 SD below mean
  - Manual flags: Founder departures, pivoting, regulatory issues
  - Alert notifications (email/Slack)
- Green flag celebration:
  - Triggers: Growth >1.5 SD above mean, Key milestones (first $1M ARR, profitability), Successful fundraise
  - Kudos system
- Sorting and filtering:
  - By health score, stage, sector, last contact, Norte partner
  - Saved filter presets
- "Top 10 Needs Attention" list:
  - Algorithm prioritizes: Red flags + time since last contact + runway urgency
  - Refreshes daily
  - Suggested actions per company

**Success Criteria:**
- Norte identifies and intervenes on 3+ red flag situations proactively in first quarter
- Team saves 10+ hours/week on manual tracking
- 100% of portfolio has health score visible

**Data Dependencies:**
- Requires metric data from Job 2 (manual input initially, auto-extracted from Job 5 later)

#### Job 5: Automated Meeting Intelligence

**User Story:** When Norte has meetings with portfolio companies, I want to automatically capture metrics and insights from transcripts, so that I have a living database without manual input.

**Features:**
- Fireflies integration:
  - OAuth connection to Norte's Fireflies account
  - Automatic transcript ingestion for meetings tagged "Portfolio" or with company names
- Nekt data lake setup:
  - Store transcripts, extracted entities, time-series metrics
  - 100+ connector support for future data sources
- AI extraction agent:
  - Powered by Claude 3.5 Sonnet via Deco's AI framework
  - Extracts: ARR/MRR mentions, growth numbers, employee count, runway comments, churn data
  - Detects: Help requests (hiring, GTM, fundraising), Sentiment (positive, neutral, concerned), Red/green flag indicators
  - Structured output matching Job 2 metric schema
- Validation UI (human-in-loop):
  - Norte team reviews extracted data before DB commit
  - Edit fields, confirm accuracy
  - Approve or reject extractions
  - Feedback loop improves extraction over time
- Auto-population of metrics:
  - Extracted data updates same database as manual Job 2 entries
  - Marks source (manual vs. auto-extracted)
  - Deduplication logic (don't double-count)
- Weekly digest email:
  - Portfolio highlights (top movers, red flags, green flags)
  - Action items from meetings
  - Sent to Norte team every Monday

**Success Criteria:**
- 90% of meeting data auto-captured and structured by end of Phase 2
- Extraction accuracy >85% (validated by Norte team review)
- Team saves 5+ hours/week on meeting notes and metric updates

**Dependencies:**
- **Requires Nekt integration:** Migration meeting needed to plan:
  - Nekt workspace setup
  - Data schema alignment between Deco and Nekt
  - MCP configuration for Deco to query Nekt data lake
  - Fireflies → Nekt pipeline
- **Requires Job 2 data model:** Must be implemented first to ensure schema compatibility

## Non-Functional Requirements

### Performance
- Page load time <2s for dashboards with 130 companies
- Search results return in <500ms
- Support 200+ concurrent users (130 founders + Norte team + guests)

### Security
- Self-hosted on Norte's infrastructure (AWS or GCP)
- Role-based access control:
  - Founders: See only their company data + public network directory
  - Norte Team: Full portfolio visibility
  - Admins: System configuration
- Data encryption at rest and in transit
- GDPR-compliant data handling (right to deletion, export)

### Scalability
- Database: PostgreSQL or SQLite (Deco-compatible)
- Horizontal scaling for Deco admin instances
- Nekt handles analytics layer scaling independently

### Usability
- Mobile-responsive design (Deco's default)
- Onboarding flow for first-time founders (<5 minutes)

## Technical Stack

### Phase 1 (Deco Only)
- **Framework:** Deco (TypeScript, web-based admin, MCP-native)
- **Database:** PostgreSQL or SQLite (self-hosted)
- **Authentication:** Deco's built-in auth (email-based, passwordless)
- **Hosting:** Self-hosted (AWS, GCP, or on-prem)
- **UI Components:** Deco's admin components (forms, tables, charts)

### Phase 2 (Deco + Nekt)
- **Analytics Layer:** Nekt (data lake, 100+ connectors, MCP for text-to-SQL)
- **AI Models:** Claude 3.5 Sonnet (via Anthropic API or Bedrock)
- **Meeting Transcripts:** Fireflies API
- **Email Delivery:** SMTP or SendGrid for notifications/digests

## Implementation Timeline

### Week 1-2: Phase 1 - Quick Wins
- **Week 1:**
  - Deco admin setup for Norte team
  - Job 1: Founder portal + request system (3 days)
  - Job 2: Metric input forms (2 days)
- **Week 2:**
  - Job 2: Personal dashboards + benchmarking (3 days)
  - Job 3: Network directory + intro requests (2 days)
  - Pilot onboarding: 10 founders

### Week 3-4: Phase 2 - Intelligence Layer
- **Week 3:**
  - Nekt migration meeting (align on data schema, setup workspace)
  - Job 4: Portfolio health dashboard for Norte team (4 days)
  - Collect first month of manual metrics from pilots
- **Week 4:**
  - Job 5: Fireflies → Nekt integration (2 days)
  - Job 5: AI extraction agent + validation UI (3 days)
  - Refine based on pilot feedback

### Month 2: Expand & Refine
- Roll out to 50 companies
- Iterate on metric definitions based on founder feedback
- Add health dashboard alerts and automation

### Month 3-4: Automate & Scale
- Full portfolio rollout (130 companies)
- Anomaly detection and predictive alerts
- Weekly digest automation
- Template library (playbooks, best practices)

## Success Metrics

### Adoption Metrics
- **Target:** 50% of portfolio companies create accounts within 3 months
- **Target:** 50% of subscribed companies submit at least one request in first month
- **Target:** 30% of companies input metrics monthly (or have them auto-captured)

### Efficiency Metrics
- **Target:** 90% of meeting data auto-captured and structured (by end of Phase 2)
- **Target:** Response time to founder requests drops from days to hours

### Value Metrics
- **Target:** 50+ successful intros made through platform in first quarter
- **Target:** Founders rate usefulness 8+/10
- **Target:** Norte identifies and intervenes on 3+ red flag situations proactively

### Business Impact
- Norte maintains high-touch approach while scaling to 150+ companies
- Founder NPS increases by 20+ points
- Norte becomes case study for Deco and Nekt (industry benchmark)

## Risks and Mitigations

### Risk: Low Founder Adoption
- **Mitigation:** Focus on reciprocal value (benchmarking, network access) from day one. Gustavo's personal outreach to each founder. Start with 10 pilot enthusiasts.

### Risk: Incomplete Metric Data
- **Mitigation:** Phase 1 establishes manual habit; Phase 2 automates. Don't over-rely on automation until data model validated.

### Risk: Nekt Integration Complexity
- **Mitigation:** Keep Phase 1 independent of Nekt. Migration meeting before Job 5 implementation ensures alignment.

### Risk: AI Extraction Accuracy
- **Mitigation:** Human-in-loop validation UI. Start with high-confidence extractions only. Iterative improvement.

## Open Questions for Nekt Migration Meeting

1. Data schema alignment: How to map Fireflies transcript entities to Norte's metric schema?
2. MCP setup: How does Deco query Nekt data lake? Authentication, rate limits?
3. Real-time vs. batch: Should meeting data be processed live or daily batch?
4. Extraction prompt engineering: What context improves accuracy (company profiles, previous metrics)?
5. Cost modeling: Token usage for 130 companies x 2-4 meetings/month?

## Appendix: Jobs to be Done (Reference)

**Phase 1:**
- Job 1: Centralized Communication Hub
- Job 2: Founder Self-Service Metrics
- Job 3: Network Discovery MVP

**Phase 2:**
- Job 4: Portfolio Health Dashboard
- Job 5: Automated Meeting Intelligence

(See `docs/jobs_to_be_done_poc.md` for detailed user stories and POC scope)

