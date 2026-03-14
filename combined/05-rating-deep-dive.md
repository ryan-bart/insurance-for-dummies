# Rating Deep Dive: From Loss Costs to Final Premium

[Back to README](../README.md)

---

## Why This Matters

The [Rating & Pricing](../cpcu/09-rating-pricing.md) chapter covers the building blocks: pure premium, expense loading, combined ratio, and the basics of rate regulation. This file goes deeper.

We're going to walk through how advisory loss costs actually become the number on your declarations page, which coverages eat most of the premium dollar, how the major rating factors really work under the hood, and what happens inside a catastrophe model. We'll also look at telematics, the rate filing process, and real-world examples from Florida and California.

If you want to understand *why* your premium is what it is — not just the formula — this is the chapter.

---

## 1. From Loss Cost to Final Premium

### The Advisory Loss Cost System

Most personal lines carriers don't build rates from scratch. They start with **advisory loss costs** published by ISO (now part of Verisk). Here's what that means in practice:

ISO collects claims and premium data from hundreds of participating insurers, pools it, and calculates what it costs — on average — to pay claims per exposure unit. These are "loss costs," not final rates. They include expected losses and loss adjustment expenses but deliberately exclude operating expenses, commissions, and profit.

### How Carriers Use ISO Loss Costs

Carriers have three basic options:

| Approach | What It Means | Who Does This |
|----------|--------------|---------------|
| **Adopt with LCM** | Use ISO's loss costs and apply a **loss cost multiplier** (LCM) to add expenses and profit | Most mid-size and smaller carriers |
| **Deviate** | Start with ISO's loss costs but modify specific factors (territory relativities, class plans, etc.) | Carriers with enough data to justify differences |
| **Independent file** | Develop rates entirely from the carrier's own data | Large carriers like State Farm, GEICO, USAA |

The **loss cost multiplier** is the key mechanism. If ISO's loss cost for a given class is $500 and the carrier's LCM is 1.35, the carrier's rate becomes $675. That 35% markup covers commissions, operating expenses, taxes, and profit margin.

### The Full Premium Waterfall

Here's how an advisory loss cost becomes the number on your dec page:

```
ISO Advisory Loss Cost (pure losses + LAE)
  x Carrier Loss Cost Multiplier (expenses + profit)
  = Manual Rate
  x Rating Factor Adjustments (territory, credit, protection class, etc.)
  = Adjusted Rate
  x Exposure Units
  = Base Premium
  - Discounts (multi-policy, protective devices, claims-free, etc.)
  + Surcharges (claims history, coverage selections)
  + Catastrophe Load
  + State Taxes & Assessments
  ─────────────────────────────
  = Final Written Premium
```

In many states, the carrier can file to automatically adopt future ISO reference filings — so when ISO updates loss costs, the carrier's rates adjust without a new filing, as long as the LCM stays the same (NAIC, 2024).

**Why this matters**: The loss cost system creates efficiency — hundreds of carriers share data through ISO, producing more statistically credible rate indications than any single carrier could develop alone. But it also means most of the market starts from the same foundation. Competitive differentiation comes from the LCM, proprietary rating factors, underwriting selection, and expense management — not from fundamentally different views of loss costs.

---

## 2. Which Coverages Drive Premium Most

### Homeowners: Where the Premium Dollar Goes

The split varies dramatically by geography, but nationally the claim data tells the story:

| Peril Category | Share of Claims (approx.) | Avg. Claim Severity | Premium Impact |
|---------------|--------------------------|--------------------|-----------------|
| **Wind & hail** | ~34-41% | ~$12,000 | Dominant in coastal/plains states |
| **Fire & lightning** | ~25-30% | ~$80,000+ | Lower frequency but highest severity |
| **Water damage & freezing** | ~20-25% | ~$12,000 | Steadily growing share |
| **Liability & med pay** | ~2-3% | Varies widely | Small share of total claims volume |
| **Theft & other** | ~5-8% | ~$5,000 | Modest impact |

(III, 2023; NAIC, 2024)

The key insight: **fire drives severity, wind drives frequency**. In Texas and the Great Plains, wind/hail can be 50%+ of premium. In California, wildfire loading dominates. In the Northeast, water damage from frozen pipes is a major cost driver. Liability is a small percentage of homeowners claims volume, but tail risk from large liability judgments keeps it relevant.

### Auto: Where the Premium Dollar Goes

Auto premium splits more evenly across coverages. Based on industry data:

| Coverage | Approximate Share of Premium | What Drives It |
|----------|------------------------------|---------------|
| **Bodily injury liability** | ~25-30% | Litigation costs, medical inflation, "social inflation" |
| **Property damage liability** | ~15-18% | Repair costs, vehicle complexity |
| **Collision** | ~20-25% | Repair/replace costs, vehicle value |
| **Comprehensive** | ~8-12% | Theft, weather, glass, animal strikes |
| **PIP / Med pay** | ~5-10% | Varies enormously by state (high in no-fault states) |
| **UM/UIM** | ~5-8% | Uninsured motorist population in the state |

(NAIC Auto Insurance Database, 2022; III, 2023)

**Geographic variation is massive.** In Michigan (unlimited PIP until 2020 reforms), PIP historically consumed 40%+ of the premium. In no-fault states generally, PIP's share is much larger than in tort states. In urban areas with high litigation, BI liability dominates.

---

## 3. Rating Factors in Depth

The [basic rating factor tables](../cpcu/09-rating-pricing.md#rating-factors) list what's used. Here we dig into *how* each one actually works.

### Territory / Geographic Rating

**How territories are defined**: Historically, ISO grouped zip codes into territories with similar loss characteristics — urban density, weather exposure, crime rates, litigation environment. A territory might span several zip codes or split a single zip code.

**Granularity evolution**: The industry has moved toward increasingly granular geographic rating. Many carriers now rate at the zip+4 or even census-block level using geocoded coordinates, though regulators in some states limit granularity to prevent unfair discrimination against small neighborhoods.

**Coastal differentials**: Coastal territories carry massive wind/hurricane loading. A home 1 mile from the coast in Miami-Dade County might be in a territory rated 3-5x higher than a home 30 miles inland — even in the same county. Many states require separate wind/hurricane deductibles (often 2-5% of Coverage A) in coastal territories.

**Wildfire territory**: Western states have developed wildfire-specific territory factors. California's FAIR Plan (the insurer of last resort) uses detailed wildfire risk scores based on vegetation, slope, access roads, and distance to fire stations. Carriers increasingly use wildfire risk models from Verisk, CoreLogic, and others to supplement traditional territory definitions.

### Credit-Based Insurance Scoring (CBIS)

**How CBIS differs from your FICO score**: A credit-based insurance score is not a credit score. While both use data from your credit report, they're built to predict different things:

| | FICO Credit Score | Credit-Based Insurance Score |
|---|---|---|
| **Predicts** | Likelihood of 90-day delinquency on debt | Likelihood of filing an insurance claim |
| **Scale** | 300-850 | Varies by model (typically 200-997) |
| **Key weight** | Payment history (~35%) | Payment history (~40%) |
| **Second weight** | Amounts owed (~30%) | Outstanding debt (~30%) |
| **Also considers** | Length of history, new credit, credit mix | Length of history (~15%), new credit (~10%), credit mix (~5%) |
| **Does NOT use** | N/A | Income, race, religion, gender, marital status, address |

(NAIC, 2024; FICO, 2024; Experian, 2024)

**Impact magnitude**: CBIS is one of the most powerful rating variables in personal lines. The difference between the best and worst credit tiers can mean a **2-3x premium difference** — comparable to the difference between a clean driving record and a DUI. A consumer with poor credit may pay double or triple what someone with excellent credit pays for the same coverage in the same zip code.

**State restrictions on CBIS**:

| Restriction Level | States |
|-------------------|--------|
| **Full ban (auto and home)** | California, Massachusetts, Hawaii |
| **Full ban (auto only)** | Michigan (since 2020 no-fault reform) |
| **Significant restrictions** | Maryland, Nevada, Oregon, Utah |
| **Temporary moratorium (expired)** | Washington (moratorium overturned by court 2022) |
| **Pending legislation** | Texas, several others |

(Experian, 2025; NAIC, 2024)

**The fairness debate**: Consumer advocates argue CBIS disproportionately impacts low-income and minority communities. Industry actuaries counter that CBIS is among the most predictive rating variables available and that removing it forces cross-subsidies. This tension is unresolved and actively debated at the state legislative level.

### Home Age, Roof, and Protection Class

**Home age**: Newer homes generally get better rates because they're built to current codes, have newer wiring/plumbing (less fire and water risk), and have newer roofs. Common thresholds:

- 0-10 years: Best rates (often 15-25% credit)
- 11-25 years: Moderate rates
- 25-40 years: Slight surcharge territory
- 40+ years: Significant surcharges possible; HO-8 (modified coverage form) may be required if replacement cost far exceeds market value

**Roof age and type**: Roof condition is increasingly the single most impactful property characteristic in wind-prone states. Many carriers now apply:

- Roof age surcharges starting at 15-20 years
- Material-based credits/debits (impact-resistant Class 4 shingles can earn 10-30% wind/hail credits in many states)
- Some carriers in Florida and coastal states won't write a home with a roof older than 15 years

**Protection class (PPC)**: ISO's Public Protection Classification rates communities from 1 to 10:

| Class | Meaning | Premium Impact |
|-------|---------|---------------|
| **1** | Superior fire protection | Lowest rates |
| **2-4** | Above average | Low to moderate |
| **5-7** | Average | Moderate |
| **8-9** | Below average | Higher rates |
| **10** | Does not meet ISO minimum criteria | Highest rates; some carriers won't write |

The PPC is based on three components: fire department capability (50 points), water supply infrastructure (40 points), and emergency communications/dispatch (10 points), with up to 5.5 bonus points for community risk reduction programs (Verisk/ISO, 2024). A PPC improvement from Class 6 to Class 4 might save a homeowner 5-15% on premium, depending on the carrier.

### Auto: Driver and Vehicle Factors

**Age curves**: Driver age is the classic U-shaped rating curve. Teenage drivers (16-19) have the highest rates — roughly 2-3x the adult baseline. Rates decline through the 20s, flatten in the 30s-50s, and begin rising modestly after 65-70 as accident frequency increases again. The sharpest rate drop typically happens between ages 19 and 25.

**Vehicle symbols and HLDI**: The **Highway Loss Data Institute** (HLDI), an affiliate of IIHS, publishes loss data for virtually every make/model on U.S. roads, covering collision, comprehensive, BI liability, PD liability, PIP, and medical payments. This data feeds into **vehicle symbols** — numeric ratings that reflect each vehicle's actual claims experience. A sports car with high collision frequency and severity gets a worse symbol than a midsize sedan. HLDI's database covers over 150 million individual passenger vehicles, approximately 80% of all privately insured vehicles on the road (IIHS-HLDI, 2024).

**Annual mileage**: More miles = more exposure. Most carriers tier mileage into bands (e.g., under 5,000, 5,000-10,000, 10,000-15,000, 15,000+). The difference between the lowest and highest bands can be 15-30% of premium.

**Gender**: Historically, young male drivers paid more than young females (higher accident frequency and severity in the 16-24 age group). Several states — including California, Hawaii, Massachusetts, Michigan, North Carolina, and Pennsylvania — prohibit gender as a rating factor. (Montana banned gender-based pricing in 1985 but repealed the ban in 2021.) The trend toward gender-neutral rating is growing, and some major carriers have voluntarily dropped it nationwide.

**Driving record**: Clean records earn significant discounts. On the surcharge side, a single at-fault accident typically adds 20-40% to premium for 3-5 years. A DUI conviction can double or triple the premium and may push a driver into the non-standard market or state assigned risk pool.

---

## 4. Catastrophe Modeling

### The Three Dominant Vendors

The cat modeling market is concentrated among three firms:

| Vendor | Current Owner | Key Strengths |
|--------|---------------|---------------|
| **RMS** | Moody's (acquired 2021 for $2B) | Industry standard for hurricane/earthquake; serves ~70% of Lloyd's managing agents |
| **AIR Worldwide** | Verisk Analytics | Original cat modeler (founded 1987); Touchstone platform; broad peril coverage including terrorism, pandemic, cyber |
| **CoreLogic** | Cotality (rebranded 2025) | Strong in U.S. flood, wildfire, and severe convective storm; large mortgage/real estate client base |

(Moody's, 2024; Verisk, 2024; Cotality, 2025)

### How a Cat Model Works

Every catastrophe model has three core modules:

**1. Hazard module** — Simulates thousands of possible events (hurricanes, earthquakes, etc.) based on historical data and atmospheric/seismic science. A hurricane model might generate 50,000+ synthetic storm tracks representing plausible events over the next year.

**2. Vulnerability module** — Estimates damage to structures given the hazard intensity. This is where building characteristics matter: construction type, roof shape, year built, number of stories, and the presence of mitigation features (hurricane shutters, roof-to-wall connections). The 25 ITV characteristics from [Homeowners](../cpcu/01-homeowners.md#the-25-itv-rating-characteristics) overlap significantly with what vulnerability modules need.

**3. Financial module** — Applies insurance policy terms (deductibles, limits, coinsurance, reinsurance layers) to the damage estimates to calculate insured losses.

**Output**: The model produces an **exceedance probability curve** — the likelihood that losses will exceed any given dollar amount. From this curve, insurers extract:

- **Average Annual Loss (AAL)**: The expected cat loss per year, averaged over thousands of simulations. This is what gets loaded into the rate.
- **Probable Maximum Loss (PML)**: The loss at a given return period (e.g., 1-in-100-year or 1-in-250-year event). This drives reinsurance purchasing and capital requirements.

### How Cat Load Enters the Rate

The AAL from the cat model is added directly to the non-cat loss costs. In hurricane-exposed coastal Florida, the cat load can be 40-60% of the total homeowners premium. In a low-cat state like Wisconsin, it might be under 5%.

### Connection to Reinsurance

Carriers buy reinsurance to protect against the tail risk — the 1-in-50-year or 1-in-100-year events. The cost of that reinsurance is factored into the rate. When reinsurance markets harden (prices rise), as they did significantly in 2022-2023 after Hurricane Ian, the cost flows through to policyholder premiums. This is one reason Florida homeowners rates have been so volatile — reinsurance costs are a direct input to the rate.

### Why Multiple Models Matter

Insurers often run two or all three vendor models and blend the results. Each model uses different assumptions about storm behavior, building vulnerability, and demand surge (post-disaster inflation in construction costs). A carrier might set its cat load at the average of AIR and RMS, or weight toward the more conservative model for capital planning. Regulators sometimes mandate specific models or require the use of multiple models — Florida's OIR, for instance, has historically required the use of an approved hurricane model from the Florida Commission on Hurricane Loss Projection Methodology.

---

## 5. Telematics and Usage-Based Insurance

### How It Works

**Telematics** uses technology — a plug-in OBD-II device, a smartphone app, or a vehicle's built-in connected-car system — to collect real-time driving data. That data feeds into the rating algorithm.

### Program Types

| Type | What's Measured | Examples |
|------|----------------|---------|
| **Pay-how-you-drive (PHYD)** | Driving behavior: hard braking, rapid acceleration, cornering, time of day, phone use | Progressive Snapshot, Allstate Drivewise, State Farm Drive Safe & Save |
| **Pay-per-mile (PPM)** | Mileage only (plus a base rate) | Metromile (now part of Lemonade), Mile, Nationwide SmartMiles |
| **Hybrid** | Both mileage and behavior | Some newer programs combine elements |

**Pay-per-mile mechanics**: The policyholder pays a fixed monthly base rate (covering liability minimums and fixed costs) plus a per-mile charge — typically $0.05-$0.14 per mile depending on location and driver profile. Most programs cap daily mileage charges (e.g., 250 miles/day) so occasional road trips don't spike the bill. PPM works best for drivers under 10,000 miles per year (Metromile, 2024).

### Typical Discounts (and Reality)

Carriers advertise telematics discounts of **10-40%**:

| Carrier | Advertised Maximum Discount |
|---------|----------------------------|
| Allstate Drivewise | Up to 40% |
| Nationwide SmartRide | Up to 40% |
| State Farm Drive Safe & Save | Up to 30% |
| Liberty Mutual RightTrack | Up to 30% |
| GEICO DriveEasy | Up to 25% |

(AutoInsurance.com, 2025; Consumer Reports, 2024)

**The reality check**: Consumer Federation of America research found that typical actual savings are closer to **10%**, and nearly a quarter of enrolled drivers saw their premiums *increase* based on telematics data. The median annual savings among all telematics users was approximately $120, according to Consumer Reports surveys (CFA, 2024; Consumer Reports, 2024).

### Regulatory Considerations

- **Privacy**: Telematics data collection raises significant privacy concerns. Some states restrict what data can be collected and how it can be used.
- **Opt-in requirement**: All current telematics programs in the U.S. are opt-in. No state allows mandatory telematics rating.
- **Rate impact transparency**: Some states require carriers to disclose how telematics data affects premium, including the possibility of surcharges, before enrollment.
- **Data ownership**: Questions around who owns driving data and whether it can be shared with third parties remain under active regulatory discussion.
- **Potential for surcharges**: While most programs are marketed as "discount only," the data collected could theoretically be used at renewal to justify higher rates. Some states require explicit disclosure that telematics participation could result in a surcharge.
- **Connected car data**: As more vehicles come with built-in telematics (GM OnStar, Ford SYNC, Tesla), the industry is shifting from plug-in devices and apps to direct data feeds from automakers. This raises new questions about consent and data monetization.

### Who Benefits Most

Telematics programs tend to benefit low-mileage drivers and consistently safe drivers the most. Young drivers who can't demonstrate their safety through years of claims-free history can use telematics as an alternative proof of low risk. Remote workers who drive well under the national average of ~14,000 miles per year are prime candidates for pay-per-mile programs.

---

## 6. Rate Filing Process in Practice

### What a Filing Contains

When a carrier wants to change its rates, it submits a filing through **SERFF** (System for Electronic Rate and Form Filing), the NAIC's electronic filing platform used in almost every state. A typical rate filing includes:

| Component | Purpose |
|-----------|---------|
| **Filing memorandum** | Summary of what's changing and why |
| **Actuarial memorandum** | Technical justification: data, methodology, assumptions |
| **Rate indication** | The actuarially indicated rate change vs. what's being requested |
| **Loss experience exhibits** | Historical loss data by coverage, territory, class |
| **Loss development factors** | How immature claims are projected to ultimate cost |
| **Trend factors** | Adjustments for loss cost inflation |
| **Catastrophe loading** | Cat model output supporting the cat provision |
| **Expense exhibits** | Commissions, operating costs, taxes |
| **Rate pages** | The actual base rates and factor tables being proposed |

### Regulatory Review Timeline

The timeline depends entirely on the state's regulatory approach (see [Rate Regulation](../cpcu/09-rating-pricing.md#rate-regulation) for the basic frameworks):

| State Approach | Typical Timeline | Example States |
|---------------|-----------------|----------------|
| **Prior approval** | 30-90 days (can stretch much longer) | Florida, New York, Texas |
| **File-and-use** | Effective on filing; reviewed after | Most states for many lines |
| **Use-and-file** | Effective immediately; file within 15-30 days | Several states for certain lines |
| **Open competition** | No filing required | Illinois (some lines) |

### Real-World Examples

**Florida homeowners**: Florida uses prior approval and has been ground zero for rate volatility. Citizens Property Insurance — the state-created insurer of last resort — filed for an average 13.5% increase on HO-3 policies for 2025. The Office of Insurance Regulation (OIR) approved changes ranging from a 10% decrease to a 14% increase depending on territory. By 2026, approved Citizens rates showed a statewide average *decrease* of 8.7%, reflecting legislative reforms (SB 2-A in 2022) that curbed assignment-of-benefits abuse and one-way attorney fees (Citizens, 2024; FLOIR, 2025).

**California auto under Proposition 103**: California's 1988 Proposition 103 created one of the most restrictive prior-approval regimes in the country. Key features:

- The Insurance Commissioner must approve all rate changes before use
- Public notice is required for all rate applications
- Public hearings are mandatory for personal lines increases above 7%
- Consumer groups can intervene in rate proceedings and recover legal fees
- Average filing delay: approximately 226 days for auto insurance — second slowest in the nation

Prop 103 has kept California auto rates below the national average for decades, but critics argue the delays discourage carriers from entering or remaining in the market (CDI, 2024; ICLE, 2024).

### The Tension Between Speed and Consumer Protection

Rate regulation always involves a trade-off. Fast-track systems (file-and-use, use-and-file) let carriers respond quickly to changing loss trends — critical after a major cat event when costs spike overnight. But they give regulators less time to scrutinize rate changes before they hit consumers.

Prior-approval systems protect consumers from sudden large increases and give advocacy groups a voice, but they can create long backlogs. When a carrier can't get a rate increase approved for a year or more, it may stop writing new business in the state, reduce coverage options, or exit entirely — all of which hurt consumers in different ways.

There's no "right" answer. The best system depends on the state's market conditions, catastrophe exposure, and consumer protection priorities. What matters for the exam (and for practice) is understanding the mechanics and trade-offs of each approach.

---

## 7. Practice Questions

**1.** A mid-size carrier uses ISO advisory loss costs with an LCM of 1.40. ISO's loss cost for a given class is $600. What is the carrier's rate, and what does the 0.40 above 1.00 represent?

<details>
<summary>Answer</summary>
The carrier's rate is $600 x 1.40 = $840. The 0.40 (or 40%) above 1.00 represents the carrier's expense and profit provision — commissions, operating expenses, taxes, and profit margin layered on top of ISO's pure loss costs.
</details>

**2.** Why can two homeowners in the same zip code, with the same home value and coverage limits, pay vastly different premiums?

<details>
<summary>Answer</summary>
Individual rating factors create the spread. Credit-based insurance score alone can create a 2-3x difference. Add in variations in roof age and material, protection class (if zip code spans different fire districts), claims history, home age, construction type, and deductible choices, and the premium range within a single zip code can be enormous. Territory is the same, but most other factors differ person to person.
</details>

**3.** A catastrophe model produces an Average Annual Loss (AAL) of $800 for a coastal property. What does this number represent, and how does it enter the premium?

<details>
<summary>Answer</summary>
The AAL of $800 is the expected annual cost of catastrophe losses for that property, averaged across thousands of simulated events (most years the loss is $0, but occasional catastrophic years bring very large losses). This $800 is added directly to the non-catastrophe loss costs as a "cat load" before applying the expense multiplier. It's why coastal premiums are high even in years with no hurricanes — the expected cost of future hurricanes is already baked in.
</details>

**4.** A consumer in California has excellent credit but is quoted a higher auto premium than a similar driver in Texas with average credit. How is this possible?

<details>
<summary>Answer</summary>
California bans credit-based insurance scoring entirely under Proposition 103. The California driver gets no benefit from their excellent credit. Meanwhile, the Texas driver with average credit is still in a "middle tier" — not penalized like a poor-credit driver would be. Combined with California's other rating restrictions and higher base costs in some territories, the California premium can exceed the Texas premium despite the credit advantage.
</details>

**5.** A carrier's telematics program advertises "up to 30% discount." A customer enrolls, drives carefully, and receives a 12% discount. Is the carrier being misleading?

<details>
<summary>Answer</summary>
Not necessarily misleading, but the gap between advertised maximums and typical outcomes is well-documented. The "up to 30%" is the maximum possible discount for the very best drivers. Research from the Consumer Federation of America found typical savings closer to 10%, and some enrolled drivers even see increases. The carrier is advertising the ceiling, not the average — a common practice, but one that can set unrealistic expectations.
</details>

**6.** Why does the cost of reinsurance affect what a homeowner pays for insurance?

<details>
<summary>Answer</summary>
Carriers buy reinsurance to cover catastrophic losses (e.g., losses from a 1-in-100-year hurricane). The cost of that reinsurance is a direct input to the carrier's rate filing — it's part of the expense and risk load built into the premium. When reinsurance markets harden and prices rise (as they did after Hurricane Ian in 2022), carriers must file for higher primary rates to cover the increased reinsurance cost. The policyholder is ultimately funding the entire risk-transfer chain: their premium pays for the carrier's losses, expenses, and the carrier's reinsurance that protects against tail risk.
</details>

---

## Sources

1. NAIC, "Credit-Based Insurance Scores," CIPR Topics, 2024. [content.naic.org](https://content.naic.org/cipr-topics/credit-based-insurance-scores)
2. Experian, "Which States Prohibit or Restrict the Use of Credit-Based Insurance Scores?" 2025. [experian.com](https://www.experian.com/blogs/ask-experian/which-states-prohibit-or-restrict-the-use-of-credit-based-insurance-scores/)
3. FICO, "Credit Scores vs. Insurance Scores," 2024. [insurancescores.fico.com](https://insurancescores.fico.com/CreditvInsurance)
4. III (Insurance Information Institute), "Facts + Statistics: Homeowners and Renters Insurance," 2023. [iii.org](https://www.iii.org/fact-statistic/facts-statistics-homeowners-and-renters-insurance)
5. NAIC, "Auto Insurance Database Report," 2022/2023 edition, adopted December 2025. [content.naic.org](https://content.naic.org/sites/default/files/publication-aut-pb-auto-insurance-database.pdf)
6. Verisk/ISO, "Public Protection Classification (PPC) Program," 2024. [isomitigation.com](https://www.isomitigation.com/ppc/)
7. IIHS-HLDI, "About HLDI," 2024. [iihs.org](https://www.iihs.org/about)
8. Citizens Property Insurance Corporation, "2025 Rate Media Kit," June 2024. [citizensfla.com](https://www.citizensfla.com/-/20240618-citizens-releases-2025-rate-media-kit)
9. Florida Office of Insurance Regulation, "Property Insurance Market Stabilization Update," October 2024. [floir.com](https://floir.com/home/2024/10/10/florida-s-insurance-commissioner-provides-update-on-continued-property-insurance-market-stabilization)
10. California Department of Insurance, "Proposition 103," 2024. [insurance.ca.gov](https://www.insurance.ca.gov/01-consumers/150-other-prog/01-intervenor/)
11. Consumer Federation of America, "Insurance Companies Claim Telematics Will Save You Money," 2024. [consumerfed.org](https://consumerfed.org/insurance-companies-claim-telematics-will-save-you-money-on-auto-insurance-the-truth-is-more-complicated/)
12. Consumer Reports, "Car Insurance Telematics Pros and Cons," 2024. [consumerreports.org](https://www.consumerreports.org/money/car-insurance/car-insurance-telematics-pros-and-cons-a5869096072/)
13. Moody's/RMS, "Catastrophe Risk Modeling," 2024. [rms.com](https://rms.com/models/)
14. Verisk, "ISO Forms, Rules, and Loss Costs," 2024. [verisk.com](https://www.verisk.com/products/forms-rules-and-loss-costs/)
15. SERFF, "System for Electronic Rate and Form Filing," NAIC. [serff.com](https://www.serff.com/)

---

[Back to README](../README.md)
