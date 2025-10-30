# PRP: Automated Meeting Intelligence (Job 5)

## Goal
Automate extraction of metrics and insights from meeting transcripts using Fireflies + Nekt + AI, eliminating manual data entry.

## Why
- **Eliminates manual work:** Norte saves 5+ hours/week on notes
- **Scales to 130 companies:** Manual tracking impossible at this scale
- **Success Metric:** 90% of meeting data auto-captured by end of Phase 2

## What
1. **Fireflies → Nekt Pipeline:** Auto-ingest transcripts to Nekt data lake
2. **AI Extraction:** Claude 3.5 extracts metrics, requests, sentiment, flags from transcripts
3. **Validation UI:** Norte reviews/edits extracted data before DB commit (human-in-loop)
4. **Auto-Population:** Updates same Job 2 schema (mark source as 'auto_extracted')
5. **Weekly Digest:** Monday email with portfolio highlights, red/green flags, action items

## Implementation Blueprint

### Database Schema
```sql
CREATE TABLE transcript_processing_log (
  id, fireflies_meeting_id, meeting_title, meeting_date, participants[],
  company_id,
  status, extracted_data JSONB, extraction_confidence,
  validated_by_user_id, validated_at
);
```

### Implementation Steps (5-6 days)
**Day 0:** Migration meeting with Norte/Deco/Nekt teams (BLOCKER)

1. **Day 1:** Configure Nekt MCP in Deco, test transcript fetching
2. **Day 2:** Build AI extraction agent (Claude 3.5 with extraction prompt)
3. **Day 3:** Validation UI (transcript view + editable extracted data)
4. **Day 4:** Deduplication logic (prefer manual over auto-extracted), weekly digest
5. **Day 5:** Testing with 20 real transcripts, tune extraction prompts

### Critical Gotchas
- **CRITICAL:** Migration meeting REQUIRED before starting (Nekt setup, schema alignment, MCP config)
- **CRITICAL:** Human-in-loop validation non-negotiable (AI won't be 100% accurate)
- **CRITICAL:** Deduplication essential (don't double-count manual + auto metrics)
- **GOTCHA:** Token costs: ~$39/mo for 130 companies x 2 meetings/month

### Extraction Prompt
```
Extract from Norte-[Company] meeting transcript:
1. METRICS: ARR/MRR, growth %, employee count, runway, churn
2. REQUESTS: Intros, GTM help, hiring, fundraising
3. SENTIMENT: positive/neutral/concerned
4. FLAGS: Red (problems, departures) or Green (wins, milestones)
Output JSON with confidence score.
```

## Validation Loop
- [ ] Nekt MCP fetches transcripts
- [ ] AI extraction runs without errors
- [ ] Validation UI displays extracted data
- [ ] Approved data inserts to DB (Job 2 schema)
- [ ] Weekly digest generates and sends

## Sign-off
- [ ] Migration meeting completed
- [ ] 90% meetings auto-ingested
- [ ] Extraction accuracy >85%
- [ ] Team feedback: 8+/10 on time savings
