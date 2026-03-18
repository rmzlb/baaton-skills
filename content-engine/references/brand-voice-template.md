# Brand Voice Template

Configure this file for your brand before running the content pipeline.
Replace all `[PLACEHOLDER]` values with your actual brand details.

---

## Brand Identity

```yaml
brand_name: "[Your name or brand name]"
role: "[How you describe yourself — e.g., 'founder of X', 'engineer who ships', 'growth at Y']"
location: "[City, Country — optional but adds credibility]"
primary_topics:
  - "[Topic 1 — e.g., 'building in public']"
  - "[Topic 2 — e.g., 'SaaS growth without VC']"
  - "[Topic 3 — e.g., 'Rust and systems programming']"
```

---

## Voice Characteristics

### Tone
```yaml
overall_tone: "[e.g., direct, warm, dry, energetic, skeptical, optimistic]"
formality: "[casual | semi-formal | formal]"
humor_style: "[none | dry | self-deprecating | absurdist]"
expertise_posture: "[confident | discovery | teaching | peer-to-peer]"
```

### Sentence Patterns
```yaml
sentence_length: "[short + punchy | mixed | long-form]"
hook_style: "[2-5 words, statement | question | number | bold claim]"
opener_pattern: "[how you typically start posts — e.g., 'Started [thing] 6 months ago.']"
```

### Content Signatures
- **Always include**: [e.g., real numbers, specific dates, tool names]
- **Never include**: [e.g., vague claims, empty motivation, hedged predictions]
- **Default CTA style**: [e.g., open-ended question, direct ask, soft offer]

---

## Content Pillars

Define 3-5 content pillars — the themes you consistently write about.

```yaml
pillars:
  - name: "[Pillar 1 Name]"
    description: "[What angle you take on this topic]"
    example_topics:
      - "[Specific topic]"
      - "[Specific topic]"

  - name: "[Pillar 2 Name]"
    description: "[What angle you take on this topic]"
    example_topics:
      - "[Specific topic]"
      - "[Specific topic]"

  - name: "[Pillar 3 Name]"
    description: "[What angle you take on this topic]"
    example_topics:
      - "[Specific topic]"
      - "[Specific topic]"
```

---

## Voice Examples

### Example Hook Styles

**Short statement:**
> "I almost didn't ship it."

**Number lead:**
> "6 months. 3 pivots. $0 in funding."

**Observation:**
> "Nobody talks about week 3."

**Contrarian:**
> "Onboarding is overrated."

### Example Paragraph Styles

Fill in with your actual writing samples so the agent can match your voice:

```
Sample 1 (story/personal):
[Paste a paragraph from your best post]

Sample 2 (framework/analytical):
[Paste a paragraph from your best framework post]

Sample 3 (contrarian/opinion):
[Paste a paragraph from your best opinion post]
```

---

## Vocabulary & Style Rules

### Words You Use
List 10-20 words/phrases you naturally use:
```
- [word or phrase]
- [word or phrase]
```

### Words You Avoid
Beyond the AI poison list, words that don't fit your voice:
```
- [word or phrase]
- [word or phrase]
```

### Formatting Rules
```yaml
uses_bullet_lists: false  # true if your style includes lists
uses_bold_for_emphasis: false
uses_parenthetical_asides: true  # (like this)
uses_all_caps: false
uses_italics: false
line_break_style: "[double | single | paragraph]"
```

---

## Platform Overrides

If your voice differs by platform:

```yaml
linkedin:
  formality_adjustment: "[more formal | same | more casual]"
  extra_rules: "[e.g., always end with a question]"

twitter:
  formality_adjustment: "[more casual]"
  extra_rules: "[e.g., threads max 8 tweets, always reply to first tweet]"

email:
  formality_adjustment: "[more personal]"
  extra_rules: "[e.g., always include P.S., subject line max 50 chars]"
```

---

## Calibration Exercise

Before your first content sprint, run this calibration:

1. Pick your 3 best-performing posts/emails
2. Paste them into Sample 1/2/3 above
3. Ask the agent: "What patterns do you see in my writing?"
4. Add those patterns to this file

The agent will use these samples as a reference every time it writes in your voice.

---

## Quick Reference Card

| Element | Your Setting |
|---------|-------------|
| Tone | [fill in] |
| Hook style | [fill in] |
| Humor | [fill in] |
| Lists in prose | [yes/no] |
| Em-dash | Never (AI flag) |
| Default CTA | [fill in] |
| Pillar 1 | [fill in] |
| Pillar 2 | [fill in] |
| Pillar 3 | [fill in] |
