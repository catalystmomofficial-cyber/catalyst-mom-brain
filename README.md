# Catalyst Mom — Business Brain

This repo is the shared memory for Catalyst Mom. It's a plain-Markdown,
git-tracked knowledge base that any AI agent (Claude Code, ChatGPT, OpenClaw,
custom assistants, etc.) or human team member can read before doing work —
so nobody has to re-explain the business from scratch every time.

## How it's organized

```
business/
  01-overview.md                 — what Catalyst Mom is, mission, the three stages
  02-brand-voice.md               — tone, voice rules, what to say / not say
  03-programs-and-pricing.md      — products, programs, pricing
  04-platform.md                  — app architecture, tech stack, sections
  05-coaching-and-community.md    — human + AI coaching, community, affiliate, gamification
  06-competitive-positioning.md   — how we compare to other platforms
  07-safety-and-compliance.md     — medical disclaimers, Catalyst Standard, emergency protocol

products/
  00-index.md                     — product catalog index
  fertile-ground-ttc.md           — TTC program detail
  birth-ready-pregnancy.md        — Pregnancy program detail
  core-restore-postpartum.md      — Postpartum program detail
  app-subscriptions-and-addons.md — subscriptions, starter kit, open items

marketing/
  00-overview.md                  — funnel, channels, how to use this folder
  channels.md                     — Pinterest, Instagram, assessment funnel
  content-pillars.md              — content themes per stage
  campaign-log.md                 — running log of campaigns + results (template)

customers/
  00-overview.md                  — assessment data model, score tiers
  segment-ttc.md                  — TTC segment: goals, obstacles, messaging
  segment-pregnancy.md            — Pregnancy segment
  segment-postpartum.md           — Postpartum segment
```

## How to use this with an AI agent

Point any agent at this repo (or clone it alongside your project) and tell it
to read `AGENTS.md` first. That file is the entry point — it tells the agent
what's here and how to use it.

## How to add to this brain

- Keep facts in the right file (don't duplicate — update in place).
- Write in plain Markdown, short sections, no fluff.
- If something changes in the business (new pricing, new program, new policy),
  update the relevant file and commit with a clear message — this repo is the
  source of truth, so agents reading it later will act on what's written here.

## Roadmap

Covered so far: business overview, brand voice, products, marketing
foundations, and customer segments. Planned additions:
- Real campaign results (fill in `marketing/campaign-log.md` as campaigns run)
- Real assessment-response distributions (fill in `customers/00-overview.md`
  open items once Supabase data is available)
- Support history / FAQ patterns
- Financial/ops knowledge (if useful for agent-driven tasks)
