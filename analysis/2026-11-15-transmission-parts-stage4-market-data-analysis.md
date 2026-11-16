# Stage 4 — Transmission-Parts FX Hedging: Market Data and Model Verification

**Date:** November 15, 2026  
**Scenario:** U.S. transmission-parts supplier  
**Exposure:** €12,000,000 receivable in 91 days  
**Objective:** Verify market inputs, cross-check hedge calculations, and document discrepancies.

## 1. Market Data Verification

For Stage 4, I updated the Excel workbook using market reference data dated November 13, 2026. I documented the sources and retrieval dates directly in the Inputs worksheet.

| Input | Value | Source / Explanation |
|---|---:|---|
| Foreign-currency receivable | €12,000,000 | Assigned scenario |
| Spot exchange rate | 1.1052 USD/EUR | ECB reference rate, Nov. 13, 2026 |
| Forward exchange rate | 1.1653 USD/EUR | Assigned 91-day forward quote |
| USD interest rate | 4.650% | U.S. Treasury 1-year par yield proxy |
| EUR interest rate | 3.328% | 12-month EURIBOR reference-rate proxy |
| Put strike | 1.1052 USD/EUR | Assumed at-the-money strike |
| Call strike | 1.1052 USD/EUR | Assumed at-the-money strike |
| Put premium | 0.0147 USD/EUR | Assigned premium; independent verification pending |
| Call premium | 0.0199 USD/EUR | Assigned premium; independent verification pending |
| Settlement period | 91 days | Assigned scenario |

The spot rate and interest-rate benchmarks are reference data rather than executable company-specific quotes. The forward rate remains the assigned scenario quote, and the option strikes are assumptions rather than verified market option contracts.

## 2. Hedge Results and FX Lab Comparison

I entered the updated inputs into the course FX Hedging Lab and compared its outputs with my Excel model.

| Calculation | Excel workbook | FX Hedging Lab |
|---|---:|---:|
| Forward hedge proceeds | $13,983,600 | $13,983,600 |
| EUR borrowed today | €11,899,892.81 | Approximately €11,899,893 |
| USD converted today | $13,151,761.54 | Approximately $13,151,762 |
| Money-market hedge proceeds | $13,306,349.53 | Approximately $13,306,350 |
| CIP-implied forward rate | 1.108862 | Approximately 1.1089 |

The forward and money-market calculations agree with the FX Lab within displayed rounding differences. Both use the course convention of simple interest and ACT/360.

## 3. Put Option Cross-Check

The FX Lab reports approximately $13,086,000 in put proceeds at the floor, compared with $13,083,926.57 in my Excel workbook.

The difference of approximately $2,073.43 arises because my workbook finances the put premium to settlement using the USD interest rate, while the lab's displayed figure does not include the same financing adjustment.

I retained the financed-premium convention in my workbook and documented this difference rather than changing the formula simply to match the lab.

## 4. Covered Interest-Rate Parity Assessment

The quoted forward rate is 1.165300 USD/EUR, while the covered-interest-parity-implied forward rate is approximately 1.108862 USD/EUR.

This produces a discrepancy of approximately 0.056438 USD/EUR, equivalent to about $677,256 on the €12 million exposure, or approximately 4.84% relative to the quoted forward rate.

The difference exceeds the workbook's 0.05% tolerance.

The FX Lab independently reproduced the implied forward calculation. However, this does not establish that the market inputs are economically consistent. The comparison uses a scenario forward quote and reference interest rates with different maturities and potentially different market conventions.

I therefore retained the assigned forward quote, preserved the non-parity warning, and identified the mismatch as an unresolved issue requiring further review. I did not treat it as a verified arbitrage opportunity.

## 5. Sensitivity Analysis

I compared eleven possible settlement exchange rates, ranging from a 5% euro depreciation to a 5% appreciation, in 1% increments.

The forward hedge provides fixed proceeds of $13,983,600 in every scenario, while the money-market hedge provides approximately $13,306,350.

The unhedged strategy changes directly with the settlement exchange rate. The put hedge provides a minimum level of USD proceeds while preserving participation in favorable euro appreciation, less the financed premium.

Within the modeled ±5% range, the forward hedge produces the highest USD proceeds in all eleven scenarios.

## 6. Workbook Integrity and Remaining Limitations

The workbook includes named inputs, documented sources, validation checks, formula-count reconciliation, and color-coded inputs, assumptions, formulas, outputs, and warnings.

The formula-count audit reconciles 148 expected formulas across the workbook's designated calculation ranges. This verifies formula presence and coverage, but does not independently prove that every formula is mathematically correct.

Remaining limitations include:

- The forward quote is assigned rather than a contemporaneous executable market quote.
- Interest-rate inputs are reference-rate proxies rather than matched-maturity borrowing and lending quotes.
- Option premiums and strikes are not independently verified executable quotes.
- The covered-interest-parity discrepancy remains unresolved.
- The put-premium treatment differs slightly from the FX Lab's displayed convention.

## 7. Stage 4 Conclusion

Stage 4 improved the transparency and reliability of my hedging model by replacing provisional reference inputs, recording market-data sources, and comparing calculations against the FX Hedging Lab.

The calculations agree with the lab apart from the documented put-premium financing difference. The 4.84% parity discrepancy remains an important limitation.

Based on the modeled scenarios, the forward hedge provides the highest and most predictable USD proceeds. However, a final recommendation should distinguish the assigned scenario results from what could actually be executed in the market.
