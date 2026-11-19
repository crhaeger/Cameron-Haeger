# Stage 5 — Transmission-Parts FX Hedging Validation Analysis

**Date:** November 18, 2026  
**Scenario:** U.S. transmission-parts supplier  
**Exposure:** €12,000,000 receivable in 91 days  
**Independent AI Tool:** Muse  
**Purpose:** Compare independent hedge calculations with my Stage 4 Excel model and identify any documentation gaps or discrepancies.

## 1. Independent AI Verification

For Stage 5, I used Muse in a separate AI conversation to independently calculate the company's foreign-exchange hedging outcomes. I provided only my Stage 2 FX hedging specification and Stage 4 market-data memo, without sharing my Excel workbook or previous calculations.

I asked Muse to calculate the unhedged position, forward hedge, money-market hedge, EUR put hedge, and EUR call comparison where applicable. I also requested results under different future spot exchange rates, a recommended hedging strategy, and identification of missing information or ambiguities.

Muse used the updated Stage 4 inputs, including the 3-month USD interest rate of 4.320%, 3-month EUR interest rate of 2.775%, spot rate of 1.1052 USD/EUR, and assigned forward rate of 1.1653 USD/EUR.

The independent analysis reproduced the main forward, money-market, and put hedge results reported in my workbook. However, Muse also identified several documentation limitations, including the unverified forward quote, benchmark interest-rate assumptions, differences between the original specification and updated option strikes, and inconsistencies in the memo's dates and premium-financing descriptions.

I preserved Muse's original response in `analysis/2026-11-18-transmission-parts-muse-independent-output.md` so the independent results can be reviewed separately from my validation and conclusions.

## 2. Independent Results Compared with Excel

| Hedge calculation | Muse result | Excel result | Comparison |
|---|---:|---:|---|
| Forward proceeds | $13,983,600.00 | $13,983,600.00 | Match |
| EUR borrowed today | €11,916,411.34 | €11,916,411.34 | Match |
| USD spot conversion | $13,170,017.81 | $13,170,017.81 | Match |
| Money-market proceeds | $13,313,834.41 | $13,313,834.41 | Match |
| CIP-implied forward | 1.109486 | 1.109486 | Match |
| Put premium at maturity | $178,326.29 | $178,326.29 | Match |
| Put minimum net proceeds | $13,084,073.71 | $13,084,073.71 | Match |
| Call premium at maturity | $241,407.70 | $241,407.70 | Match |

The matching results provide evidence that the workbook's core hedge calculations are consistent with an independent application of the documented formulas. However, numerical agreement does not independently establish that the assigned forward rate, benchmark interest rates, or option premiums are executable market quotes.

## 3. Independent Hand Calculations

To verify the independent AI results and my Excel workbook, I recalculated the forward hedge, money-market hedge, and EUR put hedge using the documented Stage 4 inputs.

**Inputs:**

- EUR receivable: €12,000,000
- Spot exchange rate: 1.1052 USD/EUR
- Forward exchange rate: 1.1653 USD/EUR
- USD interest rate: 4.320%
- EUR interest rate: 2.775%
- Settlement period: 91 days
- Day-count convention: ACT/360
- Put strike: 1.1052 USD/EUR
- Put premium: 0.0147 USD/EUR

### Calculation 1: Forward Hedge

The forward hedge locks in a fixed USD exchange rate for the €12 million receivable.

Forward proceeds = EUR receivable × Forward rate

= €12,000,000 × 1.1653

= **$13,983,600.00**

This matches both Muse's independent result and the Excel workbook.

### Calculation 2: Money-Market Hedge

The money-market hedge involves borrowing euros today against the future receivable, converting them into dollars, and investing the dollars until settlement.

**Step 1 — Calculate the interest factors:**

Time = 91 / 360 = 0.25277778 years

EUR interest factor = 1 + (0.02775 × 91 / 360) = 1.00701458

USD interest factor = 1 + (0.04320 × 91 / 360) = 1.01092000

**Step 2 — Borrow the present value of the receivable:**

EUR borrowing = €12,000,000 / 1.00701458

= **€11,916,411.34**

**Step 3 — Convert borrowed euros into dollars:**

USD conversion = €11,916,411.34 × 1.1052

= **$13,170,017.81**

**Step 4 — Invest dollars until settlement:**

USD proceeds = $13,170,017.81 × 1.01092000

= **$13,313,834.41**

The money-market hedge therefore produces approximately $13.31 million in fixed USD proceeds, matching Muse and Excel.

### Calculation 3: EUR Put Hedge

The EUR put option protects the receivable against depreciation while preserving the opportunity to benefit from euro appreciation.

**Step 1 — Calculate the initial put premium:**

Put premium = €12,000,000 × 0.0147

= **$176,400.00**

**Step 2 — Finance the premium to settlement:**

Premium at maturity = $176,400 × (1 + 0.04320 × 91 / 360)

= **$178,326.29**

**Step 3 — Calculate the minimum gross proceeds:**

Minimum gross proceeds = €12,000,000 × 1.1052

= **$13,262,400.00**

**Step 4 — Subtract the financed premium:**

Net put floor = $13,262,400.00 − $178,326.29

= **$13,084,073.71**

This matches the put hedge floor calculated independently by Muse and reported in Excel.

### Hand-Verification Conclusion

All three hand calculations reproduce the independent AI and Excel results within normal rounding. The agreement supports the arithmetic consistency of the model, although it does not resolve the outstanding market-data limitations or the discrepancy between the assigned forward rate and the CIP-implied forward rate.

## 4. Future Exchange-Rate Scenario Comparison

To evaluate how the hedging strategies perform under different exchange-rate conditions, I compared three settlement spot rates representing a 5% euro depreciation, no change, and a 5% euro appreciation relative to the current spot rate of 1.1052 USD/EUR.

| Future spot rate (USD/EUR) | Unhedged proceeds | Forward hedge | Money-market hedge | EUR put hedge (net) |
|---|---:|---:|---:|---:|
| 1.04994 (−5%) | $12,599,280 | $13,983,600 | $13,313,834 | $13,084,074 |
| 1.10520 (0%) | $13,262,400 | $13,983,600 | $13,313,834 | $13,084,074 |
| 1.16046 (+5%) | $13,925,520 | $13,983,600 | $13,313,834 | $13,747,194 |

The unhedged position changes directly with the future exchange rate, creating uncertainty about the amount of USD the company will receive.

The forward hedge provides fixed proceeds of $13,983,600 regardless of the settlement spot rate. Under the assigned scenario assumptions, it produces the highest proceeds in all three cases.

The money-market hedge also eliminates exchange-rate uncertainty, producing approximately $13,313,834 at settlement. However, its proceeds are lower than the forward hedge under the assigned forward quote.

The EUR put hedge provides a minimum of approximately $13,084,074 after financing the premium. When the euro appreciates above the strike price, the company can allow the option to expire and benefit from the higher exchange rate, less the financed premium.

**Scenario conclusion:** The forward hedge performs best across the three tested exchange rates. However, this comparison depends heavily on the assigned forward rate of 1.1653 USD/EUR, which has not been independently verified as an executable bank quote.

## 5. Documentation Gaps Identified by Muse

Although Muse reproduced the main hedge calculations, its independent review identified several areas where my documentation could be clearer.

1. **Forward-rate verification:** The assigned forward rate of 1.1653 USD/EUR is substantially higher than the CIP-implied rate of approximately 1.109486. A contemporaneous bank requote is needed before using the forward rate for an actual transaction.

2. **Option strike consistency:** The Stage 2 specification references an earlier put strike of 1.1188, while the updated Stage 4 memo uses an assumed at-the-money strike of 1.1052. The documentation should explicitly explain that the strike was updated with the spot-rate assumption.

3. **Interest-rate limitations:** The 3-month U.S. Treasury yield and 3-month EURIBOR are benchmark proxies, not necessarily the rates the company could obtain for borrowing or investing. Actual financing rates, credit spreads, and transaction costs could change the money-market hedge outcome.

4. **Option assumptions:** The put and call premiums are assigned scenario values rather than independently verified market quotes. The documents also do not establish the option exercise style or confirm a 91-day expiration date.

5. **Premium-financing terminology:** The memo describes $13,086,000 as put proceeds before financing. More precisely, that amount is after deducting the initial $176,400 premium but before accounting for the additional $1,926.29 financing cost.

6. **Date documentation:** The memo is dated November 15, 2026, but includes rate updates retrieved November 18, 2026. This reflects a later revision and should be clearly identified. The exact settlement calendar date should also be confirmed.

7. **Company risk considerations:** The documents do not specify the company's risk tolerance, hedging policy, counterparty credit requirements, or treatment of a delayed or unpaid receivable. These factors could affect the final hedging decision.

These findings show that an independent AI review can identify documentation gaps even when its numerical calculations agree with the workbook. The results also reinforce the importance of distinguishing an internally consistent financial model from a hedge that could actually be executed under current market conditions.

## 6. Final Validation Assessment and Recommended Improvements

The independent Muse analysis successfully reproduced the main hedge calculations from my Stage 4 Excel workbook. The forward hedge, money-market hedge, put hedge, and covered-interest-parity calculations matched within normal rounding. I also independently verified the forward, money-market, and put hedge calculations by hand.

This gives me confidence that the model's core calculations are internally consistent and that another reader can reproduce the results using my specification and market-data memo without access to my original Excel workbook.

However, the independent review also showed that correct calculations do not necessarily mean every assumption is realistic or fully documented. The largest concern is the assigned forward rate of 1.1653 USD/EUR, which produces substantially higher proceeds than the CIP-implied forward rate. Until an executable bank quote is obtained, I cannot assume that the company could actually lock in those proceeds.

Based on Muse's findings, I would make the following improvements before using the model for an actual financial decision:

- Clarify which Stage 4 inputs supersede the original Stage 2 assumptions, especially the option strike prices.
- Obtain an executable forward quote and company-specific borrowing and investing rates.
- Verify option premiums, expiration dates, and exercise terms.
- Clearly distinguish the initial option premium from its additional financing cost.
- Record the original memo date and subsequent revision dates separately.
- Incorporate counterparty, payment-timing, transaction-cost, and company risk-policy considerations.

**Overall assessment:** The model passes the numerical validation performed in Stage 5, but the underlying market assumptions require additional verification before the results can support a real transaction.

For the assigned academic scenario, the forward hedge remains the preferred strategy because it provides the highest and most predictable USD proceeds across the tested exchange rates. For an actual transaction, I would first request a current bank forward quote and reevaluate the alternatives using executable market terms.

The independent AI test demonstrated that my documentation was sufficient to reproduce the primary calculations, while also identifying assumptions and limitations that should be clarified in future revisions.

## 7. Specification Retrospective

Completing the independent Muse analysis helped me understand how important clear instructions and consistent assumptions are when building a financial model. My goal was to see whether another AI could reproduce my FX hedging calculations using only my Stage 2 specification and Stage 4 market-data memo, without having access to my Excel workbook.

Overall, Muse successfully reproduced the main results, including the forward hedge, money-market hedge, and EUR put hedge. This showed me that my specification provided enough information for another reader to follow the calculations. However, the independent test also identified areas where my documentation could have been more specific.

One issue was the difference between the original Stage 2 assumptions and the updated Stage 4 market data. For example, the option strike changed from 1.1188 to 1.1052 USD/EUR. Although Muse correctly used the updated value, I realized that my specification should explicitly state which inputs take priority when newer market observations become available.

Another important finding was the difference between my assigned forward rate and the rate implied by covered interest parity. Muse calculated the difference correctly, but the documents did not establish whether the assigned forward was an executable quote. This made me realize that a model can produce mathematically correct results while still relying on assumptions that would need verification before making a real financial decision.

Muse also identified missing details about option expiration, exercise terms, company-specific borrowing rates, and the financing treatment of option premiums. These were not major calculation errors, but they showed where another analyst might have to interpret or assume information that should have been clearly documented.

If I were to create a second version of my specification, I would add a clear input-priority rule, identify which market values are verified versus assumed, define the option terms, and require an explicit comparison between the quoted and CIP-implied forward rates. I would also clarify the treatment of premium financing and include checks for missing or inconsistent data.

The biggest lesson I learned from this stage is that **a reliable financial model depends on both accurate calculations and clear documentation**. Independent AI verification helped confirm my arithmetic while showing me how I could make my specification more transparent, reproducible, and useful for financial decision-making.
