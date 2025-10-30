# Jobs to be Done Framework - Norte Portfolio Platform (POC)

## 🚀 JOBS TO BE DONE - POC (Practical First Version)

### **Phase 1: Foundation (Weeks 1-2)**

#### **POC Job 1: Centralized Communication Hub**
**When** I need to interact with Norte or request something,  
**I want to** have one place to make requests and see my company info,  
**So that** communication is streamlined and nothing falls through the cracks.

**POC Scope:**
- Simple founder portal (Deco-based)
- Request system (intros, help with GTM/hiring/fundraising)
- Status tracking on requests
- Basic company profile page

**Why This First:** Low friction adoption, immediate value, starts data collection habit

---

#### **POC Job 2: Founder Self-Service Metrics**
**When** founders want to report their metrics,  
**I want to** input metrics in a standard format and see basic comparisons,  
**So that** I get standardized data and they get value (benchmarking).

**POC Scope:**
- Monthly metric input form (ARR, growth %, employee count, runway months, churn)
- Personal dashboard showing their trends over time
- Anonymous quartile comparison ("You're in top 25% for growth")
- Optional: auto-generate investor update from their data

**Why This Second:** Simple CRUD operation, creates immediate reciprocal value, establishes data structure and collection habit before automating it

---

#### **POC Job 3: Network Discovery MVP**
**When** a founder requests an intro to a customer/hire/investor,  
**I want to** see a curated list of relevant Norte connections,  
**So that** I can make targeted intros faster.

**POC Scope:**
- Static directory of Norte network (manually curated initially)
- Search by company type, role, sector
- One-click intro request that goes to Norte team
- Simple tracking (intro made → outcome)

**Why This Third:** High perceived value, solves immediate pain, doesn't require complex AI

---

### **Phase 2: Intelligence Layer (Weeks 3-4)**

#### **POC Job 4: Portfolio Health Dashboard**
**When** I'm planning my week,  
**I want to** see which companies need attention this week,  
**So that** I can prioritize my outreach strategically.

**POC Scope:**
- Dashboard showing all 130 companies
- Metrics from Job 2 manual input + later auto-extracted from meetings
- Simple health indicators (green/yellow/red based on rules)
- Sort/filter by stage, sector, health status
- Top 10 "needs attention" list
- Red flags: pivoting, departures, churn spike, revenue drop, <1.5 SD growth
- Green flags: >1.5 SD growth, key milestones

**Why Second Phase:** Requires data from Phase 1 (Job 2), but delivers core proactive management value. Now you have the schema and can enhance it with automation.

---

#### **POC Job 5: Automated Meeting Intelligence**
**When** Norte has meetings with portfolio companies,  
**I want to** automatically capture metrics, action items, and sentiment from transcripts,  
**So that** I have a living database of what's happening across the portfolio without manual input.

**POC Scope:**
- Fireflies -> Nekt integration
- AI agent extracting: metrics mentioned, asks made, red/green flag indicators
- Auto-populate the same database structure from Job 2
- Weekly digest email of portfolio highlights
- Validation UI: review and confirm extracted data before it updates metrics

**Why Last in POC:** More complex, requires AI/NLP work. But now you have the data model validated, the UI built, and founders are used to seeing their metrics. This just automates what they're already doing manually.

---

## 📊 POC Success Metrics

### **Adoption Metrics:**
- 80% of portfolio companies create accounts within 3 months
- 50% of companies submit at least one request in first month
- 60% of companies input metrics monthly (or have them auto-captured)

### **Efficiency Metrics:**
- Norte team saves 10+ hours/week on manual tracking
- 90% of meeting data auto-captured and structured (by end of Phase 2)
- Response time to founder requests drops from days to hours

### **Value Metrics:**
- 50+ successful intros made through platform in first quarter
- Founders rate usefulness 8+/10
- Norte identifies and intervenes on 3+ red flag situations proactively

---

## 🎬 Recommended POC Launch Sequence

### **Week 1-2: Quick Wins**
1. Set up Deco admin for Norte team
2. Create simple founder portal with request system
3. Build metric input forms + personal dashboard

### **Week 3-4: First Founder Cohort**
4. Onboard 10 pilot founders (pick ones who'll actually input data!)
5. Get first month of manual metric submissions
6. Launch network directory (v1 - even if manual/static)

### **Month 2: Expand & Refine**
7. Roll out to 50 companies based on learnings
8. Add health dashboard for Norte team (using collected metrics)
9. Refine metric definitions based on what founders actually track

### **Month 3-4: Automate & Scale**
10. Configure Nekt integration with Fireflies
11. Build AI extraction agents (now you know exact schema to extract)
12. Full portfolio rollout with hybrid manual + auto data collection
13. Implement anomaly detection and alerts
