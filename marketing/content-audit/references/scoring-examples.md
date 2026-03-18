# Scoring Examples

Reference audits showing how the scoring system works in practice.
Use these to calibrate your scoring — not to copy the content.

---

## Example A — Score 9.4/10 (Publish-ready)

**Draft (LinkedIn post):**
```
I almost didn't ship it.

6 months ago I built a feature nobody asked for. Spent 3 weeks on it.
My co-founder thought I was procrastinating. He was probably right.

Here's the thing: that feature became the reason 40% of our paid users stayed.
I know because I asked them. On a call. One by one.

Most product decisions feel obvious in hindsight. This one felt insane in the moment.

What's the last thing you built that you weren't sure about?
```

**Audit:**

```
AI PRE-CHECK: PASS
Flags: 0

🧠 Paul Graham:        9.5 / 10  (×0.25)
   Strongest: "My co-founder thought I was procrastinating. He was probably right."
   Weakest: "Most product decisions feel obvious in hindsight." (cliché but earned)
   Insight: True and slightly counter-intuitive.

🎭 Voice & Story:      9.5 / 10  (×0.25)
   Most human: "He was probably right."
   Numbers: ✓ (6 months, 3 weeks, 40%)
   Vulnerability: ✓ (admitting co-founder was right)
   Specificity: Strong

⚡ Actionability:      9.0 / 10  (×0.20)
   Best line: "I asked them. On a call. One by one."
   Missing: No explicit "try this yourself" — but implied

🎣 Hook & Flow:        9.5 / 10  (×0.15)
   Hook: "I almost didn't ship it." — strong, creates tension
   Energy dip: None
   Ending: Opens loop (question)

🔨 Builder Auth:       9.5 / 10  (×0.10)
   Real detail: "3 weeks", "40% of paid users", "On a call. One by one."
   Mechanism shown: Yes (called users)

📚 Reader Value:       9.0 / 10  (×0.05)
   Takeaway: Validate with users directly, not analytics

FINAL SCORE: 9.43 / 10

VERDICT: PUBLISH

TOP STRENGTHS:
- Hook creates genuine curiosity without being clickbaity
- Self-deprecation lands perfectly ("He was probably right")
- Numbers are specific and credible
- Ending opens a loop, invites engagement

NOTHING TO CHANGE.
```

---

## Example B — Score 7.1/10 (Fix Needed)

**Draft (LinkedIn post):**
```
Building in public is one of the most powerful strategies for growth.

Here's what I've learned after 12 months:

→ Consistency beats perfection
→ Authenticity drives engagement  
→ Community is your real moat
→ Failure posts get more traction than wins

The secret? Just start. Share your journey. People want to see the real you.

What's holding you back from sharing your story?
```

**Audit:**

```
AI PRE-CHECK: FAIL
Flags found:
- Arrow list (→) used: 1 flag
- "Authenticity" (Tier 1 poison): 1 flag
- "The secret? Just start." — rhetorical Q + short answer: 1 flag
Total: 3 flags → REWRITE REQUIRED

(Scoring shown for educational purposes only)

🧠 Paul Graham:        5.0 / 10
   "Consistency beats perfection" — not surprising to anyone
   "Community is your real moat" — LinkedIn-speak
   Zero novel insight. All statements provable false with one counterexample.

🎭 Voice & Story:      4.5 / 10
   Zero specific details. "12 months" is the only number.
   Could be posted by any of 50,000 accounts today.
   No vulnerability, no humor, no immediacy.

⚡ Actionability:      4.0 / 10
   "Just start" — not actionable. Everyone knows to start.
   No specific mechanism, no real advice.

🎣 Hook & Flow:        6.0 / 10
   Opening is generic. Arrow list kills flow.
   "The secret?" — hackneyed setup.

🔨 Builder Auth:       3.0 / 10
   "12 months" — okay. Everything else is platitude.
   No tools, no real metrics, no mechanism.

📚 Reader Value:       5.0 / 10
   Reader leaves with nothing usable.

FINAL SCORE: 4.63 / 10

VERDICT: REWRITE FROM SCRATCH

ROOT ISSUES:
1. No specific insight — remove every sentence that doesn't surprise you
2. Remove all arrow lists and replace with prose
3. What actually happened in those 12 months? Tell THAT story, with numbers.
```

---

## Example C — Score 8.6/10 (One Fix)

**Draft (tweet):**
```
After 18 months of building in public, the thing that moved the needle most wasn't 
a viral post. It was replying to every comment for 6 months straight.

Algorithm lesson most people skip: author engagement in the first 90 min decides reach.
```

**Audit:**

```
AI PRE-CHECK: PASS (with warning)
Flags: 1 — "moved the needle" (burned phrase)

🧠 Paul Graham:        9.0 / 10
   "Algorithm lesson most people skip" — genuinely useful
   Specific enough to be true.

🎭 Voice & Story:      8.0 / 10
   "Moved the needle" hurts it — remove that phrase
   Otherwise clear and specific

⚡ Actionability:      9.5 / 10
   "Replying to every comment for 6 months" — concrete and doable
   "First 90 min" — specific and actionable

🎣 Hook & Flow:        8.0 / 10
   "Wasn't a viral post" sets up good tension
   Second sentence is dense but delivers

🔨 Builder Auth:       9.0 / 10
   "18 months", "6 months", "90 min" — credible

📚 Reader Value:       9.0 / 10
   Leaves with a specific tactic

FINAL SCORE: 8.63 / 10

VERDICT: FIX + RE-AUDIT

TOP ISSUE:
1. Replace "moved the needle most" with direct language
   → Try: "After 18 months of building in public, one thing drove 80% of my growth."

WHAT'S WORKING: The 90-min insight, the specific timeframes, the contrast structure.
```

---

## Calibration Notes

**What makes a 10/10:** No sentence that could be cut. Every word earns its place.
One moment that makes the reader think "I've never heard it put that way."

**What makes a 5/10:** The ideas are okay but the execution is template. It reads like
the author wrote it in 5 minutes without thinking about who would read it.

**What makes a 2/10:** The content is entirely safe, vague, and could be generated by
pressing "make me a LinkedIn post" with zero context. It says nothing.

**The hardest score to move:** Voice (25%). You can fix hook, actionability, structure.
But if the voice isn't there, no amount of editing will save it — it needs a rewrite.
