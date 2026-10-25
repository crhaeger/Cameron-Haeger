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
