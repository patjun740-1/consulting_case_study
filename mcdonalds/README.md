# McDonald's: Can All-Day Breakfast Bring Customers Back? (client case project)

**Client question:** Should McDonald's discontinue, maintain or expand All-Day Breakfast to reverse declining customer traffic?

University of Chicago · M.S. in Applied Data Science · Autumn 2026<br>
Team (Group 5): Kaya Jeong, Yuning Ren, Jack Zhang, **Patrick Jun**, Ruby Kang<br>
Format: initial client presentation to a McDonald's regional manager (October 21, 2026)

---

## Executive summary

> **All-Day Breakfast gave traffic a short boost, not a lasting fix, so the decision should rest on profit, not revenue.**
> Breakfast revenue rose about 49% after launch, but most of the gain came from bigger orders, not more customers. Orders ran about 9% above the prior year early on, then the decline returned by summer 2016. We proposed a plan to build the business case before the client's January 1 leadership decision.

| | |
|---|---|
| **~5% a year** | decline in customer traffic over three years (the client's concern) |
| **+48.6%** | breakfast revenue, 8 weeks after launch vs. 8 weeks before |
| **83%** | of that gain came from more items per order; only 3% came from more orders |
| **+9.3%** | orders vs. the same weeks a year earlier, when orders usually fall |
| **6 months** | how long the traffic decline paused before it returned |

## Situation, complication, question

- **Situation:** Customer traffic at the client's restaurants has fallen about 5% a year for three years. All-Day Breakfast launched in October 2015.
- **Complication:** Revenue rose after launch, but it was unclear whether that meant new visits or existing customers simply ordering differently, and whether the gain covers the extra operating cost.
- **Decision:** The regional manager must recommend one of three options to leadership by **January 1**: discontinue, maintain the current McMuffin offering, or expand with more breakfast items.

## Reframing the problem

We turned the client's question into two testable ones:

1. **Demand:** Is All-Day Breakfast generating additional customer visits and revenue, or mainly changing what existing customers order?
2. **Value:** Does it create enough financial value to justify its operating costs?

## Key analytical questions

| # | Question | Why it matters for the decision |
|---|---|---|
| 1 | **Customer traffic:** did All-Day Breakfast bring extra visits? | Traffic is the client's core problem |
| 2 | **Menu substitution:** is the shift from burgers to breakfast profitable? | Revenue can rise while profit falls |
| 3 | **Restaurant differences:** which restaurants benefit the most? | Supports a targeted rollout instead of all or nothing |
| 4 | **Profitability and operations:** do the extra sales cover labor and equipment costs? | Decides between expand, maintain and discontinue |

## Early insights from the sales data

Data: 302,400 weekly sales records across 64 Michigan restaurants (45 franchise, 19 corporate-owned), 25 menu items and 189 weeks (2013 to 2016). Orders were estimated from average daily transactions as a proxy for traffic.

1. **Revenue rose 48.6%.** We compared the 8 weeks before and after launch to isolate the effect.
2. **Customers were not the main driver.** Revenue = orders × items per order × price: items per order +38.9%, price +5.8%, orders only +1.1%.
3. **But +1.1% beats a normal autumn.** Orders usually fall in those weeks; against the same weeks a year earlier they ran 9.3% higher.
4. **The effect faded.** Orders were 6 to 9% below the prior year before launch, held flat from Nov 2015 to Apr 2016, then slipped back to −3% to −6% from May to Aug 2016.
5. **Breakfast is growing while core items slip.** Breakfast rose from 5,186 to 5,994 units per store-week (2014 to 2016), while fries fell every year from 4,917 to 4,215.

## Data assessment

| What we found | Why it matters | Next step |
|---|---|---|
| 4,762 sales records missing, concentrated in a few stores | Store comparisons may be uneven | Treat as missing, not zero, before comparing restaurants |
| 253 restaurant-weeks with different transaction counts for the same store and week | Traffic, the key metric, may be measured inconsistently | Confirm how transactions are calculated and reported |
| 8,546 records where weekly and daily figures don't align | Some volumes may be misreported | Review unusual values and reporting days |
| No cost, margin or promotion data | Profitability can't be judged yet | Request it from the client |

## What we asked of the client

- **Business priorities:** How are "customer traffic" and "revenue" measured? Is the main success metric visits, revenue or profit? What would success look like to leadership?
- **Operational impact:** Has All-Day Breakfast increased kitchen workload, labor or service times? What would limit a larger breakfast menu?
- **Data and access:** total-store transaction counts, product-level margins, extra labor and equipment costs, interviews with franchise owners and corporate managers, and visits to a few restaurants.

## Workplan to the January 1 decision

| Phase | Dates | Deliverable |
|---|---|---|
| Define business objectives and success metrics | Oct 15 to 23 | Project scope |
| Validate data readiness | Oct 19 to Nov 6 | Data quality report |
| Analyze revenue and traffic impact | Nov 2 to 27 | EDA report |
| Evaluate business viability (gains vs. costs) | Nov 23 to Dec 11 | Business case |
| Final recommendation and action plan | Dec 7 to 23 | Recommendation deck |

**Decision framework:** **Expand** if All-Day Breakfast delivers sustained incremental profit, **target** the restaurants where it performs best, or **reassess** it if the incremental value is limited.

## My contribution

- Worked on the exploratory analysis of the weekly sales and restaurant data (item volumes, trends, ownership differences and data quality checks).
- Helped shape the data assessment, client questions and workplan in the team's client presentation.

## Consulting skills shown

Problem reframing · Hypothesis-driven issue structuring · Separating revenue from traffic in the evidence · Data-gap assessment and client asks · Workplan built backward from the client's decision date

---

*Class client case project. McDonald's is the case client; this is not work done for or endorsed by McDonald's. The course-provided datasets are not included.*
