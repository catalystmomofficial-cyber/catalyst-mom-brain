# Platform Architecture

## Assessment Funnel — catalystmom.online
- Three separate assessments: TTC, Pregnancy, Postpartum
- 10-11 questions per assessment
- Email capture at question 8 — "Unlock Your Results"
- Results page shows a personalised **Maternal Wellness Score** (0-100)
- Score tiers: Low (Early Foundations), Medium (Building Momentum), High
  (Strong Foundation)
- Assessment data passed via URL parameters to app signup: `name`, `email`,
  `score`, `tier`, `stage`, `primary_goal`, `biggest_obstacle`,
  `birth_experience`
- Cookie consent banner active

## App — catalystmomofficial.com
- Progressive Web App (PWA) built with React/Vite via Lovable
- Backend: Supabase
- Payments: Stripe
- Push notifications: Firebase Cloud Messaging (FCM)
- AI integrations: OpenAI, ElevenLabs
- Deployment: Netlify via GitHub auto-deployment
- Installable on mobile home screen — no app store required

## App Sections
- Dashboard (stage-specific: TTC / Pregnancy / Postpartum)
- Workouts
- Recipes
- Wellness (mood, sleep, self-care, hydration tracking)
- Community
- Progress
- Affiliate Dashboard

## Social Media
- Instagram: https://www.instagram.com/catalyst_mom
- Pinterest: https://www.pinterest.com/catalystmoms/ — 12M+ monthly views
  (primary organic traffic source)

## Contact
- Support: admin@catalystmom.online
- App login: catalystmomofficial.com/login
- Assessment: catalystmom.online
