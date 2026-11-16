# Stage 4 — Transmission-Parts FX Hedging: Market Data and Model Verification

**Date:** November 15, 2026  
**Scenario:** U.S. transmission-parts supplier  
**Exposure:** €12,000,000 receivable in 91 days  
**Objective:** Verify market inputs, cross-check hedge calculations, and document any discrepancies.

## 1. Market Data Verification

For Stage 4, I updated my Excel workbook using market reference data dated November 13, 2026, and retrieved November 15, 2026. I recorded the sources and verification notes directly in the Inputs worksheet.

| Input | Value | Source / Explanation |
|---|---|---|
| Foreign-currency receivable | €12,000,000 | Assigned scenario |
| Spot exchange rate | 1.1052 USD/EUR | ECB EUR/USD reference rate, Nov. 13, 2026 |
| Forward exchange rate | 1.1653 USD/EUR | Assigned 91-day forward quote |
| USD interest rate | 4.650% | U.S. Treasury 1-year par yield proxy |
| EUR interest rate | 3.328% | 12-month EURIBOR reference-rate proxy |
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
| EUR borrowed today | €11,899,892.81 |
| EUR converted to USD | $13,151,761.54 |
| Money-market hedge proceeds | $13,306,349.53 |
| CIP-implied forward rate | 1.108862 USD/EUR |
| Put hedge net proceeds at base spot | $13,083,926.57 |

The forward hedge produces the highest USD proceeds among the hedging strategies at the base spot rate. It also provides a fixed dollar amount regardless of the ending exchange rate.

## 3. Interest-Rate-Parity Assessment

The assigned forward rate is **1.165300 USD/EUR**, while the covered-interest-parity-implied forward rate is approximately **1.108862 USD/EUR**.

This creates a difference of approximately **0.056438 USD/EUR**, equivalent to about **$677,250 on the €12 million exposure**, or **4.84% relative to the quoted forward rate**.

The difference exceeds the workbook's 0.05% tolerance and remains flagged as **NON-PARITY**.

I retained the assigned forward quote rather than replacing it with the theoretical rate. The discrepancy may reflect the use of reference-rate proxies, differences in rate tenors or market conventions, or an assigned forward quote that does not represent a contemporaneous executable market price. It should not automatically be interpreted as an arbitrage opportunity.

## 4. FX Hedging Lab Cross-Check

I entered the updated scenario inputs into the course FX Hedging Lab and compared its outputs with my Excel workbook.

The following results matched within normal display rounding:

- Forward hedge proceeds: $13,983,600.
- Money-market EUR borrowing: approximately €11,899,893.
- Spot conversion: approximately $13,151,762.
- Money-market USD proceeds: approximately $13,306,350.
- CIP-implied forward rate: approximately 1.1089 USD/EUR.

The FX Lab calculated put proceeds of approximately **$13,086,000**, compared with **$13,083,926.57** in Excel.

The difference of approximately **$2,073.43** is attributable to the workbook financing the put premium for 91 days at the USD interest rate, whereas the lab's displayed calculation deducts the premium without the same financing adjustment.

I retained the workbook's financed-premium convention and documented the difference rather than changing the model solely to match the lab.

## 5. Sensitivity Analysis

The workbook recalculated 11 settlement-rate scenarios from −5% to +5% around the updated spot rate of 1.1052 USD/EUR.

Across this range:

- The forward hedge remains fixed at $13,983,600.
- The money-market hedge remains approximately $13,306,350.
- Unhedged proceeds increase as the euro strengthens.
- The put hedge provides a downside floor while preserving upside participation, less the financed premium.

The forward hedge generates the highest proceeds in all 11 tested scenarios. This result is specific to the assigned forward quote and the selected ±5% range; it does not establish that forwards always outperform options.

## 6. Workbook Controls and Documentation

I retained the Stage 3 workbook structure, including the named input ranges, hedge calculations, sensitivity analysis, and Notes & Assumptions checks.

The workbook also contains formula-count reconciliation controls and an audit trail for the market data and parity discrepancy.

The formula-count checks help identify missing or overwritten formulas, but they do not independently prove that every formula is mathematically correct. The FX Lab comparison provides an additional calculation check.

## 7. Conclusion

Stage 4 confirmed that my workbook recalculates consistently after the market-reference inputs are updated. The FX Lab independently reproduced the main forward, money-market, and parity calculations.

Two issues remain explicitly documented: the substantial difference between the assigned forward quote and the CIP-implied rate, and the smaller put-proceeds difference caused by the premium-financing convention.

For this scenario, the forward hedge provides the highest and most predictable USD proceeds within the tested range. I retained the original forward quote and documented the limitations of the market-rate proxies so the analysis remains transparent and reproducible.

## 8. Market Data Sources and Limitations

The following sources were used to document the market reference inputs for Stage 4. The market observations are dated November 13, 2026, and were retrieved on November 15, 2026.

| Input | Reference Source | Website |
|---|---|---|
| EUR/USD spot exchange rate | European Central Bank (ECB) | https://www.ecb.europa.eu/stats/policy_and_exchange_rates/euro_reference_exchange_rates/ |
| USD interest rate | U.S. Department of the Treasury | https://home.treasury.gov/resource-center/data-chart-center/interest-rates |
| EUR interest rate | EURIBOR reference-rate information | https://www.euribor-rates.eu/en/current-euribor-rates/ |
| Forward exchange rate | Assigned course scenario | No independently verified bank quote |
| Put and call premiums | Assigned course scenario | Assumed premiums; not live option quotes |

**Rate selection:** The 1-year U.S. Treasury yield and 12-month EURIBOR were selected as publicly available USD and EUR interest-rate benchmarks. However, they are not equivalent to executable 91-day borrowing and lending rates.

**Forward-rate limitation:** The assigned forward rate of 1.1653 USD/EUR was retained for consistency with the original scenario. A contemporaneous bank requote has not been obtained. Therefore, the forward-rate input should not be interpreted as a verified executable market quote.

**Verification limitation:** These links identify the reference sources, but the precise retrieval time was not recorded. The market observations and rates should be independently checked against the dated source records before treating them as fully verified.
