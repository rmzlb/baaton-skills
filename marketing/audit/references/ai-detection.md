# AI Detection Reference

Complete reference for detecting AI-generated content patterns.
Used by the content-audit expert panel in the pre-check phase.

---

## Typography Flags

Count each instance as one flag:

| Pattern | Count |
|---------|-------|
| Em-dash (—) | 1 per instance |
| Bullet list in prose body | 1 per list |
| Bold headers mid-post | 1 per instance |
| Arrow list (→) | 1 per instance |
| Ellipsis for dramatic effect (...) | 1 if 3+ instances |
| ALL CAPS emphasis (non-title) | 1 per word |

---

## Tier 1 Poison Words (Each = 1 Flag)

Finding any Tier 1 word counts as 1 flag per unique word found.

**Category: Academic/Formal**
```
delve          dive into      tapestry       landscape
realm          embark         journey        pivotal
crucial        vital          moreover       furthermore
comprehensive  holistic       multifaceted   myriad
plethora       paramount      
```

**Category: Corporate/Buzzword**
```
robust         cutting-edge   leverage       foster
enhance        elevate        streamline     synergy
game-changer   groundbreaking innovative     transformative
impactful      utilize        facilitate     optimize
maximize       actionable     scalable       authentic
curated        bespoke        ecosystem      paradigm
unprecedented  proactive      strategic      value-add
best-in-class  disruptive     seamlessly
```

**Category: Coaching/Motivational**
```
thought leader  pain points    low-hanging fruit
unlock          empower        inspire        ignite
catalyze        nurture        cultivate      harness
```

---

## Tier 2 Caution Words (2+ unique = 1 Flag)

```
important      significant    substantial    notable
considerable   meaningful     relevant       essential
effective      efficient      powerful       valuable
unique         special        exceptional    outstanding
excellent      amazing        incredible     remarkable
```

---

## Burned Phrases (Each = 1 Flag)

```
"It's important to note that..."
"In today's digital age..."
"In today's fast-paced world..."
"Here's the kicker..."
"Navigating the complexities of..."
"A testament to..."
"Unlock the power of..."
"Unlock the secrets of..."
"The key takeaway is..."
"At the end of the day..."
"Move the needle..."
"Circle back..."
"Boils down to..."
"It goes without saying..."
"Don't get me wrong..."
"The bottom line is..."
"Let that sink in."
"This is a game-changer."
"The future is [adjective]."
"We live in a world where..."
"As we navigate..."
"It's no secret that..."
"The reality is..."
"Here's what most people don't tell you..."
"What nobody talks about..."
"Spoiler alert:"
"Here's the thing:"
"That's the power of..."
"This changes everything."
```

---

## Structural AI Patterns (Each = 1 Flag)

**Pattern 1: The It's Not/It's Format**
> "It's not about X. It's about Y."
Allowed: 1 time per post. 2+ times = flag.

**Pattern 2: Always 3-5 Bullet Points**
Every section organized into exactly 3, 4, or 5 bullets. Real people use 2 or 7.
Flag if: 3+ separate lists all have 3-5 items.

**Pattern 3: Rhetorical Q + Immediate Short Answer**
> "Why does this matter? Because [one sentence]."
Allowed: 1 time per post. 3+ times = flag.

**Pattern 4: Uniform Sentence Length**
5+ consecutive sentences all between 10-20 words. Real writing varies dramatically.

**Pattern 5: Perfect Aphorism Ending**
> "The best time to start was yesterday. The second best time is today."
Any motivational kicker ending = 1 flag.

**Pattern 6: The "Here's What I Learned" Setup**
> "Here's what I learned:" followed by a numbered list.
= 1 flag.

**Pattern 7: Repetitive Structural Cadence**
Every paragraph has the same structure: claim → example → conclusion.
Flag if this pattern repeats 3+ times.

**Pattern 8: The Numbered Learning List**
> "3 things I wish I knew before starting [thing]:"
Not inherently AI but overused. Flag if this IS the entire format.

**Pattern 9: Overly Smooth Transitions**
> "Now that we've covered X, let's talk about Y."
Real writers don't narrate their own post structure.
= 1 flag per instance.

**Pattern 10: Everything in Threes**
Every argument has exactly 3 points. Every paragraph has 3 sentences.
Real thinking is messier.

---

## Pre-Check Decision Logic

```
Count total flags from:
- Typography flags
- Tier 1 poison words (1 per unique word)
- Burned phrases (1 per phrase)
- Structural patterns (1 per pattern)

If total flags ≥ 3:
  → FAIL: Rewrite required. Do not proceed to scoring.
  → List all flags found.
  → Show which passages need fixing.

If total flags = 1-2:
  → PASS with warnings.
  → Note flags in audit report.
  → They may lower Voice & Story score.

If total flags = 0:
  → PASS clean.
  → Proceed to full scoring.
```

---

## Common False Positives

These look like AI but aren't always:

- Using "crucial" once in a very long piece — context matters
- Numbered lists that are actually useful (steps, not lazy structure)
- "At the end of the day" in dialogue/quotes — fine
- Em-dash in a title or brand name — fine

When in doubt: if it sounds like it came from a content template, flag it.

---

## Bypass Situations

Some content types have modified rules:

**Technical documentation**: Bullet lists okay, formal language okay, "utilize" acceptable
**Ad copy**: Short, structured format expected — fewer AI flags apply
**Email subject lines**: Urgency phrases are acceptable
**Landing page copy**: Marketing phrases may be necessary for context

For these formats, reduce Tier 1 penalty: only flag words that feel gratuitously corporate.
