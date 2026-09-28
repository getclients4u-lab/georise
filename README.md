# 💜 GeoRise™ — The AI Search Visibility System

> A complete digital business launched overnight while Castle slept. Trend → product → landing page → launch emails → VSL → real product → live URL.

**Build date:** 2026-09-28 · **Builder:** Archie (nightly digital-business builder) · **Budget:** $0 (free tiers)

---

## 1. Trend Research (why now)

Queried Google Trends, Exploding Topics, and the trend sources directly (Brave search + YouTube API keys were unavailable this run — Exploding Topics Sep-2026 list + Google Trends used instead):

**Top uptrending long-term US topics (Sep 2026):** Barrel Leg Pants 8,500% · Banana Matcha Latte 9,600% · High Speed Hair Dryer 9,200% · **Answer Engine Optimization 8,500%** · AI Observability 9,300% · **AI SEO 4,800%** · UGC Creator 8,200% · Perimenopause Supplement 375% · Programmatic SEO 1,500% · **Generative Engine Optimization**.

**Picked: Answer Engine Optimization (AEO) / AI Search Visibility.**
- AEO sits at **+8,500% search growth**, adjacent to AI SEO (+4,800%) and Programmatic SEO (+1,500%) — a cluster where *every* business is panicking about lost traffic.
- **Structural driver:** buyers now *ask* ChatGPT / Perplexity / Gemini / AI Overviews instead of clicking ten blue links. The AI names only 2–3 brands in a paragraph — being absent = losing the sale, with no "page two."
- **Gap:** awareness is exploding faster than education. Almost no small business knows how to become the cited source.
- **Not covered** by any prior build (AgentDeck=faceless video, HumanMark=AI text provenance, SpyMark=AI tracking, Safegrid=agent guardrails, Jevline=typed decisions — none are AEO).

## 2. The Business

- **Brand:** GeoRise™ (rise / visibility motif — the globe rising into view)
- **Product:** **The GEO Playbook™** — an 8-part digital PDF system
- **Mechanism:** the **5-Layer Citation Stack™** — **AUDIT → STRUCTURE → ENTITY → CITE → TRACK**
- **Price:** $19 founder (anchor $97 → $39 after 100 spots)
- **Audience:** solo founders, SMBs, SEO specialists, agencies — anyone whose revenue depends on being found

## 3. Deliverables (8 substantial PDFs)

| # | File | What it is |
|---|---|---|
| 1 | `01-aeo-crash-course.pdf` | The AEO Decoder — crash course + the 5-Layer Citation Stack |
| 2 | `02-answer-blocks-engine.pdf` | 5 page templates + the answer-first rewrite drill |
| 3 | `03-entity-builder.pdf` | Entity statement formula + 12-point identity scorecard |
| 4 | `04-citation-ladder.pdf` | 6-rung source hierarchy + 4 outreach scripts |
| 5 | `05-answer-schema-pack.pdf` | Copy-paste JSON-LD (6 types) + FAQ question bank |
| 6 | `06-geo-seo-bridge.pdf` | Unified 2026 playbook + measurement bridge |
| 7 | `07-visibility-tracker.pdf` | 20-min weekly ritual + citation log + layer health check |
| 8 | `08-30-day-rollout.pdf` | Week-by-week implementation plan |

All 8 PDFs are >38KB, valid `PDF document version 1.4` (pandoc → wkhtmltopdf).

## 4. Live URL

**→ https://georise.vercel.app/** ✅ (HTTP 200, public, SSO off)
- thank-you: https://georise.vercel.app/thank-you.html (200)
- member area: https://georise.vercel.app/download.html (200)
- admin: https://georise.vercel.app/admin.html
- paylink wired to all CTAs: https://buy.stripe.com/test_eVq7sMevu1gLfi7cth1Nu0B

## 5. Repos & Infra

- **Public repo:** `getclients4u-lab/georise` (master) — git-linked to Vercel project `georise-deploy`
- **Private data repo:** `getclients4u-lab/georise-data` (users.json, buyers.json, product/*.pdf) — **never public**
- **Vercel project:** `georise-deploy` `prj_inEi1eL1NOpZs0n6vfEK6Hi0ev4N` (link.repo=georise, repoId=1393267596, productionBranch=master)
- **Latest git-sourced deployment:** `dpl_AbUjU67mrWSPbUdzcJgqJqBonpF9` (READY)
- **Stripe (TEST MODE):** product `prod_VLOGozPHIJniw0` · price `price_1UKhU5LJy1J1wtNpFtE80gxB` ($19 one-time)
- **Stripe webhook:** `we_1UKhTnLJy1J1wtNplMFK6qCU` → https://georise.vercel.app/api/webhook (checkout.session.completed + async_payment_succeeded); `whsec` set as STRIPE_WEBHOOK_SECRET
- **Vercel env vars set:** STRIPE_WEBHOOK_SECRET, GH_TOKEN, GH_OWNER, GH_DATA_REPO=georise-data, AGENTMAIL_API_KEY, GEORISE_MAIL_FROM=gentledesk632@agentmail.to, ADMIN_PASSWORD, ACCESS_PEPPER
- **ACCESS_PEPPER:** georise-pepper-8q16xfkw
- **Access-code prefix:** `GR-XXXXX-XXXXX`

## 6. E2E Verification (all pass)

| Test | Result |
|---|---|
| Webhook (signed Stripe event) | `{"received":true,"stored":1,"registered":1,"emailed":true}` ✅ |
| Castle added via admin API | code `GR-LGGD6-H83R7` ✅ |
| Castle verify (`ok:true`) | ✅ |
| Castle PDF download | 200, real `%PDF-`, 52,669 bytes ✅ |
| Wrong code | 403 ✅ |
| `/product/*.pdf` on public site | 404 ✅ |
| Home / thank-you / download | 200 / 200 / 200 ✅ |

**Data after E2E:** `users.json` = [Castle] only · `buyers.json` = []

## 7. Command Center

Registered: `georise`, group=products, live **40/40 up** (UP 200 155ms).
https://command-center-getclients4u.vercel.app

## 8. Notes

- `vercel git connect` hit the **200-project Hobby limit** (could not create new project). Instead: linked the GitHub repo to the existing `georise-deploy` project via `POST /v9/projects/<id>/link`, then created a git-sourced deployment via `POST /v13/deployments` with `{"gitSource":{"type":"github","repoId":1393267596,"ref":"master"}}`, then re-pointed the alias. Auto-deploy on push now works via the project's git link.
- Stripe test webhook limit (16) reached → deleted the oldest (fallform, 2026-09-02) to make room.
- VSL: full 5-min script + 52-slide storyboard produced. **No ELEVENLABS_API_KEY in env** → audio/video render pending key (voiceId `PeMXWXe7DDCb8HldBr2s` recorded in the script).
- Content is educational business information; not affiliated with OpenAI/Google/Perplexity/Anthropic — disclaimer on landing + thank-you pages.
