# ICP & Persona Templates

## ICP Template (Company Level)

```yaml
icp:
  name: "[Internal label — e.g., 'Growth-Stage SaaS']"

  firmographics:
    company_size: "[headcount range — e.g., 10-50]"
    revenue_range: "[ARR range — e.g., $1M-$10M]"
    industry: "[vertical — e.g., B2B SaaS, E-commerce, FinTech]"
    geography: "[regions — e.g., US + EU, English-speaking markets]"
    growth_stage: "[seed / series A / series B / growth / enterprise]"
    funding: "[bootstrapped / VC-backed / PE-backed]"

  technographics:
    current_tools: "[tools they already use — e.g., Hubspot, Stripe, Slack]"
    tech_maturity: "[low / medium / high — do they build or buy?]"
    integrations_needed: "[what must you connect to?]"
    migration_from: "[what are they replacing?]"

  behavioral_signals:
    search_terms: "[what they Google — e.g., 'how to reduce churn SaaS']"
    communities: "[where they hang out — e.g., r/SaaS, Indie Hackers, YC Slack]"
    content_consumed: "[podcasts, newsletters, blogs — e.g., Lenny's Newsletter]"
    events_attended: "[conferences — e.g., SaaStr, MicroConf]"
    job_postings: "[roles they're hiring — signals priorities]"

  pain_signals:
    primary_pain: "[the #1 thing blocking their growth]"
    secondary_pains: "[2-3 other frustrations]"
    failed_solutions: "[what they tried that didn't work]"
    budget_for_pain: "[how much they're spending on workarounds]"

  buying_process:
    initiator: "[who starts the search — role]"
    influencers: "[who shapes the decision]"
    decision_maker: "[who signs the check]"
    blocker: "[who might say no — e.g., legal, security]"
    budget_cycle: "[quarterly / annual / ad-hoc]"
    decision_timeline: "[days from first touch to purchase]"
    deal_size: "[expected ACV range]"

  disqualifiers:
    not_a_fit_if: "[clear anti-patterns — e.g., <5 employees, no budget]"
    red_flags: "[signals this prospect will waste your time]"
```

---

## Filled Example: TaskPilot (fictional B2B SaaS)

TaskPilot is a project management tool for engineering teams that integrates with GitHub.

```yaml
icp:
  name: "Growth-Stage Dev Tools SaaS"

  firmographics:
    company_size: "20-200 employees"
    revenue_range: "$2M-$25M ARR"
    industry: "B2B SaaS, DevTools, Developer Infrastructure"
    geography: "US, UK, Germany, France"
    growth_stage: "Series A to Series B"
    funding: "VC-backed"

  technographics:
    current_tools: "GitHub, Slack, Linear or Jira, Notion"
    tech_maturity: "High — eng-led org, build > buy culture for core product"
    integrations_needed: "GitHub, Slack, CI/CD (GitHub Actions, CircleCI)"
    migration_from: "Jira (too heavy), Linear (lacks reporting)"

  behavioral_signals:
    search_terms: "engineering team productivity metrics, sprint velocity alternatives, GitHub project management"
    communities: "Hacker News, r/ExperiencedDevs, Dev Twitter/X, local meetups"
    content_consumed: "The Pragmatic Engineer, LeadDev, Will Larson's blog"
    events_attended: "LeadDev, StaffPlus, local engineering meetups"
    job_postings: "Hiring Engineering Managers and DevOps — signals growing pains"

  pain_signals:
    primary_pain: "Engineering visibility — leadership can't see what's actually shipping vs. stuck"
    secondary_pains:
      - "Sprint ceremonies take too long, engineers hate the overhead"
      - "Reports to board are manual and take 4+ hours every month"
      - "Context switching between GitHub and project tracker"
    failed_solutions:
      - "Jira: too complex, engineers rebel after 3 months"
      - "Linear: clean UI but reports are too basic for leadership"
      - "Notion: flexible but no real integration with dev workflow"
    budget_for_pain: "$500-$2000/month on current tools + 8 hours/month manual reporting"

  buying_process:
    initiator: "VP Engineering or Engineering Manager"
    influencers: "Senior Engineers (they'll refuse tools they hate)"
    decision_maker: "CTO or VP Engineering"
    blocker: "Security team (SSO/SOC2 requirements), Finance (budget approval)"
    budget_cycle: "Quarterly review, can do ad-hoc for <$1000/month"
    decision_timeline: "14-30 days from first demo to purchase"
    deal_size: "$3,600-$24,000 ACV"

  disqualifiers:
    not_a_fit_if: "Solo developer, <5 engineers, doesn't use GitHub, waterfall methodology"
    red_flags: "Asking for custom features before trial, procurement-heavy process (>90 days), 'we just want to evaluate'"
```

---

## Buyer Persona Template

```yaml
persona:
  name: "[Fictional name — e.g., 'Engineering Emily']"
  role: "[Job title — e.g., VP Engineering]"
  reports_to: "[Their boss — e.g., CTO]"
  team_size: "[How many people they manage]"
  experience: "[Years in role, career background]"

  goals:
    professional: "[What they're measured on — e.g., ship velocity, team retention]"
    personal: "[Career aspiration — e.g., become CTO, build a great team]"

  frustrations:
    daily: "[What annoys them every day]"
    strategic: "[What's blocking their big goals]"

  objections:
    - "[Why they'd say no — e.g., 'my team hates new tools']"
    - "[Why they'd delay — e.g., 'not a priority this quarter']"
    - "[Why they'd choose a competitor — e.g., 'Linear is good enough']"

  channels:
    reads: "[Blogs, newsletters — e.g., Pragmatic Engineer]"
    social: "[Where they're active — e.g., LinkedIn, Twitter/X, HN]"
    communities: "[Slack groups, Discord, subreddits]"
    events: "[Conferences, meetups]"

  buying_insights:
    priority_initiative: "[What trigger made them look for a solution NOW?]"
    success_factors: "[What does 'winning' look like after buying?]"
    perceived_barriers: "[What's holding them back from switching?]"
    decision_criteria: "[How do they compare you vs. alternatives?]"
    buyers_journey: "[How did they find you? Who else was involved?]"
```

---

## Filled Persona Example: Engineering Emily

```yaml
persona:
  name: "Engineering Emily"
  role: "VP Engineering"
  reports_to: "CTO"
  team_size: "25-40 engineers across 4 squads"
  experience: "12 years in engineering, 4 years in management, ex-Stripe"

  goals:
    professional: "Ship the product roadmap on time, reduce engineer attrition below 10%"
    personal: "Become CTO within 3 years, be known as someone who builds great teams"

  frustrations:
    daily: "Spends 2 hours/day in status meetings that could be async"
    strategic: "Can't show the board what engineering is actually delivering vs. the investment"

  objections:
    - "My engineers hate switching tools, last migration took 3 months"
    - "We tried this category before (Jira), got burned"
    - "Linear is working okay, the pain isn't acute enough to switch"

  channels:
    reads: "The Pragmatic Engineer, LeadDev blog, Will Larson"
    social: "LinkedIn (posts about engineering leadership), Twitter/X (follows dev tools people)"
    communities: "Engineering Leaders Slack, LeadDev Slack, r/ExperiencedDevs"
    events: "LeadDev London, StaffPlus NYC, local CTO dinners"

  buying_insights:
    priority_initiative: "Board asked for engineering metrics. Current tools can't produce them without 8h/month manual work."
    success_factors: "Automated reporting to board, engineers don't complain, can see blockers before standup"
    perceived_barriers: "Migration cost (time + engineer frustration), security review (SSO/SOC2), proving ROI in first quarter"
    decision_criteria: "GitHub integration depth, time-to-value (<1 week), SSO/SAML, reporting quality, pricing per-seat"
    buyers_journey: "Googled 'GitHub project management', found TaskPilot blog post. Checked G2 reviews. Asked in Engineering Leaders Slack. Signed up for trial after seeing a demo video on LinkedIn."
```

---

## Validation Checklist

After building your ICP + personas, ask:

```
[ ] Would your 5 best customers match this ICP?
[ ] Would your 3 worst customers NOT match?
[ ] Can you name 3 real communities where this persona hangs out?
[ ] Do the pain signals come from real conversations (not assumptions)?
[ ] Is the buying process based on actual deal data (not guesses)?
[ ] Have you talked to at least 5 people who match the persona?
```

If you can't check all boxes, you're guessing. Go talk to more customers.
