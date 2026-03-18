---
name: measure
description: |
  Marketing measurement, reporting, and iteration frameworks. Metrics by platform,
  attribution models, content performance analysis, A/B testing, and reporting templates.
  Use when: analyzing content performance, building reports, deciding what to post next,
  setting up tracking, A/B testing content, or reviewing marketing ROI.
  Trigger words: analytics, metrics, performance, report, ROI, conversion, A/B test,
  what's working, engagement rate, attribution, funnel analysis, dashboard.
  NOT for: writing content (use write), auditing quality (use audit),
  or defining strategy (use strategy).
argument-hint: "[action: report|analyze|test|benchmark] [platform]"
---

# Marketing Analytics

Measure what matters. Ignore what doesn't. Iterate based on data.

## How to Use

Action from arguments: $ARGUMENTS

| Action | What it does |
|--------|-------------|
| `report` | Generate weekly/monthly/quarterly report |
| `analyze` | Deep-dive on content performance |
| `test` | Design an A/B test |
| `benchmark` | Compare your metrics against industry benchmarks |

If no action specified, ask what the user needs.

## The Feedback Loop

This is the entire point of analytics:

```
Analyze → Hypothesize → Test → Measure → Iterate → Analyze
```

Every report should end with: "Based on this data, here's what we should try next."
If a report doesn't lead to action, it's a vanity exercise.

## Metrics by Platform

### LinkedIn
| Metric | What it tells you | Good | Average | Poor |
|--------|------------------|------|---------|------|
| Impressions | Reach of your content | >5K (small account) | 1-5K | <1K |
| Engagement rate | Content resonance | >5% | 2-5% | <2% |
| Comments | Depth of engagement | >20 | 5-20 | <5 |
| DMs received | Conversion signal | >3/post | 1-2 | 0 |
| Profile views | Curiosity generated | >200/week | 50-200 | <50 |
| Follower growth | Audience building | >50/week | 10-50 | <10 |

### X/Twitter
| Metric | What it tells you | Good | Average | Poor |
|--------|------------------|------|---------|------|
| Impressions | Reach | >10K | 2-10K | <2K |
| Engagements | Interaction rate | >3% | 1-3% | <1% |
| Bookmarks | Save-worthy signal | >50 | 10-50 | <10 |
| Quote RTs | Amplification | >5 | 1-5 | 0 |
| Profile clicks | Curiosity | >100 | 20-100 | <20 |
| New followers | Growth from content | >10/tweet | 2-10 | <2 |

### Email
| Metric | What it tells you | Good | Average | Poor |
|--------|------------------|------|---------|------|
| Open rate | Subject line + sender trust | >35% | 20-35% | <20% |
| Click rate | Content relevance | >5% | 2-5% | <2% |
| Reply rate | Personal connection | >2% | 0.5-2% | <0.5% |
| Unsubscribe | Content-audience mismatch | <0.3% | 0.3-0.5% | >0.5% |
| Forward rate | Share-worthy | >1% | 0.2-1% | <0.2% |

### Ads (Facebook/Google)
| Metric | What it tells you | Good | Average | Poor |
|--------|------------------|------|---------|------|
| CTR | Ad relevance | >2% | 0.8-2% | <0.8% |
| CPC | Cost efficiency | <$1.50 | $1.50-$4 | >$4 |
| CPA | Acquisition cost | <$30 | $30-$80 | >$80 |
| ROAS | Return on ad spend | >3x | 1.5-3x | <1.5x |
| Frequency | Ad fatigue | <3 | 3-5 | >5 |

For full metrics glossary with formulas, see `references/metrics-reference.md`.

**Benchmarks vary by audience size, industry, and stage.** See `references/benchmarks.md`.

## Vanity Metrics vs Actionable Metrics

| Vanity (feels good) | Actionable (drives decisions) |
|---------------------|------------------------------|
| Follower count | Follower growth rate per content piece |
| Total impressions | Impressions-to-engagement conversion |
| Page views | Time on page + scroll depth |
| Email list size | Email-to-revenue attribution |
| "Likes" | Comments + DMs + saves (deep engagement) |

**Rule: if a metric doesn't change what you do next, stop tracking it.**

## Attribution

How did a customer find you? Four models:

| Model | How it works | Best for |
|-------|-------------|----------|
| First-touch | Credit goes to first interaction | Understanding discovery channels |
| Last-touch | Credit goes to last interaction before conversion | Understanding what closes |
| Multi-touch | Credit split across all touchpoints | Complex B2B journeys |
| Self-reported | Ask "how did you hear about us?" | The truth (often different from data) |

**Recommendation:** Use self-reported attribution as your primary signal.
Add a "How did you hear about us?" field to signup/checkout. The answers
will surprise you. Data attribution misses dark social (DMs, word of mouth, podcasts).

## A/B Testing for Content

Most content marketers don't A/B test because they think they need
huge sample sizes. You don't.

### What to Test (ordered by impact)

1. **Hook/headline** — Biggest impact on reach and engagement
2. **CTA type** — Question vs. direct ask vs. none
3. **Format** — Story vs. framework vs. contrarian
4. **Posting time** — Morning vs. evening, weekday vs. weekend
5. **Length** — Short (800 chars) vs. long (2,000 chars)
6. **Platform** — Same content, different platforms (via repurpose)

### How to Test with Small Audiences

You don't need statistical significance for content decisions:

1. Test for 5-10 posts (not 1 post vs 1 post)
2. Compare the same metric across the set
3. If one approach beats the other 7 out of 10 times, it's a signal
4. Act on the signal. If you're wrong, you'll see it in the next 10.

For detailed testing guide, see `references/ab-testing-guide.md`.

## Reporting Templates

### Weekly (5 min, every Monday)
```
This week's content:
- [List pieces published]
- Best performer: [which + why]
- Worst performer: [which + why]
- One pattern noticed: [observation]
- Next week's plan: [based on this week's data]
```

### Monthly (30 min, first Monday of month)
```
Monthly metrics:
- Content published: [count by platform]
- Total reach: [impressions across platforms]
- Engagement: [rate by platform, trend vs last month]
- Conversions: [DMs, signups, sales attributed to content]
- Best content piece: [which + analysis of why]
- Worst content piece: [which + what to learn]
- Audience growth: [by platform, trend]
- Content pillar performance: [which pillar drives results]
- Hypothesis for next month: [what to test]
```

### Quarterly (2 hours, every 3 months)
```
Strategic review:
- ICP still accurate? [validate against new customer data]
- Messaging still resonating? [top-performing language vs flops]
- Channel allocation: [which channels drive conversions, cut losers]
- Content format ROI: [which formats justify the time invested]
- Competitor moves: [anything changed in the landscape?]
- Budget reallocation: [shift spend to what works]
- Strategy update: [feed insights back to strategy]
```

For detailed report templates with examples, see `references/reporting-templates.md`.

## Content Performance Queries

Ask these with your content log data:

- "What are my top 5 posts by engagement rate this month?"
- "Which content pillar drives the most DMs?"
- "What hook style gets the highest engagement?"
- "Compare story posts vs framework posts on LinkedIn"
- "What's my best posting time based on the last 20 posts?"
- "Which repurposed format outperforms the original?"

For ready-to-use analysis prompts, see `references/content-performance-queries.md`.

## References

- `references/metrics-reference.md` — Full metrics glossary with formulas
- `references/reporting-templates.md` — Detailed report templates with filled examples
- `references/ab-testing-guide.md` — Practical A/B testing guide
- `references/content-performance-queries.md` — Analysis prompts for your content log
- `references/benchmarks.md` — Industry benchmarks by platform and audience size

## Related Skills

- `strategy/` — Feed quarterly insights back into strategy
- `create/` — Use performance data to write better briefs
- `repurpose/` — Track which repurposed format performs best
- `audit/` — Correlate audit scores with actual performance
