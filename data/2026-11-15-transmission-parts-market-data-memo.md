# Stage 4 — Transmission-Parts FX Hedging: Market Data and Model Verification

**Date:** November 15, 2026  
**Scenario:** U.S. transmission-parts supplier  
**Exposure:** €12,000,000 receivable in 91 days  
**Objective:** Verify market inputs, cross-check hedge calculations, and document any discrepancies.

## 1. Market Data Verification

For Stage 4, I updated my Excel workbook using market reference data dated November 13, 2026. The ECB spot rate was retrieved November 15, 2026, and the updated 3-month USD Treasury and EURIBOR rates were recorded as retrieved November 18, 2026. I documented the sources and verification notes in the Inputs worksheet. The 3-month rates were selected because their maturity more closely matches the company's 91-day receivable than the previously used 12-month benchmarks.

| Input | Value | Source / Explanation |
|---|---|---|
| Foreign-currency receivable | €12,000,000 | Assigned scenario |
| Spot exchange rate | 1.1052 USD/EUR | ECB EUR/USD reference rate, Nov. 13, 2026 |
| Forward exchange rate | 1.1653 USD/EUR | Assigned 91-day forward quote |
| USD interest rate | 4.320% | U.S. Treasury 3-month yield proxy, Nov. 13, 2026; retrieved Nov. 18, 2026 |
| EUR interest rate | 2.775% | 3-month EURIBOR benchmark proxy, Nov. 13, 2026; retrieved Nov. 18, 2026 |
| Put and call strikes | 1.1052 USD/EUR | Assumed at-the-money strikes |
| Put premium | 0.0147 USD/EUR | Assigned scenario assumption |
| Call premium | 0.0199 USD/EUR | Assigned scenario assumption |
| Settlement period | 91 days | Assigned scenario |

The interest rates are reference-rate proxies rather than actual borrowing or lending quotes available to the company. The option strikes are assumed at-the-money values, not executable market quotes. I retained the assigned forward rate and option premiums to preserve the original scenario.

## 2. Hedge Calculation Verification

After updating the named input cells, I confirmed that the workbook recalculated the hedge strategies using the new market data.

| Calculation | Excel result |
|---|---:|
| Forward hedge proceeds | $13,983,600.00 |
| EUR borrowed today | €11,916,411.34 |
| EUR converted to USD | $13,170,017.81 |
| Money-market hedge proceeds | $13,313,834.41 |
| CIP-implied forward rate | 1.109486 USD/EUR |
| Put hedge net proceeds at base spot | $13,084,073.71 |

The forward hedge produces the highest USD proceeds among the hedging strategies at the base spot rate. It also provides a fixed dollar amount regardless of the ending exchange rate.

## 3. Interest-Rate-Parity Assessment

The assigned forward rate is **1.165300 USD/EUR**, while the covered-interest-parity-implied forward rate is approximately **1.109486 USD/EUR**, using the updated 3-month interest-rate benchmarks.

This creates a difference of approximately **0.055814 USD/EUR**, equivalent to about **$669,765 on the €12 million exposure**, or **4.79% relative to the assigned forward rate**.

The difference exceeds the workbook's 0.05% tolerance and remains flagged as **NON-PARITY**.

I retained the assigned forward quote rather than replacing it with the theoretical rate. Although the updated 3-month benchmarks better match the company's 91-day exposure, they are still reference-rate proxies rather than executable bank borrowing and lending quotes. The assigned forward quote has also not been independently requoted. Therefore, the remaining discrepancy should not automatically be interpreted as an arbitrage opportunity.

## 4. FX Hedging Lab Cross-Check

I reran the course FX Hedging Lab using the updated 3-month USD interest rate of 4.320% and 3-month EUR interest rate of 2.775%, keeping the original scenario inputs unchanged.

The following calculations matched my Excel workbook within normal display rounding:

- Forward hedge proceeds: $13,983,600.
- Money-market EUR borrowing: approximately €11,916,411.
- Spot conversion: approximately $13,170,018.
- Money-market USD proceeds: approximately $13,313,834.
- CIP-implied forward rate: approximately 1.1095 USD/EUR.

The FX Lab also identified a parity gap of approximately $669,766, consistent with the workbook's approximately 4.79% forward-rate deviation. This discrepancy remains flagged because the assigned forward quote is not independently verified against executable market rates.

Using the updated USD interest rate, my workbook calculates put hedge net proceeds of $13,084,073.71. The corresponding put proceeds before financing the premium are $13,086,000, producing a $1,926.29 difference attributable to financing the put premium over 91 days at 4.320% annual interest.

The put-premium financing explanation is based on my workbook calculation. The updated FX Lab screenshot confirms the forward, money-market, and parity results, but does not display the put result for an independent comparison.

I retained the financed-premium convention and documented the difference rather than changing the workbook formulas solely to match the lab.

## 5. Sensitivity Analysis

The workbook recalculated 11 settlement-rate scenarios from −5% to +5% around the unchanged spot rate of 1.1052 USD/EUR.

Using the updated 3-month interest-rate benchmarks, the forward hedge provides fixed proceeds of $13,983,600 across all scenarios, while the money-market hedge provides fixed proceeds of $13,313,834.41.

The put hedge provides a minimum of $13,084,073.71 after financing the premium, while allowing additional upside if the euro appreciates.

Within the tested −5% to +5% range, the forward hedge continues to produce the highest USD proceeds. Although the forward hedge performs best under these assumptions, its quoted rate remains subject to the unresolved parity discrepancy.

## 6. Workbook Controls and Documentation

I retained the Stage 3 workbook structure, including the named input ranges, hedge calculations, sensitivity analysis, and Notes & Assumptions checks.

The workbook also contains formula-count reconciliation controls and an audit trail for the market data and parity discrepancy.

The formula-count checks help identify missing or overwritten formulas, but they do not independently prove that every formula is mathematically correct. The FX Lab comparison provides an additional calculation check.

## 7. Conclusion

Stage 4 confirmed that my workbook recalculates consistently after updating the interest rates to 3-month benchmarks that better match the company's 91-day exposure. The FX Hedging Lab independently reproduced the main forward, money-market, and interest-rate-parity calculations.

The updated results show that the forward hedge provides fixed proceeds of $13,983,600, compared with $13,313,834.41 from the money-market hedge and minimum put hedge proceeds of $13,084,073.71.

The forward hedge continues to provide the highest and most predictable USD proceeds within the tested scenarios. However, the assigned forward rate remains substantially higher than the CIP-implied rate, with a discrepancy of approximately 4.79%.

Although the updated interest rates better match the hedging period, they remain benchmark proxies rather than executable borrowing and lending quotes. I retained the assigned forward rate and documented this limitation, along with the put-premium financing convention, to keep my analysis transparent and reproducible.

## 8. Market Data Sources and Limitations

The following sources were used to document the market reference inputs for Stage 4. The market observations are dated November 13, 2026, and were retrieved on November 15, 2026.

| Input | Reference Source | Website |
|---|---|---|
| EUR/USD spot exchange rate | European Central Bank (ECB) | https://www.ecb.europa.eu/stats/policy_and_exchange_rates/euro_reference_exchange_rates/ |
| USD interest rate | U.S. Department of the Treasury | https://home.treasury.gov/resource-center/data-chart-center/interest-rates |
| EUR interest rate | EURIBOR reference-rate information | https://www.euribor-rates.eu/en/current-euribor-rates/ |
| Forward exchange rate | Assigned course scenario | No independently verified bank quote |
| Put and call premiums | Assigned course scenario | Assumed premiums; not live option quotes |

**Rate selection:** I updated the USD interest rate to the 3-month U.S. Treasury yield of 4.320% and the EUR interest rate to the 3-month EURIBOR benchmark of 2.775%, using observations dated November 13, 2026, retrieved November 18, 2026. I selected these maturities because three months more closely matches the company's 91-day receivable than the previously used 1-year benchmarks. However, these rates are still publicly available reference-rate proxies rather than executable 91-day borrowing and lending quotes. The remaining maturity and market-rate differences are limitations of the analysis.

**Forward-rate limitation:** The assigned forward rate of 1.1653 USD/EUR was retained for consistency with the original scenario. A contemporaneous bank requote has not been obtained. Therefore, the forward-rate input should not be interpreted as a verified executable market quote.

**Verification limitation:** These links identify the reference sources, but the precise retrieval time was not recorded. The market observations and rates should be independently checked against the dated source records before treating them as fully verified.
