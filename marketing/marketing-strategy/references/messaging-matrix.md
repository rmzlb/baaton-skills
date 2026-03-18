# Messaging Matrix

## Structure

Rows = buyer personas. Columns = funnel stages.
Each cell = what you say to THIS person at THIS stage.

```
              │ Awareness          │ Consideration         │ Decision
──────────────┼────────────────────┼───────────────────────┼─────────────────
Persona 1     │ Headline           │ Headline              │ Headline
(Role)        │ Supporting points  │ Supporting points     │ Supporting points
              │ Proof point        │ Proof point           │ Proof point
              │ CTA                │ CTA                   │ CTA
──────────────┼────────────────────┼───────────────────────┼─────────────────
Persona 2     │ ...                │ ...                   │ ...
```

---

## Cell Template

```yaml
headline: "[1 sentence. Speaks to their pain at this stage.]"
supporting_points:
  - "[Point that backs up the headline]"
  - "[Second proof or benefit]"
  - "[Third if needed — max 3]"
proof: "[Specific number, case study, or customer quote]"
cta: "[What you want them to do RIGHT NOW]"
channel: "[Where this message lives — LinkedIn, email, ad, landing page]"
```

---

## Filled Example: TaskPilot

### Persona 1: VP Engineering ("Engineering Emily")

**Awareness** — She doesn't know TaskPilot exists. She's frustrated but not actively searching.

```yaml
headline: "Your board is asking what engineering shipped last quarter. You spent 8 hours building that report manually."
supporting_points:
  - "67% of VP Engs spend 5+ hours/month on manual reporting (our survey, n=200)"
  - "Board reports should come from real data, not status meetings"
  - "The gap between what engineering ships and what leadership sees is growing"
proof: "Acme Corp's VP Eng went from 8h/month reporting to 15 minutes after switching from Linear"
cta: "Read: 'Why Your Engineering Metrics Are Lying to Your Board' (blog post)"
channel: "LinkedIn post, targeted LinkedIn ad, engineering newsletter sponsorship"
```

**Consideration** — She knows the problem exists. She's comparing solutions.

```yaml
headline: "GitHub-native means your engineers actually use it. That's why our adoption rate is 94% vs. Jira's 41%."
supporting_points:
  - "Zero-ceremony mode: no ticket updates, no sprint rituals, no standups about standups"
  - "Engineers stay in their IDE. TaskPilot reads GitHub activity directly."
  - "Unlike Linear, reports go beyond velocity — you see actual shipping output"
proof: "94% weekly active rate across 200+ engineering teams (our internal data)"
cta: "Start a free 14-day trial with your GitHub org (5-minute setup)"
channel: "Comparison landing page, retargeting ad, email sequence #3"
```

**Decision** — She's ready to buy. She needs to justify it internally.

```yaml
headline: "Here's exactly what to tell your CTO: TaskPilot pays for itself in the first month."
supporting_points:
  - "8h/month × $150/hour VP Eng time = $1,200/month saved on reporting alone"
  - "SOC2 compliant, SSO/SAML included, no extra security review needed"
  - "Migration from Linear/Jira takes < 1 day with our import tool"
proof: "Average customer sees ROI in 23 days. 96% renewal rate after year one."
cta: "Book a 20-min demo with our engineering lead (not a sales rep)"
channel: "Email sequence #5, pricing page, case study PDF"
```

### Persona 2: Senior Engineer ("Dev Dan")

**Awareness**

```yaml
headline: "You spend 45 minutes/day updating Jira tickets nobody reads."
supporting_points:
  - "That's 3.75 hours/week — almost a full day of coding lost"
  - "The irony: leadership still asks 'what's the status?' in Slack"
  - "Tools should read your work, not the other way around"
proof: "Survey: 71% of engineers say their project tracker slows them down"
cta: "See the '5 signs your PM tool is wasting engineering time' checklist"
channel: "Dev Twitter/X, Hacker News comment, r/ExperiencedDevs"
```

**Consideration**

```yaml
headline: "TaskPilot reads your Git activity. You never update a ticket again."
supporting_points:
  - "PR merged? Ticket moves automatically. No manual drag-and-drop."
  - "Works with your existing GitHub workflow. No new habits."
  - "Your IDE plugin shows context without leaving your editor"
proof: "Engineers at Acme Corp shipped 23% more after dropping manual ticket updates"
cta: "Try it on your personal repo — free, no credit card, 2 minutes"
channel: "GitHub README badge, dev blog post, Show HN"
```

**Decision**

```yaml
headline: "Tell your VP Eng: this tool makes their reporting problem disappear AND makes your life better."
supporting_points:
  - "You get fewer interruptions (no more 'what's the status on X?')"
  - "Leadership gets automated reports (stops bothering you)"
  - "It's the rare tool that makes both sides happy"
proof: "NPS among engineers: 72 (vs. Jira's 11)"
cta: "Forward our pitch deck to your VP Eng (we wrote it so you don't have to)"
channel: "In-product sharing flow, engineer-to-manager email template"
```

---

## Jobs-to-be-Done Messaging Lens

Before writing any cell, identify the job:

```
When [situation/trigger],
I want to [motivation/goal],
so I can [desired outcome].
```

**Engineering Emily:**
- "When the board asks for engineering metrics, I want to generate a report in minutes, so I can spend my time on strategic work instead of data entry."

**Dev Dan:**
- "When I finish a PR, I want the project status to update itself, so I can go back to coding without context-switching to a tracker."

The job-to-be-done becomes your headline. The desired outcome becomes your proof point.

---

## Using the Matrix

1. Fill ONE persona completely first (all 3 stages)
2. Check: does the story flow from awareness to decision?
3. Check: does each CTA naturally lead to the next stage?
4. Then fill the second persona
5. Look for shared messaging (some points work across personas)
6. Identify gaps: which cells have weak proof? Go find better data.

Feed this matrix into `content-engine` — each cell becomes a content brief.
