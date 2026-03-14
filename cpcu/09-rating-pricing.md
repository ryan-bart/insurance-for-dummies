# CPCU 556: Rating & Pricing

[Back to README](../README.md) | [Previous: Underwriting](08-underwriting-personal-lines.md) | [Next: Claims Handling](10-claims-handling.md)

---

## Why This Matters

Rating is where underwriting meets math. It determines what a policyholder actually pays. Understanding how premiums are built — and how regulators oversee the process — is core CPCU 556 material.

---

## How Premiums Are Built

A premium isn't a random number. It's constructed from layers:

```
Pure Premium (Loss Costs)
  + Loss Adjustment Expenses (LAE)
  + Operating Expenses (commissions, admin, IT)
  + Profit & Contingency Loading
  ──────────────────────────────
  = Gross Premium
```

### Pure Premium / Loss Costs
The expected cost of claims per exposure unit. This is the foundation.

> **Pure Premium = Expected Losses / Number of Exposure Units**

An exposure unit varies by line:
- **Homeowners**: Per dwelling
- **Auto liability**: Per car-year
- **Auto physical damage**: Per car-year

### Expense Loading
Everything besides claims: commissions (typically 10–15% for independent agents on personal lines), operating costs, taxes, and profit margin. Typically adds 30-40% on top of loss costs.

---

## Rating Factors

Rating factors adjust the base rate for individual risk characteristics:

### Homeowners Rating Factors

| Factor | Impact |
|--------|--------|
| **Territory** | Geographic area — coastal, urban, wildfire zone, etc. |
| **Protection class** | ISO 1-10 fire protection rating |
| **Construction type** | Frame, masonry, fire-resistive |
| **Coverage amount** | Higher replacement cost = higher premium |
| **Deductible** | Higher deductible = lower premium |
| **Age of home** | Newer homes get credits; older homes may be surcharged |
| **Claims history** | Claims-free discounts; surcharges for recent claims |
| **Credit score** | Where allowed by state |
| **Protective devices** | Alarms, deadbolts, smoke detectors = credits |
| **Roof type and age** | Major factor — old roofs or wood shingles cost more |

#### ITV Rating Characteristics & Replacement Cost

The coverage amount factor above depends on an accurate **Insurance to Value (ITV)** calculation. Verisk's research identified **25 property characteristics** that drive replacement cost estimation — 9 primary (year built, square footage, quality grade, number of stories, foundation type, finished % of lowest level, exterior wall finish, garage/carport, fireplaces) and 16 secondary (bathroom count, floor covering, cooling system, roof cover, kitchen count, kitchen counters, heating, property slope, site access, interior wall finish, foundation shape, roof shape, wall height, exterior wall construction, foundation material, interior wall material).

The more of these characteristics captured during quoting and underwriting, the more accurate the ITV — which directly affects both premium adequacy and whether the insured triggers a coinsurance penalty after a loss. See [Homeowners: ITV Rating Characteristics](01-homeowners.md#the-25-itv-rating-characteristics) for the full breakdown.

### Auto Rating Factors

| Factor | Impact |
|--------|--------|
| **Driver age/gender** | Young males historically highest rated (gender use varies by state) |
| **Driving record** | Clean = discount; DUI = massive surcharge |
| **Territory** | Zip code drives congestion, theft, litigation rates |
| **Vehicle type** | Safety ratings, repair costs, theft frequency |
| **Annual mileage** | More driving = more exposure |
| **Credit-based insurance score** | Where permitted |
| **Coverage and deductible selections** | Higher limits/lower deductibles = more premium |
| **Multi-car discount** | Insuring multiple vehicles |
| **Multi-policy discount** | Bundling auto with homeowners |
| **Good student discount** | Young drivers with good grades |
| **Defensive driving course** | Credit for completion |

---

## Common Rating Approaches

### Class Rating
Group risks with similar characteristics into classes and charge the same rate. This is how most personal lines work.

> All 35-year-old drivers with clean records in zip code 28205 driving a 2023 Honda Accord pay roughly the same base rate.

### Individual (Merit) Rating
Adjusts the class rate based on individual experience:

- **Experience rating**: Adjusts based on the individual's own loss history
- **Schedule rating**: Adjusts based on specific characteristics (more common in commercial)
- **Retrospective rating**: Premium adjusted after the policy period based on actual losses (rare in personal lines)

---

## The Combined Ratio

The most important profitability metric in insurance:

> **Combined Ratio = Loss Ratio + Expense Ratio**

| Component | Formula | What It Means |
|-----------|---------|--------------|
| **Loss Ratio** | Incurred Losses / Earned Premium | % of premium going to claims |
| **Expense Ratio** | Underwriting Expenses / Written Premium | % of premium going to expenses |
| **Combined Ratio** | Loss Ratio + Expense Ratio | Overall underwriting profitability |

- **Combined ratio < 100%** = underwriting profit
- **Combined ratio > 100%** = underwriting loss
- **Combined ratio = 105%** means the insurer is losing 5 cents on every premium dollar from underwriting (investment income may still make overall profit)

**Industry context**: Personal auto combined ratios ran 100–112% from 2020–2023 due to post-pandemic inflation, but improved sharply to ~95% in 2024 after successive rate increases. Homeowners is more volatile due to catastrophe exposure.

---

## Rate Regulation

Insurance rates are regulated at the state level. The three main approaches:

### Prior Approval
- Insurer must file rates and get state approval **before** using them
- Slowest to respond to market changes
- Most common approach historically
- Gives regulators the most control

### File-and-Use
- Insurer files rates and can start using them immediately
- Regulator reviews after the fact and can disapprove
- Faster than prior approval

### Use-and-File
- Insurer can use new rates immediately
- Must file with the regulator within a set period (e.g., 30 days)
- Even less regulatory friction

### Open Competition (No File)
- No filing requirement — or informational filings only
- Market forces determine rates
- Illinois uses this approach for property/casualty lines (the only state with no P/C rating law)
- Least common approach

### Rate Standards
Regardless of the approach, rates must be:
- **Adequate**: Enough to pay claims and expenses (protects insurer solvency)
- **Not excessive**: Not gouging consumers
- **Not unfairly discriminatory**: Rate differences must be based on actuarial justification, not prohibited categories

---

## Actuarial Concepts in Plain Language

### Law of Large Numbers
The more policies you write, the more predictable your losses become. A single homeowner is unpredictable. A million homeowners is very predictable in aggregate.

### Credibility
How much weight to give your own data vs industry data. A small insurer with 500 auto policies can't rely solely on their own loss experience — not enough data. They blend with industry data.

### Loss Development
Claims take time to fully settle. A $50,000 reserve today might become a $75,000 payment next year. Actuaries estimate the "ultimate" cost of claims using development factors.

### Trending
Losses trend upward over time (inflation, social inflation, medical costs). Actuaries project current cost levels into the future policy period.

### Catastrophe Loading
Models estimate expected catastrophe losses (hurricanes, earthquakes) and add a loading to the rate. This is why coastal homeowners rates are so high — even in years without hurricanes, the expected cost of future hurricanes is baked into the premium.

---

## Practice Questions

**1.** An insurer's loss ratio is 65% and expense ratio is 32%. What's the combined ratio, and is the insurer profitable from underwriting?

<details>
<summary>Answer</summary>
Combined ratio = 65% + 32% = 97%. Yes, the insurer is making an underwriting profit — they're keeping 3 cents on every premium dollar after claims and expenses. Plus they earn investment income on top of this.
</details>

**2.** Why does a higher deductible lower your premium?

<details>
<summary>Answer</summary>
The insurer is taking on less risk — they don't pay the first $X of every claim. This eliminates small claims entirely and reduces the payout on larger claims. The premium reduction reflects the reduced expected loss to the insurer.
</details>

**3.** What's the difference between "prior approval" and "file-and-use" rate regulation?

<details>
<summary>Answer</summary>
Prior approval: the insurer must get regulator approval BEFORE using new rates. File-and-use: the insurer can start using rates immediately upon filing, with the regulator reviewing after the fact. File-and-use is faster and more responsive to market conditions.
</details>

**4.** Why are homeowners rates in coastal Florida so much higher than in Ohio?

<details>
<summary>Answer</summary>
Catastrophe loading. Even in a year with no hurricanes, the premium includes the expected cost of future hurricanes based on catastrophe models. Florida's coastal exposure to hurricanes drives massive cat loading. Also: higher litigation costs, assignment of benefits issues, and roof damage frequency from storms.
</details>

**5.** An insurer has 200 auto policies and wants to set rates. Can they rely entirely on their own loss data?

<details>
<summary>Answer</summary>
No. With only 200 policies, their own experience isn't statistically credible — a couple of large claims could wildly skew the data. They'd need to blend their experience with industry data, giving more weight to industry data (low credibility for their own). This is the concept of actuarial credibility.
</details>

---

**Want to go deeper?** See [Rating Deep Dive: From Loss Costs to Final Premium](../combined/05-rating-deep-dive.md) for the full ISO loss cost waterfall, catastrophe modeling, telematics, credit-based insurance scoring mechanics, and real-world rate filing examples.

---

## Sources

1. Insurance Information Institute (III), "Personal Auto 2024 Underwriting Results Best Since Pandemic," 2025. [iii.org](https://insuranceindustryblog.iii.org/personal-auto-2024-underwriting-results-best-since-pandemic/)
2. Verisk / ISO, "Loss Costs and Rating." [verisk.com](https://www.verisk.com/)
3. NAIC, "State Insurance Regulation," rate regulation overview. [naic.org](https://content.naic.org/)
4. Insurance Business America, "Illinois Nixes Insurance Rate Bill Amid Affordability, Competition Concerns," 2025. [insurancebusinessmag.com](https://www.insurancebusinessmag.com/us/news/regulatory/illinois-nixes-insurance-rate-bill-amid-affordability-competition-concerns-555510.aspx)
5. A.M. Best, "U.S. Personal Auto Insurance Segment Sustains Underwriting Turnaround Into 2025." [ambest.com](https://news.ambest.com/pr/PressContent.aspx?refnum=36480&altsrc=2)
6. Brightway Insurance, "How Insurance Agents Get Paid: Commission Models, Compensation Types," 2024. [brightway.com](https://www.brightway.com/news/how-insurance-agents-get-paid-commission-models-compensation-types-and-what)
7. CPCU Society / The Institutes, *CPCU 556: Personal Risk Management and Insurance*, course materials.

---

[Next: Claims Handling](10-claims-handling.md)
