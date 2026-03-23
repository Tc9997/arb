# Legal and Liability Scan — YMYL Risk Assessment

**Bead:** arb-e44
**Date:** 2026-03-23
**Purpose:** Assess legal/liability risk for all 13 niche candidates under Google's YMYL (Your Money Your Life) quality rater guidelines, FTC/FDA disclosure requirements, and content liability precedent.

---

## Rating System

| Rating | Meaning |
|--------|---------|
| 🟢 GREEN | Safe — low YMYL signal, minimal regulatory exposure, no liability precedent |
| 🟡 YELLOW | Caution — moderate YMYL signal or regulatory nuance; feasible with disclaimers |
| 🔴 RED | Avoid — high YMYL, significant liability risk, regulatory requirements likely unachievable at programmatic scale |

---

## YMYL Background

Google's Search Quality Rater Guidelines define YMYL topics as those that "could significantly impact the health, financial stability, or safety of people." YMYL pages face the highest E-E-A-T (Experience, Expertise, Authoritativeness, Trustworthiness) scrutiny. Programmatic AI content in YMYL niches faces compounded risk: both Google's algorithmic demotion of thin YMYL content AND potential legal liability if content causes harm.

---

## Niche Assessments

### 1. Medication Interactions

**Rating: 🔴 RED**

**YMYL classification:** Explicitly YMYL — health/medical. Google's quality rater guidelines specifically call out medical information as the highest-risk YMYL category.

**Legal/regulatory risk:**
- **FDA:** Drug interaction information is regulated. While informational content is protected speech, presenting drug interaction data programmatically risks omitting critical context (dosage, patient-specific factors, contraindications) that could cause direct physical harm.
- **Liability precedent:** Courts have held that publishers of medical information can be liable under negligence theories when content is presented as authoritative and a reader relies on it to their detriment. *Brandt v. Weather Channel* and similar cases establish that even aggregators of factual data can face liability when the data relates to health decisions.
- **Professional licensing:** In some jurisdictions, providing specific drug interaction guidance without a medical license could be construed as practicing medicine without a license.

**Google ranking outlook:** Near-zero chance of ranking. Google's Helpful Content system heavily demotes AI-generated medical content lacking demonstrated E-E-A-T. Sites like WebMD, Drugs.com, and Mayo Clinic dominate this space with editorial review boards.

**Verdict:** Existential liability risk. A single incorrect interaction claim could result in physical harm and litigation. Disclaimers are insufficient — courts have found disclaimers inadequate when content is presented with apparent authority. **Do not pursue.**

---

### 2. Job Salary by City

**Rating: 🟢 GREEN**

**YMYL classification:** Low-to-moderate. Financial information, but salary data is broadly informational and non-actionable (no one makes a life decision solely based on a salary lookup page).

**Legal/regulatory risk:**
- **FTC:** No disclosure requirements for presenting publicly available BLS data.
- **Liability:** Essentially zero. Salary estimates are understood to be approximations. No precedent for liability from salary comparison content. BLS data is public domain (US government work).
- **Data licensing:** BLS Occupational Employment and Wage Statistics is explicitly public domain. No licensing issues.

**Google ranking outlook:** Moderate YMYL signal but manageable. Sites like Glassdoor, Indeed, and Salary.com rank well, but long-tail queries ("[specific title] salary in [small city]") are underserved. E-E-A-T bar is lower because the data is verifiable government statistics.

**Verdict:** Safe. Government data source, no regulatory exposure, low liability. Standard disclaimers about estimates being approximate are sufficient.

---

### 3. Dog/Cat Breed Comparisons

**Rating: 🟢 GREEN**

**YMYL classification:** Not YMYL. Pet information is explicitly outside YMYL scope in Google's guidelines.

**Legal/regulatory risk:**
- **FTC:** No disclosure requirements.
- **Liability:** Negligible. No legal precedent for liability from pet breed comparison content. Even incorrect information (e.g., overstating a breed's friendliness) does not create actionable harm in a legal sense.
- **Data licensing:** AKC breed standards are published publicly. Breed characteristics are factual/descriptive and not copyrightable.

**Google ranking outlook:** Good. Long-tail breed comparisons are underserved. Existing players (DogTime, PetFinder) focus on individual breeds, not head-to-head comparisons.

**Verdict:** Safe. Zero regulatory concern, no liability exposure, non-YMYL category.

---

### 4. Plant Growing by Zone

**Rating: 🟢 GREEN**

**YMYL classification:** Not YMYL. Gardening/horticulture is outside YMYL scope.

**Legal/regulatory risk:**
- **FTC:** No disclosure requirements.
- **Liability:** Negligible. Incorrect growing advice might cause a failed garden, which is not legally actionable harm. No precedent for liability from horticultural content.
- **Data licensing:** USDA Plant Hardiness Zone data is public domain. Growing guides based on zone data are standard informational content.
- **Pesticide/chemical claims:** If content recommends specific pesticides or fertilizers, EPA labeling regulations could theoretically apply — but this is avoidable by keeping content focused on growing conditions rather than chemical treatments.

**Google ranking outlook:** Good. Long-tail "[plant] in [zone]" queries are highly fragmented and underserved.

**Verdict:** Safe. Clean regulatory environment, public domain data, non-YMYL.

---

### 5. Food Nutrition

**Rating: 🟡 YELLOW**

**YMYL classification:** Moderate YMYL — health-adjacent. Nutrition information sits at the boundary of YMYL. Google treats it with more scrutiny than lifestyle content but less than medical advice.

**Legal/regulatory risk:**
- **FDA:** Nutrition labeling regulations (21 CFR Part 101) apply to food *products* and their *labels*, not to informational websites. However, if content makes health claims about foods ("broccoli prevents cancer"), FDA regulations on health claims could be relevant.
- **FTC:** If content is monetized and makes health claims, FTC Section 5 (unfair/deceptive acts) could apply. Pure calorie/macro lookups are safe; health benefit claims are not.
- **Liability:** Low if limited to USDA FoodData Central data (calories, macros, micros). Risk increases significantly if content includes health advice, dietary recommendations, or allergy information. Incorrect allergy information could cause physical harm.
- **Allergen risk:** Programmatically generated food content that fails to mention common allergens in a food item could theoretically create liability if someone relies on the content. This is an edge case but worth noting.

**Google ranking outlook:** Moderate. USDA-sourced calorie data is verifiable and factual. However, sites like MyFitnessPal, CalorieKing, and Nutritionix have strong E-E-A-T. Long-tail preparation-specific queries ("[food] [preparation method] calories") are less competitive.

**Mitigation:**
- Stick strictly to USDA FoodData Central numbers — no health claims
- Include allergen disclaimers on all pages
- Do not provide dietary advice or recommendations
- Clear attribution to USDA data source

**Verdict:** Feasible with discipline. Must stay within factual nutritional data and avoid any health claims or dietary advice. Allergen disclaimer required.

---

### 6. College Comparisons

**Rating: 🟡 YELLOW**

**YMYL classification:** Moderate YMYL — financial/life decisions. College choice has significant financial implications (debt, earning potential). Google applies moderate E-E-A-T scrutiny.

**Legal/regulatory risk:**
- **FTC:** If the site includes affiliate links to college recruitment services, FTC disclosure requirements apply. Pure informational comparison with ad monetization only has no FTC issue.
- **Higher Education Act:** Federal regulations require certain disclosures from institutions, but these apply to the *institutions*, not to third-party comparison sites.
- **Liability:** Low for factual data (acceptance rates, tuition, enrollment). Risk increases with subjective assessments ("better school for engineering") — but this is reputational risk, not legal liability. NCES/IPEDS data is public and authoritative.
- **Defamation:** Programmatically generated content that makes unfavorable factual claims about an institution could theoretically invite defamation claims, though truth is an absolute defense and IPEDS data is government-sourced.

**Google ranking outlook:** Competitive. US News, Niche, CollegeVine dominate head terms. Long-tail "[school A] vs [school B]" for non-top-100 schools is underserved.

**Mitigation:**
- Source all data from NCES/IPEDS (government, authoritative)
- Avoid subjective rankings or recommendations
- Present data side-by-side without editorial judgment
- Clearly attribute data sources and dates

**Verdict:** Feasible with care. Stick to government data, avoid editorializing, and include clear data attribution. Moderate YMYL signal is manageable because the data is verifiable.

---

### 7. Product Alternatives

**Rating: 🟡 YELLOW**

**YMYL classification:** Low YMYL. Product information is generally not YMYL unless the products relate to health or financial decisions.

**Legal/regulatory risk:**
- **FTC:** This is the primary risk vector. If the site includes affiliate links or sponsored listings, FTC endorsement guidelines (16 CFR Part 255) require clear disclosure. Even without affiliates, presenting "alternatives" implies a comparison/recommendation that could be seen as an endorsement.
- **Trademark:** Using product names and trademarks in page titles and content is nominative fair use and legally protected for comparison/informational purposes. However, trademark holders occasionally send cease-and-desist letters, creating operational overhead.
- **Defamation/trade libel:** If programmatically generated content makes false claims about a product ("Product X has a high failure rate"), this could invite trade libel claims. AI-generated content increases this risk because hallucination could produce false statements.

**Google ranking outlook:** Mixed. "Alternatives to [product]" is a well-established query pattern. Sites like G2, AlternativeTo, and Capterra are strong incumbents. Individual product pages are competitive.

**Mitigation:**
- No affiliate links (pure ad monetization)
- Source product data from verified databases
- Avoid subjective quality claims
- Include standard disclaimer about trademark ownership

**Verdict:** Feasible but requires careful content templating to avoid hallucinated product claims. FTC compliance is straightforward if no affiliate links are used. Trademark C&D risk creates ongoing operational overhead.

---

### 8. City Cost of Living

**Rating: 🟢 GREEN**

**YMYL classification:** Low-to-moderate. Financial information, but cost-of-living data is broadly informational — similar to salary data.

**Legal/regulatory risk:**
- **FTC:** No disclosure requirements for presenting publicly available economic data.
- **Liability:** Negligible. Cost-of-living estimates are understood as approximations. No precedent for liability from cost-of-living comparison content.
- **Data licensing:** BLS Consumer Expenditure Survey, Census Bureau data, and BLS CPI data are all public domain. C2ER (Council for Community and Economic Research) cost-of-living index is proprietary — must use government sources only.

**Google ranking outlook:** Good. Long-tail "[city A] vs [city B] cost of living" is underserved beyond the top 100 cities. Numbeo and BestPlaces dominate head terms but miss small-city combinations.

**Verdict:** Safe. Government data, no regulatory exposure, low liability. Avoid proprietary data sources (C2ER).

---

### 9. Baby Name Meanings

**Rating: 🟢 GREEN**

**YMYL classification:** Not YMYL. Baby name content is lifestyle/entertainment, outside YMYL scope.

**Legal/regulatory risk:**
- **FTC:** No disclosure requirements.
- **Liability:** Essentially zero. Name meanings and origins are cultural/historical information. No legal precedent for liability from name meaning content.
- **Cultural sensitivity:** While not a legal risk, programmatically generating content about names from diverse cultural traditions carries reputational risk if meanings are incorrect or culturally insensitive. This is an editorial quality concern, not a legal one.
- **Data licensing:** SSA baby name data is public domain. Name etymology and meaning data is widely available from public sources.

**Google ranking outlook:** Moderate. BabyCenter, Nameberry, and BehindTheName are strong incumbents. However, combination queries ("[name] meaning and origin") and less common names are underserved.

**Verdict:** Safe. Zero regulatory concern, no liability exposure, non-YMYL.

---

### 10. Supplement Interactions

**Rating: 🔴 RED**

**YMYL classification:** Explicitly YMYL — health/medical. Supplement interaction information carries the same YMYL weight as drug interactions in Google's guidelines.

**Legal/regulatory risk:**
- **FDA:** Dietary supplements are regulated under DSHEA (1994). While the FDA does not pre-approve supplements, it actively regulates health claims. Content claiming supplements interact in specific ways could be construed as making implicit health claims subject to FDA scrutiny.
- **FTC:** The FTC has been increasingly aggressive in enforcement against health claims in supplement-related content, particularly since the 2023 Health Products Compliance Guidance. If the site is monetized, FTC could view interaction claims as material health information subject to substantiation requirements.
- **Liability:** High. Supplement interactions are less well-studied than drug interactions, meaning data quality is lower and the risk of harmful misinformation is higher. If someone takes a dangerous supplement combination based on content that said it was safe, liability exposure is significant.
- **State AG enforcement:** Multiple state attorneys general have taken action against supplement misinformation sites. California's consumer protection laws are particularly aggressive.

**Google ranking outlook:** Near-zero. Same E-E-A-T barriers as medication interactions. Examine.com and similar expert-reviewed sites dominate.

**Verdict:** Same risk profile as medication interactions with even less reliable underlying data. **Do not pursue.**

---

### 11. Hiking Trail Guides

**Rating: 🟡 YELLOW**

**YMYL classification:** Low YMYL, but with a safety dimension. Outdoor recreation content is generally not YMYL, but trail information has a physical safety component (trail conditions, difficulty ratings, hazard warnings).

**Legal/regulatory risk:**
- **Liability:** This is the primary concern. If a trail guide fails to mention a known hazard (cliff, river crossing, seasonal closure) and someone is injured, there is theoretical liability exposure. Courts have generally protected guidebook publishers under First Amendment grounds (*Winter v. G.P. Putnam's Sons*, 1991 — mushroom guide liability case was dismissed), but the legal landscape is not uniformly settled.
- **Land agency data:** USFS and NPS trail data is public domain, but trail conditions change. Programmatically generated content cannot reflect current conditions (washouts, closures, fire damage), creating a stale-data hazard.
- **Wilderness permits:** Some trails require permits. Failing to mention permit requirements could cause legal issues for hikers, creating a negative user experience that impacts site reputation.

**Google ranking outlook:** Moderate. AllTrails dominates with user-generated content and GPS data. Long-tail "[specific trail] in [location]" queries for less popular trails are underserved.

**Mitigation:**
- Prominent disclaimer: "Trail conditions change. Verify current conditions with the managing agency before hiking."
- Link to official land management agency for each trail
- Do not rate trail difficulty without sourcing from official data
- Include seasonal considerations from official sources
- Never claim a trail is "safe"

**Verdict:** Feasible with strong disclaimers and linkage to official sources. The stale-data problem is real but manageable with prominent disclaimers. Lower risk than medical niches because courts have generally protected outdoor guide publishers.

---

### 12. Car Comparisons

**Rating: 🟢 GREEN**

**YMYL classification:** Low YMYL. While cars are expensive purchases, comparison/specification content is informational and not in the financial advice YMYL category.

**Legal/regulatory risk:**
- **FTC:** No disclosure requirements for presenting factual vehicle specifications. If affiliate links to dealer sites are included, standard FTC disclosure applies — but pure ad monetization has no FTC issue.
- **Liability:** Negligible for specification comparisons (horsepower, MPG, dimensions). Risk increases only if content makes safety claims ("Car X is safer than Car Y") — NHTSA safety ratings should be sourced and attributed, not editorially generated.
- **Trademark:** Vehicle names are trademarks, but nominative fair use protects comparison content.
- **Data licensing:** NHTSA data is public domain. EPA fuel economy data is public domain. Manufacturer specifications are publicly available.

**Google ranking outlook:** Competitive but viable. Edmunds, KBB, and CarAndDriver dominate head terms. Long-tail "[car A] vs [car B]" for non-flagship models is moderately underserved, especially for older model years.

**Verdict:** Safe. Stick to government and manufacturer specification data, attribute safety ratings to NHTSA, and avoid subjective safety claims.

---

### 13. Recipe Nutrition

**Rating: 🟡 YELLOW**

**YMYL classification:** Moderate YMYL — same health-adjacent concerns as food nutrition (#5), but with added complexity because recipe nutrition requires calculating aggregate nutritional values from ingredients.

**Legal/regulatory risk:**
- **FDA:** Same considerations as food nutrition. Calculated nutrition for recipes is inherently approximate, which is fine — but presenting calculated values with false precision could be misleading.
- **Allergen risk:** Higher than single-food nutrition because recipes contain multiple ingredients. Failing to flag allergens in a recipe's nutritional profile could cause harm. This is the primary liability vector.
- **FTC:** No specific issues beyond standard ad monetization disclosure.
- **Liability:** Moderate. The calculation layer (summing nutrition across ingredients, accounting for cooking methods) introduces error. If someone with a medical condition (diabetes, kidney disease) relies on significantly incorrect calorie or macro counts, there is theoretical liability exposure.

**Google ranking outlook:** Competitive. Recipe sites (AllRecipes, Food Network) have enormous E-E-A-T. However, "[specific recipe] nutrition facts" as a long-tail pattern is underserved — most recipe sites show nutrition as an afterthought.

**Mitigation:**
- Source all ingredient nutrition from USDA FoodData Central
- Show calculation methodology transparently ("Based on USDA data for [ingredients]")
- Prominent disclaimer: "Nutritional values are estimates. Consult a healthcare provider for dietary needs."
- Flag common allergens (Big 9) programmatically for all recipes
- Do not provide dietary advice

**Verdict:** Feasible with careful implementation. The allergen flagging requirement adds engineering complexity but is essential for liability management. Higher risk than single-food nutrition due to the calculation layer.

---

## Summary Matrix

| # | Niche | YMYL Level | Legal Risk | FTC/FDA Exposure | Liability Precedent | Rating |
|---|-------|-----------|-----------|-----------------|-------------------|--------|
| 1 | Medication interactions | **High** | Severe | FDA regulated | Yes — medical reliance | 🔴 RED |
| 2 | Job salary by city | Low | Minimal | None | None | 🟢 GREEN |
| 3 | Dog/cat breed comparisons | None | None | None | None | 🟢 GREEN |
| 4 | Plant growing by zone | None | None | None | None | 🟢 GREEN |
| 5 | Food nutrition | Moderate | Low-moderate | FDA if health claims | Allergen edge case | 🟡 YELLOW |
| 6 | College comparisons | Moderate | Low | FTC if affiliates | Defamation edge case | 🟡 YELLOW |
| 7 | Product alternatives | Low | Low-moderate | FTC if affiliates | Trade libel edge case | 🟡 YELLOW |
| 8 | City cost of living | Low | Minimal | None | None | 🟢 GREEN |
| 9 | Baby name meanings | None | None | None | None | 🟢 GREEN |
| 10 | Supplement interactions | **High** | Severe | FDA + FTC active | Yes — health reliance | 🔴 RED |
| 11 | Hiking trail guides | Low-moderate | Moderate | None | Mixed — safety data | 🟡 YELLOW |
| 12 | Car comparisons | Low | Minimal | None | None | 🟢 GREEN |
| 13 | Recipe nutrition | Moderate | Low-moderate | FDA if health claims | Allergen edge case | 🟡 YELLOW |

---

## Recommendations

### Tier 1 — GREEN (pursue without hesitation)
- **Job salary by city** — Public domain BLS data, zero regulatory exposure
- **Dog/cat breed comparisons** — Non-YMYL, zero liability
- **Plant growing by zone** — Non-YMYL, public domain USDA data
- **City cost of living** — Public domain government data, minimal YMYL
- **Baby name meanings** — Non-YMYL, zero liability
- **Car comparisons** — Government spec data, low YMYL

### Tier 2 — YELLOW (pursue with documented mitigation)
- **Food nutrition** — Feasible if limited to USDA data, no health claims, allergen disclaimers
- **College comparisons** — Feasible with NCES/IPEDS data only, no editorializing
- **Product alternatives** — Feasible with no affiliates, careful templating against hallucination
- **Hiking trail guides** — Feasible with strong disclaimers, links to official sources
- **Recipe nutrition** — Feasible but requires allergen flagging infrastructure

### Tier 3 — RED (do not pursue)
- **Medication interactions** — Existential liability risk, will not rank in Google
- **Supplement interactions** — Same risk profile with worse data quality

---

## Key Legal Principles

1. **Section 230 protects platforms, not publishers.** A site that programmatically generates content is a publisher, not a platform. Section 230 immunity likely does not apply to AI-generated content presented as the site's own.

2. **Disclaimers reduce but do not eliminate liability.** Courts have found disclaimers insufficient when content is presented with apparent authority and a reasonable person would rely on it for health/safety decisions.

3. **Government data sourcing is the strongest legal shield.** Content derived from and attributed to authoritative government sources (BLS, USDA, NCES) benefits from the original source's authority and accuracy. The publisher's liability is limited to accurate reproduction.

4. **The FTC cares about monetization context.** Pure informational content with display ads faces minimal FTC scrutiny. The moment affiliate links, sponsored content, or product recommendations enter the picture, FTC disclosure and substantiation requirements activate.

5. **YMYL is a ranking signal, not a legal standard.** A niche can be legally safe but still fail commercially because Google won't rank it. The two RED niches fail on both dimensions.
