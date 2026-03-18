# Agent Skills Collection

Open-source skills for AI coding agents. Works with **Claude Code**, **Cursor**, **OpenClaw**, **Gemini CLI**, **Goose**, and any tool supporting the [AgentSkills](https://agentskills.io) standard.

Skills are structured instruction sets that make AI agents dramatically better at specific tasks. Instead of generic prompts, skills encode expert-level workflows with quality gates, scoring systems, and verification loops.

---

## Marketing Skills Suite (6 skills)

A complete marketing pipeline from strategy to analytics. Each skill handles one phase. Together, they cover the full loop:

```
Strategy → Create → Audit → Repurpose → Distribute → Analyze → ♻️ Strategy
```

### 🧭 [marketing-strategy/](./marketing-strategy/) — Strategic Foundations

Everything BEFORE content creation: ICP definition, buyer personas, positioning (April Dunford framework), messaging matrices, competitive analysis, and go-to-market planning.

- ICP builder with firmographics, technographics, behavioral signals
- Buyer personas with Adele Revella's 5 Rings of Buying Insight
- Positioning framework (Obviously Awesome adapted) + category decision tree
- Messaging matrix: persona × funnel stage with filled examples
- Competitive analysis templates (feature matrix, positioning map, SWOT)
- GTM launch checklist: pre-launch (60 days), launch week, post-launch

### 🔧 [content-engine/](./content-engine/) — Production Pipeline

Full end-to-end content pipeline: **Brief → Research → Write → Audit → Iterate → Publish-Ready**.

- Hard gates at every phase (no writing without a complete brief)
- Orchestrates `content-writer` and `content-audit` skills
- 10-point pre-publication checklist with evidence
- Content logging for building intelligence over time
- Configurable brand voice template

### ✍️ [content-writer/](./content-writer/) — Platform Writing Frameworks

Platform-specific writing frameworks with brand voice configuration.

- **LinkedIn**: 4 post formats with algorithm rules and timing
- **X/Twitter**: Single tweets and threads with hook patterns
- **Email**: Singles and sequences (Welcome, Launch, Nurture, Re-engagement)
- **Ad Copy**: Facebook/Instagram and Google Ads formulas
- **Landing Pages**: Above-fold formula, section flow, 40+ headline patterns
- Anti-AI writing rules with 30+ poison words and replacements
- Copy length reference for every format

### 🎯 [content-audit/](./content-audit/) — Expert Panel Scoring

Multi-expert quality checker with weighted scoring. Minimum 9.0/10 to publish.

- **AI Pre-Check** — Binary gate: 3+ AI flags = rewrite
- **Paul Graham lens** (25%) — Is the idea true, novel, clear?
- **Voice & Storytelling** (25%) — Authentic or template?
- **Actionability** (20%) — Monday morning test
- **Hook & Flow** (15%) — Scroll-stop, tension, pacing
- **Builder Authenticity** (10%) — Real numbers, real tools
- **Reader Value** (5%) — Useful takeaway

### 🔄 [content-repurpose/](./content-repurpose/) — 1→N Content Multiplication

Transform one piece into 5-8 platform-optimized versions. Not reformatting — real adaptation.

- Content atomization: break into reusable atomic units (insight, data, story, framework)
- Transformation matrix: source × target with specific rules per pair
- Platform adaptation: tone shifts, hook rewriting, CTA changes, algorithm optimization
- Staggered publishing schedules (7-14 day spread for maximum reach)
- 3 ready-to-use workflows: Weekly Sprint, Blog-to-Social Series, Video Cascade

### 📊 [marketing-analytics/](./marketing-analytics/) — Measurement & Iteration

The feedback loop that makes everything better over time.

- Metrics framework with benchmarks by platform and audience size
- Vanity metrics vs actionable metrics (follower count vs DM conversion rate)
- Attribution models: first-touch, last-touch, multi-touch, self-reported
- A/B testing guide for small audiences (the "7 out of 10" rule)
- Weekly/monthly/quarterly report templates with filled examples
- Ready-to-use content performance analysis prompts

---

## Project Management

### 📋 [baaton/](./baaton/) — Issue Tracking for Agents

API-first project management via [Baaton](https://baaton.dev). Create issues, update statuses, post work summaries, and manage workflows.

---

## Installation

### Claude Code

```bash
# Clone and install all marketing skills
git clone https://github.com/rmzlb/baaton-skills.git /tmp/baaton-skills
for skill in marketing-strategy content-engine content-writer content-audit content-repurpose marketing-analytics; do
  cp -r /tmp/baaton-skills/$skill ~/.claude/skills/$skill
done
```

### Cursor / VS Code Copilot

```bash
git clone https://github.com/rmzlb/baaton-skills.git /tmp/baaton-skills
for skill in marketing-strategy content-engine content-writer content-audit content-repurpose marketing-analytics; do
  cp -r /tmp/baaton-skills/$skill .claude/skills/$skill
done
```

### OpenClaw

```bash
openclaw skills install rmzlb/baaton-skills/marketing-strategy
openclaw skills install rmzlb/baaton-skills/content-engine
# ... repeat for each skill
```

### Manual (any agent)

Copy the skill directory to wherever your agent reads instructions. Each skill is self-contained with a `SKILL.md` entry point and `references/` directory.

---

## Quick Start

1. Install the marketing skills
2. Copy `content-engine/references/brand-voice-template.md` and fill in your voice
3. Run `/marketing-strategy icp` to define your target audience
4. Run `/content-engine linkedin "your topic"` to create a post
5. The engine collects a brief → drafts → audits (9.0/10 minimum) → iterates → delivers
6. Run `/content-repurpose linkedin` to transform it into X thread + email + carousel
7. After 10+ posts, run `/marketing-analytics report` to see what's working

---

## How Skills Work

Each skill follows the [AgentSkills](https://agentskills.io) open standard:

```
skill-name/
├── SKILL.md              # Main instructions (YAML frontmatter + markdown)
└── references/           # Detailed reference files (loaded on demand)
    ├── framework.md
    └── examples.md
```

- `SKILL.md` = entry point with YAML frontmatter (name, description, triggers)
- `references/` = detailed docs loaded only when needed (keeps context small)
- The agent reads skill descriptions and decides when to apply them automatically

Compatible with: Claude Code, Cursor, Gemini CLI, OpenClaw, Goose, VS Code Copilot, Roo Code, OpenHands, and [30+ other tools](https://agentskills.io).

---

## Contributing

PRs welcome. Follow AgentSkills structure (SKILL.md + references/), keep SKILL.md under 500 lines, include real examples, test with at least one agent.

## License

MIT
