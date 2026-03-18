---
name: repurpose
description: |
  Transform one piece of content into multiple platform-optimized formats.
  1-to-N content multiplication: LinkedIn post to X thread, email, carousel,
  video script, and more. Includes platform adaptation rules, not just reformatting.
  Use when: repurposing a post for other platforms, maximizing content ROI,
  creating a content series from one idea, or building a multi-channel campaign.
  Trigger words: repurpose, transform, adapt, cross-post, multi-platform,
  content multiplication, 1-to-N, carousel, thread from post, atomize.
  NOT for: writing original content (use write), quality scoring
  (use audit), or strategic planning (use strategy).
argument-hint: "[source-platform] [content-or-file-path]"
---

# Content Repurpose

Turn 1 piece of content into 5-8 platform-optimized versions.
Not reformatting. Real adaptation: different hooks, different tone,
different structure, different CTA — same core insight.

## How It Works

Input: $ARGUMENTS (source platform + content text or file path)

If no arguments, ask: "Paste the content and tell me where it was originally published."

### Process:
1. **Atomize** — Break the source into atomic content units
2. **Select** — Choose which atoms work for each target platform
3. **Adapt** — Rewrite for each platform's rules (not just shorten)
4. **Audit** — Run anti-AI check on each version
5. **Schedule** — Stagger publishing for maximum reach

## Step 1: Atomize the Source

Break any content piece into these atomic units:

| Atom type | What it is | Example |
|-----------|-----------|---------|
| Key insight | The core idea in 1 sentence | "Author replies in first 90 min decide reach" |
| Supporting data | A number or stat that proves it | "94% weekly active rate across 200+ teams" |
| Personal story | A specific moment or experience | "January 15th. 23 users. I almost quit." |
| Framework | A process or mental model | "Brief → Write → Audit → Iterate → Ship" |
| Contrarian take | What you disagree with + why | "'Post every day' advice is wrong for 94% of people" |
| Quotable line | A line that stands alone | "I rewrote our database layer. Introduced 4 new bugs." |
| Question | An open question for engagement | "What's the last thing you built that you weren't sure about?" |
| CTA | The action you want | "Try this framework on your next post" |

For detailed atomization process, see `references/atomization-guide.md`.

## Step 2: Transformation Rules

Each source → target pair has specific rules. Don't copy-paste and trim.

### LinkedIn Post → Other Formats

| Target | Keep | Change | Length |
|--------|------|--------|--------|
| X Thread | Insight, data, story | Shorter hook. No blank lines. Add thread opener. | 5-10 tweets, 200-270 chars each |
| Single Tweet | Best quotable line OR contrarian take | Must stand alone. No context needed. | 200-270 chars |
| Email | Story + insight + CTA | More personal. Add P.S. Subject line from hook. | 150-300 words |
| Carousel | Framework atoms, step-by-step | 1 idea per slide. 30-50 words/slide. Visual. | 8-12 slides |
| Short video script | Story + 1 key insight | Conversational, present tense. Hook in 3 sec. | 60-90 seconds |

### Blog Post → Other Formats

| Target | Keep | Change | Length |
|--------|------|--------|--------|
| LinkedIn series | Break into 3-5 standalone posts | Each needs its own hook. | 1,300-2,000 chars each |
| X Thread | Key framework + data | Compress. 1 tweet per section. | 6-12 tweets |
| Email sequence | Each section = 1 email | Personal context. Standalone value each. | 3-5 emails, 200-300 words |
| Social quotes | Quotable lines as graphics | Pull 5-8 standalone sentences. | 10-20 words each |

For complete transformation matrix, see `references/transformation-matrix.md`.

## Step 3: Platform Adaptation

This is where repurposing fails or succeeds.

### Tone Shifts

| Platform | Tone | What changes |
|----------|------|-------------|
| LinkedIn | Professional-personal. Builder sharing lessons. | More context. Complete thoughts. Self-deprecation plays well. |
| X/Twitter | Sharp, direct, opinionated. | Less context. Stronger opinions. Hot takes welcome. |
| Email | Personal, 1-on-1 conversation. | "I" and "you" heavy. Feels like writing to a friend. |
| Carousel | Visual, scannable, bite-sized. | One idea per card. Bold text on simple backgrounds. |
| Video | Conversational, immediate, casual. | Talk like telling a friend. No corporate tone. |

### Hook Rewriting

Same content, different hooks per platform:

**Original LinkedIn hook:** "I almost didn't ship it."

- **X/Twitter:** "Shipped a feature nobody asked for. It became 40% of our revenue."
- **Email subject:** "The feature I was embarrassed to ship"
- **Carousel slide 1:** "THE FEATURE NOBODY ASKED FOR (that drove 40% of revenue)"
- **Video first 3 sec:** "I built something my co-founder said was a waste of time."

For detailed adaptation rules, see `references/platform-adaptation.md`.

## Step 4: Quick Audit

Before publishing each repurposed version:

```
REPURPOSE AUDIT (30 seconds per piece)
[ ] Hook is REWRITTEN for this platform (not copied from original)
[ ] Length fits platform optimal range
[ ] Tone matches platform norms
[ ] Standalone value (doesn't need the original to make sense)
[ ] CTA is platform-appropriate
[ ] No cross-platform artifacts ("as I said in my LinkedIn post")
[ ] Anti-AI check: no poison words, no em-dashes, no template patterns
```

For high-stakes pieces, run full `audit` scoring (9.0/10 minimum).

## Step 5: Publishing Schedule

Don't publish everything at once. Stagger for reach.

### Default Schedule (LinkedIn source):
```
Day 0: LinkedIn original (primary)
Day 1: X thread (different audience)
Day 2: Single tweet (best quote from the thread)
Day 3: Email to list (personal angle added)
Day 5: Carousel (visual summary on LinkedIn)
Day 7: Repurposed angle (new hook, same insight, LinkedIn)
```

For more schedules + rationale, see `references/scheduling-templates.md`.

## Common Workflows

### Weekly Content Sprint
1. Write 1 LinkedIn post (create)
2. Repurpose → X thread + email + 2 tweets
3. Result: 5 pieces from 1 writing session

### Blog-to-Social Series
1. Write 1 blog post (2,000 words)
2. Repurpose → 4 LinkedIn + 2 X threads + 5-email sequence
3. Result: 11 pieces across 3 weeks

### Video Content Cascade
1. Record 1 video/podcast (30 min)
2. Transcribe, extract key moments
3. Repurpose → blog + 3 LinkedIn + 5 tweets + 2 emails + 3 clips
4. Result: 14 pieces from 1 recording

## References

- `references/transformation-matrix.md` — Complete source × target rules
- `references/platform-adaptation.md` — Deep platform-specific adaptation
- `references/atomization-guide.md` — Breaking content into reusable atoms
- `references/scheduling-templates.md` — Publishing schedules with rationale

## Related Skills

- `create/` — Create the original content piece
- `audit/` — Score repurposed versions before publishing
- `write/` — Platform writing rules for each version
- `measure/` — Track which repurposed format performs best
