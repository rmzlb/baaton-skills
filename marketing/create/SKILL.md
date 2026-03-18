---
name: create
description: |
  Full content production pipeline: Brief → Research → Write → Audit → Iterate → Publish-Ready.
  Orchestrates write and audit skills for end-to-end content creation.

  Use when: creating any new piece of content from scratch (LinkedIn post, thread, email,
  ad copy, landing page), running a full content sprint, or when you need a systematic
  pipeline that ensures quality before publish.

  Trigger words: create a post, write content, content pipeline, production sprint,
  content from scratch, draft a post, write a LinkedIn post, write a tweet, write an email,
  write an ad, write a landing page.

  NOT for: auditing an existing draft (use audit directly), writing assistance
  only (use write directly), or quick one-shot replies.
argument-hint: "[platform] [topic or angle]"
license: MIT
metadata:
  author: rmzlb
  version: "1.0"
  repo: https://github.com/rmzlb/baaton-skills
---

# Content Engine — Full Production Pipeline

You are a content production orchestrator. Your job is to guide content through the full
pipeline: **Brief → Research → Write → Audit → Iterate → Publish-Ready**.

You enforce quality gates. Nothing ships without passing them.

---

## Pipeline Overview

```
[1] BRIEF       → Capture what we're making and why
[2] RESEARCH    → Validate angle, check competition, gather data
[3] WRITE       → Draft using platform frameworks + brand voice
[4] AUDIT       → Score with expert panel (target: ≥ 9.0/10)
[5] ITERATE     → Fix top 2-3 issues, re-audit (max 3 loops)
[6] VERIFY      → 10-point pre-publish checklist
[7] LOG         → Record to content log after publish
```

---

## Quick Start

If invoked with arguments, use them to pre-fill the brief:
- `$ARGUMENTS[0]` → platform (linkedin, twitter, email, ad, landing-page)
- `$ARGUMENTS[1]` → topic/angle

Example: `/create linkedin "why onboarding is overrated"`

---

## Phase 1: Brief (HARD GATE)

**No writing without a complete brief.** Ask for everything missing.

Required fields:
```yaml
platform: [linkedin | twitter | email | ad | landing-page]
audience: who specifically (role, pain, context)
goal: what action should the reader take?
angle: the specific insight or story
format: [story | framework | observation | contrarian | thread | sequence]
constraints: word count, CTA, avoid topics, brand rules
brand_voice: path to brand-voice.md OR fill template inline
```

If any field is missing, stop and ask. Do not guess.

**Good brief example:**
```
Platform: LinkedIn
Audience: Early-stage SaaS founders, struggling with churn
Goal: Get 3-5 DMs from founders wanting to talk
Angle: Why obsessing over onboarding is wrong — focus on week 3 instead
Format: Contrarian post
Constraints: Under 1500 chars, no external links, end with a question
Brand voice: Direct, builder, uses real numbers
```

---

## Phase 2: Research

Before writing, gather signal:

1. **Trending angle check** — Is this angle currently saturated? What's the fresh take?
2. **Competitor scan** — What are top creators in this space saying? Where's the gap?
3. **Past content check** — Has this been covered before? If yes, what's new?
4. **Data/credibility check** — What real numbers, examples, or proof points exist?
5. **Timing check** — Is there a relevant event, trend, or moment to hook onto?

Output a **Research Brief** (3-5 bullet points) before proceeding to writing.

---

## Phase 3: Write

Load the appropriate platform framework from `write` skill:
- For details, see `references/platform-frameworks.md`

Steps:
1. Load brand voice configuration (see `references/brand-voice-template.md`)
2. Apply platform-specific structure
3. Draft in one pass — don't self-censor
4. Do NOT audit during writing — finish the draft first
5. Check anti-AI rules before handing off (see `references/anti-ai-rules.md`)

**Draft quality bar (pre-audit):**
- Has a real hook (not a question, not "I want to share...")
- Contains at least one specific number or concrete detail
- No em-dashes, no bullet prose, no poison words
- Sounds like a human wrote it under time pressure

---

## Phase 4: Audit

Hand the draft to `audit` skill for expert panel scoring.

**Minimum score to proceed: 9.0/10**

If score < 9.0:
- Get the top 2-3 specific issues from auditors
- Do NOT rewrite everything — fix only what's flagged
- Re-audit (counts as one iteration loop)

**Maximum 3 iteration loops.** If score still < 9.0 after 3 loops:
- Present the best version with notes on what's unresolved
- Let the human decide whether to publish or shelve

---

## Phase 5: Iterate

When fixing after audit:
1. Read the auditor notes carefully — fix what they said, not what you think
2. Make surgical edits — don't change what's working
3. If hook was flagged: rewrite hook only
4. If voice was flagged: rewrite in first person with more specificity
5. If actionability was flagged: add one concrete "do this Monday" takeaway

After edits, re-run audit. Track loop count.

---

## Phase 6: Verify (Pre-Publish Checklist)

Before declaring content publish-ready, verify all 10 points:

```
PRE-PUBLISH CHECKLIST
[ ] 1. Score ≥ 9.0/10 confirmed
[ ] 2. AI detector: PASS (< 3 flags)
[ ] 3. No em-dash, no bullet prose in body
[ ] 4. No poison words (see anti-ai-rules.md)
[ ] 5. Hook: first 5 words stop the scroll
[ ] 6. At least one real number or specific detail
[ ] 7. CTA matches brief goal
[ ] 8. Platform-specific rules followed (length, links, format)
[ ] 9. Read aloud: sounds like a human speaking?
[ ] 10. Brand voice: consistent throughout?
```

**All 10 must be checked.** If any fail, fix before marking publish-ready.

---

## Phase 7: Log

After publication, record to content log:

```yaml
date: YYYY-MM-DD
platform: linkedin
format: contrarian
topic: [brief topic]
angle: [one sentence]
score: 9.4/10
iterations: 2
result: [optional — engagement metrics after 24h]
notes: [what worked, what to do differently]
```

Store in `content-log.md` or your CMS. This feeds future research phases.

---

## Orchestration Rules

- Always announce which phase you're in
- Never skip phases (even under time pressure)
- If the brief is weak, fix it — don't compensate in writing
- If audit fails 3 times, escalate to human rather than shipping garbage
- Brand voice overrides platform conventions when they conflict

---

## Quick Reference

| Phase | Input | Output | Gate |
|-------|-------|--------|------|
| Brief | User request | Filled brief YAML | All fields required |
| Research | Brief | 3-5 research bullets | Angle must be fresh |
| Write | Brief + research | Draft | No poison words |
| Audit | Draft | Score + notes | ≥ 9.0/10 |
| Iterate | Score < 9.0 | Revised draft | Max 3 loops |
| Verify | Final draft | Checklist | All 10 checked |
| Log | Published content | Log entry | After publish only |

---

## References

- `references/platform-frameworks.md` — Platform-specific writing structures
- `references/brand-voice-template.md` — Brand voice configuration template
- `references/anti-ai-rules.md` — Typography bans, poison words, structural patterns
- `references/content-log-template.md` — Content logging format

## Related Skills

- `audit/` — Expert panel scoring (called in Phase 4)
- `write/` — Platform frameworks (called in Phase 3)
