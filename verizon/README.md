# Verizon: Device-Financing Risk Strategy (client case project)

**Client question:** How can Verizon approve, negotiate or deny phone financing faster and more consistently in store, while making more profit?

University of Chicago · M.S. in Applied Data Science · Autumn 2026<br>
Team (Group 5): Kaya Jeong, **Patrick Jun**, Ruby Kang, Yuning Ren, Jack Zhang<br>
Format: competitive proposal, presented live to the client's steering committee (8 minutes)

---

## Executive summary

> **Keep every approval Verizon makes today, and start testing the profitable customers it turns away.**
> A transparent risk model finds about **+$10.6M of profit per 1M applications (+8.8%)**, and even the conservative case adds **+$3.2M**. We recommend a capped pilot on the lowest-risk group, with a stop rule if defaults exceed predictions.

| | |
|---|---|
| **+$10.6M** | added profit per 1M applications, with no change to current approvals |
| **+$3.2M** | conservative case (defaults 50% above prediction, 60% take-up) |
| **41.7%** | break-even default probability; the riskiest approved group defaults at about 19% |
| **95.7%** | of the 18,131 applicants turned away in the latest period are predicted below break-even |
| **5,380** | low-risk applicants to start the pilot with (worth $6.8M per 1M applications on their own) |

## Situation, complication, question

- **Situation:** Verizon buys the phone and the customer repays over 24 months. A bad approval costs 35% of the device price; a wrongly denied good customer costs the 25% margin.
- **Complication:** Verizon changed its approval rules twice (Aug 2023, May 2024), so the same internal score meant different risk at different times. Defaults then rose from about 7% to 11%, and store decisions were driven by score cut-offs that ignore this.
- **Key question:** Where is Verizon losing profit today, and how can a better model become a simple, low-risk decision in store?

Because the two kinds of mistakes cost different amounts, we set the goal as **maximizing total profit, not minimizing defaults**.

## How we structured the problem

| Issue | What we tested | Answer |
|---|---|---|
| 1. Where is value lost? | Profit per plan = Price × (0.25 − 0.60·p) | Any applicant below a 41.7% default chance is profitable on average |
| 2. Is the current policy the problem? | Default rates within risk-score bands before and after the May 2024 tightening | No. Defaults rose about 3 points in every band, which points to outside economic conditions; the tightening helped slightly |
| 3. Does the score miss risk? | Actual vs. predicted defaults by segment | Yes. Existing customers (9.4% actual vs 7.6% predicted) and under-25s (12% vs 8% at 25+) are underestimated |
| 4. Should Verizon decline more? | Profit impact of cutting the riskiest current approvals | No. Cutting the riskiest 5% would lose $3.7M per 1M; for every default avoided, about five good customers are turned away |
| 5. Where is the upside? | Predicted default for the 18,131 applicants not funded | 17,352 are below break-even, so the value is in today's rejections |

## Recommendation: four decisions instead of one "rejected" group

| Decision | Predicted default | Applicants | What the store does |
|---|---|---|---|
| **Approve** | ≤ 20% | 5,380 | Offer the standard plan, starting with a capped pilot |
| **Negotiate** | < 41.7% | 10,416 | Offer a lower-priced phone or a bigger down payment |
| **Hold** | 20 to 30% | 1,556 | No new offer yet; revisit after the pilot |
| **Reject** | ≥ 41.7% | 779 | Stay declined |

**In the store:** the rep enters the score, the existing-customer flag and age, and the tool returns the decision with its main reasons, so decisions are consistent and explainable to the customer.

## Business case per 1M applications

**Value formula:** ΔProfit = profit from newly funded applicants − profit lost from newly declined applicants (none, since every current approval is kept).

| Group | Action | New plans | Added profit |
|---|---|---|---|
| Walked away from revised terms, p ≤ 20% | Approve | ≈53,700 | $6.8M |
| Denied, p < 41.7% | Negotiate | ≈62,300 | $3.8M |
| Walked away, p 20 to 30% | Hold | 0 | $0 |
| Predicted default ≥ 41.7% | Reject | 0 | $0 |
| **Total** | | **≈116,000** | **≈$10.6M (+8.8% over $119.7M today)** |

| Scenario | Assumption | Added profit |
|---|---|---|
| Conservative | Defaults 50% above prediction; 60% accept approvals | $3.2M |
| Base | Assumptions in the table above | $10.6M |
| Upside | Everyone below break-even gets standard terms | $15.5M |

The Approve group stays profitable even if defaults are 2.7× our prediction, so the downside of starting there is small.

## Implementation and risk management

1. **Protect today's profit:** keep every current approval; nothing Verizon earns today is put at risk.
2. **Pilot first:** start with the 5,380 Approve group, cap the volume, and stop if defaults exceed predictions.
3. **Monitor:** track defaults, profit and fairness by segment; the model's edge is smaller in current conditions, so the pilot checks it.
4. **Scale:** extend to the Negotiate group once early defaults match predictions.

## Why this model works for the client

We chose a logistic regression built on Verizon's own score rather than a black-box model:

- **Decision fit:** it gives a default probability that compares directly with the 41.7% break-even.
- **Transparency:** each term is one risk driver, so the model can be audited and stores can state decline reasons.
- **Same accuracy:** gradient boosting and CatBoost reached the same accuracy (holdout AUC about 0.62); ours scored 0.625 vs. 0.586 for Verizon's score alone, and predicted 10.7% defaults vs. 10.7% actual.
- **Easy to deploy:** it uses fields already collected at the point of sale, so no new data pipeline is needed.

## My contribution

- Wrote an individual risk review of 300,000 applications (Jan 2023 to Dec 2024) that found the two rule-change dates, showed the 2024 default rise came from outside conditions rather than the tighter policy, flagged the segments the score misprices, and set out the 41.7% break-even logic.
- Worked with the team to turn those findings into the four-decision recommendation, the business case and the pilot plan in the final proposal.

## Consulting skills shown

Hypothesis-driven problem structuring · Turning a model into a business decision · Business case with sensitivity scenarios · Low-risk pilot design · Executive storytelling to a steering committee

---

*Class client case project. Verizon is the case client; this is not work done for or endorsed by Verizon. The course-provided dataset and analysis code are not included.*
