# Public Data Source Audit — All 13 Niche Candidates

> Research deliverable for arb-njr. March 2026.

For each niche: exact public dataset, access method (API vs bulk download), format, schema/fields, record count, license/terms, update frequency, and coverage gaps.

---

## Summary Table

| # | Niche | Primary Source | Access | Format | Records | License | Update Freq | Coverage Grade |
|---|-------|---------------|--------|--------|---------|---------|-------------|----------------|
| 1 | Medication interactions | FDA FAERS + NIH DailyMed | API + bulk | JSON/XML/CSV | 1.4M+ interactions (DrugBank) | Public domain (FDA); CC BY-NC (DrugBank) | Quarterly (FAERS); ongoing (DailyMed) | B — interactions well-covered, but DrugBank requires license for commercial |
| 2 | Job salary by city | BLS OEWS | Bulk + API | CSV/XLSX | ~830 occupations × ~530 metros | Public domain | Annual (May release) | A — comprehensive, clean 1:1 mapping |
| 3 | Dog/cat breed comparisons | AKC breed data (scraped/community) | Bulk CSV + APIs | CSV/JSON | 200-340 breeds | Factual data (not copyrightable) | Static/infrequent | B — good breed coverage, no single authoritative API |
| 4 | Plant growing by zone | USDA Plant Hardiness + extension data | Bulk + static API | CSV/GeoJSON/SHP | 13 zones × ~43,000 ZIP codes | Public domain | Infrequent (last update 2023) | B — zone data strong, plant-specific growing advice is sparse |
| 5 | Food nutrition | USDA FoodData Central | API + bulk | JSON/CSV | ~400K+ foods (branded + legacy) | Public domain | Every 6 months (branded monthly) | A — excellent structured data |
| 6 | College comparisons | NCES IPEDS + College Scorecard | Bulk + API | CSV/JSON | 7,000+ institutions × 250+ vars | Public domain | Annual | A — rich multi-dimensional data |
| 7 | Product alternatives | None (no single public dataset) | N/A | N/A | N/A | N/A | N/A | F — no viable public data source |
| 8 | City cost of living | BEA Regional Price Parities + BLS CPI | Bulk + API | CSV/XLSX | 50 states + ~380 metros | Public domain | Annual (RPP); monthly (CPI) | A — solid government data |
| 9 | Baby name meanings | SSA baby names + supplemental | Bulk | CSV/TXT | ~2M name-year records (1880-present) | Public domain | Annual | C — names/counts excellent, meanings require supplemental sources |
| 10 | Supplement interactions | NIH DSLD + NatMed (licensed) | API + bulk | CSV/JSON | 130K+ products (DSLD) | Public domain (DSLD); commercial license (NatMed) | Monthly (DSLD) | D — interaction data locked behind commercial license |
| 11 | Hiking trail guides | USFS trails + NPS + RIDB | API + bulk | SHP/GeoJSON/JSON | 158K+ miles of trails (USFS) | Public domain | Varies | C — trail geometry exists, descriptive trail data is thin |
| 12 | Car comparisons | NHTSA vPIC + NCAP ratings | API + bulk | JSON/CSV/SQL | All vehicles 1981-present | Public domain | Ongoing | B — specs and safety good, lacks subjective comparison data |
| 13 | Recipe nutrition | USDA FoodData Central (reused) | API + bulk | JSON/CSV | Same as #5 | Public domain | Same as #5 | B — per-ingredient nutrition strong, recipe-level assembly required |

---

## Detailed Analysis by Niche

### 1. Medication Interactions

**Query pattern:** "[drug A] and [drug B]"

#### Primary Sources

**FDA Adverse Event Reporting System (FAERS)**
- **URL:** https://open.fda.gov/data/faers/
- **Access:** REST API (openFDA) + quarterly bulk downloads
- **Format:** JSON (API), CSV/XML (bulk)
- **Schema:** Report ID, drug names, reactions, outcomes, patient demographics, report source, date
- **Records:** 30M+ adverse event reports; drug-drug co-occurrences extractable but not pre-computed as "interactions"
- **License:** Public domain (US government work)
- **Update frequency:** Quarterly bulk releases; API updated ongoing
- **Rate limits:** API: 240 requests/minute without key, 120,000/day with key

**NIH DailyMed**
- **URL:** https://dailymed.nlm.nih.gov/dailymed/
- **Access:** REST API + bulk download (SPL files)
- **Format:** XML (SPL — Structured Product Labeling), JSON (API)
- **Schema:** Drug name, NDC, labeling sections (indications, warnings, interactions, dosage), manufacturer
- **Records:** 140,000+ drug labels
- **License:** Public domain
- **Update frequency:** Ongoing (as labels are submitted to FDA)

**DrugBank (supplemental — licensed)**
- **URL:** https://go.drugbank.com/
- **Access:** Bulk download (requires license)
- **Format:** XML, CSV
- **Schema:** Drug properties, targets, enzymes, carriers, transporters, drug-drug interactions with severity/evidence
- **Records:** 1,413,791 drug-drug interactions; 16,000+ drug entries
- **License:** CC BY-NC 4.0 (free for academic; commercial license required)
- **Update frequency:** ~Annually

#### Coverage Gaps
- FAERS has raw adverse event co-reports, not curated interaction pairs — requires significant processing
- DailyMed interaction data is embedded in unstructured label text (warnings sections), not structured fields
- DrugBank has the best structured interaction data but requires a commercial license for our use case
- **Critical gap:** No single freely-licensed, structured, commercially-usable drug interaction dataset exists
- YMYL risk compounds this: inaccurate data = liability (see 05-legal-scan.md)

---

### 2. Job Salary by City

**Query pattern:** "[job title] salary in [city]"

#### Primary Source

**BLS Occupational Employment and Wage Statistics (OEWS)**
- **URL:** https://www.bls.gov/oes/tables.htm
- **Access:** Bulk download (primary), BLS Public Data API (secondary)
- **Format:** XLSX, CSV, TXT (bulk); JSON (API)
- **Schema:**
  - `OCC_CODE` — SOC occupation code
  - `OCC_TITLE` — Occupation title
  - `AREA` — Metro area FIPS code
  - `AREA_TITLE` — Metro area name
  - `TOT_EMP` — Total employment
  - `H_MEAN`, `A_MEAN` — Mean hourly/annual wage
  - `H_PCT10/25/50/75/90`, `A_PCT10/25/50/75/90` — Wage percentiles
  - `OWN_CODE` — Ownership type
- **Records:** ~830 occupations × ~530 metro areas = ~440,000 occupation-area data points per release
- **License:** Public domain (US government work, 17 USC §105)
- **Update frequency:** Annual (May reference period; released following April, ~11 months lag)
- **API:** BLS Public Data API v2 — requires free registration key; 500 queries/day, 50 series per query
- **Current release:** May 2024 data (released April 2025)

#### Supplemental Source

**BLS Area Cost-of-Living / BEA Regional Price Parities**
- **URL:** https://www.bea.gov/data/prices-inflation/regional-price-parities-state-and-metro-area
- **Access:** Bulk download + BEA API
- **Format:** CSV, XLSX
- **Schema:** State/metro FIPS, RPP (all items), RPP (goods), RPP (services: housing), RPP (services: other)
- **Records:** 50 states + DC + ~380 metro areas
- **License:** Public domain
- **Update frequency:** Annual (December release, ~2 year lag)

#### Coverage Gaps
- **Minor:** ~830 SOC codes don't cover every job title people search for (e.g., "prompt engineer" has no SOC code yet). Mapping informal titles to SOC codes requires a synonym layer.
- **Minor:** Some occupation × metro cells are suppressed for confidentiality (marked with `**`). Small metros and rare occupations are most affected.
- **Strength:** This is the cleanest dataset of all 13 niches. Government data, public domain, structured, 1:1 mapping to query pattern.

---

### 3. Dog/Cat Breed Comparisons

**Query pattern:** "[breed A] vs [breed B]"

#### Primary Sources

**AKC Breed Data (community-extracted)**
- **URL:** https://github.com/tmfilho/akcdata (277 breeds); https://github.com/kkakey/dog_traits_AKC (traits)
- **Access:** Bulk download (CSV/JSON from GitHub)
- **Format:** CSV, JSON
- **Schema:** Breed name, group, height (min/max), weight (min/max), life expectancy (min/max), energy level, trainability, shedding, barking, good with kids/dogs, coat type, coat length, popularity rank (2013-2020), 16 trait ratings on 1-5 scale
- **Records:** 277 breeds (tmfilho), ~200 breeds with trait scores (kkakey)
- **License:** Factual data extracted from AKC.org — breed characteristics are factual/descriptive and not copyrightable. AKC has no public API terms prohibiting this.
- **Update frequency:** Static snapshots; would need periodic re-scraping

**The Dog API / Dog CEO API**
- **URL:** https://thedogapi.com/ ; https://dog.ceo/dog-api/
- **Access:** REST API (free tier available)
- **Format:** JSON
- **Schema:** Breed name, temperament, origin, life span, height, weight, breed group, images
- **Records:** 172-340 breeds depending on API
- **License:** Free for non-commercial and commercial use (with attribution for TheDogAPI)
- **Rate limits:** TheDogAPI: 10,000 requests/month (free tier)

**Pawsome Authority Dataset**
- **URL:** https://pawsomeauthority.com/dog-breeds/dataset/
- **Access:** Bulk download
- **Format:** JSON-LD, CSV
- **Schema:** Origins, physical measurements, coat characteristics, temperament ratings, health indicators, lifestyle suitability
- **Records:** 200+ breeds

#### Coverage Gaps
- **Cat breeds:** No equivalent structured dataset to AKC data. Cat breed data is scattered across CFA, TICA registries without structured bulk downloads. Would need scraping.
- **No single authoritative API** with complete trait-by-trait comparison data. Best approach: merge AKC trait dataset + TheDogAPI for images/supplemental data.
- **Subjectivity:** Traits like "good with kids" are rated 1-5 but inherently subjective. Source attribution is important.
- **Update frequency:** Breed standards rarely change, so static data is acceptable.

---

### 4. Plant Growing by Zone

**Query pattern:** "how to grow [plant] in [zone]"

#### Primary Sources

**USDA Plant Hardiness Zone Map Data**
- **URL:** https://planthardiness.ars.usda.gov/ ; https://prism.oregonstate.edu/phzm/
- **Access:** Bulk download + static JSON API (phzmapi.org)
- **Format:** CSV (ZIP code → zone), GeoJSON, Shapefile, GeoTIFF
- **Schema:** ZIP code, zone (1a-13b), min temp range (°F), latitude, longitude
- **Records:** ~43,000 US ZIP codes mapped to 26 half-zones (1a through 13b)
- **License:** Public domain (USDA); GIS data owned by Oregon State University under cooperative agreement
- **Update frequency:** Infrequent — last major update was 2023 map (prior was 2012)

**USDA PLANTS Database**
- **URL:** https://plants.usda.gov/
- **Access:** Web interface + bulk download (limited)
- **Format:** CSV
- **Schema:** Scientific name, common names, native status, growth habit, duration, height, hardiness zones (sometimes)
- **Records:** ~100,000 plant entries (native + naturalized US species)
- **License:** Public domain
- **Update frequency:** Ongoing

#### Coverage Gaps
- **Critical gap:** No single structured dataset mapping {plant species} → {growing requirements by zone}. The PLANTS database has taxonomy but NOT "how to grow X in zone Y" information.
- **Zone → plant** mapping exists partially (what grows in zone 7?), but **plant → zone-specific growing guide** requires synthesis from extension service publications, which are unstructured PDFs.
- **Workaround:** Use zone data for temperature context + LLM to synthesize growing advice from established horticultural knowledge. This increases LLM load from "connective prose" to "meaningful generation."
- **Extension services:** Each state's cooperative extension (e.g., extension.uga.edu) has plant-specific guides but in unstructured formats (PDFs, HTML articles). Not viable for bulk ingest.

---

### 5. Food Nutrition

**Query pattern:** "calories in [food] [preparation]"

#### Primary Source

**USDA FoodData Central (FDC)**
- **URL:** https://fdc.nal.usda.gov/
- **Access:** REST API + bulk download
- **Format:** JSON (API), CSV (bulk)
- **API base:** `https://api.nal.usda.gov/fdc/v1/`
- **Key endpoints:**
  - `/food/{fdcId}` — single food details
  - `/foods/search` — search by keyword
  - `/foods/list` — paginated list
- **Schema:**
  - `fdcId` — unique food identifier
  - `description` — food name
  - `dataType` — SR Legacy, Foundation, Branded, Survey (FNDDS)
  - `foodNutrients[]` — array of nutrient values
    - `nutrientId`, `nutrientName`, `unitName`, `amount`
  - `servingSize`, `servingSizeUnit`
  - `brandOwner`, `brandName` (branded foods only)
  - `foodCategory`
  - Up to 150 nutrient components per food
- **Records by data type:**
  - SR Legacy: 7,793 foods (generic foods — "Chicken, breast, roasted")
  - Foundation Foods: ~2,700 foods (detailed analytical data)
  - Branded Foods: ~400,000+ foods (GS1/GDSN product data — packaged foods)
  - FNDDS: ~8,000 foods (survey-coded foods)
  - **Total: ~420,000+ food records**
- **License:** Public domain (US government work)
- **Update frequency:** Major release every 6 months; Branded Foods updated monthly
- **Rate limits:** API requires free key (api.nal.usda.gov); 3,600 requests/hour

#### Coverage Gaps
- **Preparation methods:** SR Legacy has some preparation variants ("boiled," "raw," "roasted") but not exhaustive. "Calories in air-fried chicken breast" may not have an exact match.
- **Restaurant/fast food:** Branded Foods covers packaged goods well; restaurant items are spottier.
- **Strength:** This is the gold-standard nutrition database. Direct 1:1 mapping for most queries. Extremely clean for programmatic use.

---

### 6. College Comparisons

**Query pattern:** "[school A] vs [school B]"

#### Primary Sources

**NCES Integrated Postsecondary Education Data System (IPEDS)**
- **URL:** https://nces.ed.gov/ipeds/use-the-data
- **Access:** Bulk download (primary) + Data Explorer web tool
- **Format:** CSV (bulk), Access DB (2004+)
- **Schema (key variables among 250+):**
  - Institution name, ID (UNITID), address, sector (public/private)
  - Enrollment (total, by race, gender, full/part-time)
  - Tuition & fees (in-state, out-of-state)
  - Room & board costs
  - Financial aid (% receiving, average amount)
  - Graduation rates (4-year, 6-year, by demographic)
  - Admissions (acceptance rate, SAT/ACT scores)
  - Faculty (student-faculty ratio, salaries)
  - Degrees conferred by field
- **Records:** 7,000+ institutions, data from 1980-81 to present
- **License:** Public domain (US government work)
- **Update frequency:** Annual (surveys collected annually; data released ~12-18 months after)

**College Scorecard API**
- **URL:** https://collegescorecard.ed.gov/data/api/
- **Access:** REST API (requires free api.data.gov key)
- **Base URL:** `https://api.data.gov/ed/collegescorecard/v1/schools`
- **Format:** JSON
- **Schema:** Institution-level data (costs, earnings, demographics, completion) + field-of-study data (median earnings by major, debt by major)
- **Records:** Same institutions as IPEDS (~7,000+), with additional earnings outcomes data from IRS/Treasury
- **License:** Public domain
- **Update frequency:** Annual
- **Unique data:** Post-graduation earnings by institution and field of study (not in IPEDS)

#### Coverage Gaps
- **Minor:** Very small or specialized institutions may have suppressed data (small cell sizes).
- **Strength:** Arguably the richest niche dataset after BLS salary data. Two complementary government sources (IPEDS for inputs, Scorecard for outcomes) create a complete comparison picture.
- **Page generation:** Each pair = 2 IPEDS lookups + comparison logic. With ~4,000 4-year institutions, that's ~8M possible pairs — need to filter to meaningful comparisons.

---

### 7. Product Alternatives

**Query pattern:** "[product] alternatives"

#### Data Sources

**No viable public dataset exists.**

- There is no government database of products and their alternatives.
- Product databases (UPC databases, Google Shopping, Amazon) are proprietary and behind APIs that prohibit scraping or bulk use for content generation.
- Open-source product databases (Open Food Facts, Open Beauty Facts) cover narrow categories.
- Wikidata has product entities but no "alternative to" relationships at scale.

#### Coverage Gaps
- **Fatal gap:** The query pattern requires knowing what products exist AND what substitutes for them. This is fundamentally subjective and opinion-based — exactly the kind of content that requires heavy LLM generation with no data anchor.
- **Feasibility rating:** F (see 06-feasibility.md)
- **Recommendation:** Drop this niche. It violates the core thesis (real structured data backing each page).

---

### 8. City Cost of Living

**Query pattern:** "cost of living in [city]"

#### Primary Sources

**BEA Regional Price Parities (RPPs)**
- **URL:** https://www.bea.gov/data/prices-inflation/regional-price-parities-state-and-metro-area
- **Access:** Bulk download + BEA API
- **Format:** CSV, XLSX (bulk); JSON (API)
- **Schema:**
  - State/metro FIPS code
  - RPP All Items (overall price level, US avg = 100)
  - RPP Goods
  - RPP Services: Rents
  - RPP Services: Other
- **Records:** 50 states + DC + ~380 metro areas
- **License:** Public domain
- **Update frequency:** Annual (December release, ~2 year lag — latest is typically 2022 data in 2024 release)

**BLS Consumer Price Index (CPI) — Metro Areas**
- **URL:** https://www.bls.gov/cpi/data.htm
- **Access:** BLS Public Data API + bulk download
- **Format:** TXT/CSV (bulk); JSON (API)
- **Schema:** Area code, item code (food, housing, transportation, etc.), period, CPI value
- **Records:** ~25 metro areas tracked monthly for detailed CPI; less granular for others
- **License:** Public domain
- **Update frequency:** Monthly

**BLS OEWS (salary context — same as Niche #2)**
- Can cross-reference salary data with cost of living for "adjusted salary" context.

**Census Bureau American Community Survey (ACS)**
- **URL:** https://data.census.gov/
- **Access:** API (api.census.gov) + bulk download
- **Format:** JSON (API), CSV (bulk)
- **Schema:** Median household income, median rent, housing costs, commute times, population demographics — by metro/county/ZIP
- **Records:** ~32,000 places, ~3,000 counties
- **License:** Public domain
- **Update frequency:** Annual (1-year estimates for areas 65K+ pop; 5-year for smaller areas)

#### Coverage Gaps
- **Minor:** BEA RPPs cover ~380 metros, not every city. Small cities/towns require county-level or state-level estimates.
- **Strength:** Multiple complementary government datasets create a rich cost-of-living profile. Salary + RPP + CPI + ACS = comprehensive page content.
- **Excellent candidate** for data-rich pages: every page can show price level, comparison to national average, median income, median rent, and breakdown by category.

---

### 9. Baby Name Meanings

**Query pattern:** "what does the name [X] mean" / "[name] meaning and origin"

#### Primary Source

**SSA Baby Names Dataset**
- **URL:** https://www.ssa.gov/oact/babynames/limits.html
- **Access:** Bulk download (ZIP files)
- **Format:** TXT (CSV-like: name,sex,count per year)
- **Schema:** Name, sex (M/F), count of births registered with SSA
- **Records:** ~2M name-year-sex records, covering 1880 to present
  - National data: one file per year
  - State-level data: one file per state
- **License:** Public domain
- **Update frequency:** Annual (typically May, covering prior calendar year)
- **Privacy threshold:** Names with <5 occurrences in a year are excluded

#### Supplemental Sources Needed

**Name meanings and origins — NO authoritative public dataset:**
- Behind the Name (behindthename.com) — comprehensive but proprietary, no API/bulk download
- Wikidata — has some name entities with origin/meaning but very sparse (~15K given names vs. 100K+ in SSA)
- Baby name meaning sites are all proprietary content

#### Coverage Gaps
- **Critical gap:** The SSA dataset provides **popularity data only** (name, sex, count by year). It has **zero information about meanings, origins, etymology, or cultural significance**.
- **The query pattern requires meanings**, which is the primary user intent. Popularity is supplemental context.
- **No public structured dataset for name meanings exists.** This would require either:
  1. Licensing Behind the Name data (commercial terms unclear)
  2. Heavy LLM generation for meanings (exactly what we want to avoid)
  3. Wikidata extraction (very incomplete)
- **Recommendation:** Viable but with a significant LLM dependency for the core content (meanings). The SSA popularity data enriches pages but doesn't address the primary query intent.

---

### 10. Supplement Interactions

**Query pattern:** "[supplement A] and [supplement B]" / "[supplement] and [drug]"

#### Primary Sources

**NIH Dietary Supplement Label Database (DSLD)**
- **URL:** https://dsld.od.nih.gov/
- **Access:** REST API + CSV download
- **Format:** JSON (API), CSV (download)
- **Schema:** Product name, brand, ingredients, amounts per serving, serving size, product type, target groups
- **Records:** 130,000+ supplement product labels
- **License:** Public domain (US government work)
- **Update frequency:** Monthly
- **Note:** Contains **label information only** — what's in the product, NOT interaction data

**NIH Office of Dietary Supplements (ODS) Fact Sheets**
- **URL:** https://ods.od.nih.gov/
- **Access:** Web + limited API
- **Format:** HTML, JSON
- **Schema:** Supplement name, health effects, interactions, safety concerns, recommended intake
- **Records:** ~100 supplement fact sheets
- **License:** Public domain

**Natural Medicines Database (NatMed) — COMMERCIAL LICENSE REQUIRED**
- **URL:** https://naturalmedicines.therapeuticresearch.com/
- **Access:** Licensed API endpoints
- **Format:** JSON
- **Schema:** Ingredient monographs, drug-nutrient interactions, mechanistic pathways, evidence ratings
- **Records:** Comprehensive (thousands of supplements × drugs)
- **License:** Commercial subscription required ($$$)
- **Accuracy:** 93.7% validated accuracy for interaction identification

#### Coverage Gaps
- **Fatal gap for structured data:** The DSLD tells you what's IN a supplement (label data). It does NOT tell you about interactions.
- **Interaction data is behind a paywall.** NatMed is the authoritative source but requires commercial licensing.
- **ODS fact sheets are limited** (~100 supplements) and unstructured (HTML prose, not structured interaction pairs).
- **YMYL risk** applies equally here as to medication interactions (see 05-legal-scan.md).
- **Recommendation:** Not viable for programmatic data-driven pages. The core content (interactions) requires either expensive licensing or heavy LLM generation in a YMYL category.

---

### 11. Hiking Trail Guides

**Query pattern:** "hiking [trail name]" / "best hikes in [park/area]"

#### Primary Sources

**USFS National Forest System Trails**
- **URL:** https://data-usfs.hub.arcgis.com/datasets/usfs::national-forest-system-trails-feature-layer
- **Access:** ArcGIS REST API + bulk download
- **Format:** Shapefile, GeoJSON, CSV (attribute table), File Geodatabase
- **Schema:** Trail name, trail number, trail type, trail class, managed use (hike/bike/horse/ATV), surface type, trail length, minimum/maximum elevation, national forest
- **Records:** 158,000+ miles of trails across National Forests
- **License:** Public domain
- **Update frequency:** Varies; geodata periodically refreshed

**National Park Service Data API**
- **URL:** https://www.nps.gov/subjects/developer/api-documentation.htm
- **Access:** REST API (requires free API key)
- **Format:** JSON
- **Schema:** Park info (description, hours, fees, directions), alerts, campgrounds, visitor centers, activities
- **Records:** 470+ NPS units
- **License:** Public domain
- **Note:** Trail-specific data is LIMITED — the NPS API focuses on park-level info, not individual trail descriptions

**NPS Trail GIS Data**
- **URL:** https://data-usfs.hub.arcgis.com/ (via IRMA portal)
- **Access:** Bulk download
- **Format:** Shapefile, Feature Service
- **Schema:** Trail geometry, trail name, administering unit
- **Records:** National Historic Trails + select park trails
- **License:** Public domain

**Recreation Information Database (RIDB)**
- **URL:** https://ridb.recreation.gov/
- **Access:** REST API (requires free API key from recreation.gov)
- **Format:** JSON
- **Schema:** Recreation areas, facilities, campsites, tours, permits, activities — organized by federal agency
- **Records:** Covers 12 federal agencies' recreation sites
- **License:** Public domain (federal data)

#### Coverage Gaps
- **Critical gap:** Trail **geometry** (where the trail goes) is well-covered. Trail **descriptions** (difficulty, scenic views, best season, water crossings, trailhead parking) are NOT in any structured dataset.
- USFS trails have attributes (length, class, use type) but no prose description, difficulty rating, or experiential information.
- NPS API doesn't expose individual trails within parks.
- **AllTrails** is the de facto source for trail descriptions/reviews but is fully proprietary.
- **Workaround:** Use USFS/NPS geometry + basic attributes as data anchor, then LLM generates descriptive content. This puts heavy load on the LLM for the most valuable content.
- **Recommendation:** Viable but data-thin. The structured data provides the skeleton (trail name, length, elevation, location) but the flesh (what makes the hike interesting) must be generated.

---

### 12. Car Comparisons

**Query pattern:** "[car A] vs [car B]"

#### Primary Sources

**NHTSA vPIC (Vehicle Product Information Catalog)**
- **URL:** https://vpic.nhtsa.dot.gov/api/
- **Access:** REST API (free, no key required, 24/7)
- **Format:** JSON, CSV, XML
- **Key endpoints:**
  - `/vehicles/DecodeVin/{vin}` — full vehicle specs from VIN
  - `/vehicles/GetModelsForMakeYear/make/{make}/modelyear/{year}` — list models
  - `/vehicles/GetMakesForVehicleType/{type}` — makes by vehicle type
- **Schema:** Make, model, model year, body class, drive type, engine (cylinders, displacement, fuel type), doors, GVWR, plant, manufacturer
- **Records:** All vehicles with VINs 1981-present (thousands of make/model/year combinations)
- **License:** Public domain
- **Update frequency:** Ongoing (manufacturers submit data continuously)

**NHTSA NCAP 5-Star Safety Ratings**
- **URL:** https://one.nhtsa.gov/webapi/api/SafetyRatings/
- **Access:** REST API (free, no key required)
- **Format:** JSON
- **Schema:** Model year, make, model, variant, overall rating, frontal crash rating, side crash rating, rollover rating, complaints count, recalls count, investigations count
- **Records:** Crash-tested vehicles from ~2011 onward (subset of all vehicles)
- **License:** Public domain

**EPA Fuel Economy Data**
- **URL:** https://www.fueleconomy.gov/feg/download.shtml
- **Access:** Bulk download + API
- **Format:** CSV (bulk), XML (API)
- **Schema:** Make, model, year, city/highway/combined MPG, engine size, transmission, fuel type, CO2 emissions, annual fuel cost
- **Records:** ~45,000 vehicles (1984-present)
- **License:** Public domain

#### Coverage Gaps
- **Specs + safety + fuel economy** are well-covered across three government sources.
- **Missing:** Price/MSRP (no public dataset — manufacturer data), reliability ratings (proprietary: JD Power, Consumer Reports), insurance costs, resale value, trunk space, infotainment details.
- **Comparison content:** The data provides objective specs for side-by-side tables. Subjective "which should you buy?" content requires LLM generation.
- **Strength:** Clean structured data for the core comparison table. Three APIs, all free, all public domain, no rate limit concerns.

---

### 13. Recipe Nutrition

**Query pattern:** "nutrition in [recipe]" / "[dish] calories"

#### Primary Source

**USDA FoodData Central (same as Niche #5)**
- Same dataset, different query pattern
- Per-ingredient nutrition data is comprehensive
- See Niche #5 for full details

#### Additional Source Needed

**Recipe databases — NO comprehensive public dataset:**
- Open-source recipe databases exist (RecipeNLG: 2.2M recipes, academic use) but have licensing restrictions
- Allrecipes, Food Network, etc. are proprietary
- Schema.org Recipe markup is widespread but requires web scraping

#### Coverage Gaps
- **Structural complexity:** Unlike "calories in chicken breast" (direct FDC lookup), "calories in chicken parmesan" requires:
  1. A recipe (ingredient list + quantities)
  2. Per-ingredient nutrition lookup in FDC
  3. Aggregation accounting for preparation changes (oil absorption, moisture loss)
- **No public recipe → nutrition dataset exists.** Must either:
  1. Build/curate a recipe database (significant effort)
  2. Use LLM to generate "standard" recipes, then compute nutrition (risks hallucination)
- **Preparation factors:** Cooking changes nutrition (frying adds fat, boiling leaches vitamins). FDC has some cooked variants but not comprehensive recipe-level data.
- **Recommendation:** Viable if scoped to per-ingredient queries ("calories in [food]") using FDC directly. Recipe-level queries add significant pipeline complexity with weak data anchoring.

---

## Cross-Cutting Findings

### Tier 1 — Excellent Data (can build pages almost entirely from data)

| Niche | Why |
|-------|-----|
| **2. Job salary by city** | BLS OEWS: 830 occupations × 530 metros, public domain, clean 1:1 mapping, annual updates |
| **5. Food nutrition** | FDC: 420K+ foods, API + bulk, public domain, direct lookup per query |
| **6. College comparisons** | IPEDS + Scorecard: 7K+ schools, 250+ variables, earnings data, public domain |
| **8. City cost of living** | BEA RPP + BLS CPI + Census ACS: comprehensive multi-source, public domain |

### Tier 2 — Good Data (data backbone exists, LLM fills moderate gaps)

| Niche | Why |
|-------|-----|
| **3. Dog/cat breed comparisons** | AKC trait data exists but cat data weak; no single API; static is OK |
| **12. Car comparisons** | Three government APIs cover specs/safety/MPG; missing price and subjective data |
| **13. Recipe nutrition** | FDC is excellent per-ingredient; recipe assembly adds complexity |
| **4. Plant growing by zone** | Zone data excellent; plant-specific growing guides unstructured |

### Tier 3 — Weak Data (LLM carries heavy load, data is supplemental)

| Niche | Why |
|-------|-----|
| **9. Baby name meanings** | SSA has popularity only; meanings have no public structured source |
| **11. Hiking trail guides** | Geometry and basic attributes exist; descriptive content absent |

### Tier 4 — Unviable (no public data pipeline possible)

| Niche | Why |
|-------|-----|
| **1. Medication interactions** | Structured data requires commercial license + YMYL liability risk |
| **10. Supplement interactions** | Interaction data behind paywall + YMYL liability risk |
| **7. Product alternatives** | No public dataset exists; fundamentally opinion-based content |

---

## Key Takeaways

1. **Best candidates for token arbitrage thesis:** Niches 2, 5, 6, 8 — where public government data maps directly to query patterns with minimal LLM generation needed.

2. **All Tier 1 niches use US government data** — public domain, no licensing concerns, well-maintained, structured formats.

3. **YMYL niches (1, 10) should be eliminated** regardless of data availability — the legal scan (05-legal-scan.md) already flagged them as RED.

4. **Product alternatives (#7) should be eliminated** — violates the core premise of data-backed content.

5. **API rate limits are manageable** for all viable niches — we're generating static pages, not serving real-time lookups. Bulk downloads are available for every Tier 1 source.
