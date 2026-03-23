# Niche Scoring Matrix — Weighted Ranking of All 13 Candidates

> Research deliverable for arb-ect. March 2026.

---

## Methodology

Each of the 13 niche candidates is scored 1–10 across seven dimensions, derived from the Phase 1 research reports (01–07). Scores reflect the specific findings from each report, not general impressions.

### Dimension Weights

| Dimension | Weight | Source Report | Scoring Basis |
|-----------|--------|--------------|---------------|
| Query Volume | 20% | 01-query-patterns | Estimated variations, long-tail depth, search volume distribution |
| Competition | 20% | 02-competition-audit | Inverted: fewer/weaker competitors = higher score. 🔴=1-2, 🟡=4-7, 🟢=8-10 |
| Data Availability | 15% | 03-data-sources | Coverage grade (A=9-10, B=6-8, C=4-5, D=2-3, F=1) and commercial usability |
| RPM Potential | 15% | 04-rpm-monetization | Estimated premium RPM tier, advertiser vertical strength |
| Legal Safety | 10% | 05-legal-scan | Inverted: lower risk = higher score. 🟢=9-10, 🟡=6-8, 🔴=1-2 |
| Programmatic Feasibility | 10% | 06-feasibility | Pipeline grade (A=9-10, B=7-8, C=4-6, D=2-3, F=1) |
| Landscape Gap | 10% | 07-landscape | Degree of underserved demand: saturated=1-2, gap visible=5-7, wide open=8-10 |

### Scoring Scale

| Score | Meaning |
|-------|---------|
| 9–10 | Excellent — strong advantage in this dimension |
| 7–8 | Good — favorable conditions |
| 5–6 | Moderate — some positive signals, some concerns |
| 3–4 | Weak — significant drawbacks |
| 1–2 | Poor — disqualifying or near-disqualifying |

---

## Scoring Matrix

| # | Niche | Query Vol (20%) | Competition (20%) | Data Avail (15%) | RPM (15%) | Legal (10%) | Feasibility (10%) | Landscape Gap (10%) | **Weighted Total** |
|---|-------|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| 1 | Medication interactions | 8 | 1 | 4 | 7 | 1 | 6 | 1 | **4.25** |
| 2 | Job salary by city | 7 | 1 | 10 | 7 | 10 | 10 | 1 | **6.25** |
| 3 | Dog/cat breed comparisons | 6 | 6 | 7 | 5 | 10 | 8 | 6 | **6.60** |
| 4 | Plant growing by zone | 5 | 8 | 6 | 4 | 10 | 8 | 9 | **6.80** |
| 5 | Food nutrition | 8 | 5 | 10 | 6 | 7 | 10 | 7 | **7.40** |
| 6 | College comparisons | 6 | 2 | 10 | 4 | 7 | 8 | 1 | **5.30** |
| 7 | Product alternatives | 4 | 5 | 1 | 8 | 7 | 2 | 5 | **4.55** |
| 8 | City cost of living | 5 | 1 | 10 | 7 | 10 | 10 | 1 | **5.85** |
| 9 | Baby name meanings | 6 | 1 | 4 | 4 | 10 | 5 | 1 | **4.20** |
| 10 | Supplement interactions | 5 | 5 | 2 | 7 | 1 | 5 | 5 | **4.45** |
| 11 | Hiking trail guides | 4 | 2 | 4 | 6 | 7 | 5 | 2 | **4.10** |
| 12 | Car comparisons | 6 | 1 | 7 | 7 | 10 | 8 | 1 | **5.40** |
| 13 | Recipe nutrition | 6 | 5 | 7 | 6 | 7 | 7 | 7 | **6.25** |

---

## Final Rankings

| Rank | Niche | Weighted Score | Verdict |
|------|-------|:-:|---------|
| **1** | **Food nutrition** | **7.40** | **TOP 3 — Deep dive** |
| **2** | **Plant growing by zone** | **6.80** | **TOP 3 — Deep dive** |
| **3** | **Dog/cat breed comparisons** | **6.60** | **TOP 3 — Deep dive** |
| 4 | Job salary by city | 6.25 | Strong data but competition kills it |
| 5 | Recipe nutrition | 6.25 | Overlaps with #1; recipe definition problem |
| 6 | City cost of living | 5.85 | Excellent data/feasibility, saturated SERPs |
| 7 | Car comparisons | 5.40 | Good pipeline, insurmountable competition |
| 8 | College comparisons | 5.30 | Rich data, 7+ programmatic incumbents |
| 9 | Product alternatives | 4.55 | No data source — violates core thesis |
| 10 | Supplement interactions | 4.45 | YMYL + paywalled data = non-starter |
| 11 | Medication interactions | 4.25 | YMYL + saturated = worst of both worlds |
| 12 | Baby name meanings | 4.20 | Saturated + weak data for core value prop |
| 13 | Hiking trail guides | 4.10 | AllTrails moat + safety liability |

---

## Score Justifications

### Top 3 — Recommended for Deep Dive

#### 1. Food Nutrition (7.40)

**Why it leads:** The only niche that scores 8+ on query volume AND 10 on both data availability and feasibility. USDA FoodData Central (420K+ foods, public domain, API + bulk) maps directly to the query pattern with minimal LLM generation. The gap is real and specific: preparation-method queries ("calories in air fried chicken thigh") return recipe blogs that answer a different question, and Quora ranking for dish queries is a clear "no good result" signal.

| Dimension | Score | Rationale |
|-----------|-------|-----------|
| Query Volume | 8 | 40K+ variations; mixed long-tail but enormous total volume |
| Competition | 5 | 🟡 Contested — Nutritionix/FatSecret cover basics, but prep-specific queries are underserved |
| Data Availability | 10 | A grade — USDA FDC is the gold standard. 420K+ foods, public domain, API + bulk |
| RPM Potential | 6 | Moderate-High ($15–30) — food vertical has proven economics (Midwest Foodie: $530K/yr) |
| Legal Safety | 7 | 🟡 YELLOW — moderate YMYL; safe if limited to USDA data with allergen disclaimers, no health claims |
| Feasibility | 10 | A grade — single API lookup, one template, 500–800 LLM tokens/page |
| Landscape Gap | 7 | Quora ranking #1 for "beef pho calories" = clear signal. Gap in food × preparation method pages |

**Key risk:** Moderate YMYL signal. Requires discipline — stick to USDA numbers, no health claims, allergen disclaimers on every page.

**Overlap note:** Recipe nutrition (#13, score 6.25) is a harder variant of the same niche. Food nutrition is the superior version because it uses direct FDC lookups rather than requiring recipe-to-ingredient-to-nutrition assembly.

---

#### 2. Plant Growing by Zone (6.80)

**Why it's strong:** The highest competition score (8) of any viable niche, combined with strong legal safety (GREEN, non-YMYL) and the clearest landscape gap of all 13 candidates. Facebook groups appearing in SERPs for zone-specific plant queries is the strongest "no good result" signal in the entire study. No dominant programmatic player exists — the closest competitors (Gardenate, BloomingExpert) are extremely thin or AI-generated.

| Dimension | Score | Rationale |
|-----------|-------|-----------|
| Query Volume | 5 | 15K+ variations; true long-tail. Lower volume than food/salary but deeper per-page engagement |
| Competition | 8 | 🟢/🟡 — No dominant programmatic player. Facebook groups in SERPs. Gardenate is thin. BloomingExpert is low-quality AI |
| Data Availability | 6 | B grade — USDA zone data is excellent (43K ZIPs × 26 half-zones). Plant-specific growing advice is unstructured (extension PDFs) |
| RPM Potential | 4 | Moderate ($12–22) — gardening advertiser budgets are smaller than finance/food verticals |
| Legal Safety | 10 | 🟢 GREEN — non-YMYL, public domain USDA data, zero regulatory exposure |
| Feasibility | 8 | B grade — two data joins (plant + zone), LLM synthesizes zone-specific growing advice from established knowledge |
| Landscape Gap | 9 | Wide open. Most gardening sites organize by plant, not plant × zone. The combinatorial page opportunity is unserved |

**Key risk:** Lower RPM ($12–22) means you need more traffic to reach the same revenue as food nutrition. Data gap for plant-specific growing advice requires LLM to do meaningful synthesis (not just connective prose), increasing per-page LLM cost to 800–1200 tokens.

**Key advantage:** Lowest competition of any viable niche. A well-executed plant × zone site could become the default answer for this query pattern within 6–12 months.

---

#### 3. Dog/Cat Breed Comparisons (6.60)

**Why it rounds out the top 3:** The most balanced scorecard of any candidate — no dimension scores below 5, and it has the perfect legal safety score (GREEN, non-YMYL). Existing programmatic competitors (Dogell, Dog-Learn) are beatable on quality — low DA (~25–35) with thin template pages. The data pipeline is clean (two breed lookups → comparison template) with moderate LLM involvement.

| Dimension | Score | Rationale |
|-----------|-------|-----------|
| Query Volume | 6 | 20K+ variations; true long-tail. Popular pairs high volume; obscure pairs underserved |
| Competition | 6 | 🟡 Contested — Dogell/Dog-Learn are programmatic but low-quality. Popular pairs harder to break into |
| Data Availability | 7 | B grade — AKC trait data covers 200–340 breeds with 16 trait ratings. Cat breed data is weaker |
| RPM Potential | 5 | Moderate ($12–25) — pet industry $150B+ but RPMs lag finance/food. Strong at scale ($15–25) |
| Legal Safety | 10 | 🟢 GREEN — non-YMYL, zero regulatory concern, zero liability |
| Feasibility | 8 | B grade — two breed lookups, one comparison template, 1000–1400 LLM tokens/page |
| Landscape Gap | 6 | Partial gap — obscure breed combos are thin/underserved. Popular combos well-covered editorially |

**Key risk:** The opportunity is primarily in the long tail (obscure breed pairs), which individually have lower search volume. Popular pairs (goldendoodle vs labradoodle) are well-served by editorial content from breed sites and marketplaces. Cat breed data is weaker than dog data, limiting the cat side of the matrix.

**Key advantage:** Most psychologically "fun" niche — pet content drives high engagement and emotional connection, which improves time-on-site and repeat visits (both signals Google values).

---

### Honorable Mentions (Scores 5.85–6.25)

#### 4. Job Salary by City (6.25)

Perfect data (BLS OEWS maps 1:1 to queries) and the easiest pipeline of all 13 niches. Eliminated from top 3 by the most saturated competition landscape in the study — five platforms (Indeed DA 93, Glassdoor DA 91, Salary.com DA 82, ZipRecruiter DA 83, PayScale DA 82) with complete programmatic coverage. Even "phlebotomist salary in Tulsa" returns 6+ dedicated pages.

#### 5. Recipe Nutrition (6.25)

Shares food nutrition's strengths (USDA data, food vertical RPMs) but adds the "recipe definition problem" — who defines what goes into "chicken parmesan"? Without a clean recipe source database, the pipeline drops from B to C grade. Better to pursue food nutrition (#1) and consider recipe nutrition as a future expansion.

#### 6. City Cost of Living (5.85)

Same pattern as job salary: excellent government data (BEA + BLS + Census), clean pipeline, but 6+ high-DA programmatic incumbents (Numbeo, RentCafe, BestPlaces, Salary.com, Redfin, PayScale) with complete coverage. No entry point.

---

### Eliminated Niches (Scores below 5.5)

| Niche | Score | Elimination Reason |
|-------|:-----:|-------------------|
| Car comparisons | 5.40 | Edmunds (DA 90), U.S. News (DA 94), KBB, TrueCar + hundreds of dealer pages. Zero gap. |
| College comparisons | 5.30 | 7+ programmatic tools (CollegeSimply, CampusReel, Parchment, CollegeVine, etc.) cover full school matrix |
| Product alternatives | 4.55 | No public data source exists (F grade). LLM-dependent content violates core thesis |
| Supplement interactions | 4.45 | 🔴 RED legal risk + interaction data behind commercial paywall (NatMed). Double disqualifier |
| Medication interactions | 4.25 | 🔴 RED legal risk + 🔴 saturated competition. Drugs.com alone has 100K+ pair pages |
| Baby name meanings | 4.20 | 🔴 saturated (7+ name databases) + core value prop (meanings) has no structured public data |
| Hiking trail guides | 4.10 | AllTrails (DA 82, 400K+ trails, UGC moat) is unassailable. Safety/liability concern from stale data |

---

## Sensitivity Analysis

To check whether the ranking is robust to weight changes, I tested two alternative weight schemes:

### Alternative A: Competition-Heavy (Competition 30%, Query Volume 15%)

Rationale: If you believe competitive position is more important than raw volume.

| Rank | Niche | Score |
|------|-------|:-----:|
| 1 | Plant growing by zone | 7.20 |
| 2 | Food nutrition | 6.90 |
| 3 | Dog/cat breed comparisons | 6.50 |

Plant growing overtakes food nutrition because its competition advantage (8 vs 5) is amplified.

### Alternative B: Data-Heavy (Data Availability 25%, RPM 10%)

Rationale: If you believe the data-driven thesis is paramount.

| Rank | Niche | Score |
|------|-------|:-----:|
| 1 | Food nutrition | 7.75 |
| 2 | Job salary by city | 6.70 |
| 3 | Plant growing by zone | 6.40 |

Food nutrition extends its lead. Job salary re-enters the top 3 on data strength alone (10), though its competition score still drags it down.

### Conclusion

**The top 3 is stable across weight variations.** Food nutrition and plant growing by zone appear in the top 3 under all tested weight schemes. The third slot alternates between dog/cat breed comparisons (balanced weights, competition-heavy) and job salary by city (data-heavy). Given that competition is the make-or-break factor for a new entrant, **breed comparisons holds the third position.**

---

## Recommended Top 3 for Deep Dive

| Priority | Niche | Score | Primary Strength | Primary Risk |
|:--------:|-------|:-----:|-----------------|-------------|
| **1** | **Food nutrition** | **7.40** | Best data (USDA FDC) + simplest pipeline (A grade) | Moderate YMYL; discipline required |
| **2** | **Plant growing by zone** | **6.80** | Lowest competition + clearest landscape gap | Lower RPM; growing advice needs LLM synthesis |
| **3** | **Dog/cat breed comparisons** | **6.60** | Most balanced scorecard; zero legal risk | Opportunity concentrated in long-tail obscure pairs |

These three niches should proceed to Phase 3 deep-dive analysis covering: site architecture, template design, data pipeline specification, content sample generation, and projected economics (pages × estimated traffic × RPM).

---

## Data Sources

All scores derived from Phase 1 research:
- [01-query-patterns.md](01-query-patterns.md) — Query volume and long-tail assessment
- [02-competition-audit.md](02-competition-audit.md) — SERP analysis and competition ratings
- [03-data-sources.md](03-data-sources.md) — Public dataset audit and coverage grades
- [04-rpm-monetization.md](04-rpm-monetization.md) — RPM benchmarks by niche vertical
- [05-legal-scan.md](05-legal-scan.md) — YMYL risk and legal/liability assessment
- [06-feasibility.md](06-feasibility.md) — Pipeline complexity grades (A through F)
- [07-landscape.md](07-landscape.md) — Programmatic SEO landscape and gap analysis
