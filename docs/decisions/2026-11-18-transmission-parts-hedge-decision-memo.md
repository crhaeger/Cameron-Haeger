# FX Hedging Decision Memo — Transmission-Parts Receivable

**To:** Chief Financial Officer  
**From:** Cameron Haeger, Finance Analyst  
**Date:** November 18, 2026  
**Subject:** Recommended FX Hedging Strategy for €12 Million Receivable

## A. Exposure Summary

Our company is expecting to receive €12 million from a Slovak automotive assembly customer in 91 days. Because the payment will be received in euros but our company operates in U.S. dollars, we face foreign-exchange risk between now and settlement.

Using the November 13, 2026 reference spot rate of 1.1052 USD/EUR, the receivable currently has an estimated value of $13,262,400. However, the actual USD amount received will depend on the exchange rate when the customer makes the payment.

If the euro depreciates against the U.S. dollar, the company will receive fewer dollars when converting the payment. If the euro appreciates, the company could receive more dollars. This uncertainty creates risk for cash-flow planning, budgeting, and financial performance.

To evaluate how we can manage this exposure, I compared four approaches: remaining unhedged, entering a forward contract, establishing a money-market hedge, and purchasing a EUR put option. I also evaluated a EUR call option for comparison, although a call is designed to protect a EUR payable rather than our EUR receivable.

The objective is to identify a strategy that protects the company's expected USD cash flows while considering certainty, cost, flexibility, and the reliability of the available market assumptions.

## B. Hedge Outcomes

Using the updated Stage 4 market-data assumptions, I calculated the expected USD proceeds under each hedging strategy. The results show meaningful differences in the amount of cash the company can protect and the flexibility each strategy provides.

| Hedging strategy | USD proceeds | Main consideration |
|---|---:|---|
| Unhedged | $13,262,400 at current spot | Fully exposed to future exchange-rate movements |
| Forward hedge | $13,983,600 | Fixed proceeds, no upfront option premium |
| Money-market hedge | $13,313,834 | Fixed proceeds, but requires borrowing and investing |
| EUR put hedge | Minimum $13,084,074 | Downside protection with upside potential, less premium |
| EUR call comparison | Not applicable to receivable | Protects a EUR payable, not a EUR receivable |

**Forward hedge:** By selling €12 million forward at the assigned rate of 1.1653 USD/EUR, the company would lock in $13,983,600 at settlement. This is the highest guaranteed amount among the modeled alternatives. However, the assigned rate has not been verified as an executable bank quote.

**Money-market hedge:** The company could borrow approximately €11,916,411 today, convert the euros into dollars, and invest the proceeds at the assumed USD interest rate. This would produce approximately $13,313,834 at settlement. Although the strategy removes exchange-rate uncertainty, its actual cost would depend on the company's borrowing and investing rates.

**EUR put hedge:** Purchasing a put option with a strike of 1.1052 USD/EUR would establish minimum net proceeds of approximately $13,084,074 after financing the option premium. The company could still benefit if the euro appreciates, but the financed premium of approximately $178,326 reduces its proceeds.

**Unhedged position:** At the current spot rate, the receivable is worth $13,262,400. Remaining unhedged avoids the direct costs of hedging but exposes the entire payment to exchange-rate changes over the next 91 days.

The forward hedge produces approximately **$669,766 more than the money-market hedge** under the assigned inputs. This difference is significant and requires further examination because the assigned forward rate is substantially above the rate implied by covered interest parity.

Overall, the forward hedge offers the strongest modeled cash-flow certainty and the highest guaranteed proceeds. However, the reliability of this result depends on confirming the forward quote before execution.

## C. Sensitivity Analysis

To understand how exchange-rate movements could affect the company's cash flows, I evaluated three potential settlement rates: a 5% euro depreciation, no change, and a 5% euro appreciation relative to the current spot rate of 1.1052 USD/EUR.

| Future spot rate (USD/EUR) | Unhedged | Forward | Money-market | EUR put (net) |
|---|---:|---:|---:|---:|
| 1.04994 (−5%) | $12,599,280 | $13,983,600 | $13,313,834 | $13,084,074 |
| 1.10520 (0%) | $13,262,400 | $13,983,600 | $13,313,834 | $13,084,074 |
| 1.16046 (+5%) | $13,925,520 | $13,983,600 | $13,313,834 | $13,747,194 |

The results show that remaining unhedged creates the greatest uncertainty. A 5% depreciation would reduce the receivable's USD value to $12,599,280, while a 5% appreciation would increase it to $13,925,520. This represents a $1,326,240 difference between the two scenarios.

Both the forward and money-market hedges eliminate exchange-rate uncertainty by fixing the USD proceeds. Under the assigned forward rate, the forward hedge consistently produces the highest proceeds across all three scenarios.

The EUR put offers a different balance between protection and flexibility. It establishes a minimum net value of approximately $13.08 million while allowing the company to benefit from euro appreciation. At the +5% scenario, the put produces approximately $13.75 million after the financed premium, compared with $13.98 million from the forward hedge.

The forward hedge remains more favorable than the unhedged position until the settlement exchange rate exceeds 1.1653 USD/EUR. Similarly, the EUR put would outperform the forward only if the euro appreciates beyond approximately 1.18016 USD/EUR, assuming the modeled premiums and forward rate remain unchanged.

**Sensitivity conclusion:** The forward hedge is the strongest choice within the tested scenarios because it offers predictable cash flows and the highest modeled proceeds. The put becomes more attractive if management expects substantial euro appreciation and is willing to pay for flexibility. However, the final decision should be based on risk management rather than relying solely on an exchange-rate forecast.

## D. Recommendation and Forward-Rate Evaluation

Based on the modeled results, I recommend that the company use a **91-day EUR forward contract**, provided that the assigned forward rate of 1.1653 USD/EUR can be confirmed through an executable bank quote.

At this rate, the company would lock in $13,983,600, eliminating uncertainty about the USD value of its €12 million receivable. The forward also avoids the upfront premium required for an option and does not require the borrowing and investing transactions associated with a money-market hedge.

However, an important concern is the difference between the assigned forward rate and the rate implied by covered interest parity (CIP). Using the updated Stage 4 interest-rate assumptions:

**CIP-implied forward rate:**

F = 1.1052 × [1 + (0.04320 × 91/360)] / [1 + (0.02775 × 91/360)]

F ≈ **1.109486 USD/EUR**

The assigned forward rate of 1.1653 exceeds the CIP-implied rate by approximately **0.055814 USD/EUR**.

For the €12 million receivable, this difference represents:

€12,000,000 × (1.1653 − 1.109486)

≈ **$669,766**

The assigned forward rate is approximately 5.03% above the CIP-implied rate when measured relative to the implied rate. This is a substantial discrepancy for a 91-day hedge.

Possible explanations include the use of an assigned scenario quote rather than a live market quote, differences between benchmark and company-specific interest rates, transaction costs, or inconsistent market observations. The available documentation does not establish which explanation is responsible.

This discrepancy is particularly important because it accounts for nearly the entire advantage of the forward hedge over the modeled money-market hedge. If the company receives an executable forward quote closer to 1.109486 USD/EUR, the forward proceeds would decline to approximately $13,313,834, making the forward and money-market alternatives nearly equivalent under the benchmark assumptions.

Therefore, I would recommend the following before execution:

1. Request a current, executable 91-day EUR/USD forward quote from the company's bank.
2. Confirm the company's actual EUR borrowing and USD investing rates.
3. Obtain current EUR put option premiums and terms for the same settlement horizon.
4. Recalculate the strategies using the verified quotes before selecting the final hedge.

**Final recommendation:** The forward contract is the preferred strategy under the assigned academic scenario because it provides the highest guaranteed proceeds and strong cash-flow certainty. For an actual transaction, I would not execute the hedge until the forward rate is verified. If the executable rate is close to the CIP-implied rate, I would still consider a forward for its operational simplicity, but the choice between the forward, money-market hedge, and put would depend on actual costs and management's need for flexibility.

## E. Executive Justification

From a financial management perspective, the main purpose of hedging this receivable is to protect the company's expected USD cash flows rather than speculate on future exchange-rate movements. Because the €12 million payment is due in 91 days, having a predictable dollar amount would help management plan for operating expenses, supplier payments, and other financial obligations.

**Cash-flow certainty:** A forward contract provides a fixed exchange rate, making it easier to forecast the USD proceeds from the receivable. Under the assigned assumptions, the company would receive $13,983,600 regardless of future currency movements.

**Liquidity and financing:** Unlike the money-market hedge, a forward generally does not require the company to borrow euros and invest dollars today. This makes the strategy operationally simpler and avoids using borrowing capacity for the hedge. However, bank credit requirements, collateral arrangements, or margin provisions could still affect liquidity.

**Cost and flexibility:** The forward avoids the upfront option premium but also removes the opportunity to benefit from favorable euro appreciation. The EUR put preserves that upside potential while providing downside protection, although its financed premium of approximately $178,326 reduces the company's net proceeds. Management must determine whether that flexibility is worth the additional cost.

**Execution and counterparty risk:** Before entering a forward contract, the company should verify the quoted rate, settlement date, and counterparty requirements. Management should also consider the possibility of a delayed customer payment, since a forward obligation may remain in place even if the underlying receivable is not received on schedule.

**Financial reporting:** The company should consult its accounting team to determine the appropriate treatment of the hedge and whether hedge accounting is available under the applicable reporting standards.

### Final Decision

I recommend a forward hedge for the €12 million receivable, subject to verification of an executable 91-day forward quote and confirmation of the company's settlement and credit requirements.

The modeled forward provides the strongest combination of cash-flow certainty, operational simplicity, and guaranteed USD proceeds. However, the unusually large difference between the assigned forward rate and the CIP-implied rate means that the company's actual decision must be based on verified market terms rather than the assigned scenario alone.

This approach allows management to prioritize financial stability while ensuring that the hedge is both economically reasonable and practical to execute.

