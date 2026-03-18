# A/B Testing Guide for Content Marketers

Practical testing without a statistics degree.

---

## The Problem

Most content marketers don't test because they think they need:
- 10,000 people per variant
- Statistical significance calculators
- PhD-level understanding of p-values

You don't. Here's how to test with a small audience.

---

## What to Test (Ordered by Impact)

Test the thing that makes the biggest difference first.

### Tier 1: Highest Impact
1. **Hook/Headline** — The hook decides if anyone reads the rest. Test this first, always.
2. **Content format** — Story vs. framework vs. contrarian vs. observation. Different formats reach different people.
3. **CTA type** — Question vs. direct ask vs. none vs. soft ask. Changes conversion, not just engagement.

### Tier 2: Medium Impact
4. **Posting time** — Morning vs. evening, weekday vs. weekend. Easy to test, clear signal.
5. **Content length** — Short (800 chars) vs. long (2,000 chars). Audience-dependent.
6. **Platform** — Same content adapted for LinkedIn vs. X. Which audience cares more?

### Tier 3: Lower Impact (test later)
7. **Visual vs. text-only** — Image/carousel vs. pure text post.
8. **Hashtags** — With vs. without (LinkedIn). Usually minimal impact.
9. **Tone** — Formal vs. casual. Subtle but meaningful over time.

---

## How to Test with Small Audiences

### The 10-Post Method

You don't compare 1 post vs. 1 post. That's a coin flip, not a test.

**Method:**
1. Pick ONE variable to test (e.g., hook style)
2. Write 5 posts with Style A hooks (e.g., short statement)
3. Write 5 posts with Style B hooks (e.g., question)
4. Keep everything else the same (similar topics, same posting time, same length)
5. Compare the average engagement across all 5 in each group

**Example:**
```
Style A (Statement hooks):         Style B (Question hooks):
Post 1: 4.2% engagement           Post 1: 3.1% engagement
Post 2: 5.1%                      Post 2: 2.8%
Post 3: 3.8%                      Post 3: 4.5%
Post 4: 6.2%                      Post 4: 3.2%
Post 5: 4.5%                      Post 5: 2.9%
Average: 4.76%                    Average: 3.30%
```

Style A wins by 1.46 percentage points across 5 posts. That's a signal.

### The "7 Out of 10" Rule

If Approach A beats Approach B in 7+ out of 10 comparisons, act on it.
If it's 6/10, keep testing. If it's 5/10, there's no real difference — move on.

You don't need p-values. You need patterns over 10+ data points.

---

## Testing Calendar

### Month 1: Hook Styles
- Week 1-2: Statement hooks ("I almost quit.")
- Week 3-4: Contrarian hooks ("The advice is wrong.")
- Compare: Which style gets higher avg engagement?

### Month 2: Content Format
- Week 1-2: Story format (personal narrative)
- Week 3-4: Framework format (step-by-step process)
- Compare: Which format drives more DMs/conversions?

### Month 3: Posting Time
- Week 1-2: 8am posts (before work)
- Week 3-4: 12pm posts (lunch break)
- Compare: Which time gets more impressions?

### Month 4: Based on Results
- Double down on Month 1-3 winners
- Test next tier variables

---

## Common Mistakes

### Testing Too Many Variables at Once
"I changed the hook, the format, the length, and the posting time."
Now you don't know which change made the difference. Test ONE thing.

### Drawing Conclusions from 1-2 Posts
"My story post got 10K impressions, so stories work best."
That could be the topic, the timing, or luck. Need 5+ data points.

### Not Controlling for Topic
If you test hooks with different topics, you're testing topics, not hooks.
Keep topics similar when testing format/hook/timing.

### Ignoring the Right Metric
Testing hooks? Measure impressions (reach = hook effectiveness).
Testing CTAs? Measure clicks/DMs (conversion = CTA effectiveness).
Testing format? Measure engagement rate (resonance = format effectiveness).

### Giving Up Too Early
"A/B testing didn't work for me." = "I tested 2 posts and saw no difference."
Real testing takes 4-8 weeks. If you can't commit to 10 posts per variant, don't start.

---

## Tracking Template

```yaml
test:
  name: "[What you're testing]"
  variable: "[hook_style | format | timing | length | cta | platform]"
  hypothesis: "[I think A will outperform B because...]"
  variant_a: "[Description of variant A]"
  variant_b: "[Description of variant B]"
  metric: "[Which metric you're comparing]"
  duration: "[How many posts per variant]"
  
results:
  variant_a_scores: [4.2, 5.1, 3.8, 6.2, 4.5]
  variant_b_scores: [3.1, 2.8, 4.5, 3.2, 2.9]
  variant_a_avg: 4.76
  variant_b_avg: 3.30
  winner: "A"
  confidence: "A won 4/5 comparisons"
  
decision: "[What you'll do based on this result]"
next_test: "[What to test next]"
```
