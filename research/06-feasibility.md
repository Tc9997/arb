# Programmatic Feasibility: Data-to-Page Pipeline Complexity

> For each of the 13 niche candidates: how hard is the data→page pipeline?

## Rating Scale

| Rating | Meaning |
|--------|---------|
| **A — Trivial** | Structured data maps 1:1 to page. LLM writes connective prose only. Single template. |
| **B — Straightforward** | Minor data joins or light transformation. LLM synthesizes but doesn't invent. 1-2 templates. |
| **C — Moderate** | Multiple data sources, some gaps to fill. LLM does meaningful generation. 2-4 templates. |
| **D — Complex** | Sparse or unstructured data. LLM carries heavy load. Many template variants. |
| **F — Impractical** | No reliable data pipeline. LLM would hallucinate core content. Not viable for programmatic SEO. |

---

## Summary Table

| # | Niche | Pipeline Grade | Templates | Data Joins | LLM Tokens/Page | LLM Role |
|---|-------|---------------|-----------|------------|-----------------|----------|
| 1 | Medication interactions | B | 1-2 | 2-3 | 800-1200 | Synthesis + safety framing |
| 2 | Job salary by city | A | 1 | 1-2 | 600-900 | Connective prose only |
| 3 | Dog/cat breed comparisons | B | 2 | 1 | 1000-1400 | Comparative synthesis |
| 4 | Plant growing by zone | B | 1-2 | 2 | 800-1200 | Zone-specific advice synthesis |
| 5 | Food nutrition | A | 1 | 1 | 500-800 | Minimal — data display + context |
| 6 | College comparisons | B | 2 | 2-3 | 1000-1500 | Comparative narrative |
| 7 | Product alternatives | D | 3-5 | 3+ | 1500-2500 | Heavy generation — no single dataset |
| 8 | City cost of living | A | 1 | 2 | 700-1000 | Connective prose + context |
| 9 | Baby name meanings | C | 2 | 2-3 | 1000-1500 | Moderate generation — cultural context |
| 10 | Supplement interactions | C | 1-2 | 2-3 | 1000-1500 | Synthesis + safety framing |
| 11 | Hiking trail guides | C | 2-3 | 3+ | 1200-1800 | Moderate — trail description generation |
| 12 | Car comparisons | B | 2 | 2 | 1000-1500 | Comparative synthesis |
| 13 | Recipe nutrition | B | 1-2 | 2 | 800-1200 | Light synthesis — data-heavy |

---

## Detailed Analysis by Niche

### 1. Medication Interactions

**Query pattern:** "[drug A] and [drug B]"
**Pipeline grade:** B — Straightforward

**Data-to-page mapping:**
- FDA Adverse Event Reporting System (FAERS) and NIH DailyMed provide structured interaction data
- Each page needs: two drug profiles (class, mechanism) + interaction severity + clinical significance
- Data maps cleanly to the query — the pair IS the lookup key

**Template structure:**
- 1 primary template: drug-A-and-drug-B interaction page
- 1 variant for no-known-interaction cases (still valuable — "no interaction found" is an answer)

**Data joins:**
1. Drug A profile (DailyMed → name, class, mechanism, common uses)
2. Interaction record (FAERS/DrugBank → severity, type, evidence level)
3. Drug B profile (same as #1)

**LLM role:** Synthesis + safety framing. The data provides facts; the LLM writes the explanatory paragraph ("Why this matters," "What to tell your doctor"). LLM does NOT invent interaction data — it frames existing data for a lay reader.

**LLM tokens/page:** 800-1200 output tokens (~400-600 words of prose around structured data)

**Key risk:** YMYL (Your Money or Your Life) — Google scrutinizes health content heavily. Must include disclaimers and cite sources. Does not disqualify but raises the quality bar.

**Verdict:** Strong candidate. Rich structured data, clean 1:1 mapping, manageable LLM role. YMYL risk is the main concern.

---

### 2. Job Salary by City

**Query pattern:** "[job title] salary in [city]"
**Pipeline grade:** A — Trivial

**Data-to-page mapping:**
- BLS Occupational Employment and Wage Statistics (OEWS) provides exact salary data by metro area and occupation
- Each page IS a direct database lookup: occupation code × metro area code → salary percentiles
- Schema: 10th/25th/50th/75th/90th percentile wages, employment count, hourly vs annual

**Template structure:**
- 1 template handles all pages. Every page has identical structure: salary range, percentiles, comparison to national average, cost-of-living context

**Data joins:**
1. BLS OEWS data (occupation × metro → salary percentiles)
2. Optional: BLS area cost-of-living index for context

**LLM role:** Minimal. Connective prose between data points. "A [title] in [city] earns a median salary of $X, which is Y% above/below the national median of $Z." The data IS the content.

**LLM tokens/page:** 600-900 output tokens. Most of the page is tables and structured data.

**Key risk:** Extremely competitive — sites like Glassdoor, Indeed, PayScale already dominate. But they focus on popular titles in large cities; the long tail (niche titles × small metros) is underserved.

**Verdict:** Easiest pipeline of all 13. Data is clean, structured, and perfectly maps to the query pattern. Competition is the concern, not feasibility.

---

### 3. Dog/Cat Breed Comparisons

**Query pattern:** "[breed A] vs [breed B]"
**Pipeline grade:** B — Straightforward

**Data-to-page mapping:**
- AKC (dogs) and breed registries provide structured breed attributes: size, weight, lifespan, temperament tags, exercise needs, grooming level, good-with-kids rating
- Each page compares two breeds across these attributes
- The combination IS the lookup: breed A attributes × breed B attributes → comparison

**Template structure:**
- 1 template for dog-vs-dog comparisons
- 1 template for cat-vs-cat (slightly different attributes — indoor/outdoor, litter behavior)
- Could stretch to dog-vs-cat but query volume is minimal

**Data joins:**
1. Breed A profile (registry → all attributes)
2. Breed B profile (same source)
- No complex joins — it's two lookups and a diff

**LLM role:** Comparative synthesis. Data provides the numbers; LLM writes "If you're choosing between these breeds..." narrative. LLM adds lifestyle-fit advice ("better for apartments," "needs a yard") that isn't in raw data but is inferrable from size/exercise/temperament fields.

**LLM tokens/page:** 1000-1400 output tokens. Comparison narrative is the value-add.

**Key risk:** Breed data is somewhat subjective (temperament descriptions vary by source). Need consistent source.

**Verdict:** Clean pipeline. Two lookups, one template family, moderate LLM role. Good candidate.

---

### 4. Plant Growing by Zone

**Query pattern:** "how to grow [plant] in [zone]"
**Pipeline grade:** B — Straightforward

**Data-to-page mapping:**
- USDA Plant Hardiness Zone Map provides zone definitions
- Various agricultural extension databases provide plant requirements (sun, soil pH, water, frost tolerance, planting dates)
- Each page: plant requirements × zone constraints → growing advice

**Template structure:**
- 1 primary template: plant-in-zone guide
- 1 variant for "can't grow" cases (plant is incompatible with zone — still a valid page: "alternatives to [plant] in [zone]")

**Data joins:**
1. Plant profile (extension DB → requirements, growing season, soil needs)
2. Zone profile (USDA → temperature ranges, frost dates, typical conditions)

**LLM role:** Zone-specific advice synthesis. Data says the plant needs X conditions and the zone has Y conditions. LLM bridges the gap: "In Zone 7, start [plant] indoors in March because your last frost date is typically April 15." This is inference from data, not pure generation.

**LLM tokens/page:** 800-1200 output tokens. Practical growing advice around structured data.

**Key risk:** Data fragmentation — no single source covers all plants with all attributes. May need to merge multiple extension databases. Coverage gaps for ornamental/exotic plants.

**Verdict:** Good pipeline. Data exists but is scattered across sources — the join complexity is the main challenge, not the LLM role.

---

### 5. Food Nutrition

**Query pattern:** "calories in [food] [preparation method]"
**Pipeline grade:** A — Trivial

**Data-to-page mapping:**
- USDA FoodData Central is the gold standard: 380,000+ food items with full nutrient profiles
- Each page IS a direct lookup: food item → macros, micros, serving sizes
- API is well-documented, bulk download available in CSV/JSON

**Template structure:**
- 1 template. Every page is identical: nutrition facts table, macronutrient breakdown, comparison to daily values, serving size context.

**Data joins:**
1. USDA FoodData Central (food item → full nutrient profile)
- Single source, single lookup. The simplest possible pipeline.

**LLM role:** Minimal. "A [serving] of [food] contains [X] calories, [Y]g protein..." The data IS the answer. LLM adds 2-3 sentences of context ("This is considered a [high/moderate/low]-calorie food").

**LLM tokens/page:** 500-800 output tokens. Mostly structured data display.

**Key risk:** Dominated by established players (MyFitnessPal, Nutritionix, CalorieKing). The long tail exists in specific preparation methods ("air-fried chicken thigh" vs "deep-fried chicken thigh") where big sites lack granularity.

**Verdict:** Simplest pipeline alongside job salary. One API, one lookup, one template. Competition is fierce but the long tail is deep.

---

### 6. College Comparisons

**Query pattern:** "[school A] vs [school B]"
**Pipeline grade:** B — Straightforward

**Data-to-page mapping:**
- NCES/IPEDS (Integrated Postsecondary Education Data System) provides rich structured data: tuition, enrollment, acceptance rate, graduation rate, student demographics, financial aid, test scores
- Each page compares two institutions across these dimensions
- College Scorecard API adds earnings data and loan repayment rates

**Template structure:**
- 1 primary template for 4-year institution comparisons
- 1 variant for community college comparisons (different relevant metrics)

**Data joins:**
1. School A profile (IPEDS → all metrics)
2. School B profile (IPEDS → all metrics)
3. Optional: College Scorecard (earnings outcomes, loan data)

**LLM role:** Comparative narrative. Data provides the numbers; LLM writes "Students choosing between [A] and [B] should consider..." synthesis. LLM contextualizes differences ("School A's 15% acceptance rate vs School B's 45% means...").

**LLM tokens/page:** 1000-1500 output tokens. Comparison narrative is substantial.

**Key risk:** Niche.com and US News already cover popular comparisons. Long tail is less-searched school pairs. Also some comparisons are meaningless (community college vs Ivy League).

**Verdict:** Clean pipeline. Well-structured federal data, clear comparison template. Moderate competition in the long tail.

---

### 7. Product Alternatives

**Query pattern:** "[product] alternatives"
**Pipeline grade:** D — Complex

**Data-to-page mapping:**
- **No single structured dataset exists.** Product information is scattered across manufacturer sites, Amazon, review sites, and proprietary databases.
- "Alternatives" requires understanding product category, feature set, and competitive landscape — this is knowledge, not data.
- Product landscape changes constantly — new products launch, old ones discontinue.

**Template structure:**
- 3-5 templates needed: software alternatives, physical product alternatives, service alternatives, free-vs-paid alternatives, open-source alternatives
- Each category has fundamentally different comparison axes

**Data joins:**
- No clean joins possible. Would need to:
  1. Identify product category (manual or LLM classification)
  2. Find competitors (no API — requires web scraping or LLM knowledge)
  3. Compare features (no structured source)

**LLM role:** Heavy generation. The LLM IS the data source — it's generating alternative lists from training knowledge. This is exactly what programmatic SEO should NOT rely on: unverifiable LLM-generated content.

**LLM tokens/page:** 1500-2500 output tokens. Almost entirely generated prose.

**Key risk:** Content staleness (products change fast), accuracy (LLM may hallucinate products or features), and competition (G2, AlternativeTo, Capterra are entrenched).

**Verdict:** Not viable for programmatic SEO. No structured data pipeline. LLM carries almost the entire content load. This is a traditional content site, not a data-driven one.

---

### 8. City Cost of Living

**Query pattern:** "cost of living in [city]" / "[city A] vs [city B] cost of living"
**Pipeline grade:** A — Trivial

**Data-to-page mapping:**
- BLS Consumer Expenditure Survey and regional price parities provide structured cost data
- Census Bureau provides housing costs, income data
- C2ER (Council for Community and Economic Research) publishes the Cost of Living Index
- Each page: city → housing, groceries, transportation, healthcare, utilities indices

**Template structure:**
- 1 template. Every city page has the same structure: overall index, category breakdown, comparison to national average, salary needed to live comfortably.

**Data joins:**
1. BLS regional price parities (city → overall cost index)
2. Census/ACS data (city → median rent, median income, housing costs)
- Two clean joins on city/metro identifier

**LLM role:** Connective prose + context. "Living in [city] costs X% more/less than the national average, primarily driven by housing costs that are..." The data tells the story; LLM narrates it.

**LLM tokens/page:** 700-1000 output tokens. Data-heavy pages with light narrative.

**Key risk:** Numbeo, Nerdwallet, and BestPlaces are established. But their data is often crowd-sourced and inconsistent. Federal data + clean presentation is a differentiator.

**Verdict:** Excellent pipeline. Clean federal data, single template, minimal LLM role. Competition exists but the data advantage is real.

---

### 9. Baby Name Meanings

**Query pattern:** "[name] meaning" / "what does the name [name] mean"
**Pipeline grade:** C — Moderate

**Data-to-page mapping:**
- SSA (Social Security Administration) provides name popularity data: frequency by year, rank, trends
- Name etymology/meaning is NOT in a single structured database — scattered across etymological references
- Each page needs: meaning, origin, popularity trend, famous namesakes

**Template structure:**
- 1 template for name detail pages
- 1 variant for name comparison pages ("[name A] vs [name B]")

**Data joins:**
1. SSA name popularity data (name → yearly counts, rank, gender distribution)
2. Etymology data (name → meaning, origin language, cultural context) — **no clean API**
3. Optional: famous namesakes — **no structured source**

**LLM role:** Moderate generation. SSA provides popularity data, but meaning/origin/cultural context must come from LLM knowledge or scraped reference data. This is a hybrid: half data-driven, half knowledge-driven.

**LLM tokens/page:** 1000-1500 output tokens. Etymology and cultural sections are LLM-generated.

**Key risk:** Nameberry, BehindTheName, and BabyCenter are massive incumbents. Name etymology is inherently subjective and often disputed. LLM-generated etymology could contain errors.

**Verdict:** Moderate feasibility. Popularity data is clean (SSA) but the core value proposition (meaning/origin) lacks structured data. LLM fills the gap but accuracy is hard to verify at scale.

---

### 10. Supplement Interactions

**Query pattern:** "[supplement A] and [supplement B]" / "[supplement] and [drug]"
**Pipeline grade:** C — Moderate

**Data-to-page mapping:**
- NIH Office of Dietary Supplements provides supplement fact sheets
- Natural Medicines database (requires license) has interaction data
- FDA MedWatch for adverse event reports involving supplements
- Data is much sparser than drug interactions — many combinations have no studied interaction

**Template structure:**
- 1 template for supplement-supplement interactions
- 1 template for supplement-drug interactions (different severity framework)

**Data joins:**
1. Supplement A profile (NIH ODS → mechanism, common uses, dosing)
2. Interaction record (Natural Medicines / published studies — **sparse**)
3. Supplement B or Drug profile

**LLM role:** Synthesis + safety framing, but with more generation than drug interactions. Many interaction pairs have minimal published data, so LLM must synthesize from mechanism-of-action reasoning ("Both supplements affect blood clotting, so concurrent use may increase bleeding risk").

**LLM tokens/page:** 1000-1500 output tokens. More interpretive than drug interactions.

**Key risk:** YMYL scrutiny (same as medications). Sparser data means more LLM interpretation, which increases hallucination risk for health content. Regulatory gray area — supplements are not FDA-regulated like drugs.

**Verdict:** Moderate feasibility. The data pipeline is weaker than drug interactions due to sparser research. LLM role is larger, and YMYL stakes make inaccuracy more costly.

---

### 11. Hiking Trail Guides

**Query pattern:** "[trail name] guide" / "hiking [trail] in [park]"
**Pipeline grade:** C — Moderate

**Data-to-page mapping:**
- USFS (US Forest Service) and NPS (National Park Service) provide trail data: length, elevation gain, difficulty rating, coordinates
- But a trail "guide" needs more than stats: trailhead directions, what to expect, seasonal conditions, permits, gear recommendations
- Trail data quality varies wildly — some trails have rich data, many have only a name and coordinates

**Template structure:**
- 1 template for well-documented trails (has full stats + official description)
- 1 template for minimal-data trails (coordinates + LLM-generated description)
- 1 variant for "best trails in [area]" roundup pages

**Data joins:**
1. Trail profile (USFS/NPS → name, length, elevation, difficulty, coordinates)
2. Park/area context (NPS → hours, fees, permits, seasonal closures)
3. Weather/conditions (NOAA → typical conditions by season) — **optional**

**LLM role:** Moderate to heavy. Trail stats are data-driven, but the actual "guide" content (what you'll see, difficulty assessment, when to go) requires either local knowledge or LLM generation. For popular trails, training data is rich. For obscure trails, LLM may produce generic filler.

**LLM tokens/page:** 1200-1800 output tokens. Trail narrative is the bulk of the page.

**Key risk:** AllTrails dominates this space with user-generated reviews and GPS tracks. Trail conditions change seasonally — static pages can become dangerously outdated ("bridge washed out" etc.). Liability concern if someone follows outdated advice into unsafe conditions.

**Verdict:** Moderate feasibility. Stats pipeline is clean but the guide content that users actually want requires substantial LLM generation. AllTrails' user-generated content moat is strong. Safety/liability is a real concern.

---

### 12. Car Comparisons

**Query pattern:** "[car A] vs [car B]"
**Pipeline grade:** B — Straightforward

**Data-to-page mapping:**
- NHTSA provides safety ratings and recall data
- EPA provides fuel economy data (fueleconomy.gov — excellent API)
- Vehicle specs (dimensions, engine, features) available from various sources (Edmunds API, CarQuery)
- Each page compares two vehicles across safety, fuel economy, specs, pricing

**Template structure:**
- 1 template for same-class comparisons (sedan vs sedan)
- 1 template for cross-class comparisons (SUV vs truck — different emphasis)

**Data joins:**
1. Vehicle A profile (specs + safety + fuel economy)
2. Vehicle B profile (same sources)
3. Optional: pricing data (MSRP from manufacturer, used prices from market data)

**LLM role:** Comparative synthesis. Data provides specs; LLM writes "The [A] edges out the [B] in fuel economy, but the [B] offers more cargo space..." narrative. Similar role to breed and college comparisons.

**LLM tokens/page:** 1000-1500 output tokens. Comparison narrative around structured data.

**Key risk:** Extremely competitive — CarAndDriver, Edmunds, MotorTrend, KBB all have comparison tools. They also have editorial authority Google respects. Long tail exists in obscure model-year combinations.

**Verdict:** Clean pipeline but fierce competition. Data is well-structured from federal sources (EPA, NHTSA). The challenge is ranking against automotive authority sites, not building the pipeline.

---

### 13. Recipe Nutrition

**Query pattern:** "nutrition in [recipe]" / "[dish] calories"
**Pipeline grade:** B — Straightforward

**Data-to-page mapping:**
- USDA FoodData Central provides per-ingredient nutrition data
- A "recipe" is a list of ingredients × quantities → sum the nutrition
- Common recipes have well-known ingredient lists; the pipeline is: recipe definition → ingredient lookup → nutrient aggregation

**Template structure:**
- 1 primary template: recipe nutrition breakdown (per serving, per recipe, macros, micros)
- 1 variant for recipe comparison pages ("[dish A] vs [dish B] nutrition")

**Data joins:**
1. Recipe definition (ingredient list + quantities — **this is the gap**)
2. Per-ingredient nutrition (USDA FoodData Central → nutrients per 100g)
3. Aggregation: sum across ingredients, divide by servings

**LLM role:** Light synthesis around data. But there's a hidden dependency: who defines the "standard" recipe? For "chicken parmesan nutrition," someone must specify the ingredient list. Options: (a) use a published recipe database, (b) have LLM generate a "standard" recipe, (c) show ranges. Option (b) undermines the data-driven premise.

**LLM tokens/page:** 800-1200 output tokens. Mostly data display + health context.

**Key risk:** The recipe definition problem. Unlike pure lookups (food → nutrition), this requires an intermediate step (dish → recipe → ingredients → nutrition). Recipe variation is huge — "mac and cheese" has infinite versions. Need a defensible approach to "standard" recipes.

**Verdict:** Good pipeline IF the recipe definition problem is solved. The nutrition calculation itself is trivial (USDA data is excellent). The question is where the recipe ingredients come from. Using a published recipe database (e.g., Open Recipe Format datasets) would make this A-grade; relying on LLM-generated recipes drops it to C.

---

## Pipeline Complexity Ranking (Easiest to Hardest)

| Rank | Niche | Grade | Rationale |
|------|-------|-------|-----------|
| 1 | Food nutrition | A | Single API lookup, one template, minimal LLM |
| 2 | Job salary by city | A | BLS data maps perfectly to query pattern |
| 3 | City cost of living | A | Clean federal data, single template |
| 4 | Dog/cat breed comparisons | B | Two lookups, straightforward comparison |
| 5 | Plant growing by zone | B | Two joins, zone-specific synthesis |
| 6 | College comparisons | B | Rich IPEDS data, comparison template |
| 7 | Car comparisons | B | Multiple federal APIs, comparison template |
| 8 | Recipe nutrition | B | Trivial calculation IF recipe source exists |
| 9 | Medication interactions | B | Good data but YMYL raises quality bar |
| 10 | Baby name meanings | C | SSA for popularity, LLM for etymology |
| 11 | Supplement interactions | C | Sparse data, YMYL, more LLM interpretation |
| 12 | Hiking trail guides | C | Stats are clean, guide content needs LLM |
| 13 | Product alternatives | D | No structured data, LLM-dependent |

---

## Key Findings

### Three pipeline archetypes emerged:

**1. Pure Lookup (A-grade):** One data source, one query, one template. The data IS the page.
- Food nutrition, job salary, cost of living
- LLM tokens: 500-1000/page. Cheapest to produce.
- Risk: competition from established data sites.

**2. Structured Comparison (B-grade):** Two entity lookups + comparison template. LLM writes the narrative bridge.
- Breed comparisons, college comparisons, car comparisons, plant guides, medication interactions, recipe nutrition
- LLM tokens: 800-1500/page. Moderate cost.
- Risk: comparison template must feel natural, not robotic.

**3. Knowledge-Dependent (C/D-grade):** Data is sparse or absent for key page content. LLM fills gaps from training knowledge.
- Baby names, supplement interactions, hiking guides, product alternatives
- LLM tokens: 1000-2500/page. Most expensive.
- Risk: accuracy, staleness, hallucination. Undermines the data-driven thesis.

### Recommendations for niche selection:

1. **Prioritize A and B-grade pipelines.** The business model's core advantage is data-driven pages at near-zero marginal cost. C/D-grade niches erode this advantage.

2. **YMYL niches (medication, supplement interactions) require extra investment** in accuracy verification, source citation, and disclaimers — even with B-grade pipelines.

3. **Product alternatives should be eliminated.** It has no programmatic data pipeline and would produce the kind of AI-generated listicles Google explicitly devalues.

4. **Recipe nutrition is B-grade only with a recipe source database.** Without one, it falls to C-grade. Confirm the data source exists before committing.

5. **The ideal first niche has:** A/B-grade pipeline + low competition + high RPM + deep long tail. Job salary by city and food nutrition score highest on pipeline ease but face the most competition. Breed comparisons and plant growing by zone may offer the best pipeline-to-competition ratio.
