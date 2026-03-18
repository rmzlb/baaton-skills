# Content Atomization Guide

How to break any content piece into reusable atomic units.

---

## The Concept

One piece of content contains 5-10 "atoms" — self-contained ideas that can be
extracted, recombined, and published independently on different platforms.

Think of it like cooking: a whole chicken becomes stock, pulled meat, crispy skin,
and bone broth. Same ingredient, different dishes.

---

## Step-by-Step Process

### 1. Read the source piece and highlight

Go through the content and tag every passage with its atom type:

```
[INSIGHT]   — A non-obvious observation or conclusion
[DATA]      — A specific number, stat, or measurement
[STORY]     — A personal experience or anecdote
[FRAMEWORK] — A process, system, or mental model
[OPINION]   — A strong take that not everyone agrees with
[QUOTE]     — A line that works on its own out of context
[QUESTION]  — Something that invites discussion
[EXAMPLE]   — A concrete illustration of an abstract point
```

### 2. Extract each atom into a standalone unit

For each tagged passage, write it as a standalone piece:
- Can someone understand this without reading the rest?
- Does it make a complete point?
- Would someone share/save this on its own?

If no → it's supporting material, not an atom. Attach it to the nearest atom.

### 3. Grade each atom

| Grade | Meaning | Use for |
|-------|---------|---------|
| A | Strong standalone. Could be a full post. | Tweet, email hook, carousel title |
| B | Good with light context. | Thread tweet, email body, carousel slide |
| C | Needs the original to make sense. | Supporting detail. Don't repurpose alone. |

Only repurpose A and B atoms. C atoms stay in the original.

---

## Extraction Example

**Source: LinkedIn post about engineering metrics**

> "I spent 8 months measuring the wrong thing."
→ [STORY] Grade A — Works as tweet, email subject, video hook

> "Velocity measures output, not impact. We shipped 47 features in Q3. Revenue went down."
→ [INSIGHT + DATA] Grade A — Tweet, thread hook, carousel slide

> "The metric that actually mattered: time-to-value for new users. We found it was 23 days. Should have been 3."
→ [DATA + FRAMEWORK] Grade A — Email key point, thread tweet, carousel

> "My co-founder asked 'are we measuring what customers care about or what makes us feel productive?' That question changed everything."
→ [QUOTE] Grade A — Standalone tweet, carousel slide, video hook

> "After switching to customer-outcome metrics, we cut 60% of our roadmap. Felt terrifying. Revenue went up 34% in 2 months."
→ [STORY + DATA] Grade A — Email story, LinkedIn post, video punchline

> "Most teams track what's easy to measure, not what matters."
→ [OPINION] Grade B — Tweet, but needs example for LinkedIn

> "What's the one metric that actually moves your business?"
→ [QUESTION] Grade B — LinkedIn closer, thread closer, email CTA

**Result: 7 atoms, 6 Grade A, 1 Grade B.** This source can produce:
- 1 X thread (5-6 tweets from the A atoms)
- 3 standalone tweets (the quote, the insight, the opinion)
- 1 email (story arc: problem → data → shift → result)
- 1 carousel (8 slides: hook, problem, wrong metric, right metric, data, result, takeaway, CTA)
- 1 video script (60 sec: hook with quote, story of measuring wrong, the shift, the result)

---

## Atom Recombination Rules

Different platforms need different atom combinations:

### Tweet (single)
Pick ONE atom. Grade A only. Must be complete in 270 chars.
Best atoms: [QUOTE], [OPINION], [DATA] with context.

### X Thread
Pick 5-8 atoms. Thread opener = strongest [INSIGHT] or [OPINION].
Each tweet = 1 atom. Last tweet = [QUESTION] or CTA.

### Email
Lead with [STORY] or [INSIGHT]. Support with [DATA].
Close with [QUESTION] or CTA. P.S. = bonus [DATA] or [QUOTE].

### Carousel
Lead with [INSIGHT] as title slide. Body = [FRAMEWORK] or [DATA] slides.
Each slide = 1 atom, visual format. Close with CTA slide.

### LinkedIn Post
Combine 3-4 atoms into a narrative. Hook = [STORY] or [OPINION].
Body = [DATA] + [EXAMPLE]. Close = [QUESTION].

### Video Script
Hook (3 sec) = [QUOTE] or [OPINION]. Body = [STORY] + [DATA].
Punchline = [INSIGHT]. CTA spoken naturally.

---

## Common Mistakes

**Extracting C-grade atoms**: "As I mentioned earlier in the post..." is not standalone.
Don't force it into a tweet. It needs context.

**Too many atoms from one source**: A 1,500-char LinkedIn post has 3-5 atoms max.
Don't pretend it has 10.

**Not rewriting the hook**: The LinkedIn hook doesn't work as a tweet hook.
Every atom needs a new hook for each platform.

**Copying structure**: LinkedIn uses blank-line spacing. X uses threads.
Email uses paragraphs. Carousel uses slides. Same atom, different container.

**Forgetting the anti-AI check**: Run poison word check on every repurposed version.
AI patterns can creep in during rewriting.
