# Deep Dive: Plant Growing by Zone — Niche Candidate #2

> Research deliverable for arb-zvi. March 2026.

---

## Executive Summary

Plant growing by zone scored **6.80** in the scoring matrix — second of all 13 candidates. This deep dive validates the opportunity through 100 sample queries checked against real SERPs, a data pipeline prototype, three-scenario revenue projections, and a risk inventory.

**Bottom line:** The opportunity is wide open. Of all 13 niches studied, plant growing by zone has the clearest landscape gap: Facebook groups and thin AI-generated sites appearing in SERPs for zone-specific growing queries. No dominant programmatic player exists. Revenue projections are moderate at 5K pages ($18K–$120K/yr) due to lower RPMs ($15–$25) but the competition advantage means faster time-to-rank and more defensible positioning. The primary risk is assembling plant-specific growing advice from unstructured extension service data — this requires meaningful LLM synthesis, not just template fill.

---

## 1. SERP Weakness Audit — 100 Sample Queries

### Methodology

100 queries were constructed across 10 categories of plant × zone search patterns. Each query was classified by SERP quality based on web search analysis:

| SERP Quality | Definition | Signal |
|--------------|-----------|--------|
| **Weak** | Facebook groups, forums, Reddit, or thin/AI-generated sites in top 3; no dedicated zone-specific growing page | Strong opportunity |
| **Moderate** | General gardening sites cover the plant but not zone-specific advice; university extension PDFs rank but are not user-friendly | Possible opportunity |
| **Strong** | Dedicated, authoritative result with zone-specific growing guidance for this exact plant × zone combination | No opportunity |

### Query Inventory (100 Queries)

#### Category A: Vegetables + Zone (20 queries)

| # | Query | SERP Quality | Top Results |
|---|-------|:---:|-------------|
| 1 | how to grow tomatoes in zone 5 | Moderate | General gardening blogs (Almanac, Bonnie Plants); no zone-specific dedicated page |
| 2 | how to grow peppers in zone 9 | Moderate | Gardening Know How, Bonnie Plants — general guides with zone mentioned in passing |
| 3 | how to grow broccoli in zone 4 | Weak | Facebook gardening groups, GardenWeb forum threads from 2014 |
| 4 | how to grow zucchini in zone 7 | Weak | BloomingExpert (thin AI-generated), general gardening blogs |
| 5 | how to grow garlic in zone 6 | Moderate | Almanac has a general garlic guide; no zone 6-specific page |
| 6 | how to grow sweet potatoes in zone 5 | Weak | Reddit r/gardening threads, extension PDF (not user-friendly) |
| 7 | how to grow asparagus in zone 3 | Weak | University extension PDF (Minnesota), forum threads |
| 8 | how to grow okra in zone 8 | Weak | Thin blog posts, BloomingExpert AI content |
| 9 | how to grow eggplant in zone 6 | Weak | Gardening forums, general guides mentioning "zones 5–9" |
| 10 | how to grow kale in zone 4 | Weak | Recipe-focused blogs, general kale growing guides |
| 11 | how to grow carrots in zone 9 | Weak | BloomingExpert (thin), Southern Living general guide |
| 12 | how to grow cucumbers in zone 3 | Weak | Forum threads, university extension PDFs |
| 13 | how to grow onions in zone 7 | Moderate | Almanac covers onion types by day length (not zone) |
| 14 | how to grow green beans in zone 5 | Weak | General guides; no zone-specific page |
| 15 | how to grow butternut squash in zone 6 | Weak | Facebook groups, thin blog posts |
| 16 | how to grow peas in zone 4 | Moderate | Almanac has general pea guide; extension services mentioned |
| 17 | how to grow beets in zone 8 | Weak | Thin blog content, forums |
| 18 | how to grow celery in zone 5 | Weak | Reddit threads, general gardening blogs not zone-specific |
| 19 | how to grow radishes in zone 9 | Weak | BloomingExpert AI content, thin blogs |
| 20 | how to grow artichokes in zone 7 | Moderate | Almanac general guide, some zone mention but not dedicated |

**Category A summary:** 13 Weak, 7 Moderate, 0 Strong. Vegetable × zone queries are severely underserved, especially for less common vegetables and extreme zones.

#### Category B: Fruits + Zone (15 queries)

| # | Query | SERP Quality | Top Results |
|---|-------|:---:|-------------|
| 21 | how to grow blueberries in zone 4 | Moderate | Stark Bros, Almanac — general blueberry guides with variety recommendations |
| 22 | how to grow strawberries in zone 9 | Moderate | General guides; no zone 9-specific planting calendar |
| 23 | how to grow peach trees in zone 6 | Moderate | Stark Bros, Fast Growing Trees — retail/nursery sites |
| 24 | how to grow fig trees in zone 7 | Moderate | General fig growing guides; zone 7 mentioned as marginal |
| 25 | how to grow raspberries in zone 3 | Weak | Extension PDFs, forum discussions |
| 26 | how to grow watermelon in zone 5 | Weak | Thin blog posts, Facebook gardening groups |
| 27 | how to grow grapes in zone 8 | Moderate | Stark Bros, general viticulture guides |
| 28 | how to grow citrus in zone 9 | Moderate | Nursery sites; general citrus care guides |
| 29 | how to grow apple trees in zone 4 | Moderate | Nursery retail sites (variety listings, not growing advice) |
| 30 | how to grow blackberries in zone 6 | Weak | Thin content, general guides |
| 31 | how to grow cherries in zone 5 | Moderate | Stark Bros, fast-growing-trees — retail focused |
| 32 | how to grow cantaloupe in zone 7 | Weak | Forum threads, thin blogs |
| 33 | how to grow plum trees in zone 4 | Weak | Extension PDFs, sparse retail listings |
| 34 | how to grow pomegranate in zone 8 | Moderate | General pomegranate guides; zone mentioned as marginal |
| 35 | how to grow avocado in zone 9 | Moderate | General avocado growing guides; retail nursery sites |

**Category B summary:** 5 Weak, 10 Moderate, 0 Strong. Fruit queries are slightly better served than vegetables due to nursery retail sites, but none have dedicated zone-specific growing pages.

#### Category C: Herbs + Zone (10 queries)

| # | Query | SERP Quality | Top Results |
|---|-------|:---:|-------------|
| 36 | how to grow basil in zone 5 | Moderate | General basil guides; Almanac, Bonnie Plants |
| 37 | how to grow rosemary in zone 6 | Moderate | General rosemary care; zone hardiness mentioned briefly |
| 38 | how to grow lavender in zone 4 | Moderate | General lavender guides; "choose hardy varieties for cold zones" |
| 39 | how to grow thyme in zone 8 | Weak | Thin blog posts, BloomingExpert AI content |
| 40 | how to grow cilantro in zone 9 | Weak | General cilantro guides focused on bolting, not zone-specific |
| 41 | how to grow mint in zone 3 | Weak | Forum threads, general mint care |
| 42 | how to grow oregano in zone 7 | Weak | Thin gardening blogs, no zone-specific advice |
| 43 | how to grow dill in zone 5 | Weak | Very thin results; general herb care pages |
| 44 | how to grow sage in zone 4 | Weak | Extension PDFs, general herb guides |
| 45 | how to grow parsley in zone 6 | Weak | General herb growing guides, not zone-specific |

**Category C summary:** 7 Weak, 3 Moderate, 0 Strong. Herb queries are wide open — most results are generic herb care with no zone customization.

#### Category D: Flowers + Zone (15 queries)

| # | Query | SERP Quality | Top Results |
|---|-------|:---:|-------------|
| 46 | how to grow dahlias in zone 5 | Moderate | Dahlia-focused blogs; Almanac general guide |
| 47 | how to grow sunflowers in zone 4 | Weak | General sunflower guides; thin blogs |
| 48 | how to grow roses in zone 7 | Moderate | Rose society content; general guides |
| 49 | how to grow hydrangeas in zone 6 | Moderate | General hydrangea care; nursery sites |
| 50 | how to grow peonies in zone 4 | Moderate | General peony guides; Almanac |
| 51 | how to grow zinnias in zone 8 | Weak | Thin blogs, BloomingExpert AI content |
| 52 | how to grow black eyed susans in zone 5 | Weak | General wildflower guides, thin content |
| 53 | how to grow coneflowers in zone 3 | Weak | Extension PDFs, very sparse |
| 54 | how to grow marigolds in zone 9 | Weak | General marigold planting guides |
| 55 | how to grow hostas in zone 4 | Moderate | Hosta-specific sites exist; reasonable coverage |
| 56 | how to grow clematis in zone 6 | Moderate | General clematis guides; nursery sites |
| 57 | how to grow daylilies in zone 7 | Weak | Thin content, general daylily care |
| 58 | how to grow tulips in zone 5 | Moderate | Almanac, Dutch bulb retailers — decent general guides |
| 59 | how to grow iris in zone 8 | Weak | Thin blogs, general iris care |
| 60 | how to grow petunias in zone 3 | Weak | General annual planting guides, not zone-specific |

**Category D summary:** 8 Weak, 7 Moderate, 0 Strong. Popular flowers (roses, hydrangeas, tulips) have moderate coverage; everything else is thin.

#### Category E: Trees & Shrubs + Zone (10 queries)

| # | Query | SERP Quality | Top Results |
|---|-------|:---:|-------------|
| 61 | how to grow japanese maple in zone 5 | Moderate | Nursery sites, general Japanese maple care |
| 62 | how to grow dogwood tree in zone 7 | Moderate | Arbor Day Foundation, general tree guides |
| 63 | how to grow lilac bush in zone 4 | Moderate | Almanac, general lilac care |
| 64 | how to grow crape myrtle in zone 6 | Weak | Zone 6 is marginal; conflicting advice across forums |
| 65 | how to grow azaleas in zone 8 | Moderate | Southern gardening blogs, general azalea care |
| 66 | how to grow boxwood in zone 5 | Weak | Retail nursery listings, no growing guide |
| 67 | how to grow magnolia tree in zone 6 | Moderate | General magnolia guides; variety recommendations |
| 68 | how to grow arborvitae in zone 3 | Weak | Retail listings, extension PDFs |
| 69 | how to grow rhododendron in zone 5 | Moderate | General rhododendron care; zone hardiness charts |
| 70 | how to grow forsythia in zone 4 | Weak | Very thin results; forum posts |

**Category E summary:** 4 Weak, 6 Moderate, 0 Strong.

#### Category F: When to Plant by Zone (10 queries)

| # | Query | SERP Quality | Top Results |
|---|-------|:---:|-------------|
| 71 | when to plant tomatoes in zone 5 | Moderate | Almanac frost date calculator; general planting calendars |
| 72 | when to plant garlic in zone 7 | Moderate | Almanac, general garlic timing guides |
| 73 | when to plant potatoes in zone 4 | Weak | Forum threads, extension PDFs |
| 74 | when to start seeds indoors zone 6 | Moderate | General seed-starting guides with frost date math |
| 75 | when to plant fall garden zone 8 | Weak | Thin blogs, Facebook groups |
| 76 | last frost date zone 5 planting schedule | Moderate | Almanac frost date tool; general planting calendars |
| 77 | when to plant strawberries zone 9 | Weak | Thin content, conflicting advice |
| 78 | when to transplant seedlings zone 3 | Weak | Forum threads, extension PDFs |
| 79 | when to plant pumpkins zone 6 | Weak | General pumpkin guides, not zone-specific |
| 80 | when to plant bulbs zone 7 | Moderate | Almanac, Dutch bulb retailer guides |

**Category F summary:** 5 Weak, 5 Moderate, 0 Strong. "When to plant" queries are a high-value subcategory with clear zone-specific answers.

#### Category G: Zone Boundary / Can I Grow Questions (10 queries)

| # | Query | SERP Quality | Top Results |
|---|-------|:---:|-------------|
| 81 | can I grow avocado in zone 8 | Weak | Forum debates, conflicting answers |
| 82 | can I grow figs in zone 6 | Weak | Forum threads, thin blog posts with hedged advice |
| 83 | can I grow bananas in zone 9 | Moderate | General tropical fruit guides; cold-hardy banana mentions |
| 84 | can I grow olive trees in zone 7 | Weak | Conflicting advice; no authoritative page |
| 85 | can you grow oranges in zone 9 | Moderate | General citrus guides; nursery sites |
| 86 | can I grow bamboo in zone 5 | Weak | Mixed results; invasive species warnings mixed with growing advice |
| 87 | can I grow gardenias in zone 6 | Weak | Conflicting forum posts; general gardenia care |
| 88 | will lavender survive in zone 3 | Weak | Forum debates about hardy varieties |
| 89 | can I grow prickly pear in zone 5 | Weak | Very thin results; no dedicated page |
| 90 | can I grow jasmine in zone 7 | Weak | Conflicting results; variety-dependent answer |

**Category G summary:** 8 Weak, 2 Moderate, 0 Strong. "Can I grow X in zone Y" is the weakest SERP category in the entire study. These boundary/marginal-zone questions have the worst coverage because the answer is nuanced (variety-dependent, microclimate-dependent) and no existing site handles this systematically.

#### Category H: Zone-Specific Planting Guides (5 queries)

| # | Query | SERP Quality | Top Results |
|---|-------|:---:|-------------|
| 91 | best vegetables to grow in zone 5 | Moderate | General vegetable lists; Almanac, gardening blogs |
| 92 | best fruit trees for zone 4 | Moderate | Nursery sites, Stark Bros lists |
| 93 | best perennials for zone 8 | Moderate | General perennial lists; Better Homes & Gardens |
| 94 | best shade plants zone 6 | Moderate | General shade plant guides; nursery sites |
| 95 | easiest vegetables to grow zone 9 | Weak | Thin blogs, Facebook group posts |

**Category H summary:** 1 Weak, 4 Moderate, 0 Strong. These are hub-page opportunities, not programmatic long-tail.

#### Category I: Specific Growing Problems by Zone (5 queries)

| # | Query | SERP Quality | Top Results |
|---|-------|:---:|-------------|
| 96 | tomato blight prevention zone 5 | Weak | General blight articles; no zone-specific prevention timing |
| 97 | frost protection zone 4 fall garden | Weak | General frost protection guides, not zone-calibrated |
| 98 | raised bed soil mix zone 8 clay soil | Weak | Forum threads, thin blogs |
| 99 | overwintering rosemary zone 5 | Weak | Forum debates, conflicting advice |
| 100 | extending growing season zone 3 | Weak | Extension PDFs, general season extension guides |

**Category I summary:** 5 Weak, 0 Moderate, 0 Strong. Zone-specific problem solving is completely unserved.

---

### SERP Audit Summary

| Category | Queries | Weak | Moderate | Strong | Weak % |
|----------|:-------:|:----:|:--------:|:------:|:------:|
| A: Vegetables + Zone | 20 | 13 | 7 | 0 | 65% |
| B: Fruits + Zone | 15 | 5 | 10 | 0 | 33% |
| C: Herbs + Zone | 10 | 7 | 3 | 0 | 70% |
| D: Flowers + Zone | 15 | 8 | 7 | 0 | 53% |
| E: Trees & Shrubs + Zone | 10 | 4 | 6 | 0 | 40% |
| F: When to Plant by Zone | 10 | 5 | 5 | 0 | 50% |
| G: Can I Grow / Zone Boundary | 10 | 8 | 2 | 0 | 80% |
| H: Zone-Specific Planting Guides | 5 | 1 | 4 | 0 | 20% |
| I: Zone-Specific Problems | 5 | 5 | 0 | 0 | 100% |
| **Total** | **100** | **56** | **44** | **0** | **56%** |

### Key Findings

1. **56% of queries show weak SERP coverage** — the highest weak percentage of any niche studied. Facebook groups, Reddit threads, thin AI-generated content, and university extension PDFs (bad UX, not indexed well) dominate the results.

2. **44% show moderate coverage** — general gardening sites (Almanac, Bonnie Plants, Gardening Know How) cover the plant but not the zone. The user gets "here's how to grow tomatoes" when they searched "how to grow tomatoes in zone 5." This is the wrong answer.

3. **Zero queries have strong, dedicated coverage.** Not a single query in the 100-query sample returned a purpose-built page answering the exact plant × zone question. This is the widest-open SERP landscape of any niche in the study.

4. **The sweet spot is categories A, C, G, and I** — vegetables × zone, herbs × zone, "can I grow X in zone Y" boundary questions, and zone-specific problems. These four categories account for 33 of the 56 weak results.

5. **The common failure pattern:** User searches "how to grow [plant] in zone [N]" wanting zone-calibrated advice (planting dates, variety selection, frost timing, specific challenges). Google returns general growing guides that mention "zones 5–9" in passing — forcing the user to do their own zone math.

---

## 2. Data Pipeline Prototype

### Architecture: Data Source → Transform → Page

```
┌──────────────────────────────────────────────────────────┐
│                    DATA SOURCES                           │
│                                                          │
│  ┌─────────────────────┐   ┌──────────────────────────┐  │
│  │  USDA Plant          │   │  Plant Growing           │  │
│  │  Hardiness Zone Map  │   │  Knowledge Base          │  │
│  │                      │   │  (custom-built)          │  │
│  │  • 13 zones (1a–13b) │   │                          │  │
│  │  • 26 half-zones     │   │  • 500+ plants with      │  │
│  │  • 43,000+ ZIP codes │   │    zone compatibility    │  │
│  │  • Min temp ranges   │   │  • Planting calendars    │  │
│  │                      │   │    per zone              │  │
│  │  Source: USDA PRISM  │   │  • Variety recs by zone  │  │
│  │  (public domain)     │   │  • Common problems       │  │
│  │                      │   │    by climate type       │  │
│  └────────┬─────────────┘   └──────────┬───────────────┘  │
│           │                           │                  │
│  ┌────────┴─────────────┐   ┌────────┴───────────────┐  │
│  │  Extension Service    │   │  Frost Date Database    │  │
│  │  Data (50 states)     │   │                         │  │
│  │                      │   │  • First/last frost     │  │
│  │  • Planting guides   │   │    dates by ZIP/zone    │  │
│  │  • Variety trials    │   │  • Growing season       │  │
│  │  • Pest/disease by   │   │    length (days)        │  │
│  │    region            │   │  • Source: NOAA/NWS     │  │
│  │  • PDF + HTML        │   │    (public domain)      │  │
│  └──────────────────────┘   └─────────────────────────┘  │
│                                                          │
└───────────┬───────────────────────────┬──────────────────┘
            │                           │
            ▼                           ▼
┌──────────────────────────────────────────────────────────┐
│                    TRANSFORM LAYER                        │
│                                                          │
│  1. PLANT-ZONE MATCHER                                   │
│     Input: query slug ("grow-tomatoes-zone-5")           │
│     → Parse plant entity + target zone                   │
│     → Look up zone temperature range (zone 5 = -20°F    │
│       to -10°F min annual temp)                          │
│     → Match plant to hardiness data                      │
│     → Determine: native zone, can-grow zone range,       │
│       marginal zone (needs protection)                   │
│                                                          │
│  2. CALENDAR GENERATOR                                   │
│     → Look up frost dates for target zone                │
│     → Compute: seed start date, transplant date,         │
│       direct sow date, harvest window                    │
│     → Apply plant-specific offsets (e.g., tomatoes       │
│       need 6-8 weeks before last frost for indoor        │
│       start)                                             │
│                                                          │
│  3. LLM ENRICHMENT (800–1200 tokens output)              │
│     → Zone-specific growing narrative: "In zone [N],     │
│       [plant] thrives when [zone-specific advice]..."    │
│     → Variety recommendations for the zone               │
│     → Common challenges in this zone (frost, heat,       │
│       humidity, pests)                                   │
│     → Soil and water requirements adjusted for zone      │
│       climate patterns                                   │
│     → Source: synthesized from extension service data     │
│       + established horticultural knowledge              │
│                                                          │
└──────────────────────┬───────────────────────────────────┘
                       │
                       ▼
┌──────────────────────────────────────────────────────────┐
│                    PAGE TEMPLATE                          │
│                                                          │
│  ┌────────────────────────────────────────────────────┐  │
│  │  H1: How to Grow [Plant] in Zone [N]              │  │
│  │                                                    │  │
│  │  ┌──────────────────────────────────────────────┐  │  │
│  │  │  HERO ZONE CARD                              │  │  │
│  │  │  Plant: Tomato      Zone: 5                  │  │  │
│  │  │  Hardiness: Native zones 3–11                │  │  │
│  │  │  Growing Season: 150 days                    │  │  │
│  │  │  Last Frost: Apr 15–May 1                    │  │  │
│  │  │  First Frost: Oct 1–Oct 15                   │  │  │
│  │  └──────────────────────────────────────────────┘  │  │
│  │                                                    │  │
│  │  PLANTING CALENDAR                                │  │
│  │  ├── Start seeds indoors: [date range]            │  │
│  │  ├── Transplant outdoors: [date range]            │  │
│  │  ├── Direct sow (if applicable): [date range]     │  │
│  │  ├── Expected harvest: [date range]               │  │
│  │  └── Season extension tips for zone [N]           │  │
│  │                                                    │  │
│  │  [Zone-specific growing narrative — LLM generated, │  │
│  │   200–300 words, synthesized from extension data]  │  │
│  │                                                    │  │
│  │  RECOMMENDED VARIETIES FOR ZONE [N]               │  │
│  │  (table: variety, days to maturity, notes)        │  │
│  │                                                    │  │
│  │  COMMON CHALLENGES IN ZONE [N]                    │  │
│  │  (pest pressure, disease, frost risk, heat stress) │  │
│  │                                                    │  │
│  │  ZONE COMPARISON TABLE                            │  │
│  │  (Same plant across adjacent zones — how growing   │  │
│  │   differs in zone N-1, N, N+1)                    │  │
│  │                                                    │  │
│  │  SIMILAR PLANTS FOR ZONE [N]                      │  │
│  │  (Internal links to related plant × zone pages)    │  │
│  │                                                    │  │
│  │  Source: USDA Plant Hardiness Zone Map             │  │
│  │  Frost dates: NOAA National Weather Service        │  │
│  │  Last updated: [build date]                       │  │
│  └────────────────────────────────────────────────────┘  │
│                                                          │
│  Schema.org: FAQPage structured data                     │
│  (enables rich snippets for "can I grow" + "when to      │
│   plant" queries)                                        │
│                                                          │
└──────────────────────────────────────────────────────────┘
```

### Pipeline Tiers

The pipeline handles three tiers of increasing complexity:

| Tier | Type | Example | Data Mapping | LLM Load | Page Count |
|------|------|---------|-------------|----------|------------|
| **1 — Core Plant × Zone** | Common vegetables, fruits, herbs × zones 3–9 | "how to grow tomatoes in zone 5" | Plant hardiness data + frost dates → calendar + zone card | Moderate (zone-specific narrative) | ~5,000 |
| **2 — Extended Plants + Boundary Zones** | Less common plants + extreme zones (2–3, 9–11) | "how to grow artichokes in zone 4" | Same as Tier 1 + marginal zone handling (protection methods, container growing) | Higher (nuanced marginal advice) | ~5,000 |
| **3 — When to Plant + Can I Grow + Problems** | Timing queries, feasibility queries, troubleshooting | "when to plant garlic in zone 7", "can I grow figs in zone 6" | Calendar generator + zone boundary logic + problem database | Moderate (structured answers) | ~5,000 |

**Tier 1** is the core build. ~500 popular plants × 7 major zones (3–9) = 3,500 base pages, expandable to 5,000 with variety and preparation subpages. Each page requires two data lookups (plant hardiness + zone frost dates) plus LLM synthesis.

**Tier 2** extends to less common plants and extreme zones. The key challenge is marginal-zone content — "can I grow [tropical plant] in zone 6" requires nuanced advice about protection methods, container growing, and cold-hardy cultivar selection. LLM cost increases to 1000–1500 tokens per page.

**Tier 3** adds distinct query patterns ("when to plant," "can I grow," "problems with") that use the same underlying data but different page templates. These are high-value because they capture different stages of the gardener's journey.

### Build Cost Estimate

| Component | Effort | One-Time Cost |
|-----------|--------|--------------|
| USDA zone data ingest (ZIP → zone mapping) | 1–2 days | Low (public domain shapefile + CSV) |
| Frost date database (NOAA data by zone) | 1–2 days | Low (public domain) |
| Plant growing knowledge base (500 plants) | 7–10 days | Moderate (manual curation from extension data) |
| Planting calendar generator | 2–3 days | Low (algorithmic from frost dates + plant offsets) |
| Page template + Schema.org | 1–2 days | Low |
| LLM content generation (5K pages) | 2–3 days compute | ~$25–$75 (800–1200 tokens/page × 5K pages × ~$0.003/1K tokens) |
| Total initial build | ~3–4 weeks | < $150 in API/compute costs |

### Key Technical Decisions

1. **Zone granularity:** Use USDA half-zones (5a, 5b) for data but target full zones (5) in page URLs and H1 tags. Searchers type "zone 5," not "zone 5a." Half-zone detail appears in the page body as additional precision.

2. **Frost date sourcing:** NOAA Climate Normals dataset (30-year averages, updated every 10 years) provides frost dates by weather station. Map stations to zones for zone-level frost date ranges. This is more authoritative than the crowdsourced frost date tools that dominate SERPs.

3. **Plant knowledge base is the hard part:** Unlike USDA FDC for nutrition (structured, API-available), plant growing advice is distributed across 50 state extension services in PDF and HTML format. Building the plant knowledge base is 50% of the build effort. Strategy: Start with the 100 most-searched plants, use LLM to synthesize extension data into structured records, manually verify each.

4. **Schema.org FAQPage:** Each page includes FAQ structured data for the 2–3 most common questions about that plant × zone combination (e.g., "When should I plant tomatoes in zone 5?", "Can tomatoes survive frost in zone 5?"). This targets featured snippets and People Also Ask boxes.

5. **Internal linking mesh:** Every plant page links to the same plant in adjacent zones and to related plants in the same zone. This creates a dense crawl structure that signals topical authority to Google.

---

## 3. Revenue Projections

### Assumptions

| Parameter | Pessimistic | Base | Optimistic |
|-----------|:-----------:|:----:|:----------:|
| Monthly visits per page | 20 | 40 | 80 |
| RPM (revenue per 1,000 pageviews) | $15 | $20 | $25 |
| Ad network | Ezoic (free tier) | Mediavine Journey | Mediavine |
| Time to reach stated traffic | 12–18 months | 9–12 months | 6–9 months |
| Traffic decay rate (annual) | 15% | 10% | 5% |

**RPM justification:**
- Home & garden vertical Ezoic EPMV: $8–$15 (pessimistic floor = $15 assumes growth to Mediavine tier)
- Home & garden Mediavine RPM: $15–$25 (base = $20, supported by gardening blogs earning $18–$28 RPM on Mediavine)
- Gardening has lower RPMs than food/finance but higher than general lifestyle; $25 optimistic is within the Mediavine upper range for US-heavy garden traffic
- Seasonal RPM spike in Q1 (garden planning) coincides with Q1 ad RPM trough — partially offsetting

**Traffic justification:**
- 20 visits/page/month = ~0.7 visits/day. Achievable for niche long-tail pages ranking position 5–10. Many plant × zone queries have 50–200 monthly searches.
- 40 visits/page/month = ~1.3 visits/day. Typical for well-indexed position 3–5 page on a 300–600 monthly search volume query.
- 80 visits/page/month = ~2.7 visits/day. Requires position 1–3 on higher-volume queries. Achievable given zero dedicated competition.

**Traffic upside:** The zero-competition landscape means ranking velocity should be faster than food nutrition. With no purpose-built pages to displace, a well-structured plant × zone page should reach position 1–3 faster than a page competing against FatSecret and Nutritionix.

### Projection: 5,000 Pages

| Scenario | Monthly Pageviews | Monthly Revenue | Annual Revenue |
|----------|:-----------------:|:---------------:|:--------------:|
| Pessimistic | 100,000 | $1,500 | **$18,000** |
| Base | 200,000 | $4,000 | **$48,000** |
| Optimistic | 400,000 | $10,000 | **$120,000** |

### Projection: 10,000 Pages

| Scenario | Monthly Pageviews | Monthly Revenue | Annual Revenue |
|----------|:-----------------:|:---------------:|:--------------:|
| Pessimistic | 200,000 | $3,000 | **$36,000** |
| Base | 400,000 | $8,000 | **$96,000** |
| Optimistic | 800,000 | $20,000 | **$240,000** |

### Projection: 15,000 Pages (Full Build — All Three Tiers)

| Scenario | Monthly Pageviews | Monthly Revenue | Annual Revenue |
|----------|:-----------------:|:---------------:|:--------------:|
| Pessimistic | 300,000 | $4,500 | **$54,000** |
| Base | 600,000 | $12,000 | **$144,000** |
| Optimistic | 1,200,000 | $30,000 | **$360,000** |

### Revenue Ramp Timeline

```
Month   Pages    Est. Monthly Revenue (Base)
  1      1,000    $0 (indexing, no traffic yet)
  2      2,500    $150 (early indexing trickle)
  3      5,000    $600 (indexing accelerates)
  4      5,000    $1,200 (momentum building)
  5      7,000    $2,000
  6      10,000   $3,500 (Mediavine threshold approaching)
  7      10,000   $5,000 (switch to Mediavine, RPM jumps)
  8      12,000   $6,500
  9      13,000   $8,000
 10      14,000   $9,500
 11      15,000   $11,000
 12      15,000   $12,000
                   ───────
         Year 1:   ~$59,500 cumulative (base case)
```

### Seasonal Adjustment

Plant growing queries have **strong seasonality** — the strongest of any niche in this study:
- **Q1 (Jan–Mar):** +30–50% above baseline (garden planning season; seed catalogs, zone lookups)
- **Q2 (Apr–Jun):** +50–80% above baseline (peak planting season — highest traffic period)
- **Q3 (Jul–Sep):** -10% below baseline (mid-season maintenance; less "how to grow" searching)
- **Q4 (Oct–Dec):** -40–60% below baseline (dormant season, except for fall planting queries)

Net effect: Q1–Q2 traffic spike is enormous. Q4 trough is real. **Annual revenue is front-loaded into spring.** The Q4 RPM spike (high ad rates in holiday season) partially compensates for Q4 traffic drop, but not fully.

**Mitigation:** Plan cash flow around the spring peak. Consider adding "fall planting" and "winter preparation" content (Tier 3) to extend traffic through the shoulder season.

---

## 4. Top Risks

### Risk Matrix

| # | Risk | Likelihood | Impact | Severity | Mitigation |
|---|------|:----------:|:------:|:--------:|-----------|
| 1 | Plant knowledge base quality — LLM synthesizes incorrect growing advice | Medium | High | **HIGH** | Manual verification of top 200 plant entries; source all claims to extension service publications; flag confidence level per data point |
| 2 | Google HCU/spam update penalizes programmatic pages | Medium | High | **HIGH** | Unique value per page (planting calendar, zone comparison table, variety recommendations); avoid thin template-only pages |
| 3 | Extreme seasonality depresses Q4 revenue | High | Medium | **HIGH** | Add shoulder-season content (fall planting, winter prep, indoor growing); plan cash flow around spring peak |
| 4 | Lower RPM than projected ($12–$15 actual vs $15–$25 projected) | Medium | Medium | **MEDIUM** | Compensate with higher page count (the competition gap means more pages can rank); supplement with affiliate links to seed/nursery retailers |
| 5 | Extension service data is stale or region-specific rather than zone-specific | Medium | Medium | **MEDIUM** | Cross-reference multiple state extension sources; zones map roughly to latitude bands, making cross-state synthesis valid |
| 6 | Competitor enters with similar programmatic site | Low | Medium | **LOW** | First-mover advantage in an open niche; 12–18 month head start before a competitor could build + index a comparable site |
| 7 | USDA zone map updated (rare — last update was 2023) | Very Low | Low | **LOW** | Zone map updates every 10–15 years; rebuild zone assignments when it happens |
| 8 | AI content detection hurts rankings | Medium | Medium | **MEDIUM** | LLM writes 200–300 words per page; rest is structured data (calendars, tables, variety lists). Low AI content ratio relative to structured data display |

### Detailed Risk Analysis

#### Risk 1: Plant Knowledge Base Quality (HIGH)

**The core tension:** Unlike food nutrition (USDA FDC provides exact numbers), plant growing advice is inherently more qualitative and regional. "How to grow tomatoes in zone 5" requires advice about specific frost dates, soil temperatures for transplanting, variety selection, and pest pressure — none of which comes from a single structured database.

**Mitigation strategy:**
- Build the plant knowledge base from university extension service publications, which are the gold standard for regional growing advice
- Use LLM to synthesize multiple extension sources into zone-specific records, but treat LLM output as a draft requiring human verification
- Start with the 100 most-searched plants; manually verify every record before publishing
- Add a confidence indicator per data point: "USDA data" (zone hardiness, frost dates) vs "Extension-sourced" (variety recommendations, pest info) vs "General horticultural knowledge" (growing tips)
- Never present growing advice as more precise than it is — use ranges, not exact dates

**Residual risk:** Some growing advice will be imprecise for local microclimates. This is inherent to zone-level advice (zones span thousands of square miles). Prominent disclosure: "Zone-level guidance; local conditions may vary."

#### Risk 2: HCU Penalty (HIGH)

**The threat:** A programmatic site with 5K–15K template-driven pages is exactly the type of site Google's Helpful Content Update targets.

**Mitigation strategy:**
- **Planting calendars** provide genuine per-page unique utility — computed from frost dates + plant-specific timing offsets
- **Zone comparison tables** (same plant in adjacent zones) add value no general gardening site provides
- **Variety recommendation tables** are zone-specific, not boilerplate
- Write 15–20 high-quality hub articles manually ("Complete Guide to Zone 5 Gardening," "Best Vegetables for Cold Climates") to anchor the site's authority and earn backlinks
- Avoid generating pages for plant × zone combinations with insufficient data — quality over quantity

**Residual risk:** Moderate. Google's stance on programmatic content is unpredictable. The mitigation is genuine per-page utility from the computed planting calendar.

#### Risk 3: Extreme Seasonality (HIGH)

**The problem:** Gardening traffic can drop 50–60% from Q2 peak to Q4 trough. A site earning $12K/month in May might earn $4K/month in December. This is the most seasonal niche in the top 3.

**Mitigation strategy:**
- Expand content to include "when to plant fall garden zone [N]," "winter garden preparation zone [N]," and "indoor growing zone [N]" queries to extend traffic into Q3–Q4
- Build cash reserves during the Q1–Q2 peak to cover Q4 trough
- Consider launching a second site in a non-seasonal niche (food nutrition) to smooth annual revenue
- Q4 RPM spike from holiday ad spending partially offsets the traffic trough

**Residual risk:** Seasonality is inherent to the gardening niche. Revenue will always be lumpy. Plan around it.

---

## 5. Internal Linking Strategy

### Link Architecture

The plant × zone site has a naturally dense link structure organized along two axes: **plant** and **zone**.

```
                         ZONE HUB PAGES
                    ┌──────────────────────┐
                    │  Zone 3 │ Zone 4 │ Zone 5 │ Zone 6 │ ...
                    └──┬───────┬────────┬────────┬───────┘
                       │       │        │        │
                       ▼       ▼        ▼        ▼
              ┌─────────────────────────────────────────┐
              │        PLANT × ZONE PAGES               │
              │  (the 5K–15K programmatic pages)        │
              │                                         │
              │  Tomatoes in Zone 3 ←→ Tomatoes Zone 4  │
              │       ↕                    ↕             │
              │  Peppers in Zone 3 ←→ Peppers Zone 4   │
              │       ↕                    ↕             │
              │  Basil in Zone 3   ←→ Basil Zone 4     │
              └─────────┬───────────────────┬───────────┘
                        │                   │
                        ▼                   ▼
              ┌─────────────────┐  ┌─────────────────┐
              │  PLANT HUB PAGES│  │ CATEGORY PAGES  │
              │  (per-plant     │  │ (vegetables,    │
              │   across zones) │  │  fruits, herbs  │
              │                 │  │  by zone)       │
              └─────────────────┘  └─────────────────┘
```

### Link Types

| Link Type | From → To | Purpose | Quantity per Page |
|-----------|-----------|---------|:-----------------:|
| **Zone sibling** | Tomatoes in Zone 5 → Tomatoes in Zone 4, Zone 6 | Same plant, different zones | 2–4 |
| **Plant sibling** | Tomatoes in Zone 5 → Peppers in Zone 5, Basil in Zone 5 | Different plant, same zone | 4–6 |
| **Category parent** | Tomatoes in Zone 5 → Vegetables for Zone 5 | Roll-up to category hub | 1 |
| **Plant parent** | Tomatoes in Zone 5 → Tomato Growing Guide (all zones) | Roll-up to plant hub | 1 |
| **Zone parent** | Tomatoes in Zone 5 → Zone 5 Complete Guide | Roll-up to zone hub | 1 |
| **Related plants** | Tomatoes in Zone 5 → Peppers in Zone 5 (same family) | Botanical relatedness | 2–3 |

**Total internal links per page:** 11–16

### Hub Pages (Manual, High-Quality)

| Hub Type | Examples | Purpose |
|----------|---------|---------|
| Zone guides | "Complete Guide to Gardening in Zone 5" | Backlink targets; zone-level authority |
| Plant guides | "Growing Tomatoes: A Complete Guide by Zone" | Plant-level authority; links down to all zone variants |
| Category × zone | "Best Vegetables for Zone 5" | Category browsing; catches broad queries |
| Seasonal | "Spring Planting Guide for Zone 6" | Captures seasonal search spikes |

Plan for **20–30 hub pages**, written manually or with Opus-quality LLM generation. These are the backlink targets and authority anchors for the entire site.

---

## 6. Recommendation

### Go / No-Go: **GO — strong first-mover opportunity**

The SERP weakness audit confirms the widest-open landscape of any niche studied: 56% weak results, 0% strong results. No dedicated programmatic player exists. The combination of zero competition and a natural two-axis data structure (plant × zone) makes this an ideal programmatic SEO target.

### Recommended Phase Plan

| Phase | Scope | Pages | Timeline | Revenue Target |
|-------|-------|:-----:|----------|:--------------:|
| **Phase 1** | Tier 1 — 200 popular plants × zones 3–9 | 5,000 | Weeks 1–4 | $18K–$48K/yr (month 6+) |
| **Phase 2** | Tier 2 — 300 additional plants + zones 2, 10, 11 | +5,000 (10K total) | Weeks 5–8 | $36K–$96K/yr (month 9+) |
| **Phase 3** | Tier 3 — "when to plant," "can I grow," problem pages | +5,000 (15K total) | Weeks 9–14 | $54K–$144K/yr (month 12+) |

### Decision Gate Criteria

**Before proceeding to Phase 2, Phase 1 must demonstrate:**
- [ ] At least 2,500 pages indexed by Google within 60 days
- [ ] Average position < 15 for target keywords (lower bar than food nutrition due to weaker competition)
- [ ] No HCU-related ranking penalties or manual actions
- [ ] At least $400/mo revenue from initial 5K pages by month 4

If Phase 1 exceeds expectations (indexing rate > 80%, average position < 10), consider accelerating Phase 2 and Phase 3 to capitalize on the first-mover window before competitors notice.

---

## Data Sources

- USDA Plant Hardiness Zone Map: https://planthardiness.ars.usda.gov/
- NOAA Climate Normals (frost dates): https://www.ncei.noaa.gov/products/land-based-station/us-climate-normals
- Phase 1 research reports: [01-query-patterns](01-query-patterns.md) through [08-scoring-matrix](08-scoring-matrix.md)
- SERP analysis: Live web searches conducted March 2026
- RPM benchmarks: [04-rpm-monetization](04-rpm-monetization.md)
- Legal assessment: [05-legal-scan](05-legal-scan.md)
- Pipeline complexity: [06-feasibility](06-feasibility.md)
