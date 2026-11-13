# Stage 3 — AI-Assisted Build & Audit Analysis

**Project:** FX Hedging — Scenario 11: Transmission-Parts  
**Date:** November 11, 2026  
**Prepared by:** Cameron Haeger  
**AI Tool Used:** ChatGPT (GPT-6)

## 1. Overview

For Stage 3, I used AI assistance to build an Excel hedging model based on my Stage 2 specification. The model evaluates a U.S. transmission-parts supplier expecting to receive €12 million from a Slovak car-assembly plant in 91 days.

The workbook compares four strategies: remaining unhedged, entering a forward contract, using a money-market hedge, and purchasing a EUR put option. It also includes a EUR call option as a reference for payable exposures.

After generating the workbook, I manually reviewed the calculations, tested formulas, and examined the validation checks. I identified three areas where the model could be improved.

## 2. Audit Findings and Corrections

### Finding 1: Incomplete Formula-Integrity Validation

**Issue:** The original formula-integrity check used `ISNUMBER` to verify that three calculated outputs contained numerical values. However, this did not confirm that the cells actually contained Excel formulas. A hardcoded number could still pass the validation.

**Correction:** I replaced the original check with `ISFORMULA` to verify that the forward hedge, money-market hedge, and put option outputs were calculated using formulas.

**Verification:** After updating the validation, the workbook continued displaying `OK`. I also manually inspected the formulas for the forward hedge and all three money-market hedge calculations.

**Limitation:** This improvement verifies three key output cells rather than every calculated cell in the workbook.

**Additional Workbook-Wide Audit:** To address the limitation of checking only three cells, I expanded the formula-integrity review using Excel's `SUMPRODUCT` and `ISFORMULA` functions across the original calculation ranges. The audit identified 4 formulas in Forward Hedge, 7 in Money-Market Hedge, 8 in Options Hedge, 110 in Sensitivity, and 19 in Notes & Assumptions, totaling 148 formulas. The Inputs and Cover worksheets contained no formulas in the inspected ranges.

**Verification:** The results are documented in the Notes & Assumptions worksheet, with the reconciled formula count in B34 and a PASS status in B41. This confirms that the formula count matches the expected 148. However, the check verifies formula presence, not the mathematical accuracy of every formula. A complete integrity review would also compare formulas against expected calculations and identify incorrect references or unexpected changes.

### Finding 2: Insufficient Put Option Payoff Validation

**Issue:** The original put payoff check displayed a value linked from the Options Hedge worksheet but did not independently verify the option's behavior across the sensitivity scenarios.

**Correction:** I strengthened the validation formula to check that the put's minimum proceeds matched the strike payoff after accounting for the premium. I also added checks to confirm that downside scenarios did not fall below the protected floor and that upside scenarios generated proceeds above the floor.

**Verification:** After updating the formula, the validation returned `PASS`. The sensitivity analysis also displayed the expected downside protection and upside participation.

### Finding 3: Static Interest-Rate Parity Explanation

**Issue:** The model identified a significant difference between the quoted forward rate and the forward rate implied by covered interest-rate parity. However, the written explanation was static and would not automatically update when the underlying assumptions changed.

**Correction:** I replaced the static explanation with an Excel formula that dynamically displays the quoted forward rate, implied forward rate, and percentage deviation.

**Verification:** The updated explanation displayed a quoted forward rate of 1.165300, an implied rate of approximately 1.123165, and a deviation of approximately 3.62%.

The discrepancy exceeds the 0.05% tolerance. I retained the provisional inputs rather than changing them to force the model to pass. The rates and quotes will require further verification in Stage 4.

## 3. Model Testing and Results

I reviewed the workbook's calculations against the Stage 2 specification.

| Calculation | Expected Result | Audit Result |
|---|---:|---|
| Forward hedge | $13,983,600.00 | Verified |
| EUR borrowing | €11,919,672.66 | Verified |
| USD proceeds from money-market hedge | $13,477,984.97 | Verified |
| EUR put net proceeds at strike | $13,247,318.30 | Verified |
| EUR call USD cost at strike | $13,666,947.33 | Verified |
| Sensitivity scenarios | 11 scenarios | Displayed |
| Interest-rate parity | Within 0.05% when inputs are consistent | Warning retained |

The forward and money-market hedge results remained constant across the sensitivity scenarios. The put option provided a minimum USD proceeds level while allowing additional proceeds if the euro appreciated.

The call option was treated separately because the company's exposure is a EUR receivable rather than a payable.

## 4. AI-Assisted Development and Human Review

AI helped translate the Stage 2 specification into a working Excel model, organize the worksheets, and develop formulas for the hedging strategies and validation checks.

My role was to review the outputs rather than assume the AI-generated workbook was correct. I checked the underlying formulas, identified weaknesses in the validation logic, and implemented corrections.

The audit showed that a workbook can produce correct numerical results while still having limitations in its validation and documentation. Strengthening those checks made the model easier to review and more reliable for future updates.

## 5. Limitations and Next Steps

The workbook currently uses provisional market inputs, including the spot exchange rate, interest rates, and option strikes. These are not confirmed executable market quotes.

The covered interest-rate parity discrepancy remains unresolved and requires investigation during Stage 4. The workbook also excludes transaction fees, bid-ask spreads, and counterparty risk.

Before making a final recommendation to the CFO, I will verify the market inputs, review the effect of updated assumptions, and confirm that the preferred hedge provides an appropriate balance of cash-flow certainty, cost, and upside potential.

## 6. Conclusion

Stage 3 helped me understand the importance of auditing AI-generated financial models. Although the initial workbook produced the expected hedge calculations, my review identified opportunities to strengthen formula validation, option payoff testing, and interest-rate parity documentation.

By making these corrections, I improved the transparency and reliability of the model while preserving the assumptions that still require verification. The workbook now provides a foundation for Stage 4 market-data validation and the final hedging recommendation.
