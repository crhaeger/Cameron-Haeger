# AI Prompt Log

This file documents meaningful AI-assisted work completed for this portfolio.

For each meaningful AI session, I will record what I asked for help with, what the AI suggested, any issues I noticed, and how I reviewed or changed the output.

## Entries

### October 3, 2026 — GitHub Portfolio Setup Review

**What I asked:**  
I asked ChatGPT to help me understand the onboarding checklist and review whether my GitHub portfolio files were set up correctly.

**What the AI suggested:**  
ChatGPT helped me review the requirements for README.md, RESUME.md, AGENTS.md, CLAUDE.md, .gitignore, and prompt-log.md and explained what each file is used for.

**What went wrong or needed correction:**  
Some of the initial instructions did not exactly match the course onboarding checklist. After reviewing the checklist, I noticed that prompt-log.md needed a first entry and that the AI disclosure needed to be included in my README.md.

**How I reviewed or corrected it:**  
I compared the suggestions with the course onboarding checklist and corrected the files to match the course requirements.



## October 25, 2026 – Stage 2 FX Hedging Model Specification

**AI Prompt:** I asked ChatGPT to help develop a 2–3-page FX hedging model specification for a €12 million receivable due in 91 days, including required inputs, workbook structure, formulas, sensitivity analysis, and validation rules.

**AI Draft:** ChatGPT generated an initial specification exceeding 200 lines, covering eight required sections and the calculations for forward, money-market, and currency-option strategies.

**Human Correction:** I reviewed the draft and requested a shorter, more organized version that preserved the ten named inputs, required formulas, and validation checks. I also corrected the GitHub file location to `capabilities/fx-hedging/spec.md` and checked the Markdown formatting.

**Final Result:** The revised specification is approximately 121 lines and provides a clearer blueprint for building and testing the Excel hedging model in Stage 3.

### Additional October 25, 2026 – Stage 2 Template Review and Corrections

**AI Draft:** ChatGPT initially helped create the FX hedging specification without using the professor's template.

**Human Review:** I compared the draft against the provided `template-spec.md` and identified differences in option premium treatment, receivable versus payable hedging, validation checks, and required outputs.

**Corrections Made:** I revised the formulas to account for the future value of option premiums, clarified that EUR puts hedge receivables while EUR calls hedge payables, strengthened the validation rules, and added base-case outputs and model improvement notes.

**Result:** The revised specification better aligns with the professor's template and provides a more complete foundation for building the Excel model in Stage 3.

## November 11, 2026 — Stage 3 AI-Assisted Build & Audit

**AI Prompt:** I asked ChatGPT to build an Excel FX hedging model using my committed Stage 2 specification. The workbook needed ten named inputs, eight worksheets, formulas for the forward, money-market, and currency-option hedges, an 11-scenario sensitivity analysis, a chart, and validation checks.

**AI Draft:** ChatGPT generated an initial `model.xlsx` workbook using the provisional exchange rates, interest rates, and option premiums from my specification.

**Human Review:** I opened the workbook in Excel and reviewed the calculations, sensitivity table, chart, and validation results. I manually inspected formulas for the forward hedge, all three money-market hedge steps, and the put and call options. I also reviewed the workbook's validation logic to identify weaknesses.

### Audit Correction 1 — Formula Integrity

**Issue Identified:** The original validation used `ISNUMBER`, which confirmed that selected cells contained numerical values but did not verify that they were calculated using formulas.

**Human Correction:** I replaced the original check with `ISFORMULA` to verify that three key hedge outputs contained Excel formulas.

**Result:** The updated check returned `OK`. I saved the corrected workbook as `model-audit-fix1.xlsx` and uploaded it to GitHub in a separate commit.

### Audit Correction 2 — Put Option Validation

**Issue Identified:** The original put payoff validation only referenced a calculated value from another worksheet. It did not independently check downside protection or upside participation.

**Human Correction:** I updated the validation to compare the put floor with its expected payoff and check the sensitivity scenarios above and below the strike.

**Result:** The improved validation returned `PASS`. I saved the updated workbook as `model-audit-fix2.xlsx` and committed it separately.

### Audit Correction 3 — Interest-Rate Parity Warning

**Issue Identified:** The workbook flagged a mismatch between the quoted forward rate and the implied forward rate, but its written explanation contained static numbers.

**Human Correction:** I replaced the static explanation with an Excel formula that automatically displays the quoted forward rate, implied forward rate, and percentage deviation.

**Result:** The formula displayed a quoted forward rate of 1.165300, an implied forward rate of approximately 1.123165, and a deviation of approximately 3.62%. I retained the warning because the difference exceeded the 0.05% tolerance. I saved `model-audit-fix3.xlsx` and committed the correction separately.

### Final Stage 3 Result

After completing the audit, I saved the final corrected workbook as `model.xlsx` and uploaded it to `capabilities/fx-hedging/`. I also documented the findings and verification results in `analysis/2026-11-11-transmission-parts-build-audit-analysis.md`.

**What I Learned:** AI helped me build the initial financial model, but reviewing the formulas and validation checks myself was important. I learned that a model can display correct results while still having weaknesses in how it tests those results. The audit improved the workbook's reliability and helped me better understand the calculations.

## November 15, 2026 — Stage 4 Market Data Verification

**AI assistance:** Used ChatGPT to help organize the market data verification process, compare Excel hedge calculations with the FX Hedging Lab, explain the covered-interest-parity discrepancy, and draft the Stage 4 verification memo.

**My work:** Updated the Excel workbook with market reference inputs, documented sources and retrieval dates, checked the forward and money-market hedge calculations, compared sensitivity results with the FX Lab, and reviewed the final memo before committing it to GitHub.

**Verification:** Confirmed the main calculations matched the FX Lab within rounding. Documented the 4.84% forward parity discrepancy and the $2,073.43 put-premium financing difference. Retained the assigned forward quote and documented the remaining limitations.

## November 18, 2026 — Stage 5 Independent Validation and CFO Decision Memo
 
**AI Tools Used:** Muse and ChatGPT  
**Purpose:** Independently validate the FX hedging model, compare results with Excel, and prepare a financial recommendation.

### Prompt 1: Independent Hedge Verification (Muse)

**Prompt submitted:**

Using only the two attached documents (my Stage 2 FX hedging specification and Stage 4 market-data memo), independently calculate the hedge outcomes for the company's EUR receivable.

Calculate the unhedged position, forward hedge, money-market hedge, EUR put hedge, and EUR call comparison where applicable. Evaluate the outcomes at 2–3 future spot exchange rates, show your calculations, and recommend the most appropriate hedging strategy.

Identify any missing information or ambiguities in the documents. Do not assume access to my Excel workbook or any previous calculations.

**Result:** Muse independently calculated the hedge outcomes using the Stage 4 inputs. Its results matched the main Excel calculations, including the $13,983,600 forward proceeds, $13,313,834.41 money-market proceeds, and $13,084,073.71 minimum net put proceeds.

**Output saved:** `analysis/2026-11-18-transmission-parts-muse-independent-output.md`

### Prompt 2: Validation Analysis and Hand Calculations (ChatGPT)

**Task:** Help organize the independent Muse results into a validation report, compare them with the Excel workbook, and document at least three manually verified hedge calculations.

**Result:** Prepared comparison tables, verified the forward, money-market, and put calculations, evaluated three future exchange-rate scenarios, and documented the model's assumptions and limitations.

**Output saved:** `analysis/2026-11-18-transmission-parts-validation-analysis.md`

### Prompt 3: CFO Decision Memo (ChatGPT)

**Task:** Help prepare a 2–4 page CFO decision memo summarizing the exposure, hedge outcomes, sensitivity analysis, recommendation, and executive justification.

**Result:** Developed a memo recommending the forward hedge under the assigned scenario assumptions, subject to verifying an executable forward quote. The memo also addressed the approximately $669,766 difference between the assigned forward proceeds and the CIP-implied alternative.

**Output saved:** `docs/decisions/2026-11-18-transmission-parts-hedge-decision-memo.md`

### Prompt 4: Specification Retrospective (ChatGPT)

**Task:** Reflect on the independent AI validation, identify ambiguities in the Stage 2 specification, and recommend improvements for a future version.

**Result:** Identified opportunities to clarify input precedence, distinguish verified quotes from assumptions, define option terms, and improve documentation of premium financing and covered interest parity.

**Output saved:** Section 7 of `analysis/2026-11-18-transmission-parts-validation-analysis.md`

### Overall AI Use and Verification

AI was used to independently calculate hedge outcomes, organize financial comparisons, and assist with writing and reviewing the final reports. The results were compared with the Excel model and supported by separate hand calculations.

The final recommendation distinguishes between the assigned academic scenario and an actual transaction requiring verified market quotes. The independent AI output was preserved to make the validation process transparent and reproducible.
