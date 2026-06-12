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

This brain currently covers **business overview & brand voice**. Planned
additions:
- `products/` — detailed catalog per offering
- `marketing/` — campaigns, content calendar, channel performance, what's worked
- `customers/` — segments, personas, support history
