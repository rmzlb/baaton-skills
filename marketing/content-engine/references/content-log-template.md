# Content Log Template

Log every published piece. This builds your content intelligence over time.

---

## How to Use

After each piece is published:
1. Create an entry using the template below
2. Add it to `content-log.md` (append, newest first)
3. After 24-48 hours, update with performance data
4. Review weekly: what patterns drive your best results?

---

## Entry Template

```yaml
---
id: [auto-increment or YYYY-MM-DD-platform-slug]
date_published: YYYY-MM-DD
platform: [linkedin | twitter | email | facebook-ad | google-ad | landing-page]
format: [story | framework | observation | contrarian | thread | sequence | single-tweet | ad]
pillar: [your content pillar name]

brief:
  audience: [who this was for]
  goal: [what action was targeted]
  angle: [the specific insight in one sentence]

production:
  iterations: [1 | 2 | 3]
  final_score: [X.X/10]
  time_to_complete: [e.g., "45 min"]
  hardest_part: [hook | voice | actionability | flow | other]

content_snapshot:
  hook: "[first line of the published piece]"
  word_count: [number]
  char_count: [number]

performance:
  checked_at: [e.g., "24h", "48h", "7d"]
  impressions: [number or null]
  engagement_rate: [e.g., "4.2%" or null]
  comments: [number]
  shares: [number]
  clicks: [number or null]
  goal_achieved: [yes | partial | no]
  notes: "[e.g., 'Got 4 DMs, 2 converted to calls']"

lessons:
  what_worked: "[specific observation]"
  what_to_change: "[specific change for next time]"
  reuse_angle: [yes | no | modified]
---
```

---

## Example Entry

```yaml
---
id: 2024-03-15-linkedin-onboarding-myth
date_published: 2024-03-15
platform: linkedin
format: contrarian
pillar: product-growth

brief:
  audience: Early-stage SaaS founders
  goal: Get 3-5 DMs from founders wanting to discuss
  angle: Week 3 retention matters more than onboarding UX

production:
  iterations: 2
  final_score: 9.3/10
  time_to_complete: 52 min
  hardest_part: hook

content_snapshot:
  hook: "Onboarding is overrated."
  word_count: 312
  char_count: 1,847

performance:
  checked_at: 48h
  impressions: 14,200
  engagement_rate: 5.1%
  comments: 38
  shares: 12
  clicks: null
  goal_achieved: yes
  notes: "7 DMs, 3 converted to 30-min calls. Contrarian framing worked well."

lessons:
  what_worked: "Ultra-short hook with bold claim stopped scroll"
  what_to_change: "CTA was too soft — could have asked a more specific question"
  reuse_angle: yes
---
```

---

## Weekly Review Template

Every Friday, spend 10 minutes reviewing the week:

```markdown
## Week of YYYY-MM-DD

### Published
- [list pieces published]

### Best performer
- [piece name]: [why it worked]

### Worst performer  
- [piece name]: [what went wrong]

### Pattern spotted
- [e.g., "Contrarian posts consistently get 2x comments"]

### Next week focus
- [topic or format to try based on this week]
```

---

## Content Intelligence Queries

After 10+ entries, ask the agent:
- "What post format gets the most DMs?"
- "Which content pillar drives the most engagement?"
- "What hook style performs best on LinkedIn?"
- "What score threshold predicts good performance?"

The log becomes your data source for better briefs.
