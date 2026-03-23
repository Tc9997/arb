# Competition Audit — SERP Analysis Across All 13 Niches

> Research deliverable for arb-d0k. March 2026.

---

## Methodology

For each of the 13 niche candidates identified in the feasibility analysis, we selected 3–5 representative long-tail queries and analyzed real SERPs. For each query we assessed:

1. **Who ranks?** — Domain names and types of the top results
2. **Domain authority** — Whether top results are high-DA incumbents or smaller sites
3. **Content quality** — Thorough vs. thin, human vs. templated
4. **Programmatic competitors** — Are any top results from programmatic/template-driven sites?
5. **"No good result" gap** — Is there a clear opportunity where SERPs underserve the query?

### Competition Rating Scale

| Rating | Meaning |
|--------|---------|
| 🔴 **Saturated** | 3+ programmatic incumbents with high DA. No realistic entry point. |
| 🟡 **Contested** | Strong competitors exist but gaps visible in long-tail or quality. |
| 🟢 **Open** | Few or no programmatic competitors. Thin content. Clear gaps. |

---

## Summary Table

| # | Niche | Competition | Programmatic Players | "No Good Result" Gap? | Verdict |
|---|-------|-------------|---------------------|----------------------|---------|
| 1 | Medication interactions | 🔴 Saturated | Drugs.com, WebMD, Patient.info | No | Avoid |
| 2 | Job salary by city | 🔴 Saturated | Indeed, Glassdoor, Salary.com, ZipRecruiter, PayScale | No | Avoid |
| 3 | Dog/cat breed comparisons | 🟡 Contested | Dogell, Dog-Learn, A-Z Animals | Thin on obscure combos | Maybe |
| 4 | Plant growing by zone | 🟡 Contested | Bonnie Plants, Almanac (partial) | Yes — niche plant × zone combos | Strong maybe |
| 5 | Food nutrition | 🟡 Contested | Nutritionix, FatSecret, MyFoodDiary | Yes — preparation-specific queries | Maybe |
| 6 | College comparisons | 🔴 Saturated | CollegeSimply, CampusReel, Parchment, CollegeVine | No | Avoid |
| 7 | Product alternatives | 🟡 Contested | None programmatic — editorial listicles | No gap (well-served editorially) | Weak |
| 8 | City cost of living | 🔴 Saturated | Numbeo, RentCafe, Salary.com, BestPlaces, Redfin | No | Avoid |
| 9 | Baby name meanings | 🔴 Saturated | Nameberry, TheBump, BabyNames, MamaNatural, Momcozy | No | Avoid |
| 10 | Supplement interactions | 🟡 Contested | Patient.info, Drugs.com (partial) | Yes — obscure combos | Maybe (YMYL risk) |
| 11 | Hiking trail guides | 🔴 Saturated | AllTrails (dominant), Strava, Komoot | No | Avoid |
| 12 | Car comparisons | 🔴 Saturated | Edmunds, U.S. News, TrueCar, KBB, AutoTrader | No | Avoid |
| 13 | Recipe nutrition | 🟡 Contested | Recipe blogs + EatThisMuch, Nutritionix | Yes — specific dish variations | Maybe |

---

## Detailed SERP Analysis by Niche

### 1. Medication Interactions

**Sample queries tested:**
- "metformin and lisinopril interaction"
- "gabapentin and ibuprofen interaction side effects"
- "trazodone and melatonin interaction sleep"

**Who ranks (top 3):**
| Query | #1 | #2 | #3 |
|-------|----|----|-----|
| metformin + lisinopril | Drugs.com | Drugs.com (variant page) | ResearchGate |
| gabapentin + ibuprofen | Patient.info | Drugs.com | OceanRecovery.com |
| trazodone + melatonin | GoKick.com | Drugs.com | PubMed |

**Domain authority of top results:** Very high. Drugs.com (DA 89), Patient.info (DA 78), PubMed (DA 96). Even the "weaker" results like OceanRecovery and GoKick are health-focused sites with editorial content.

**Content quality:** High. Drugs.com provides structured interaction data (severity, mechanism, clinical notes). Patient.info gives clean consumer-facing summaries. Most results include pharmacodynamic detail, dosing considerations, and precautions.

**Programmatic competitors:** Drugs.com is the dominant programmatic player — it has pre-generated pages for every drug pair combination. Patient.info also has a programmatic interaction checker.

**"No good result" gap:** None. Even uncommon pairs (trazodone + melatonin) have multiple high-quality, dedicated results. The interaction checkers are comprehensive and data-driven.

**Verdict: 🔴 AVOID.** Drugs.com alone has programmatic coverage of ~100,000+ drug pairs. Combined with YMYL/E-E-A-T requirements (flagged RED in legal scan), this niche is a non-starter.

---

### 2. Job Salary by City

**Sample queries tested:**
- "dental hygienist salary in Boise Idaho"
- "phlebotomist salary in Tulsa Oklahoma"
- "veterinary technician salary in Des Moines Iowa"
- "occupational therapy assistant salary in Reno Nevada"

**Who ranks (top 3):**
| Query | #1 | #2 | #3 |
|-------|----|----|-----|
| dental hygienist / Boise | Indeed | Salary.com | Talent.com |
| phlebotomist / Tulsa | Indeed | Salary.com | Glassdoor |
| vet tech / Des Moines | Salary.com | Indeed | Indeed (state) |
| OTA / Reno | Salary.com | Talent.com | Indeed |

**Domain authority of top results:** Extremely high. Indeed (DA 93), Salary.com (DA 82), Glassdoor (DA 91), ZipRecruiter (DA 83), PayScale (DA 82). Every single result in the top 5 is a major jobs/salary platform.

**Content quality:** Good to excellent. Indeed and Glassdoor show real reported salaries from employees. Salary.com provides percentile breakdowns. Most include cost-of-living context. Even for very niche titles in small cities (phlebotomist in Tulsa), there are 6+ dedicated results.

**Programmatic competitors:** ALL top results are programmatic. Indeed, Glassdoor, Salary.com, ZipRecruiter, and PayScale each have programmatically generated pages for every title × city combination. ReadySetHire and Talent.com are smaller programmatic players filling any remaining gaps.

**"No good result" gap:** None. The programmatic coverage is essentially complete. Even "occupational therapy assistant salary in Reno Nevada" — a very specific title in a mid-sized city — returns 6+ dedicated salary pages with real data.

**Verdict: 🔴 AVOID.** This is the most saturated niche of all 13. Five major platforms with high DA, real employer-reported data, and complete programmatic coverage of the title × city matrix. Zero entry point.

---

### 3. Dog/Cat Breed Comparisons

**Sample queries tested:**
- "goldendoodle vs labradoodle"
- "shih tzu vs maltese temperament shedding"
- "basenji vs whippet comparison apartment dog"

**Who ranks (top 3):**
| Query | #1 | #2 | #3 |
|-------|----|----|-----|
| goldendoodle vs labradoodle | TexasGoldendoodleLovers | CrockettDoodles | Rover.com |
| shih tzu vs maltese | ShamelessPets | FloridaPuppiesOnline | A-Z Animals |
| basenji vs whippet | Dog-Learn.com | Dogell.com | Dogell.com |

**Domain authority of top results:** Mixed. Popular comparisons (goldendoodle vs labradoodle) attract mid-DA breed sites and marketplaces (Rover DA 74). Obscure comparisons (basenji vs whippet) are dominated by lower-DA programmatic comparison sites (Dogell DA ~35, Dog-Learn DA ~25).

**Content quality:** Variable. Popular breed comparisons have thorough, well-written articles with real breeder expertise. Obscure comparisons are thinner — Dogell and Dog-Learn use template-driven pages that swap breed stats into a fixed structure. Content is accurate but formulaic. Some results (ShamelessPets, Inkopious) are pet product companies with SEO content, not breed experts.

**Programmatic competitors:** Yes — Dogell.com and Dog-Learn.com are clearly programmatic. They generate pages for every breed × breed combination using a template. However, their DA is low and content quality is thin. A-Z Animals also has semi-programmatic breed comparison pages.

**"No good result" gap:** Partial. For obscure breed combinations (basenji vs whippet, less common pairs), the top results are thin template pages from low-DA sites. A higher-quality programmatic competitor with better content could outrank them. For popular breed pairs, the SERPs are well-served.

**Verdict: 🟡 CONTESTED.** Programmatic competitors exist but are low-quality. The opportunity is in the long tail of obscure breed combinations where current results are thin templates. However, the total addressable query volume for obscure pairs is lower than popular pairs. Risk: popular pairs are hard to break into.

---

### 4. Plant Growing by Zone

**Sample queries tested:**
- "how to grow lavender in zone 6"
- "how to grow blueberries in zone 5b"
- "how to grow artichokes in zone 7a"
- "how to grow pawpaw tree in zone 6b"

**Who ranks (top 3):**
| Query | #1 | #2 | #3 |
|-------|----|----|-----|
| lavender / zone 6 | Houzz (forum) | Almanac | Alibaba LifeTips |
| blueberries / zone 5b | Almanac | GardeningKnowHow | UMN Extension |
| artichokes / zone 7a | HartleyBotanic | Gardenate | JoeGardener |
| pawpaw / zone 6b | PetersonPawPaws | KY State Univ | ProjectPawpaw |

**Domain authority of top results:** Mixed. The Almanac (DA 82) and university extensions (DA 70+) are high authority, but they don't have zone-specific pages — they have general plant guides that mention zones. Forum results (Houzz, Facebook) and niche blogs (BloomingExpert, BonniePlants) fill the gaps. Notably, Alibaba LifeTips (an AI-generated content site) ranks for lavender/zone 6.

**Content quality:** Ranges from excellent (university extensions, Almanac) to thin (Gardenate provides just a planting calendar, LifeTips is AI-generated). For very specific queries (pawpaw in zone 6b, artichokes in zone 7a), results are often general growing guides that mention the zone in passing rather than zone-specific pages. Facebook groups appear in results for blueberries/zone 5b, indicating Google can't find a good dedicated result.

**Programmatic competitors:** Gardenate.com has programmatic plant × zone pages but they're extremely thin (just planting dates). BonniePlants has zone-specific guides but limited plant coverage. BloomingExpert.com appears to be a newer AI-generated site with plant × zone pages. No dominant programmatic player exists.

**"No good result" gap:** **Yes — significant.** The core insight: most gardening sites organize content by plant, not by plant × zone. When someone searches "how to grow [specific plant] in [specific zone]," Google often serves a general growing guide that mentions the zone range in one line, not a dedicated page with zone-specific advice (when to plant, what varieties survive, winter protection needs, etc.). Facebook groups appearing in SERPs is a strong "no good result" signal.

**Verdict: 🟢 to 🟡 — STRONG OPPORTUNITY.** No dominant programmatic player. Significant gap in zone-specific content. USDA zone data + plant data maps cleanly to the query pattern. The data is public domain and structured. AI-generated competitor (BloomingExpert) is low quality and beatable. University extension content is excellent but doesn't cover the full plant × zone matrix.

---

### 5. Food Nutrition

**Sample queries tested:**
- "calories in air fried chicken thigh"
- "calories in baked sweet potato with butter"
- "calories in homemade chicken tikka masala per serving"
- "calories in homemade beef pho per bowl"
- "healthy banana bread recipe nutrition facts per slice"

**Who ranks (top 3):**
| Query | #1 | #2 | #3 |
|-------|----|----|-----|
| air fried chicken thigh | CJEatsRecipes | AGirlCalledAdri | MyForkingLife |
| sweet potato + butter | SnapCalorie | EatThisMuch (Cracker Barrel) | EatThisMuch (Logan's) |
| chicken tikka masala | Skinnytaste | Nutritionix | Spicentice |
| beef pho | Quora | VifonUSA | KimEcopak |
| banana bread nutrition | TastesBetterFromScratch | GimmeDelicious | CleanEatingCouple |

**Domain authority of top results:** Mixed. Recipe blogs dominate most queries (DA 40-65). Nutrition databases (Nutritionix DA 62, FatSecret DA 68, EatThisMuch DA 55) appear for some queries. For specific homemade dish queries (beef pho, tikka masala), Quora and food brand sites appear — a "no good result" signal.

**Content quality:** Highly variable. Recipe blogs provide nutrition for THEIR recipe, not for the food in general — unhelpful if you're looking up a dish you already made or ate at a restaurant. Nutritionix and FatSecret provide generic entries but often lack preparation-specific detail. Quora appearing for beef pho calories indicates poor dedicated coverage.

**Programmatic competitors:** Nutritionix and FatSecret are programmatic for basic foods (apple, chicken breast). But preparation-specific queries ("air fried chicken thigh," "baked sweet potato with butter") are NOT well-covered programmatically. SnapCalorie has some prepared-food pages but limited coverage.

**"No good result" gap:** **Yes — for preparation-specific queries.** The gap is clear: "calories in [food] [specific preparation]" queries return recipe blogs (which answer a different question) rather than a nutrition lookup page. Nobody has built a programmatic site for food × preparation method nutrition data. USDA FoodData Central has the raw data but terrible UX and no preparation-specific pages optimized for search.

**Verdict: 🟡 CONTESTED with clear gap.** The opportunity is specifically in preparation-specific nutrition queries. Basic nutrition lookups (calories in an apple) are well-served. But "calories in air fried chicken thigh" or "calories in homemade beef pho" return recipe blogs, not dedicated nutrition pages. USDA data covers ~370,000 food items with preparation variants — massive structured dataset waiting to be surfaced.

---

### 6. College Comparisons

**Sample queries tested:**
- "University of Oregon vs Oregon State University comparison"
- "Gonzaga vs Santa Clara University comparison admission"

**Who ranks (top 3):**
| Query | #1 | #2 | #3 |
|-------|----|----|-----|
| UO vs OSU | Empowerly | CollegeSimply | CollegeVine |
| Gonzaga vs SCU | CampusReel | CollegeSimply | Parchment |

**Domain authority of top results:** High. CollegeSimply (DA ~55), CollegeVine (DA 65), Parchment (DA 58), CampusReel (DA ~45). Even for less popular matchups, 3-4 dedicated comparison tools appear. Forum results (CollegeConfidential, Quora) also rank, adding user perspectives.

**Content quality:** Good. CollegeSimply provides structured side-by-side comparisons with real NCES/IPEDS data (acceptance rates, SAT scores, tuition, graduation rates). CampusReel adds video tours. Parchment shows cross-admit preferences. CollegeVine offers admissions predictions. Each brings a unique angle.

**Programmatic competitors:** ALL are programmatic. CollegeSimply, CampusReel, Parchment, CollegeTuitionCompare, UnivStats, CollegeDroid, and PickUniversity each generate comparison pages for every school × school combination. This is one of the most programmatically saturated niches.

**"No good result" gap:** None. Even obscure matchups (Gonzaga vs Santa Clara) have 5+ dedicated comparison pages with real data.

**Verdict: 🔴 AVOID.** At least 7 programmatic comparison tools already cover the full school × school matrix. The data (IPEDS/NCES) is the same public dataset we'd use. No differentiation opportunity.

---

### 7. Product Alternatives

**Sample queries tested:**
- "alternatives to Notion for project management"
- "best alternatives to Slack for team communication 2026"

**Who ranks (top 3):**
| Query | #1 | #2 | #3 |
|-------|----|----|-----|
| Notion alternatives | TheDigitalProjectManager | Experte.com | Zapier Blog |
| Slack alternatives | Zapier Blog | Rock.so | RemoteWize |

**Domain authority of top results:** High to medium. Zapier (DA 89) dominates this space. TDPM (DA 65), Experte (DA 55), and various SaaS blogs fill out results. SaaS companies themselves rank for their competitors' alternatives queries (Airtable, Chanty, Nifty PM).

**Content quality:** High. Most results are well-researched editorial listicles with screenshots, pricing, pros/cons. Zapier's articles are particularly thorough with hands-on testing. These are not thin template pages — they're genuinely useful reviews.

**Programmatic competitors:** None truly programmatic. These are hand-written or AI-assisted editorial articles. The closest to programmatic would be G2 or Capterra for software comparisons, but those sites don't dominate the "[product] alternatives" query pattern as strongly.

**"No good result" gap:** Not really. While there's no single programmatic player, the editorial coverage is comprehensive. Major products have 10+ "alternatives to X" articles. The challenge is that this query type rewards editorial depth (hands-on testing, screenshots, nuanced comparisons), not programmatic breadth.

**Verdict: 🟡 WEAK.** No programmatic gap to exploit. The SERPs reward editorial quality, not data-driven templates. A programmatic approach would produce thinner content than what currently ranks. The niche also has a freshness problem — product features and pricing change constantly, requiring ongoing updates.

---

### 8. City Cost of Living

**Sample queries tested:**
- "cost of living in Spokane Washington 2026"
- "cost of living in Chattanooga Tennessee vs national average"
- "cost of living comparison Bozeman Montana vs Bend Oregon"

**Who ranks (top 3):**
| Query | #1 | #2 | #3 |
|-------|----|----|-----|
| Spokane | RentCafe | Salary.com | NickBriggsRealty |
| Chattanooga | Apartments.com | Salary.com | PayScale |
| Bozeman vs Bend | BestPlaces | BestPlaces | BozemanRealEstateGroup |

**Domain authority of top results:** Very high. RentCafe (DA 72), Salary.com (DA 82), Numbeo (DA 73), BestPlaces (DA 72), Redfin (DA 92), PayScale (DA 82). Even comparison queries (city A vs city B) are well-served by BestPlaces' programmatic calculator.

**Content quality:** Good. Most sites provide structured data on housing, groceries, transportation, healthcare costs relative to national average. Some include salary comparison tools. MIT Living Wage Calculator also appears with authoritative data.

**Programmatic competitors:** All major results are programmatic. RentCafe, Numbeo, BestPlaces, Salary.com, Expatistan, PayScale, and Redfin each have programmatically generated pages for every US city and city × city comparison. At least 6 established programmatic players.

**"No good result" gap:** None. Even niche queries (Bozeman vs Bend) have dedicated comparison calculators.

**Verdict: 🔴 AVOID.** 6+ high-DA programmatic incumbents with complete city coverage. They have proprietary data (rent listings, salary surveys) that we can't match. No entry point.

---

### 9. Baby Name Meanings

**Sample queries tested:**
- "meaning of the name Juniper for a baby girl"
- "meaning of the name Soren for a boy origin"
- "baby name Elowen meaning origin popularity"

**Who ranks (top 3):**
| Query | #1 | #2 | #3 |
|-------|----|----|-----|
| Juniper | Nameberry | Wikipedia | TheBump |
| Soren | Nameberry | TheBump | Wikipedia |
| Elowen | Nameberry | TheBump | BabyNames.com |

**Domain authority of top results:** High. Nameberry (DA 72), TheBump (DA 82), BabyNames.com (DA 62), MamaNatural (DA 60), FamilyEducation (DA 72), Momcozy (DA 45). Even uncommon names (Elowen) have 8+ dedicated results.

**Content quality:** Good to excellent. Nameberry provides etymology, popularity charts, famous bearers, sibling suggestions, user reviews. TheBump and MamaNatural offer similar depth. Wikipedia covers etymology for established names. Content is thorough and differentiated across sites.

**Programmatic competitors:** ALL are programmatic. Nameberry, TheBump, BabyNames.com, MamaNatural, Momcozy, MomJunction, and FamilyEducation each have programmatic pages for thousands of names. Some sites have 50,000+ name pages.

**"No good result" gap:** None. Even a revival Cornish name like "Elowen" (not in the top 500) has 8+ dedicated pages with meaning, origin, popularity trends, and similar names.

**Verdict: 🔴 AVOID.** At least 7 programmatic name databases compete for every query. The data (etymology, popularity stats from SSA) is the same for all. No differentiation opportunity.

---

### 10. Supplement Interactions

**Sample queries tested:**
- "can I take magnesium and ashwagandha together"
- "can you take turmeric and fish oil together"
- "zinc and quercetin supplement interaction benefits"

**Who ranks (top 3):**
| Query | #1 | #2 | #3 |
|-------|----|----|-----|
| magnesium + ashwagandha | Patient.info | TheBetterHealthStore (product) | Swisse (brand) |
| turmeric + fish oil | SouthShoreHealth | Drugs.com | IntelligentLabs |
| zinc + quercetin | PMC (NIH) | BioticsResearch (brand) | DiscoverMagazine |

**Domain authority of top results:** Mixed. Patient.info (DA 78) and Drugs.com (DA 89) appear for some queries. But many results are supplement brand blogs (Swisse, Cymbiotika, Sandhus Nutrition) or wellness sites (DrOracle.ai, Dawn.health, AuraHealth.io) with lower DA (20-45). Research papers (PMC, PubMed) appear for more niche combos.

**Content quality:** Highly variable. Patient.info and Drugs.com provide evidence-based interaction data. Brand blogs provide reasonable but self-interested content (they're selling the supplements). Some results (DrOracle.ai) appear to be AI-generated. For common supplement combos (magnesium + ashwagandha), there are many results but quality is uneven. For obscure combos, research papers may be the only dedicated results.

**Programmatic competitors:** Patient.info and Drugs.com have supplement interaction checkers, but their coverage is thinner than for pharmaceuticals — many supplement pairs return no result. No dedicated programmatic supplement interaction site exists.

**"No good result" gap:** **Partial.** Common supplement combos (magnesium + ashwagandha, turmeric + fish oil) are well-covered, though by a mix of brand blogs and health sites rather than a definitive resource. The real gap is in the long tail: less common supplement combinations, multi-supplement stacks, and interaction details (timing, dosage, specific forms like magnesium glycinate vs citrate).

**Verdict: 🟡 CONTESTED with YMYL risk.** There's a gap — no dominant programmatic supplement interaction site exists. But this is YMYL-adjacent territory. The legal scan rated supplement interactions as 🟡 YELLOW (not RED like medication interactions, but still requires caution). The content quality bar is high and claims need citations. Supplement brand blogs ranking well suggests Google's quality bar is lower here than for pharmaceuticals, but still higher than non-YMYL niches.

---

### 11. Hiking Trail Guides

**Sample queries tested:**
- "best hiking trails near Sedona Arizona with difficulty rating"
- "best day hikes Olympic National Park easy moderate"
- "Cathedral Peak trail Yosemite difficulty elevation gain"

**Who ranks (top 3):**
| Query | #1 | #2 | #3 |
|-------|----|----|-----|
| Sedona trails | TheDetourEffect | EarthTrekkers | GinaOnAPlane |
| Olympic NP hikes | 57Hours | WheatlessWanderlust | TheNatureSeeker |
| Cathedral Peak | AllTrails | TheOutbound | PhotographersTrailNotes |

**Domain authority of top results:** AllTrails (DA 82) dominates specific trail queries. For "best hikes in [location]" queries, travel blogs (EarthTrekkers DA 55, various travel blogs DA 30-50) compete. NPS.gov (DA 92) appears for national park queries. Strava (DA 88) and Komoot (DA 75) appear as secondary trail databases.

**Content quality:** AllTrails provides structured trail data (distance, elevation gain, difficulty rating, user reviews, GPS tracks) — excellent for specific trails. Travel blog results are editorial "best of" lists — good quality but hand-written. For specific trail detail queries (Cathedral Peak difficulty), AllTrails' user-review aggregation provides the richest data.

**Programmatic competitors:** AllTrails is the dominant programmatic player with 400,000+ trail pages, each with structured data + user reviews. Strava and Komoot also have programmatic trail pages but with less review content. EarthTrekkers and travel blogs compete editorially for "best hikes in X" queries.

**"No good result" gap:** Minimal. AllTrails has comprehensive coverage. The only gaps are very new or unofficial trails not yet in AllTrails' database, and "best hikes for [specific criteria]" editorial queries where blogs compete. But the core "[trail name] [stats]" and "[location] trails" patterns are saturated.

**Verdict: 🔴 AVOID.** AllTrails is an 800-pound gorilla with 400K+ trail pages, user reviews, GPS data, and DA 82. Their data moat (user-contributed reviews and GPS tracks) is unassailable. No point competing.

---

### 12. Car Comparisons

**Sample queries tested:**
- "Honda CR-V vs Toyota RAV4 2025 comparison"
- "Subaru Outback vs Mazda CX-50 2025 comparison reliability"
- "Kia Telluride vs Hyundai Palisade 2025 towing capacity"

**Who ranks (top 3):**
| Query | #1 | #2 | #3 |
|-------|----|----|-----|
| CR-V vs RAV4 | Dealer site | Dealer site | Dealer site |
| Outback vs CX-50 | IgotaSTi (forum) | DealerSite | Autoblog |
| Telluride vs Palisade | DealerSite | DealerSite | DealerSite |

**Domain authority of top results:** Mixed but deep. Edmunds (DA 90), U.S. News (DA 94), TrueCar (DA 79), AutoTrader (DA 84) appear in SERPs. But dealer websites dominate the top results for many queries — Honda of Kirkland, Montrose Kia, etc. These are templated comparison pages that dealers generate using manufacturer data.

**Content quality:** Dealer comparison pages are templated and promotional (biased toward the brand they sell). Edmunds and U.S. News provide objective, editorial comparisons. Autoblog provides first-hand reviews. The quality spectrum is wide, but the volume of content is enormous.

**Programmatic competitors:** Edmunds, U.S. News Cars, TrueCar, and KBB all have programmatic comparison tools. Additionally, hundreds of dealer websites generate templated "[Brand A] vs [Brand B]" pages. The sheer volume of programmatic content is overwhelming.

**"No good result" gap:** None. Every make × model comparison has 10+ dedicated pages. The SERPs are so saturated that dealer sites with thin templated content still rank because there's so much content competing.

**Verdict: 🔴 AVOID.** Edmunds, U.S. News, KBB, and TrueCar dominate with high DA and comprehensive data. Hundreds of dealer sites add templated competition. The data (specs, pricing) requires manufacturer relationships or scraping. Freshness is critical (annual model years). No opportunity.

---

### 13. Recipe Nutrition

**Sample queries tested:**
- "healthy banana bread recipe nutrition facts per slice"
- "calories in homemade chicken tikka masala per serving"
- "calories in homemade beef pho per bowl"

**Who ranks (top 3):**
| Query | #1 | #2 | #3 |
|-------|----|----|-----|
| banana bread nutrition | TastesBetterFromScratch | GimmeDelicious | CleanEatingCouple |
| tikka masala calories | Skinnytaste | Nutritionix | Spicentice |
| beef pho calories | Quora | VifonUSA | KimEcopak |

**Domain authority of top results:** Medium. Recipe blogs (DA 35-60) dominate. Nutritionix (DA 62) appears for some queries. Quora (DA 93) appearing for beef pho is notable — it means no good dedicated result exists. Brand sites (VifonUSA, Spicentice) and niche food blogs fill gaps.

**Content quality:** Recipe blogs provide nutrition for their specific recipe, which is a partial answer — users searching "calories in beef pho" want a general answer, not one blogger's specific recipe with exact ingredient amounts. Nutritionix gives generic calorie counts but lacks preparation-specific detail. Quora gives crowd-sourced ranges. The overall quality for "how many calories in [homemade dish]" is mediocre.

**Programmatic competitors:** Nutritionix and EatThisMuch are partially programmatic for basic foods, but their coverage of specific homemade dishes and preparation methods is thin. No one has built a comprehensive programmatic calorie database for dish × preparation combinations. FatSecret has some user-contributed entries but inconsistent coverage.

**"No good result" gap:** **Yes — significant for homemade dish queries.** Quora ranking #1 for "beef pho calories" is a clear signal. The gap is: generic ingredients (calories in chicken breast) are well-served by USDA/Nutritionix. But specific dishes (chicken tikka masala, beef pho, banana bread) have no authoritative programmatic source. Users get recipe blogs (which answer "how many calories in MY version"), not a definitive "a typical serving of beef pho has X calories."

**Verdict: 🟡 CONTESTED with opportunity.** The gap is real but the data challenge is harder than other niches. There's no clean public dataset of dish × preparation → nutrition. You'd need to aggregate from recipe databases or synthesize from ingredient combinations. The LLM role would be heavier than ideal. However, the query volume for "calories in [popular dish]" is substantial.

---

## Top-Line Findings

### Niches to Eliminate (🔴 Saturated — 7 niches)

These niches have 3+ programmatic incumbents with high DA and complete query coverage:

1. **Medication interactions** — Drugs.com owns this + YMYL risk
2. **Job salary by city** — 5+ salary platforms with complete coverage
3. **College comparisons** — 7+ comparison tools covering full school matrix
4. **City cost of living** — 6+ platforms (Numbeo, RentCafe, Salary.com, BestPlaces, Redfin, PayScale)
5. **Baby name meanings** — 7+ name databases with complete name coverage
6. **Hiking trail guides** — AllTrails dominates with user-generated moat
7. **Car comparisons** — Edmunds, U.S. News, KBB, TrueCar + hundreds of dealer pages

### Niches Worth Further Analysis (🟡/🟢 — 6 niches)

These have identifiable gaps, weaker programmatic competition, or clear "no good result" signals:

| Rank | Niche | Opportunity Signal | Key Risk |
|------|-------|--------------------|----------|
| **1** | **Plant growing by zone** | No dominant programmatic player; Facebook groups in SERPs; zone-specific gap is clear | Moderate content depth needed per page |
| **2** | **Food nutrition (prep-specific)** | Quora ranking #1 for dish queries; recipe blogs answer wrong question | No clean public dataset for dishes |
| **3** | **Dog/cat breed comparisons** | Low-DA programmatic competitors beatable on quality | Popular pairs already well-served |
| **4** | **Recipe nutrition** | Same gap as food nutrition; specific dish × recipe combos | Overlaps with #2; data challenge |
| **5** | **Supplement interactions** | No dedicated programmatic site; brand blogs dominate | YMYL risk; citation requirements |
| **6** | **Product alternatives** | No programmatic player | Editorial quality needed; not a data play |

### The Clearest Opportunities

**Plant growing by zone** stands out as the strongest candidate:
- ✅ Clean data (USDA hardiness zones + plant databases)
- ✅ No dominant programmatic competitor
- ✅ Clear "no good result" gap (Facebook groups in SERPs)
- ✅ Non-YMYL (green in legal scan)
- ✅ Evergreen content
- ✅ 15,000+ plant × zone combinations
- ✅ Easy pipeline (rated B in feasibility)

**Food nutrition (preparation-specific)** is the second strongest:
- ✅ Quora ranking for dish queries = clear gap
- ✅ USDA FoodData Central has 370,000+ entries
- ⚠️ Moderate YMYL (yellow in legal scan)
- ⚠️ Data mapping for "homemade dishes" is harder
- ✅ Enormous query volume

---

## Methodology Notes

- Searches conducted March 2026 from US IP
- Results may vary by location and personalization
- Domain authority estimates based on publicly known ranges (exact DA requires Ahrefs/Moz)
- "No good result" gap assessed by presence of forums (Quora, Reddit, Facebook), brand blogs, or irrelevant results in top 3
