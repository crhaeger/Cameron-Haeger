---
type: brief
engagement: fx-hedging
capability: fx-hedging
date: 2026-10-25
status: committed
hypothesis: "A forward hedge will provide the most predictable USD proceeds, while a EUR put may offer a better balance of downside protection and upside potential after accounting for its premium."
---

# FX Hedging Executive Brief: Transmission-Parts

**To:** Chief Financial Officer  
**From:** Finance Analyst  
**Date:** October 25, 2026  
**Subject:** Managing EUR/USD Exposure on a €12 Million Receivable

## Exposure and Business Risk

Our company, a U.S. transmission-parts supplier, expects to receive €12,000,000 from a Slovak car-assembly plant in 91 days. Because our operating expenses and financial reporting are primarily in U.S. dollars, the final dollar value of this receivable depends on the EUR/USD exchange rate at settlement. A weaker euro would reduce the dollars received and potentially affect cash flow, budgeting, and profitability.

Our indicative 91-day forward rate is $1.1653 per euro, which would lock in $13,983,600 before transaction costs. As an illustration, if the euro weakened to $1.07, the unhedged receivable would convert to $12,840,000, a $1,143,600 reduction compared with the forward-locked amount. This demonstrates why managing the exposure matters even though the euro amount owed is fixed.

## Hedging Alternatives

**1. Forward contract.** Selling euros forward locks in an exchange rate today for the future settlement date. At the quoted rate, this guarantees $13,983,600 before transaction costs, assuming the contract covers the full receivable. Its primary advantage is certainty for cash-flow planning. However, the company gives up additional gains if the euro strengthens, and it must consider counterparty exposure and contractual obligations.

**2. Money-market hedge.** This strategy involves borrowing the present value of the expected euro receivable, converting the borrowed euros into dollars at spot, and investing the dollar proceeds until settlement. It can create a predictable dollar value similar to a forward hedge. However, its effectiveness depends on available borrowing and investment rates, transaction costs, and access to credit. Preliminary reference data dated October 23, 2026, show a three-month U.S. Treasury rate of approximately 4.22% and three-month EURIBOR of 2.666%. These are market benchmarks, not necessarily the company's actual borrowing or deposit rates.

**3. EUR put option.** Buying a put on euros gives the company the right, but not the obligation, to sell euros at the strike price. The quoted premium is $0.0147 per euro, or $176,400 for €12 million. This strategy establishes downside protection while allowing the company to benefit if the euro strengthens, but the premium reduces net proceeds regardless of whether the option is exercised.

## Assumptions and Hypothesis

This analysis assumes the full receivable arrives in 91 days, the amount does not change, and the company can access the quoted forward contract and option. The final model must verify the spot quote, applicable interest rates, day-count conventions, and transaction costs.

I expect the forward hedge to provide the most predictable proceeds because it fixes the exchange rate without an option premium. However, the EUR put could prove more attractive if the euro appreciates sufficiently to offset its premium. This hypothesis would be challenged if the modeled net option proceeds consistently outperform the forward across realistic exchange-rate scenarios, or if actual forward terms materially differ from the indicative quote.

## Next Steps

Stage 2 will specify the model structure, formulas, and validation checks. Stage 3 will build and audit the workbook. Stage 4 will incorporate dated, sourced market data. Stage 5 will independently validate the results and produce a final decision memo comparing net proceeds, downside protection, and upside potential. No final hedge recommendation will be made until these comparisons are complete.

## Preliminary Sources

- Federal Reserve, Selected Interest Rates: https://www.federalreserve.gov/releases/h15/
- Bank of Finland, EURIBOR rates: https://www.suomenpankki.fi/en/statistics/interest-rates-and-exchange-rates/euribor-rates/
- European Central Bank, EUR/USD reference rates: https://www.ecb.europa.eu/stats/policy_and_exchange_rates/euro_reference_exchange_rates/html/index.en.html
