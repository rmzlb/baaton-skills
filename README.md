# baaton-skills

Open-source agent skills. Plug them into **Claude Code**, **Cursor**, **Gemini CLI**, **Goose**, or [any AgentSkills-compatible tool](https://agentskills.io).

Skills aren't prompts. They're structured workflows with quality gates, scoring systems, and feedback loops that make your agent actually good at the job — not just "generate me a LinkedIn post" good. We're talking *9.0/10 scored by 6 weighted expert lenses before it touches your timeline* good.

---

## `marketing/` — The Full Marketing Stack

6 skills. 37 files. One pipeline. Everything from "who's my customer?" to "did that post actually work?"

```
Strategy → Create → Audit → Repurpose → Analyze → ♻️ Strategy
```

Most people ask their AI to "write a LinkedIn post." That's like asking a chef to cook without knowing who's eating. These skills fix that.

| Skill | What it does | The boring version |
|-------|-------------|-------------------|
| [marketing-strategy/](./marketing/marketing-strategy/) | Figures out who you're selling to before you write a word | ICP, personas, positioning, messaging, competitive analysis |
| [content-engine/](./marketing/content-engine/) | Runs the full show: brief → write → audit → iterate → ship | Pipeline orchestrator with hard gates |
| [content-writer/](./marketing/content-writer/) | Knows that LinkedIn ≠ Twitter ≠ Email ≠ Ads | Platform-specific frameworks + anti-AI rules |
| [content-audit/](./marketing/content-audit/) | 6 experts roast your draft. Minimum 9.0/10 or rewrite. | Paul Graham + storytelling + actionability + hook + builder + reader |
| [content-repurpose/](./marketing/content-repurpose/) | 1 post → 5-8 pieces. Not copy-paste. Real adaptation. | Atomization + platform adaptation + scheduling |
| [marketing-analytics/](./marketing/marketing-analytics/) | Tells you what actually worked (spoiler: not what you thought) | Metrics, benchmarks, A/B testing, reporting |

### The audit is the secret weapon

Your AI-written content sounds AI-written because nobody checks it. Our audit panel catches:
- **30+ poison words** (if your post says "delve" or "leverage," it's dead on arrival)
- **Structural AI patterns** (the "It's not X. It's Y." contrast that every LLM loves)
- **6 weighted expert lenses** scoring independently (Paul Graham doesn't care about your hook — that's Nina Ramen's job)
- **Binary AI pre-check** — 3+ flags and you rewrite. No scoring. No mercy.

The result: content that passes as written by a human who actually builds things.

---

## `baaton/` — Project Management for Agents

API-first issue tracking via [Baaton](https://baaton.dev). Because your agent should be able to create a ticket, not just write code.

---

## Install

### Claude Code (all marketing skills)
```bash
git clone https://github.com/rmzlb/baaton-skills.git /tmp/baaton-skills
for skill in marketing-strategy content-engine content-writer content-audit content-repurpose marketing-analytics; do
  cp -r /tmp/baaton-skills/marketing/$skill ~/.claude/skills/$skill
done
```

### Cursor / VS Code
```bash
git clone https://github.com/rmzlb/baaton-skills.git /tmp/baaton-skills
for skill in marketing-strategy content-engine content-writer content-audit content-repurpose marketing-analytics; do
  cp -r /tmp/baaton-skills/marketing/$skill .claude/skills/$skill
done
```

### Just one skill
```bash
cp -r /tmp/baaton-skills/marketing/content-audit ~/.claude/skills/content-audit
```

Each skill works standalone. Install all 6 for the full pipeline, or pick what you need.

---

## Quick Start (5 minutes to your first audited post)

```
You:    /marketing-strategy icp
Agent:  [Walks you through ICP definition with templates + examples]

You:    /content-engine linkedin "why your onboarding is probably broken"
Agent:  [Collects brief → drafts → runs 6-expert audit → scores 7.8/10
         → iterates → rescores 9.2/10 → delivers final draft with checklist]

You:    /content-repurpose linkedin [paste the post]
Agent:  [Atomizes into 7 content atoms → generates X thread + email +
         2 standalone tweets + carousel outline → staggered schedule]

You:    /marketing-analytics report
Agent:  [Weekly report: best performer, worst performer, pattern spotted,
         recommended next test based on data]
```

One idea. Six platforms. Scored. Scheduled. Measured.

---

## What makes this different from "awesome prompts" repos

| Feature | Prompt collection | These skills |
|---------|------------------|-------------|
| Quality gate | ❌ Hope for the best | ✅ 9.0/10 minimum, 6 expert lenses |
| Anti-AI detection | ❌ "Write like a human" | ✅ 30+ poison words, structural pattern matching |
| Verification loop | ❌ One-shot | ✅ Max 3 audit loops with evidence checklist |
| Platform optimization | ❌ "Adapt for Twitter" | ✅ Algorithm rules, hook rewriting, tone shifts per platform |
| Strategy upstream | ❌ Jump to writing | ✅ ICP → Persona → Positioning → Messaging → THEN write |
| Measurement | ❌ Vibes | ✅ Metrics, benchmarks, A/B testing, quarterly strategy review |
| Format | ❌ Copy-paste prompts | ✅ AgentSkills standard (works with 30+ tools) |

---

## Repo Structure

```
baaton-skills/
├── README.md
├── LICENSE
├── baaton/                        # Project management
│   ├── SKILL.md
│   ├── references/
│   └── scripts/
└── marketing/                     # Marketing suite (6 skills)
    ├── marketing-strategy/        # ICP, positioning, GTM
    ├── content-engine/            # Pipeline orchestrator
    ├── content-writer/            # Platform frameworks
    ├── content-audit/             # Expert panel scoring
    ├── content-repurpose/         # 1→N multiplication
    └── marketing-analytics/       # Metrics & reporting
```

---

## Contributing

Build a skill that makes agents less mediocre? Open a PR.

Rules: AgentSkills format (SKILL.md + references/), under 500 lines, real examples, tested with at least one agent.

## License

MIT. Free forever. Go ship something.
