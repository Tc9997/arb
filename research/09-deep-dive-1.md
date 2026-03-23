# Deep Dive: Food Nutrition — Niche Candidate #1

> Research deliverable for arb-zvi. March 2026.

---

## Executive Summary

Food nutrition scored **7.40** in the scoring matrix — the highest of all 13 candidates. This deep dive validates the opportunity through 100 sample queries checked against real SERPs, a data pipeline prototype, three-scenario revenue projections, and a risk inventory.

**Bottom line:** The opportunity is real but narrower than the scoring matrix suggests. The gap is specifically in **food × preparation method** and **dish-level nutrition** queries, not in basic ingredient lookups. Revenue projections are viable at scale: $12K–$72K/yr at 5K pages, $24K–$144K/yr at 10K pages. The primary risk is YMYL scrutiny, mitigatable with strict USDA-only sourcing and allergen disclaimers.

---

## 1. SERP Weakness Audit — 100 Sample Queries

### Methodology

100 queries were constructed across 10 categories of food nutrition search patterns. Each query was classified by SERP quality based on web search analysis:

| SERP Quality | Definition | Signal |
|--------------|-----------|--------|
| **Weak** | Quora/Reddit/forums in top 3, recipe blogs answering wrong question, brand sites with inconsistent data | Strong opportunity |
| **Moderate** | Nutrition trackers (Nutritionix, FatSecret) cover it but with generic or restaurant-brand entries; no dedicated page | Possible opportunity |
| **Strong** | Dedicated, authoritative result with exact data for this food × preparation | No opportunity |

### Query Inventory (100 Queries)

#### Category A: Single Ingredient + Preparation Method (20 queries)

| # | Query | SERP Quality | Top Results |
|---|-------|:---:|-------------|
| 1 | calories in air fried chicken thigh | Weak | Recipe blogs (CJEats, AGirlCalledAdri, MyForkingLife) — all answer "how to cook" not "nutrition facts" |
| 2 | calories in pan fried pork chop bone in | Moderate | CalorieKing, FatSecret have generic entries; nutrifox has USDA data but poor UX |
| 3 | calories in baked sweet potato with butter | Moderate | SnapCalorie, EatThisMuch (restaurant-specific entries), FatSecret |
| 4 | calories in steamed broccoli with garlic butter | Weak | EatThisMuch (restaurant entries), recipe blogs, university dining labels |
| 5 | calories in grilled salmon fillet 6 oz | Moderate | Restaurant-specific entries (Sizzler, O'Charley's); no generic "grilled salmon" page |
| 6 | calories in smoked brisket per slice | Moderate | MyNetDiary, FatSecret, nutrifox — fragmented across multiple sites |
| 7 | calories in roasted cauliflower with olive oil | Weak | Recipe blogs dominate; no dedicated nutrition lookup page |
| 8 | calories in deep fried shrimp tempura per piece | Moderate | CalorieKing, Nutritionix have per-piece data; PerkChops covers it |
| 9 | calories in boiled corn on the cob with butter | Moderate | CalorieKing, FatSecret cover base; butter addition not well-addressed |
| 10 | calories in slow cooked pulled pork per cup | Weak | Recipe blogs and Quora-style results; no clean lookup |
| 11 | calories in sauteed mushrooms with olive oil per cup | Moderate | Nutritionix has an entry; nutritionvalue.org has USDA data |
| 12 | calories in blackened tilapia fillet | Weak | Recipe blogs; no dedicated nutrition page for this prep method |
| 13 | calories in oven roasted turkey breast per slice | Moderate | FatSecret, branded product entries (deli meat vs home-roasted confusion) |
| 14 | calories in chargrilled chicken breast no skin | Moderate | Nutritionix generic; multiple trackers with slightly different numbers |
| 15 | calories in braised short ribs per rib | Weak | Recipe blogs dominate; no clean per-rib nutrition lookup |
| 16 | calories in poached egg on toast | Moderate | Various trackers; no single authoritative result |
| 17 | calories in stir fried tofu with vegetables | Weak | Recipe blogs with wildly different calorie counts |
| 18 | calories in broiled lamb chop 4 oz | Moderate | FatSecret, nutrifox have USDA data; poor UX and discoverability |
| 19 | calories in air fried french fries per serving | Weak | Recipe blogs; no comparison to deep-fried equivalent |
| 20 | calories in smoked salmon lox 2 oz | Moderate | CalorieKing, FatSecret cover this; reasonable results |

**Category A summary:** 9 Weak, 11 Moderate, 0 Strong. Preparation-method queries are the clearest gap.

#### Category B: Prepared Dishes / Ethnic Cuisine (20 queries)

| # | Query | SERP Quality | Top Results |
|---|-------|:---:|-------------|
| 21 | calories in homemade beef pho per bowl | Weak | Quora #1, VifonUSA, KimEcopak — no authoritative nutrition page |
| 22 | calories in chicken tikka masala homemade | Weak | Skinnytaste (their recipe), Nutritionix (generic 1-cup), Spicentice |
| 23 | calories in pad thai with shrimp per serving | Moderate | SnapCalorie, EatThisMuch (restaurant), Nutritionix has generic entry |
| 24 | calories in Korean bibimbap with beef | Moderate | MyNetDiary (Hello Fresh branded), SnapCalorie, Fitia |
| 25 | calories in butter chicken with naan | Moderate | Kirkland branded, Gobble meal kit, SnapCalorie — all brand-specific |
| 26 | calories in chicken fried rice per cup | Moderate | FatSecret, Nutritionix have per-cup entries; Quora also appears |
| 27 | calories in miso soup with tofu and seaweed | Moderate | Branded packet entries (Marukome); homemade version sparse |
| 28 | calories in beef tacos with cheese 2 tacos | Weak | Recipe blogs; Taco Bell branded entries; no "generic homemade" |
| 29 | calories in chicken enchiladas with red sauce | Weak | Recipe blogs (Skinnytaste, PinchOfYum); no generic nutrition lookup |
| 30 | calories in lamb gyro with tzatziki | Weak | Nutritionix has a generic entry; mostly brand/restaurant results |
| 31 | calories in sushi california roll 8 pieces | Moderate | Nutritionix, FatSecret, CalorieKing — reasonably covered |
| 32 | calories in ramen with pork broth and egg | Weak | Recipe blogs; instant ramen entries; homemade version absent |
| 33 | calories in falafel wrap with hummus | Weak | Recipe blogs; no dedicated nutrition page |
| 34 | calories in thai green curry with chicken | Weak | Recipe blogs; SnapCalorie has a generic entry |
| 35 | calories in vegetable lo mein per serving | Moderate | Nutritionix, FatSecret cover generic versions |
| 36 | calories in black bean burrito with cheese rice | Moderate | Taco Bell branded, EatThisMuch, SnapCalorie |
| 37 | calories in chicken shawarma plate with rice | Weak | Limited; mostly restaurant-specific entries |
| 38 | calories in shakshuka with 2 eggs | Weak | Recipe blogs only; no dedicated nutrition lookup |
| 39 | calories in aloo gobi per serving | Weak | Recipe blogs; very sparse nutrition data |
| 40 | calories in poke bowl with tuna and rice | Moderate | Nutritionix has a generic entry; several trackers |

**Category B summary:** 12 Weak, 8 Moderate, 0 Strong. Ethnic/dish queries are severely underserved.

#### Category C: Breakfast / Brunch Items (10 queries)

| # | Query | SERP Quality | Top Results |
|---|-------|:---:|-------------|
| 41 | calories in overnight oats with banana peanut butter | Moderate | Recipe blogs dominate but most include calorie counts |
| 42 | calories in avocado toast with egg on sourdough | Moderate | SnapCalorie, MyNetDiary, TikTok — fragmented |
| 43 | calories in scrambled eggs with cheese 2 eggs | Moderate | Waffle House branded, recipe blogs; no clean generic result |
| 44 | calories in greek yogurt parfait with granola berries | Moderate | EatThisMuch, recipe blogs; decent coverage |
| 45 | calories in acai bowl with granola banana honey | Moderate | Sambazon, brand entries; generic version loosely covered |
| 46 | calories in pancakes with maple syrup 3 pancakes | Moderate | FatSecret, Nutritionix cover generic pancakes |
| 47 | calories in french toast with powdered sugar | Weak | Recipe blogs; no clean nutrition lookup |
| 48 | calories in breakfast burrito egg cheese bacon | Weak | Fast food branded entries; homemade version absent |
| 49 | calories in oatmeal with brown sugar and milk | Moderate | Nutritionix, FatSecret cover this reasonably |
| 50 | calories in smoothie bowl mango spinach protein | Weak | Recipe blogs with wildly varying calorie counts |

**Category C summary:** 3 Weak, 7 Moderate, 0 Strong.

#### Category D: Salads & Bowls (10 queries)

| # | Query | SERP Quality | Top Results |
|---|-------|:---:|-------------|
| 51 | calories in chicken caesar salad with croutons dressing | Moderate | Restaurant-branded entries (Costco, BJ's); no generic version |
| 52 | calories in cobb salad with ranch dressing | Moderate | Nutritionix, CalorieKing — generic entries exist |
| 53 | calories in quinoa bowl with black beans and avocado | Weak | Recipe blogs; no clean nutrition page |
| 54 | calories in mediterranean grain bowl | Weak | Recipe blogs; very fragmented |
| 55 | calories in asian sesame chicken salad | Moderate | Restaurant entries (Applebee's, Panera); generic sparse |
| 56 | calories in kale salad with dried cranberries walnuts | Weak | Recipe blogs; no dedicated page |
| 57 | calories in tuna salad sandwich on wheat bread | Moderate | Nutritionix, FatSecret cover generic version |
| 58 | calories in caprese salad with fresh mozzarella | Moderate | CalorieKing, Nutritionix have entries |
| 59 | calories in southwest chicken salad with corn beans | Weak | Restaurant entries; no homemade generic |
| 60 | calories in poke bowl salmon avocado rice | Moderate | Nutritionix, EatThisMuch — loosely covered |

**Category D summary:** 4 Weak, 6 Moderate, 0 Strong.

#### Category E: Snacks & Sides (10 queries)

| # | Query | SERP Quality | Top Results |
|---|-------|:---:|-------------|
| 61 | calories in hummus with pita chips per serving | Moderate | FatSecret, Nutritionix cover branded versions |
| 62 | calories in guacamole per tablespoon | Moderate | CalorieKing, FatSecret — well covered |
| 63 | calories in mozzarella sticks fried 3 pieces | Moderate | CalorieKing (TGI Fridays), FatSecret generic |
| 64 | calories in loaded nachos with cheese and beef | Weak | Recipe blogs; restaurant entries; no generic |
| 65 | calories in deviled eggs per egg | Moderate | Nutritionix, FatSecret — reasonably covered |
| 66 | calories in edamame shelled per cup | Strong | Nutritionix, FatSecret, CalorieKing — clean lookup |
| 67 | calories in bruschetta with tomato basil | Weak | Recipe blogs; no clean nutrition page |
| 68 | calories in cheese quesadilla with chicken | Moderate | Nutritionix generic; restaurant entries mixed in |
| 69 | calories in spring rolls fried per roll | Moderate | CalorieKing, FatSecret have per-roll entries |
| 70 | calories in garlic bread with butter 2 slices | Moderate | FatSecret, CalorieKing — reasonable coverage |

**Category E summary:** 2 Weak, 7 Moderate, 1 Strong.

#### Category F: Desserts & Sweets (10 queries)

| # | Query | SERP Quality | Top Results |
|---|-------|:---:|-------------|
| 71 | calories in homemade banana bread per slice | Weak | Recipe blogs (each with different calorie counts) |
| 72 | calories in tiramisu per serving | Moderate | Nutritionix, CalorieKing — generic entries exist |
| 73 | calories in chocolate lava cake per serving | Weak | Recipe blogs; restaurant entries; no generic |
| 74 | calories in carrot cake with cream cheese frosting | Weak | Recipe blogs; no standard reference |
| 75 | calories in apple crisp per serving homemade | Weak | Recipe blogs with varying numbers |
| 76 | calories in creme brulee per ramekin | Moderate | Nutritionix, FatSecret have generic entries |
| 77 | calories in brownies from scratch per brownie | Weak | Recipe blogs; wide variance (150–350 cal) |
| 78 | calories in pumpkin pie per slice | Moderate | Nutritionix, FatSecret — reasonably covered |
| 79 | calories in churros with chocolate sauce | Weak | Costco/Disney-branded; no generic |
| 80 | calories in rice pudding per cup homemade | Weak | Recipe blogs; generic entries in trackers |

**Category F summary:** 7 Weak, 3 Moderate, 0 Strong.

#### Category G: Beverages (5 queries)

| # | Query | SERP Quality | Top Results |
|---|-------|:---:|-------------|
| 81 | calories in chai latte with whole milk | Moderate | Starbucks branded; generic versions in trackers |
| 82 | calories in matcha latte with oat milk | Moderate | Starbucks branded; recipe blogs |
| 83 | calories in mango lassi per glass | Weak | Recipe blogs; no standard reference |
| 84 | calories in horchata per cup | Weak | Nutritionix has generic; mostly brand entries |
| 85 | calories in thai iced tea with condensed milk | Weak | Recipe blogs and forums |

**Category G summary:** 3 Weak, 2 Moderate, 0 Strong.

#### Category H: Soups & Stews (5 queries)

| # | Query | SERP Quality | Top Results |
|---|-------|:---:|-------------|
| 86 | calories in chicken tortilla soup per bowl | Moderate | Nutritionix, recipe blogs |
| 87 | calories in homemade chili con carne per cup | Moderate | FatSecret, Nutritionix — generic entries |
| 88 | calories in tom yum soup with shrimp | Weak | Recipe blogs; SnapCalorie generic |
| 89 | calories in cream of mushroom soup homemade | Moderate | FatSecret (canned vs homemade unclear) |
| 90 | calories in beef stew per bowl homemade | Moderate | Nutritionix, FatSecret generic |

**Category H summary:** 1 Weak, 4 Moderate, 0 Strong.

#### Category I: Diet-Specific Searches (5 queries)

| # | Query | SERP Quality | Top Results |
|---|-------|:---:|-------------|
| 91 | protein in grilled chicken breast 8 oz | Strong | Nutritionix, FatSecret, USDA — well covered |
| 92 | net carbs in zucchini noodles per cup | Moderate | FatSecret, Carb Manager — keto trackers cover this |
| 93 | fiber in black beans cooked per cup | Strong | Nutritionix, FatSecret, USDA — well covered |
| 94 | sugar in balsamic vinaigrette per tablespoon | Moderate | Branded entries; generic versions in trackers |
| 95 | sodium in soy sauce per tablespoon | Strong | Nutritionix, FatSecret, USDA — well covered |

**Category I summary:** 0 Weak, 2 Moderate, 3 Strong.

#### Category J: Portion-Specific & Comparison (5 queries)

| # | Query | SERP Quality | Top Results |
|---|-------|:---:|-------------|
| 96 | calories in 1 cup of white rice vs brown rice | Moderate | Healthline editorial; trackers cover both individually |
| 97 | calories in whole wheat pasta vs regular pasta | Moderate | Healthline, Nutritionix — editorial + tracker |
| 98 | calories in 100g chicken breast cooked | Moderate | FatSecret, Nutritionix — covered but fragmented |
| 99 | calories in 1 medium avocado | Strong | Nutritionix, FatSecret, CalorieKing — well covered |
| 100 | macros in 4 oz ground beef 80/20 cooked | Moderate | FatSecret, Nutritionix — covered |

**Category J summary:** 0 Weak, 4 Moderate, 1 Strong.

---

### SERP Audit Summary

| Category | Queries | Weak | Moderate | Strong | Weak % |
|----------|:-------:|:----:|:--------:|:------:|:------:|
| A: Ingredient + Prep Method | 20 | 9 | 11 | 0 | 45% |
| B: Prepared Dishes / Ethnic | 20 | 12 | 8 | 0 | 60% |
| C: Breakfast / Brunch | 10 | 3 | 7 | 0 | 30% |
| D: Salads & Bowls | 10 | 4 | 6 | 0 | 40% |
| E: Snacks & Sides | 10 | 2 | 7 | 1 | 20% |
| F: Desserts & Sweets | 10 | 7 | 3 | 0 | 70% |
| G: Beverages | 5 | 3 | 2 | 0 | 60% |
| H: Soups & Stews | 5 | 1 | 4 | 0 | 20% |
| I: Diet-Specific | 5 | 0 | 2 | 3 | 0% |
| J: Portion / Comparison | 5 | 0 | 4 | 1 | 0% |
| **Total** | **100** | **41** | **54** | **5** | **41%** |

### Key Findings

1. **41% of queries show weak SERP coverage** — recipe blogs answering the wrong question, Quora/Reddit, or no dedicated result. This is the exploitable gap.

2. **54% show moderate coverage** — nutrition trackers have entries but fragmented across multiple sites, often restaurant-branded, and with inconsistent data. A cleaner, more authoritative single-source page could compete.

3. **Only 5% are well-served** — basic single-ingredient queries (edamame, black beans, avocado, soy sauce, brown rice) where USDA data is already surfaced effectively.

4. **The sweet spot is categories A, B, and F** — food × preparation method, ethnic/prepared dishes, and desserts. These three categories account for 28 of the 41 weak results.

5. **The common failure pattern:** User searches "calories in [dish]" wanting a definitive answer. Google returns recipe blogs that answer "here's MY recipe for [dish], which has X calories." This is a **different question** — the user wants nutrition facts for a standard serving of the dish, not one blogger's specific recipe.

---

## 2. Data Pipeline Prototype

### Architecture: Data Source → Transform → Page

```
┌──────────────────────────────────────────────────────────┐
│                    DATA SOURCES                           │
│                                                          │
│  ┌─────────────────────┐   ┌──────────────────────────┐  │
│  │  USDA FoodData      │   │  Food Entity Catalog     │  │
│  │  Central (FDC)      │   │  (custom-built)          │  │
│  │                     │   │                          │  │
│  │  • SR Legacy: 7,793 │   │  • Dish → ingredient     │  │
│  │  • Foundation: 2,700│   │    mappings               │  │
│  │  • FNDDS: 8,000     │   │  • Standard serving      │  │
│  │  • Branded: 400K+   │   │    sizes                  │  │
│  │                     │   │  • Preparation method     │  │
│  │  API: 3,600 req/hr  │   │    modifiers              │  │
│  │  Bulk: CSV download │   │                          │  │
│  └────────┬────────────┘   └──────────┬───────────────┘  │
│           │                           │                  │
└───────────┼───────────────────────────┼──────────────────┘
            │                           │
            ▼                           ▼
┌──────────────────────────────────────────────────────────┐
│                    TRANSFORM LAYER                        │
│                                                          │
│  1. FOOD RESOLVER                                        │
│     Input: query slug ("air-fried-chicken-thigh")        │
│     → Parse food entity + preparation method             │
│     → Match to FDC food ID(s) using fuzzy search         │
│     → Pull nutrient array (up to 150 nutrients)          │
│                                                          │
│  2. NUTRITION CALCULATOR                                 │
│     → Normalize to standard serving size                 │
│     → Apply preparation-method modifiers                 │
│       (e.g., frying adds ~8% calories from oil           │
│        absorption; boiling reduces sodium ~15%)          │
│     → Compute per-serving macros + key micros            │
│                                                          │
│  3. LLM ENRICHMENT (500–800 tokens output)               │
│     → Contextual paragraph: "A [food] prepared by        │
│       [method] provides [X] calories per [serving]..."   │
│     → Comparison to similar preparations                 │
│     → Allergen callouts (auto-detected from FDC data)    │
│     → USDA source attribution + disclaimer               │
│     → NO health claims, NO dietary advice                │
│                                                          │
└──────────────────────┬───────────────────────────────────┘
                       │
                       ▼
┌──────────────────────────────────────────────────────────┐
│                    PAGE TEMPLATE                          │
│                                                          │
│  ┌────────────────────────────────────────────────────┐  │
│  │  H1: Calories in [Food] [Preparation]              │  │
│  │                                                    │  │
│  │  ┌──────────────────────────────────────────────┐  │  │
│  │  │  HERO NUTRITION CARD                         │  │  │
│  │  │  Calories: 354    Protein: 24g               │  │  │
│  │  │  Fat: 28g         Carbs: 0g                  │  │  │
│  │  │  Serving: 1 thigh (112g)                     │  │  │
│  │  └──────────────────────────────────────────────┘  │  │
│  │                                                    │  │
│  │  [Contextual paragraph — LLM generated, 100-150    │  │
│  │   words, sourced from USDA data]                   │  │
│  │                                                    │  │
│  │  DETAILED NUTRITION TABLE                          │  │
│  │  ├── Macronutrients (calories, protein, fat, carbs)│  │
│  │  ├── Fat breakdown (saturated, mono, poly, trans)  │  │
│  │  ├── Vitamins (A, C, D, E, K, B-complex)          │  │
│  │  ├── Minerals (iron, calcium, potassium, zinc)     │  │
│  │  └── % Daily Value column                          │  │
│  │                                                    │  │
│  │  PREPARATION COMPARISON TABLE                      │  │
│  │  (Same food, different methods: raw vs baked vs     │  │
│  │   fried vs grilled — using FDC variants)           │  │
│  │                                                    │  │
│  │  SIMILAR FOODS SECTION                             │  │
│  │  (Internal links to related nutrition pages)        │  │
│  │                                                    │  │
│  │  ⚠️ ALLERGEN DISCLAIMER                            │  │
│  │  📊 Source: USDA FoodData Central (FDC ID: XXXXX)  │  │
│  │  📅 Data updated: [FDC release date]               │  │
│  └────────────────────────────────────────────────────┘  │
│                                                          │
│  Schema.org: NutritionInformation structured data        │
│  (enables rich snippets in Google SERPs)                 │
│                                                          │
└──────────────────────────────────────────────────────────┘
```

### Pipeline Tiers

The pipeline handles three tiers of increasing complexity:

| Tier | Type | Example | FDC Mapping | LLM Load | Page Count |
|------|------|---------|-------------|----------|------------|
| **1 — Direct Lookup** | Single ingredient + standard prep | "calories in grilled chicken breast" | Direct FDC match (SR Legacy has "Chicken, breast, meat only, cooked, grilled") | Minimal (connective prose) | ~5,000 |
| **2 — Modified Lookup** | Single ingredient + specific prep | "calories in air fried chicken thigh" | FDC base food + preparation modifier applied computationally | Low (explain the modifier) | ~10,000 |
| **3 — Composed Dish** | Multi-ingredient dish | "calories in chicken tikka masala" | Food Entity Catalog → ingredient list → per-ingredient FDC lookups → sum | Moderate (contextualize composite) | ~5,000–20,000 |

**Tier 1** is launch-ready today. USDA SR Legacy and FNDDS together cover ~15,000 food items with preparation variants already computed. Each page is a single API call.

**Tier 2** requires a preparation-modifier database (e.g., "air frying adds X% fat vs baking") sourced from USDA research publications and food science literature. This is a fixed upfront investment — perhaps 50 common cooking methods × modifier tables.

**Tier 3** requires the Food Entity Catalog — a curated mapping of common dishes to standardized ingredient lists. This is the hardest tier to get right and the most vulnerable to inaccuracy. Start with 500–1,000 well-known dishes, each manually verified.

### Build Cost Estimate

| Component | Effort | One-Time Cost |
|-----------|--------|--------------|
| FDC bulk data ingest + parser | 2–3 days | Low (public domain CSV) |
| Food Entity Catalog (500 dishes) | 5–7 days | Moderate (manual curation) |
| Preparation modifier database | 2–3 days | Low (food science refs) |
| Page template + Schema.org | 1–2 days | Low |
| LLM content generation (5K pages) | 1–2 days compute | ~$15–$50 (500–800 tokens/page × 5K pages × ~$0.003/1K tokens) |
| Total initial build | ~2–3 weeks | < $100 in API/compute costs |

### Key Technical Decisions

1. **Bulk download, not API:** Download FDC bulk CSV (~2GB), load into SQLite/Postgres, generate all pages at build time. The API's 3,600 req/hr limit makes real-time queries impractical for 10K+ pages.

2. **Schema.org NutritionInformation:** Every page gets structured data for Google rich snippets. This is a significant competitive advantage — most recipe blogs have Recipe schema, not NutritionInformation schema for standalone nutrition pages.

3. **Preparation comparison tables:** If FDC has the same food in multiple preparations (raw, boiled, baked, fried), show them all in a comparison table. This adds unique value that no single recipe blog provides and addresses the prep-method gap directly.

4. **Internal linking mesh:** Every food page links to related foods and alternative preparations. This creates the crawl structure that programmatic SEO relies on for indexing velocity.

---

## 3. Revenue Projections

### Assumptions

| Parameter | Pessimistic | Base | Optimistic |
|-----------|:-----------:|:----:|:----------:|
| Monthly visits per page | 20 | 40 | 80 |
| RPM (revenue per 1,000 pageviews) | $15 | $20 | $30 |
| Ad network | Ezoic (free tier) | Mediavine Journey | Mediavine/Raptive |
| Time to reach stated traffic | 12–18 months | 9–12 months | 6–9 months |
| Traffic decay rate (annual) | 15% | 10% | 5% |

**RPM justification:**
- Food vertical Ezoic EPMV: $6–$12 (pessimistic floor = $15 assumes growth to Mediavine Journey tier)
- Food vertical Mediavine RPM: $15–$35 (base = $20, well within range)
- Raptive premium for food: $30–$50 (optimistic $30 is conservative for premium tier)
- Midwest Foodie blog earned $530K/yr on Raptive, demonstrating food vertical RPMs in the $30+ range at scale.

**Traffic justification:**
- 20 visits/page/month = ~0.7 visits/day. Achievable for even marginal long-tail pages that rank position 5–10.
- 40 visits/page/month = ~1.3 visits/day. Typical for a well-indexed page ranking position 3–5 on a low-competition query.
- 80 visits/page/month = ~2.7 visits/day. Requires position 1–3 ranking on queries with 500+ monthly search volume.

### Projection: 5,000 Pages

| Scenario | Monthly Pageviews | Monthly Revenue | Annual Revenue |
|----------|:-----------------:|:---------------:|:--------------:|
| Pessimistic | 100,000 | $1,500 | **$18,000** |
| Base | 200,000 | $4,000 | **$48,000** |
| Optimistic | 400,000 | $12,000 | **$144,000** |

**Note on pessimistic 5K:** $18K/yr may not justify the effort for a solo operator. However, 5K pages is only Tier 1 (direct FDC lookups), which takes ~2–3 weeks to build. At $18K/yr for 3 weeks of work + minimal maintenance, the ROI is still strong.

### Projection: 10,000 Pages

| Scenario | Monthly Pageviews | Monthly Revenue | Annual Revenue |
|----------|:-----------------:|:---------------:|:--------------:|
| Pessimistic | 200,000 | $3,000 | **$36,000** |
| Base | 400,000 | $8,000 | **$96,000** |
| Optimistic | 800,000 | $24,000 | **$288,000** |

**Note on base 10K:** 400K monthly pageviews qualifies for Mediavine (50K sessions threshold, assuming 1.2 pages/session = ~333K sessions). This unlocks the $20+ RPM tier, making the base case self-reinforcing.

### Projection: 20,000 Pages (Full Build — All Three Tiers)

| Scenario | Monthly Pageviews | Monthly Revenue | Annual Revenue |
|----------|:-----------------:|:---------------:|:--------------:|
| Pessimistic | 400,000 | $6,000 | **$72,000** |
| Base | 800,000 | $16,000 | **$192,000** |
| Optimistic | 1,600,000 | $48,000 | **$576,000** |

### Revenue Ramp Timeline

```
Month   Pages    Est. Monthly Revenue (Base)
  1      1,000    $0 (indexing, no traffic yet)
  2      3,000    $200 (early indexing trickle)
  3      5,000    $800 (indexing accelerates)
  4      5,000    $1,500 (momentum building)
  5      7,000    $2,500
  6      10,000   $4,000 (Mediavine threshold hit)
  7      10,000   $5,500 (switch to Mediavine, RPM jumps)
  8      12,000   $7,000
  9      15,000   $9,000
 10      15,000   $10,500
 11      18,000   $12,500
 12      20,000   $16,000
                   ───────
         Year 1:   ~$69,500 cumulative (base case)
```

### Seasonal Adjustment

Food nutrition queries have moderate seasonality:
- **Q1 (Jan–Mar):** +20–30% above baseline (New Year's resolutions, calorie counting spike)
- **Q2 (Apr–Jun):** Baseline (summer body prep sustains interest)
- **Q3 (Jul–Sep):** -10% below baseline (summer, less calorie tracking)
- **Q4 (Oct–Dec):** -5% (holiday cooking bumps volume; RPMs spike due to Q4 ad spending)

Net effect: Q1 traffic spike partially offset by Q1 RPM trough. Q4 RPM spike partially offset by flat traffic. **Seasonality largely self-cancels in this niche**, unlike pure recipe sites where Q4 (holiday baking) creates extreme spikes.

---

## 4. Top Risks

### Risk Matrix

| # | Risk | Likelihood | Impact | Severity | Mitigation |
|---|------|:----------:|:------:|:--------:|-----------|
| 1 | YMYL demotion by Google | Medium | High | **HIGH** | Strict USDA-only sourcing, allergen disclaimers, no health claims, NutritionInformation schema, cite FDC IDs |
| 2 | Google HCU/spam update penalizes programmatic pages | Medium | High | **HIGH** | Ensure unique value per page (prep comparison tables, detailed micro breakdowns); avoid thin template-only pages |
| 3 | Tier 3 dish-level data inaccuracy | High | Medium | **HIGH** | Start with Tier 1 only; expand to Tier 3 slowly with manual verification; prominently label estimates |
| 4 | Nutritionix/FatSecret build competing dedicated pages | Low | High | **MEDIUM** | They've had the data for years and haven't done it; their business model is app-based tracking, not SEO content |
| 5 | USDA FDC data staleness (6-month update cycle) | Low | Low | **LOW** | Nutrition facts for whole foods rarely change; branded foods update monthly. Rebuild pages quarterly. |
| 6 | Ad network rejection due to programmatic content | Low | Medium | **LOW** | Ezoic accepts all; Mediavine requires manual review — quality pages with USDA data should pass |
| 7 | Allergen liability from incorrect data | Low | High | **MEDIUM** | Use only FDC-reported allergens; every page gets "consult your doctor" + "verify labels" disclaimer |
| 8 | AI content detection hurts rankings | Medium | Medium | **MEDIUM** | LLM writes only 100–150 words per page; rest is structured data display. Low AI content ratio. |

### Detailed Risk Analysis

#### Risk 1: YMYL Demotion (HIGH)

**The core tension:** Nutrition information sits at the YMYL boundary. Google explicitly treats medical/health information with higher E-E-A-T scrutiny. Calorie lookups are informational (not medical advice), but allergies and dietary restrictions blur the line.

**Mitigation strategy:**
- Every page cites the specific USDA FDC ID for its data source
- Allergen disclaimer on every page: "This information is from USDA FoodData Central. Always check packaging labels for allergen information."
- No health claims whatsoever — no "eat this for weight loss," no "good for your heart"
- Schema.org NutritionInformation with `source` attribute pointing to USDA
- Consider adding a registered dietitian "reviewed by" attribution (cost: ~$500–$1,000 for batch review of template + 50 sample pages)

**Residual risk:** Even with mitigations, a YMYL-focused algorithm update could impact the entire site. This is uncontrollable.

#### Risk 2: HCU Penalty (HIGH)

**The threat:** Google's Helpful Content Update (HCU) has hit programmatic and AI-generated sites hard since 2023. A nutrition lookup site is at risk if pages look templated.

**Mitigation strategy:**
- **Preparation comparison tables** add genuinely unique value that no single recipe blog provides
- **Detailed micronutrient breakdowns** (vitamins, minerals, %DV) go deeper than most food trackers
- **Internal linking mesh** creates topical authority signals
- **"Why this matters" contextual paragraphs** are LLM-written but unique per page (not boilerplate)
- Avoid generating pages for foods with insufficient FDC data — quality over quantity

**Residual risk:** Moderate. Google may view any site with 10K+ template-driven pages skeptically regardless of quality. The mitigation is to ensure genuine per-page value.

#### Risk 3: Tier 3 Data Accuracy (HIGH)

**The problem:** "Calories in chicken tikka masala" has no single correct answer. Different recipes vary by 2–3× in calorie count. Any number we provide will be wrong for many users' specific versions.

**Mitigation strategy:**
- Defer Tier 3 launch until Tier 1 proves the model
- When launched, label all composite-dish pages as "Estimated based on a standard recipe"
- Show ingredient breakdown so users can see what's included
- Provide calorie range, not single number (e.g., "350–550 calories depending on recipe")
- Manual verification of the top 200 dish entries before launch

**Residual risk:** High for Tier 3 specifically. Tier 1 (direct FDC lookups) has essentially zero accuracy risk.

---

## 5. Competitive Moat Assessment

### Current Competitors

| Competitor | Type | Strengths | Weaknesses |
|-----------|------|-----------|-----------|
| **Nutritionix** | Nutrition tracker/API | Large food database; natural language search; restaurant coverage | App-focused UX, not SEO-optimized; no preparation comparison tables; no Schema.org NutritionInformation |
| **FatSecret** | Calorie tracker | Strong SEO presence (DA 68); community-contributed entries | User-submitted data often inaccurate; no USDA attribution; cluttered UX |
| **CalorieKing** | Nutrition database | Clean per-food pages; decent SEO | Limited to branded/restaurant items; thin on homemade/preparation variants |
| **MyFitnessPal** | Fitness app | Massive user base; 14M+ food entries | Walled behind app; poor web SEO; user-contributed data quality is mixed |
| **USDA FDC itself** | Government database | Authoritative source of truth | Terrible UX; no SEO optimization; no contextual content; no Schema.org |
| **SnapCalorie** | AI calorie estimator | Emerging player; some programmatic pages | Thin coverage; low DA; new entrant |
| **EatThisMuch** | Meal planner | Good nutrition pages for some foods | Primarily meal-planning focused; coverage gaps in non-Western dishes |

### Defensible Advantages

1. **USDA attribution:** The only site that would consistently cite specific FDC IDs on every page, building E-E-A-T trust signals.

2. **Preparation comparison:** No existing competitor shows "here are the calories for this food raw, baked, fried, grilled, and air-fried side by side." This is unique and high-value.

3. **Schema.org NutritionInformation:** Most recipe blogs use Recipe schema. Most trackers don't use structured data at all. Rich snippets from NutritionInformation schema would be a significant SERP advantage.

4. **Dish-level coverage (Tier 3):** No competitor has clean, standardized nutrition pages for ethnic/world cuisine dishes. This is a blue ocean if accuracy risk can be managed.

---

## 6. Recommendation

### Go / No-Go: **GO — with phased rollout**

The SERP weakness audit confirms a real gap: 41% of food nutrition queries have weak results, and the gap is widest in exactly the categories where USDA FDC data can provide authoritative answers.

### Recommended Phase Plan

| Phase | Scope | Pages | Timeline | Revenue Target |
|-------|-------|:-----:|----------|:--------------:|
| **Phase 1** | Tier 1 only — direct FDC lookups for single ingredients with standard preparations | 5,000 | Weeks 1–3 | $18K–$48K/yr (month 6+) |
| **Phase 2** | Tier 2 — add preparation method modifiers | +5,000 (10K total) | Weeks 4–6 | $36K–$96K/yr (month 9+) |
| **Phase 3** | Tier 3 — composed dishes (top 500 dishes, manually verified) | +5,000 (15K total) | Weeks 7–12 | $54K–$144K/yr (month 12+) |
| **Phase 4** | Scale Tier 3 + expand Tier 2 coverage | +5,000 (20K total) | Months 3–6 | $72K–$288K/yr (month 15+) |

### Decision Gate Criteria

**Before proceeding to Phase 2, Phase 1 must demonstrate:**
- [ ] At least 2,000 pages indexed by Google within 60 days
- [ ] Average position < 20 for target keywords (GSC data)
- [ ] No YMYL-related ranking penalties or manual actions
- [ ] At least $500/mo revenue from initial 5K pages by month 4

If Phase 1 fails these gates, pivot to plant growing by zone (niche #2, score 6.80) which has lower YMYL risk and wider-open competition.

---

## Data Sources

- USDA FoodData Central: https://fdc.nal.usda.gov/
- Phase 1 research reports: [01-query-patterns](01-query-patterns.md) through [08-scoring-matrix](08-scoring-matrix.md)
- SERP analysis: Live web searches conducted March 2026
- RPM benchmarks: [04-rpm-monetization](04-rpm-monetization.md)
- Legal assessment: [05-legal-scan](05-legal-scan.md)
- Pipeline complexity: [06-feasibility](06-feasibility.md)
