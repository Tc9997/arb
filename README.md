# Token Arbitrage: Programmatic SEO Content Engine

## One-Line Thesis

Spend $0.02 in AI tokens to generate a page that earns $0.10-0.50/month in ad revenue forever.

---

## The Business

Build a network of niche content sites where every page targets a specific long-tail search query that no one else has bothered to answer. Monetize with premium display ads (Mediavine/Raptive). One person, no employees, no customers to support, no fulfillment.

**Why it works:** There are millions of queries searched 30-200 times/month that have no good result. No human will write an article for 50 visits/month. But a machine will, and 10,000 of those pages = 300,000+ visits/month.

---

## Unit Economics

| Item | Number |
|------|--------|
| Cost to generate 1 page (Haiku 4.5 @ $1/$5 per M tokens, ~1200 words) | $0.01-0.03 |
| Cost to generate 10,000 pages | $100-300 |
| Hosting (Vercel/Cloudflare) | $20/mo |
| Domain | $12/yr |
| Display ad RPM (US traffic, Mediavine) | $15-35 per 1,000 views |
| Revenue per page at 40 visits/mo, $20 RPM | $0.80/mo |
| Revenue at 10,000 pages × 40 visits × $20 RPM | **$8,000/mo** |
| Revenue at 10,000 pages × 80 visits × $25 RPM | **$20,000/mo** |
| Ongoing cost | ~$20/mo hosting |
| **Gross margin at scale** | **~99%** |

Total upfront investment: ~$500 in tokens + 3-4 weeks of build time.
Break-even: Month 4-6 (after Google indexes and ranks).

---

## How It Works

```
Niche Research (Week 1)
    → Find query pattern with 10,000+ variations, <30 KD each

Data Layer (Week 2)
    → Build structured dataset from public sources (BLS, FDA, USDA, etc.)

Content Generation (Week 2-3)
    → Claude Haiku Batch API (50% discount) generates 10,000 pages
    → Each page: real data + LLM synthesis + structured template
    → Cost: ~$150-200 using batch pricing

Site Build (Week 3)
    → Static site (Astro/Next.js) on Cloudflare Pages
    → Programmatic routes from data layer
    → Internal linking mesh between related pages

Seed Authority (Week 3-4)
    → Write 10 genuinely great "hub" articles manually or with Opus
    → These earn backlinks → authority flows to long-tail pages
    → Submit sitemap to Google Search Console

Wait (Month 2-4)
    → Google indexes pages over 2-8 weeks
    → Rankings start appearing month 3-4
    → Apply for Mediavine at 50,000 sessions/mo (usually month 4-6)

Scale (Month 6+)
    → Analyze which pages rank → double down on similar patterns
    → Add 5,000-10,000 more pages in adjacent query patterns
    → Launch site #2 in different niche
    → Repeat
```

---

## Niche Selection Criteria

The niche must have ALL of these:

1. **10,000+ query variations** from a single pattern (e.g., "[X] vs [Y]", "[X] in [city]")
2. **Real structured data** backing each page (not hallucinated content)
3. **Low keyword difficulty** (<30 KD per individual query)
4. **US search intent** (highest ad RPMs: $20-35 vs $5-10 internationally)
5. **Informational, not transactional** (no one is buying — they're learning. This means low competition from businesses.)
6. **Evergreen** (no expiring content that needs constant updates)

### Strong Niche Candidates

| Niche | Query Pattern | Est. Pages | Data Source |
|-------|--------------|-----------|-------------|
| Medication interactions | "[drug A] and [drug B]" | 50,000+ | FDA/NIH public databases |
| Job salary by city | "[title] salary in [city]" | 30,000+ | BLS Occupational Outlook |
| Dog/cat breed comparisons | "[breed] vs [breed]" | 20,000+ | AKC/breed registries |
| Plant growing guides | "how to grow [plant] in [zone]" | 15,000+ | USDA hardiness data |
| Food nutrition lookup | "calories in [food] [preparation]" | 40,000+ | USDA FoodData Central |
| College comparisons | "[school] vs [school]" | 25,000+ | NCES/IPEDS public data |
| Tool/product alternatives | "[product] alternatives" | 10,000+ | Product databases |

---

## Risk & Mitigation

| Risk | Likelihood | Mitigation |
|------|-----------|------------|
| Google doesn't rank the site | Medium | Invest in 10 high-quality hub pages that earn links; build on aged domain if possible |
| Google penalizes AI content | Low | Each page uses real data + unique synthesis; passes helpful content guidelines |
| Niche is more competitive than expected | Medium | Validate with Ahrefs before building; pivot niche in 2 weeks if needed |
| Mediavine rejects the site | Low | Fallback to Ezoic (10k sessions minimum) or Google AdSense while growing |
| Ad RPM drops seasonally | Certain | Q1 RPMs drop 30-40% vs Q4; plan cash flow around this |
| Content goes stale | Low if evergreen niche | Choose niches where data doesn't change yearly |

---

## Why One Person Can Run This

- **No customers.** Visitors come from Google, look at page, see ads, leave. No support tickets, no refunds, no sales calls.
- **No inventory.** Digital pages on a CDN.
- **No employees.** The LLM does the writing. The static site generator does the building. Cloudflare does the serving.
- **No ongoing content creation.** Pages are generated once and earn indefinitely. Unlike a blog that dies without weekly posts, a programmatic site's 10,000 pages are durable.
- **Marginal cost of next page ≈ $0.** Once the template and data pipeline exist, generating 10,000 more pages costs pennies.

---

## Milestones

| Milestone | Timeline | Metric |
|-----------|----------|--------|
| Niche selected, data sourced | Week 1 | Query pattern identified, 10k+ variations confirmed |
| 10,000 pages live | Week 3-4 | Site deployed, sitemap submitted |
| First organic traffic | Month 2-3 | Google Search Console showing impressions |
| 10,000 sessions/mo | Month 3-4 | Apply for Ezoic |
| 50,000 sessions/mo | Month 4-6 | Apply for Mediavine |
| $5,000/mo revenue | Month 6-8 | First site profitable |
| Site #2 launched | Month 6-8 | Second niche, same playbook |
| $15,000/mo combined | Month 9-12 | Two sites at scale |

---

## The Math That Matters

```
Token cost to generate 10,000 pages:     ~$200  (one-time)
Monthly hosting:                          ~$20
Monthly revenue at 50k sessions, $20 RPM: ~$1,000
Monthly revenue at 300k sessions, $25 RPM: ~$7,500
Monthly revenue at 500k sessions, $30 RPM: ~$15,000

Return on $200 token investment at $7,500/mo = 37.5x per month
```

This is the purest expression of token arbitrage:
you spend tokens once, and the output earns money every month, forever.
