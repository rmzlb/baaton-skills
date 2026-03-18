# Competitive Analysis Templates

## Research Methodology

### Where to Find Competitor Intelligence

| Source | What you learn | Time |
|--------|---------------|------|
| Their website + pricing page | Positioning, target market, pricing model | 15 min |
| G2/Capterra reviews (sort by 1-star) | Real pain points, what users hate | 30 min |
| Their job postings | What they're building next, team priorities | 10 min |
| Their blog/social content | Messaging angles, content strategy, topics they own | 20 min |
| Their changelog/release notes | Product velocity, feature priorities | 10 min |
| Customer interviews ("what else did you consider?") | How buyers compare you, decision criteria | 30 min each |
| Crunchbase/PitchBook | Funding, growth trajectory, runway | 5 min |
| BuiltWith/Wappalyzer | Tech stack, integrations, scale signals | 5 min |

### 5-Competitor Deep Dive Process

1. Pick 3 direct competitors + 2 indirect (or status quo alternatives)
2. For each, fill the competitor profile template below
3. Build the feature matrix
4. Draw the positioning map
5. Run the messaging gap analysis
6. Write your competitive advantage summary

---

## Competitor Profile Template

```yaml
competitor:
  name: "[Company name]"
  category: "[direct / indirect / status-quo]"
  website: "[URL]"
  
  positioning:
    tagline: "[Their homepage headline]"
    target_market: "[Who they claim to serve]"
    key_claim: "[Their #1 differentiator]"
    pricing: "[Model + price range]"
  
  strengths:
    - "[What they do well]"
    - "[What customers praise in reviews]"
  
  weaknesses:
    - "[What customers complain about]"
    - "[What they're missing]"
    - "[Where their product breaks down]"
  
  messaging_angles:
    - "[Theme 1 they push in content]"
    - "[Theme 2]"
  
  recent_moves:
    - "[Last 6 months: new features, funding, pivots]"
  
  threat_level: "[low / medium / high]"
  your_advantage: "[Why you beat them for your ICP]"
```

---

## Feature Matrix

Compare what matters to your ICP. Not every feature — just the ones that drive buying decisions.

```
Feature              │ You    │ Comp A │ Comp B │ Comp C │ Status Quo
─────────────────────┼────────┼────────┼────────┼────────┼───────────
[Key feature 1]      │ ✅ Yes │ ✅ Yes │ ❌ No  │ ⚠️ Partial │ ❌ No
[Key feature 2]      │ ✅ Yes │ ❌ No  │ ✅ Yes │ ❌ No  │ ❌ No
[Key feature 3]      │ ✅ Yes │ ⚠️ Partial │ ❌ No │ ✅ Yes │ ⚠️ Manual
...
─────────────────────┼────────┼────────┼────────┼────────┼───────────
Pricing (per seat)   │ $12    │ $15    │ $8     │ $20    │ $0 + time
Setup time           │ 5 min  │ 30 min │ 10 min │ 2 hours│ N/A
```

**Rules:**
- Only include features your ICP actually cares about (from decision criteria in personas)
- Be honest: if a competitor is better, mark it
- Include "status quo" column — your real competitor is often inaction
- Weight the features: not all rows are equal

---

## Positioning Map (2x2)

Pick two axes that matter most to your ICP. Plot competitors.

```
                    High [Axis 2]
                         │
           Quadrant 2    │    Quadrant 1
           (Comp B)      │    (YOU)
                         │
   Low [Axis 1] ────────┼──────── High [Axis 1]
                         │
           Quadrant 3    │    Quadrant 4
           (Status quo)  │    (Comp A)
                         │
                    Low [Axis 2]
```

**Good axis pairs:**
- Ease of use × Depth of features
- Price × Customization
- Speed to value × Scalability
- Technical depth × Business user friendliness

**Example (TaskPilot):**
- Axis 1: GitHub integration depth (low → high)
- Axis 2: Leadership reporting quality (low → high)
- TaskPilot: top-right (deep GitHub + great reports)
- Linear: middle-right (decent GitHub, basic reports)
- Jira: bottom-left (poor GitHub, configurable but complex reports)
- GitHub Projects: top-left (native GitHub, no real reporting)

**Your goal: own a quadrant where no competitor sits.**

---

## Messaging Gap Analysis

What are competitors NOT saying? That's your opening.

| Angle | Comp A | Comp B | Comp C | Opportunity |
|-------|--------|--------|--------|-------------|
| [Topic 1] | Talks about it | Silent | Silent | Low — Comp A owns it |
| [Topic 2] | Silent | Mentions it | Silent | Medium — under-covered |
| [Topic 3] | Silent | Silent | Silent | HIGH — nobody owns this |
| [Topic 4] | Weak take | Weak take | Silent | HIGH — you can own it with stronger POV |

**How to find gaps:**
1. Read competitors' last 20 blog posts / social posts
2. List every topic/angle they cover
3. Cross-reference with what your ICP cares about (from persona research)
4. Gaps = topics your ICP cares about that nobody is addressing

Feed these gaps into `content-engine` as content briefs.

---

## Marketing SWOT

Not the generic SWOT. This is positioning-specific.

```
STRENGTHS (internal + real)          │ WEAKNESSES (internal + honest)
What you do better than anyone       │ Where competitors beat you
─────────────────────────────────────┼─────────────────────────────────
- [Your unique attribute #1]         │ - [Where you're weaker]
- [Your unique attribute #2]         │ - [Feature gap]
- [Your team's unfair advantage]     │ - [Brand awareness deficit]
                                     │
OPPORTUNITIES (external)             │ THREATS (external)
Market gaps you can exploit          │ External risks to your position
─────────────────────────────────────┼─────────────────────────────────
- [Messaging gap nobody owns]        │ - [Competitor raising $50M]
- [Market trend favoring you]        │ - [Platform risk if GitHub changes]
- [Competitor weakness you can hit]  │ - [New entrant from adjacent market]
```

**Action from SWOT:**
- Strengths → Double down in messaging
- Weaknesses → Mitigate in FAQ / objection handling
- Opportunities → Turn into content briefs
- Threats → Monitor quarterly, build contingency positioning
