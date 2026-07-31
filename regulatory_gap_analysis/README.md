
# Regulatory Gap Analysis — Introduction

**Skill file:** `RegulatoryGapAnalysis-SKILL.md`
**Tier:** 2 — augments a workflow to go further and detect new patterns. It runs as a structured, multi-step sequence rather than one single request, and works best with someone who already has a general sense of which regulations apply to their company
**Who it's for:** Environmental, Social and Governance (ESG) or legal/compliance teams who need to know, systematically, where their current disclosures fall short of what a regulation actually requires

---

## What this skill does

You upload what you already publish (a sustainability report, climate disclosure, CDP submission, and so on) and tell Claude which regulations you need to check against. It works through your documents requirement-by-requirement and produces a **gap register** — a table showing, for every requirement, whether you're compliant, partially compliant, or silent, plus what it would take to close each gap.

## Why it matters

Companies today can face several overlapping mandatory reporting regimes at once — for example, European Union rules, U.S. state rules, and international investor-facing standards — each phasing in on a different timeline. Doing this mapping by hand typically takes a consulting team 6–12 weeks. This skill compresses that to a couple of hours of active review time and produces something structured enough to hand to legal or import into a compliance tracking tool.

## Which regulations it covers

- **Corporate Sustainability Reporting Directive (CSRD) / European Sustainability Reporting Standards (ESRS)** — mandatory for large European Union (EU) companies and non-EU companies with meaningful EU revenue
- **International Sustainability Standards Board (ISSB) IFRS S1 and S2** — investor-facing global standards, adopted in 20+ jurisdictions
- **California SB 253 and SB 261** — mandatory emissions and climate-risk disclosure for companies doing business in California above certain revenue thresholds, regardless of where they're headquartered
- **Taskforce on Nature-related Financial Disclosures (TNFD)** — voluntary today, but increasingly the reference methodology for EU nature-related requirements
- **U.S. Securities and Exchange Commission (SEC) Climate Rules** — treated here as **preparatory** rather than an active deadline, since these rules are currently held up in litigation and their final form is uncertain
- Existing **Global Reporting Initiative (GRI)**, **Task Force on Climate-related Financial Disclosures (TCFD)**, and **Sustainability Accounting Standards Board (SASB)** disclosures are used as your starting baseline

## Before you start: what you'll need

| What | In plain terms |
|------|----------------|
| Existing disclosure documents | Your sustainability report, TCFD report, CDP submission, 10-K climate section — whatever you already publish |
| Company profile | A short paragraph: legal structure, listing status, EU presence, headcount, revenue |
| Which regulations apply to you | The skill checks your existing disclosures against the ones you name — it doesn't independently determine which regulations you're subject to |
| Your first compliance deadline | When mandatory reporting starts for you under each relevant regulation |

## What happens when you run it

This is a five-step sequence, and the steps build on each other in order:

1. **Scoping** — confirms which specific rules apply to your company based on your profile.
2. **Disclosure inventory** — catalogues what you currently disclose, topic by topic. Before this runs, Claude will list the documents it has and ask you to confirm nothing relevant is missing — the register is only as complete as what it can see.
3. **Gap mapping** — the core step, run once per regulation — checks your inventory against each requirement and rates it Compliant, Partially Compliant, or Gap.
4. **Consolidated gap register** — merges the findings across all regulations into one prioritized table.
5. **Remediation roadmap** — sequences the fixes into a phased action plan.

Before Step 1, Claude will ask how familiar your team is with these frameworks and whether this output is headed for legal/board review or is an internal working document, to calibrate how much explanation and how many legal caveats to surface along the way.

**Plan for 2–4 hours** if you have a couple of years of existing disclosures ready to upload.

## What you'll get back

An executive summary, the full gap register (one row per requirement), a coverage summary by regulation, and a phased remediation roadmap with owners and rough effort estimates.

## Good to know — please read this one

- **This is not legal advice.** The register is a compliance management tool. Scoping questions (which entities are covered, which standards are material to you) need a qualified lawyer, not just this skill.
- **Regulations change.** Treat the analysis as current as of when you run it, and verify anything material against the primary regulatory text before filing.
- **The register only reflects what you upload.** If a relevant document is missing, the gap register will understate your compliance gaps rather than flag the omission — this is why Step 2 asks you to confirm your document set is complete.

## How to run it

1. Open Claude and share `RegulatoryGapAnalysis-SKILL.md` as context.
2. Upload your existing disclosure documents.
3. Confirm which regulations are in scope and answer the calibration questions.
4. Work through the five steps in order — don't skip ahead, since each step depends on the last.
5. Export the final gap register and route it to legal/compliance for review.
