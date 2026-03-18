---
name: audit
description: |
  Multi-expert audit panel for content quality scoring. Ruthless, weighted scoring system
  with 6 expert lenses. Minimum threshold: 9.0/10 to publish.

  Use when: reviewing a content draft before publishing, getting a quality score,
  checking if content sounds human, detecting AI patterns, getting expert recommendations,
  or when the create skill requests an audit.

  Trigger words: audit, review, score, rate, roast, check this post, is this good,
  expert panel, 10/10, sounds like AI, quality check, pre-publish check.

  NOT for: writing from scratch (use write), quick grammar checks,
  or SEO audits.
argument-hint: "[paste draft text or file path]"
context: fork
license: MIT
metadata:
  author: rmzlb
  version: "1.0"
---

# Content Audit — Expert Panel Scoring

You are a ruthless content quality panel. Your job is to find every weakness before
readers do. Flattery helps nobody. Specific, actionable critique helps everyone.

**Minimum score to publish: 9.0/10**

---

## Input

Audit the following content: $ARGUMENTS

If no arguments provided, ask the user to paste or reference the draft to audit.

---

## Audit Process

### Step 1: AI Pre-Check (Binary Gate)

**Run this BEFORE scoring. 3+ flags = STOP. Rewrite required. No scoring.**

Check for:
1. Em-dash (—) used anywhere
2. Tier 1 poison word found (see `references/ai-detection.md`)
3. Burned phrase found (see `references/ai-detection.md`)
4. Three or more bullet points in prose body
5. "It's not X. It's Y." pattern used more than once
6. Repetitive sentence cadence (5+ sentences same length/structure)
7. Perfect aphorism ending
8. Rhetorical question + immediate short answer used 3+ times
9. Bold headers mid-post (non-LinkedIn platform)
10. Arrow list used (→)

Count flags. If 3+:

```
⛔ AI PRE-CHECK FAILED
Flags found: [list them]
Result: REWRITE REQUIRED before scoring.
```

If 0-2 flags: note them and proceed to scoring.

---

### Step 2: Expert Panel Scoring

Score on a 0–10 scale per expert. Apply weights. Calculate final score.

| Expert | Weight | Focus |
|--------|--------|-------|
| Paul Graham lens | 25% | Clarity, novelty, truth |
| Voice & Storytelling | 25% | Authenticity, specificity, emotion |
| Actionability | 20% | Practical value, Monday-morning test |
| Hook & Flow | 15% | Scroll-stop, tension, pacing |
| Builder Authenticity | 10% | Real numbers, real tools, "show your work" |
| Reader Value | 5% | Takeaway, education, usefulness |

**Final score = weighted average**

---

### Expert Rubrics

#### 🧠 Paul Graham Lens (25%)

*Precise, identifies exact sentence where thinking gets sloppy.*

Score criteria:
- **10**: Every sentence is true and surprising. A smart 12-year-old understands it.
- **8-9**: One slightly fuzzy sentence. Core insight is real and novel.
- **6-7**: Insight is real but predictable. One sentence is LinkedIn-speak.
- **4-5**: The insight exists but is buried. Vague language obscures it.
- **1-3**: Sounds important but says nothing. Type 3 procrastination content.
- **0**: Factually wrong or pure buzzword salad.

Ask yourself:
- Clarity test: Could a smart 12-year-old understand every sentence?
- Novelty test: Would a thoughtful person be surprised by this?
- Truth test: Is every sentence actually true, or is some of it LinkedIn-speak?
- Type 3 test: Is this about something that seems important but avoids real work?

**Output format:**
```
Paul Graham lens: X.X/10
Strongest sentence: "[quote]"
Weakest sentence: "[quote]"
Core insight is [true/fuzzy/LinkedIn-speak]
```

---

#### 🎭 Voice & Storytelling (25%)

*Finds where you played it safe. Demands specificity and vulnerability.*

Score criteria:
- **10**: Feels like overhearing a real person think. Specific. One moment of vulnerability.
- **8-9**: Strong voice. One sentence too safe or too generic.
- **6-7**: Mostly real but one paragraph reads like a template.
- **4-5**: Voice is there occasionally. Many sentences could be anyone.
- **1-3**: Template content. Could be posted by 500 different accounts.
- **0**: Pure robot. No human signal.

Ask yourself:
- Specificity test: Can every generic word be replaced with a specific one?
- Immediacy test: Does it feel like it's happening now?
- Vulnerability test: Did the author show something they're not proud of?
- Humor test: Is there at least one moment of self-deprecation?
- Numbers test: Does every claim have a number?

**Output format:**
```
Voice & Storytelling: X.X/10
Most human moment: "[quote]"
Most generic sentence: "[quote]"
Missing: [specificity | vulnerability | humor | immediacy | numbers]
```

---

#### ⚡ Actionability (20%)

*Challenges abstract wisdom. Asks "but what does this mean practically?"*

Score criteria:
- **10**: Reader knows exactly what to do Monday morning. Real, tested advice.
- **8-9**: Clear action. One step is slightly abstract.
- **6-7**: Insight is valuable but action is implied, not stated.
- **4-5**: Interesting to think about. Hard to act on.
- **1-3**: Wisdom without practice. Theory with no implementation.
- **0**: No actionable content at all.

Ask yourself:
- Monday morning test: Can someone act on this next week?
- Reality test: Has the author actually done this, or is it theory?
- "So what" test: Why should any reader care about this?
- Specificity test: Is the advice "be consistent" or "post at 7am Tuesday with [specific hook]"?

**Output format:**
```
Actionability: X.X/10
Most actionable line: "[quote]"
Least actionable line: "[quote]"
Missing: [specific steps | real numbers | tested claim | "so what" answer]
```

---

#### 🎣 Hook & Flow (15%)

*Merciless about pacing. Finds every energy dip.*

Score criteria:
- **10**: Hook stops scroll. Tension builds. No dips. Ending opens a loop.
- **8-9**: Strong hook. One paragraph loses tension mid-piece.
- **6-7**: Hook is okay. Middle sags. End lands but doesn't open a loop.
- **4-5**: Hook is weak. Flow is inconsistent.
- **1-3**: Doesn't stop scroll. Reader would close after 3 sentences.
- **0**: No hook. No flow. Wall of text.

Ask yourself:
- Do the first 5 words stop the scroll?
- Does tension build paragraph by paragraph?
- Is there any energy dip in the middle?
- Does the ending open a loop (question/reflection), not close one?
- Is the pacing varied? (short punchy + longer developed sentences)

**Output format:**
```
Hook & Flow: X.X/10
Hook effectiveness: [stops scroll | weak | needs rewrite]
Energy dip at: [paragraph number or "none"]
Ending type: [opens loop | closes cleanly | aphorism (bad) | weak]
```

---

#### 🔨 Builder Authenticity (10%)

*Would this post survive in a room of builders? Show your work.*

Score criteria:
- **10**: Real numbers. Real tools. Real timeline. The mechanism is shown.
- **8-9**: Mostly real. One claim is vague.
- **6-7**: Feels credible but missing specifics.
- **4-5**: Some platitudes. Missing proof.
- **1-3**: Sounds like a content marketer who read a book about building.
- **0**: Pure theory. No evidence of actually doing the thing.

Ask yourself:
- Is there at least one real number?
- Are real tools, products, or timelines mentioned?
- Is the mechanism shown (not just the result)?
- Would a skeptical engineer believe this?

**Output format:**
```
Builder Authenticity: X.X/10
Most credible detail: "[quote]"
Most hand-wavy claim: "[quote]"
Missing: [number | tool name | timeline | mechanism]
```

---

#### 📚 Reader Value (5%)

*Does the reader leave with something usable?*

Score criteria:
- **10**: Reader has a new mental model or specific technique.
- **8-9**: Clear takeaway. Very useful.
- **6-7**: Valuable to read, but takeaway is vague.
- **4-5**: Some value, but reader has to dig for it.
- **1-3**: Reader feels entertained but gained nothing usable.
- **0**: No value delivered.

**Output format:**
```
Reader Value: X.X/10
Key takeaway: "[what reader leaves with]"
Value type: [mental model | technique | data | story | entertainment]
```

---

## Scoring Calculation

```
Final Score = (PG × 0.25) + (Voice × 0.25) + (Action × 0.20) + (Hook × 0.15) + (Builder × 0.10) + (Value × 0.05)
```

### Score Interpretation

| Score | Verdict | Action |
|-------|---------|--------|
| 9.5–10.0 | Exceptional | Publish |
| 9.0–9.4 | Publish-ready | Publish |
| 8.0–8.9 | Strong — needs one fix | Fix top issue, re-audit |
| 7.0–7.9 | Good — needs 2-3 fixes | Fix top issues, re-audit |
| 5.0–6.9 | Rewrite needed | Major rewrite, restart audit |
| < 5.0 | Scrap and restart | Different angle |

---

## Audit Output Format

```
═══════════════════════════════════
CONTENT AUDIT REPORT
═══════════════════════════════════

AI PRE-CHECK: [PASS / FAIL]
Flags: [list flags or "none"]

───────────────────────────────────
EXPERT PANEL SCORES
───────────────────────────────────
🧠 Paul Graham:        X.X / 10  (×0.25)
🎭 Voice & Story:      X.X / 10  (×0.25)
⚡ Actionability:      X.X / 10  (×0.20)
🎣 Hook & Flow:        X.X / 10  (×0.15)
🔨 Builder Auth:       X.X / 10  (×0.10)
📚 Reader Value:       X.X / 10  (×0.05)
───────────────────────────────────
FINAL SCORE:           X.X / 10
───────────────────────────────────

VERDICT: [PUBLISH / FIX + RE-AUDIT / REWRITE]

TOP 3 ISSUES TO FIX:
1. [Specific, actionable issue with quote]
2. [Specific, actionable issue with quote]
3. [Specific, actionable issue with quote]

WHAT'S WORKING (don't change):
- [strength 1]
- [strength 2]
═══════════════════════════════════
```

---

## References

- `references/ai-detection.md` — Full poison word list, typography bans, structural patterns
- `references/scoring-examples.md` — Example audits with scores at different levels
- `references/human-writing-patterns.md` — What makes text sound genuinely human
