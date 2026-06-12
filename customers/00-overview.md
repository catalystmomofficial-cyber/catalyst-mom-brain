# Customers — Overview

## How Segments Are Defined

Every user enters through one of three stage-specific assessments
(catalystmom.online), which capture this data — carried into the app via URL
params (see `../business/04-platform.md`):

| Field | Description |
|---|---|
| `stage` | TTC / Pregnancy / Postpartum |
| `score` | Maternal Wellness Score, 0-100 |
| `tier` | Low (Early Foundations) / Medium (Building Momentum) / High (Strong Foundation) |
| `primary_goal` | What the user is most trying to achieve |
| `biggest_obstacle` | What's currently in the way |
| `birth_experience` | (Postpartum/Pregnancy) C-section, vaginal, etc. |

This is the richest source of real customer-segment data — **the assessment
answers themselves**. As assessment response data becomes available (via
Supabase), this brain should be updated with actual distributions (e.g. "X%
of postpartum users select C-section as birth_experience").

## Segment Files
- `segment-ttc.md`
- `segment-pregnancy.md`
- `segment-postpartum.md`

Each file describes the segment's likely goals, obstacles, and which
resources/program features map to them — useful for personalising content,
email sequences, and AI coaching responses.

## Score Tiers (apply across all stages)
- **Low / Early Foundations** — needs the most structure and reassurance;
  good candidate for the $35 Core Restore entry offer (postpartum) or
  starter content (other stages)
- **Medium / Building Momentum** — has some habits in place; messaging
  should focus on consistency and the 14-day Progression Sync milestone
- **High / Strong Foundation** — already doing well; messaging can focus on
  optimization, community leadership, or the affiliate program

## Open Items for This Brain
- [ ] Pull real `primary_goal` / `biggest_obstacle` distributions from
      Supabase once available
- [ ] Add testimonial/case-study snippets per segment (with permission)
- [ ] Document email/lifecycle sequences per tier
