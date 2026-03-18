# Agent Skills Collection

Open-source skills for AI agents. Works with **Claude Code**, **Cursor**, **OpenClaw**, and any tool supporting the [AgentSkills](https://agentskills.io) standard.

Skills are structured instruction sets that make AI agents dramatically better at specific tasks. Instead of generic prompts, skills encode expert-level workflows with quality gates, scoring systems, and verification steps.

---

## Skills

### 📋 [baaton/](./baaton/) — Project Management

API-first project management for AI agents via [Baaton](https://baaton.dev). Create issues, update statuses, post work summaries (TLDRs), and manage workflows.

- Issue CRUD with status transitions
- TLDR summaries with files changed and test status
- Webhook subscriptions for real-time events
- Helper scripts with auth and error handling

### 🔧 [content-engine/](./content-engine/) — Content Production Pipeline

Full end-to-end content pipeline: **Brief → Research → Write → Audit → Iterate → Publish-Ready**.

- Hard gates at every phase (no writing without a complete brief)
- Orchestrates `content-writer` and `content-audit` skills
- 10-point pre-publication checklist with evidence, not assumptions
- Content logging for building intelligence over time
- Configurable brand voice template

### 🎯 [content-audit/](./content-audit/) — Expert Panel Scoring

Ruthless multi-expert quality checker with weighted scoring. Minimum 9.0/10 to publish.

- **AI Pre-Check** — Binary gate: 3+ AI flags = rewrite, no scoring
- **Paul Graham lens** (25%) — Is the idea true, novel, clear?
- **Voice & Storytelling** (25%) — Authentic or template?
- **Actionability** (20%) — Monday morning test
- **Hook & Flow** (15%) — Scroll-stop, tension, pacing
- **Builder Authenticity** (10%) — Real numbers, real tools
- **Reader Value** (5%) — Useful takeaway

Includes full poison word lists, structural AI pattern detection, and calibrated scoring examples.

### ✍️ [content-writer/](./content-writer/) — Platform Writing Frameworks

Platform-specific writing frameworks with brand voice configuration.

- **LinkedIn**: 4 post formats (Story, Framework, Contrarian, Observation) with algorithm rules
- **X/Twitter**: Single tweets and threads with hook patterns
- **Email**: Singles and sequences (Welcome, Launch, Nurture, Re-engagement)
- **Ad Copy**: Facebook/Instagram and Google Ads formulas
- **Landing Pages**: Above-fold formula, section flow, headline patterns
- Anti-AI writing rules with replacement examples
- Copy length reference for every format
- Self-check checklists per platform

---

## Installation

### Claude Code

```bash
# Install a specific skill
git clone https://github.com/rmzlb/baaton-skills.git /tmp/baaton-skills
cp -r /tmp/baaton-skills/content-engine ~/.claude/skills/content-engine
cp -r /tmp/baaton-skills/content-audit ~/.claude/skills/content-audit
cp -r /tmp/baaton-skills/content-writer ~/.claude/skills/content-writer

# Or install all marketing skills at once
for skill in content-engine content-audit content-writer; do
  cp -r /tmp/baaton-skills/$skill ~/.claude/skills/$skill
done
```

### Cursor

```bash
git clone https://github.com/rmzlb/baaton-skills.git /tmp/baaton-skills
cp -r /tmp/baaton-skills/content-engine .claude/skills/content-engine
cp -r /tmp/baaton-skills/content-audit .claude/skills/content-audit
cp -r /tmp/baaton-skills/content-writer .claude/skills/content-writer
```

### OpenClaw

```bash
# Install individual skills
openclaw skills install rmzlb/baaton-skills/content-engine
openclaw skills install rmzlb/baaton-skills/content-audit
openclaw skills install rmzlb/baaton-skills/content-writer
```

### Manual (any agent)

Copy the skill directory to wherever your agent reads instructions. Each skill is self-contained with a `SKILL.md` entry point and a `references/` directory.

---

## How Skills Work

Each skill follows the [AgentSkills](https://agentskills.io) open standard:

```
skill-name/
├── SKILL.md              # Main instructions (YAML frontmatter + markdown)
├── references/           # Detailed reference files (loaded on demand)
│   ├── framework.md
│   └── examples.md
└── scripts/              # Helper scripts (optional)
    └── setup.sh
```

- `SKILL.md` is the entry point. It contains YAML frontmatter (name, description, triggers) and markdown instructions.
- `references/` holds detailed docs that the agent loads only when needed, keeping context small.
- The agent reads the skill description and decides when to apply it automatically, or you invoke it with `/skill-name`.

For more on the format: [AgentSkills spec](https://agentskills.io) | [Claude Code skills docs](https://code.claude.com/docs/en/skills)

---

## Quick Start: Content Pipeline

1. Install the 3 content skills (engine + audit + writer)
2. Copy `content-engine/references/brand-voice-template.md` and fill in your voice
3. Ask your agent: "Write a LinkedIn post about [topic]"
4. The engine will: collect a brief → research → draft → audit → iterate → deliver

The audit panel scores against 6 expert lenses. Under 9.0/10, it iterates automatically (max 3 loops). You get a final draft with a scored checklist proving quality.

---

## Repo Structure

```
baaton-skills/
├── README.md
├── LICENSE
├── baaton/                    # Project management skill
│   ├── SKILL.md
│   ├── references/
│   └── scripts/
├── content-engine/            # Pipeline orchestrator
│   ├── SKILL.md
│   └── references/
├── content-audit/             # Expert panel scoring
│   ├── SKILL.md
│   └── references/
└── content-writer/            # Platform frameworks
    ├── SKILL.md
    └── references/
```

---

## Contributing

PRs welcome. If you build a skill that's useful, open a PR to add it.

Guidelines:
- Follow the AgentSkills structure (SKILL.md + references/)
- Keep SKILL.md under 500 lines (move details to references/)
- Include real examples, not just theory
- Test with at least one agent (Claude Code, Cursor, or OpenClaw)

---

## License

MIT
