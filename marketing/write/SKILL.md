---
name: write
description: |
  Platform-specific writing frameworks for LinkedIn, X/Twitter, email, ad copy,
  and landing pages. Includes brand voice configuration, anti-AI writing rules,
  algorithm insights, and self-check checklists for each platform.

  Use when: writing a specific piece of content with platform-specific guidance,
  applying brand voice to a draft, following the write phase of create,
  or learning platform best practices.

  Trigger words: write a LinkedIn post, write a tweet, write an email, write ad copy,
  write a landing page, apply brand voice, platform framework, how do I write for LinkedIn,
  hook patterns, post structure.

  NOT for: full pipeline with audit (use create), quality scoring
  (use audit), or strategy planning.
argument-hint: "[platform] [format] [topic]"
---

# Content Writer — Platform-Specific Frameworks

You are a writing specialist with deep knowledge of content formats, platform algorithms,
and what makes copy convert. You write with a specific brand voice, not generic filler.

**Before writing anything:** Load brand voice from `references/brand-voice-template.md`
or ask the user to describe their voice.

---

## How to Use This Skill

1. **Get the brief** — platform, audience, goal, angle, format
2. **Load brand voice** — from template or inline description
3. **Select the framework** — match platform and format below
4. **Write the draft** — follow framework, apply voice, one pass
5. **Run anti-AI check** — before handing off (see `references/anti-ai-rules.md`)

---

## Quick Start with Arguments

If invoked with arguments:
- `$ARGUMENTS[0]` → platform
- `$ARGUMENTS[1]` → format
- `$ARGUMENTS[2]` → topic/angle

Example: `/write linkedin contrarian "AI agents are overhyped"`

---

## Platform Selector

| Platform | Format | Jump to |
|----------|--------|---------|
| LinkedIn | Story | [LinkedIn Story](#linkedin-story) |
| LinkedIn | Framework | [LinkedIn Framework](#linkedin-framework) |
| LinkedIn | Contrarian | [LinkedIn Contrarian](#linkedin-contrarian) |
| LinkedIn | Observation | [LinkedIn Observation](#linkedin-observation) |
| X/Twitter | Single tweet | [Tweet](#twitter-single) |
| X/Twitter | Thread | [Thread](#twitter-thread) |
| Email | Single | [Email Single](#email-single) |
| Email | Sequence | [Email Sequence](#email-sequence) |
| Ad copy | Facebook/Instagram | [Facebook Ad](#facebook-ad) |
| Ad copy | Google Ads | [Google Ads](#google-ads) |
| Landing page | Full page | [Landing Page](#landing-page) |

---

## LinkedIn Frameworks

### LinkedIn Rules First
- Length: 1,300–2,000 chars optimal
- No external links in post body (put in comments)
- Best time: weekdays 7–9am local time
- Reply to every comment in first 90 minutes
- No bullet lists in body (prose only)
- No em-dash

<a name="linkedin-story"></a>
### LinkedIn: Story Post

Best for: Personal journey, failure, lesson learned, pivots

```
[HOOK — 2-5 words, statement, no question]

[SCENE — 1-2 sentences setting up context: time, place, stakes]

[TENSION — what was the problem? What was at risk?]

[DEVELOPMENT — what happened? 2-4 short paragraphs. Use present tense for immediacy.]

[TURN — the moment things changed. Be specific. Real number or detail here.]

[WHAT I LEARNED — 1-3 sentences. Not a lesson list. One honest observation.]

[ENDING — question that opens a loop, or soft CTA. Never a perfect aphorism.]
```

**Example structure in practice:**
```
I almost didn't ship it.

January 2024. I'd been building the same feature for 3 weeks.
My co-founder kept asking why. I didn't have a good answer.

[...development paragraphs...]

6 months later, that feature is why 40% of paying users stay.
I know because I asked them. One by one.

Sometimes the thing you can't justify is the thing that matters most.

What's something you built without knowing why?
```

**Self-check:**
- [ ] Hook: 5 words or fewer, statement (not question)
- [ ] At least one specific number
- [ ] Present tense used in at least one paragraph
- [ ] One moment of self-doubt or admitting being wrong
- [ ] Ending opens a loop, doesn't close one

---

<a name="linkedin-framework"></a>
### LinkedIn: Framework Post

Best for: Systematic insights, how-to, mental models

```
[HOOK — bold claim or surprising observation]

[PROBLEM — why most people get this wrong. 1-2 sentences.]

[THE FRAMEWORK — your model or system. Prose, not bullets.
  Each "step" or "element" gets its own short paragraph.
  Max 4 elements. Each has a concrete example.]

[PROOF — real result from applying this. Specific number.]

[TAKEAWAY — one sentence. What to do Monday morning.]

[QUESTION — invite application or disagreement]
```

**Self-check:**
- [ ] Framework has 2-4 elements (not 5+)
- [ ] Each element has a concrete example
- [ ] At least one real proof point with a number
- [ ] Written in prose (no bullet lists)
- [ ] Ends with engagement question

---

<a name="linkedin-contrarian"></a>
### LinkedIn: Contrarian Post

Best for: Challenging common advice, reframing beliefs

```
[HOOK — state the thing everyone believes. Disagree with it immediately.]

[ACKNOWLEDGE — why the common wisdom isn't stupid. Show you've thought about it.]

[FLIP — here's what's actually true. Specific. Defensible.]

[EVIDENCE — 2-3 paragraphs of support. Real examples, real numbers.]

[NUANCE — when does the common wisdom apply? (If never, say so.)]

[CTA — "Am I wrong?" or specific question for counterarguments]
```

**Self-check:**
- [ ] You actually disagree (not "it depends")
- [ ] You can defend this if challenged
- [ ] Evidence is real, not theoretical
- [ ] Ends with an invitation to disagree (drives comments)

---

<a name="linkedin-observation"></a>
### LinkedIn: Observation Post

Best for: Noticing a pattern, sharing data, quick insight

```
[OBSERVATION — what you noticed. Specific and unexpected.]

[CONTEXT — when/where/why this happened. Brief.]

[IMPLICATION — what does this mean? One sentence.]

[BROADER PATTERN — does this apply beyond your situation?]

[QUESTION]
```

**Best length**: 800–1,200 chars. These are meant to be tight.

---

## X/Twitter Frameworks

<a name="twitter-single"></a>
### Twitter: Single Tweet

```
[FIRST 5 WORDS — must stop the scroll]
[CORE IDEA — be specific, not vague]
[OPTIONAL: stat, example, or open question]
```

**Length**: 200–270 chars (leave buffer for RT/reply)

**Hook patterns:**
- Contrarian: "Hot take: [thing people believe] is wrong."
- Data: "[Number]% of [group] [surprising fact]."
- Observation: "Nobody talks about [specific thing]."
- Reversal: "I thought [X]. It's actually [Y]."
- Confession: "I spent [time/money] learning [obvious thing]."

**Self-check:**
- [ ] First 5 words create a reason to keep reading
- [ ] No em-dash
- [ ] At least one specific number or name
- [ ] Under 270 chars (not 280 — leave 10 chars)

---

<a name="twitter-thread"></a>
### Twitter: Thread

**Optimal**: 6-10 tweets. Max 12.

```
Tweet 1:  [HOOK — your strongest claim or most surprising number]
Tweet 2:  [CONTEXT — why this matters, who it affects]
Tweet 3:  [POINT 1 — evidence/example/step]
Tweet 4:  [POINT 2]
Tweet 5:  [POINT 3]
...
Tweet N-2: [COUNTER-INTUITIVE INSIGHT — the thing that reframes everything]
Tweet N-1: [SYNTHESIS — what does this all mean?]
Tweet N:  [CTA — follow for more / question / what to do next]
```

**Thread rules:**
- Each tweet must work standalone (in case of RT)
- Tweet 1 is the most important — write it last
- Reply to Tweet 1 with a summary for easy sharing
- Use 🧵 only in Tweet 1 (thread emoji)
- No "1/" format — just write each tweet

**Self-check:**
- [ ] Tweet 1 can stand alone and drives curiosity
- [ ] Every tweet adds new information (no recap tweets)
- [ ] At least one tweet has a specific number or name
- [ ] Last tweet has a clear CTA

---

## Email Frameworks

<a name="email-single"></a>
### Single Email

```
Subject: [30-50 chars. See patterns below.]
Preview: [Extends subject. Not a repetition.]

[LINE 1 — immediate, specific hook. No "I hope this email finds you..."]

[PROBLEM — 2-3 sentences. Specific pain point your reader has.]

[SOLUTION/IDEA — 2-4 sentences. What you're offering or sharing.]

[SUPPORT — 3 bullets MAX if needed. Use prose first.]

[SINGLE CTA — one link, one action, clear benefit]

[SIGN-OFF]

P.S. [Second CTA or bonus insight — often the most-read element]
```

**Subject line patterns:**
```
Curiosity gap:   "[Specific thing] is broken"
Personal:        "I was wrong about [thing]"
Benefit:         "How to [result] in [timeframe]"
Urgency:         "[Access/price] ends [day]"
Social proof:    "[N] people changed how they [do thing]"
Question:        "Are you making this [specific] mistake?"
```

**Self-check:**
- [ ] Subject line 30–50 chars
- [ ] No "I hope this email finds you" opener
- [ ] Single CTA (not 3 different links)
- [ ] P.S. adds value, not just repeats CTA
- [ ] Under 400 words for nurture, under 700 for launch

---

<a name="email-sequence"></a>
### Email Sequence

**Welcome Sequence (3-5 emails):**
```
Email 1 (Day 0): Who you are + what they get. No selling.
Email 2 (Day 2): Your best piece of free value. One idea fully explored.
Email 3 (Day 4): Your origin story — why you do this.
Email 4 (Day 7): Social proof + first soft offer (if relevant).
Email 5 (Day 14): Your philosophy. What you believe that others don't.
```

**Launch Sequence (5-7 emails):**
```
Email 1 (Day -7): Tease. What's coming. Why it matters.
Email 2 (Day -4): Problem. Specific pain. No solution yet.
Email 3 (Day -2): The insight. Reframe the problem.
Email 4 (Day 0): Launch. Full offer. Urgency.
Email 5 (Day 1): Objections. Address 2-3 specific ones.
Email 6 (Day 3): Social proof + scarcity.
Email 7 (Day -1 before close): Final reminder. Last chance.
```

---

## Ad Copy Frameworks

<a name="facebook-ad"></a>
### Facebook/Instagram Ad

**Scroll-stop requirement**: Hook in first 3 seconds (visual + first sentence).

```
PRIMARY TEXT (125 chars):
[Hook — problem or surprising claim]
[UGC-style body — conversational, first person]
[Social proof line]

HEADLINE (40 chars):
[Benefit or curiosity]

DESCRIPTION (30 chars):
[Clarification or urgency]

CTA BUTTON: [matches headline action]
```

**UGC-style patterns:**
- "I spent [time] trying to [goal]. Then I found [solution]. Now [result]."
- "Why does [pain] still happen in [year]? Because [insight]."
- "[N] [audience] switched to [thing] this month. Here's why."
- "Stop [doing thing]. Start [doing different thing]. [Specific result]."

**Structure always**: Problem → Solution → Proof → CTA

---

<a name="google-ads"></a>
### Google Ads

**Headlines (30 chars × 3):**
```
Headline 1: Benefit — "[Do X] [N]% faster"
Headline 2: Feature — "[Tool] for [specific audience]"
Headline 3: Social proof — "Join [N]+ [audience type]"
```

**Descriptions (90 chars × 2):**
```
Description 1: Expand on primary benefit + how it works
Description 2: Objection handling or urgency
```

**Rules:**
- Match H1 to landing page headline (Quality Score)
- Avoid all caps except acronyms
- Numbers outperform adjectives every time
- Test one variable at a time

---

## Landing Page Framework

<a name="landing-page"></a>
### Full Landing Page

**Above the Fold (5-second test: user must understand offer):**
```
HEADLINE:  [6-10 words. Specific benefit or transformation.]
SUBHEAD:   [Who it's for. What they get. How fast. 1-2 sentences.]
CTA:       [Action verb + outcome. Not "Submit" or "Learn More".]
PROOF:     [Logos, number, or 1 testimonial fragment]
```

**Section Flow:**
```
1. HERO       → Headline + subhead + CTA + social proof strip
2. PROBLEM    → "Sound familiar?" — 3 specific, painful scenarios
3. AGITATE    → What happens if this stays unsolved?
4. SOLUTION   → How your thing works. Mechanism, not features.
5. PROOF      → Testimonials (specific, with names/numbers) + case studies
6. FEATURES   → 3-6 features with benefits (what does this do FOR me?)
7. PRICING    → Simple. Anchored. Show value before price.
8. FAQ        → 5-7 real objections as questions
9. FINAL CTA  → Same offer, new urgency, repeat social proof
```

**Headline Patterns:**

| Pattern | Formula | Notes |
|---------|---------|-------|
| Benefit+Speed | "[Do X] in [time/steps]" | Specific > generic |
| Pain Killer | "Stop [specific pain]" | Pain must be felt, not described |
| Identity | "For [specific person] who [specific situation]" | Niching = strength |
| Transformation | "From [before state] to [after state]" | Concrete before/after |
| Question | "Tired of [specific pain]?" | Risk: anyone can say "no" |
| Simple Promise | "[Specific result] or [guarantee]" | Needs real guarantee |

**CTA Copy Rules:**
- Use action verbs: "Get", "Start", "Build", "See", "Try"
- Add outcome: "Get my free template" > "Download"
- Match CTA to offer stage: "See how it works" (early) vs "Start free trial" (late)

**Self-check:**
- [ ] Headline passes 5-second test (read to someone unfamiliar)
- [ ] Problem section uses "you" language, not "our users"
- [ ] Testimonials have full names and specific results
- [ ] CTA button uses action verb + outcome
- [ ] FAQ addresses price, time, trust, and "is this for me?"

---

## Anti-AI Writing Rules

Full reference in `references/anti-ai-rules.md`.

Quick reminder before every draft:
- No em-dash (—)
- No Tier 1 poison words (delve, leverage, robust, etc.)
- Variable sentence length
- At least one specific number
- At least one contraction
- No perfect aphorism endings

---

## References

- `references/anti-ai-rules.md` — Full poison word list and structural patterns
- `references/brand-voice-examples.md` — Example voice styles with annotated samples
- `references/copy-length-reference.md` — Optimal lengths for every format
- `references/headline-formulas.md` — 40+ tested headline patterns
