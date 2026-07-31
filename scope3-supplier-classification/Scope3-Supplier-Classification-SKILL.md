---
name: scope3-supplier-classification
description: >
  Maps a company's procurement or accounts payable data to Greenhouse Gas (GHG) Protocol
  Scope 3 categories at scale. Handles supplier deduplication, spend classification,
  emission factor assignment, and produces an auditable output ready for Scope 3 inventory
  or supplier engagement. What previously took analysts weeks now runs as a structured,
  repeatable pipeline. Use when a company needs to move from a raw supplier spend list
  to a credible Scope 3 Category 1–15 breakdown without rebuilding the logic from scratch
  each reporting cycle.
category: Reporting & Disclosure
framework_alignment: GHG Protocol | Science Based Targets initiative (SBTi) | CDP
audience_level: Intermediate
claude_interface: Claude.ai (with file upload)
---

# Scope 3 Supplier Classification — Skill

**Description:** Maps procurement or accounts payable (AP) data to Greenhouse Gas (GHG) Protocol Scope 3 categories. Handles supplier name deduplication, spend classification, emission factor lookup, and gap flagging. Produces a structured, auditable output ready to feed a Scope 3 inventory or supplier engagement programme.

**When to use:** When a sustainability or procurement team needs to classify a supplier spend list against GHG Protocol Scope 3 categories — particularly Category 1 (purchased goods and services) — and does not want to rebuild the classification logic manually each reporting cycle. Designed for Consumer Packaged Goods (CPG) companies where procurement data spans hundreds to thousands of supplier lines across ingredients, packaging, contract manufacturing, logistics, and indirect spend.

**Created by:** Rochelle March, University of Vermont (March.Rochelle@uvm.edu)

---

## Background: the problem this solves

For a mid-to-large CPG company, Scope 3 Category 1 alone can represent 60–80% of total emissions. Yet the raw input — an AP or procurement export — is typically messy: the same supplier appears under three different name variants, spend categories use internal cost codes that do not map cleanly to GHG Protocol categories, and emission factors must be sourced and documented separately.

The manual equivalent of this workflow is a spreadsheet-based classification exercise that takes a sustainability analyst 2–4 weeks per reporting cycle, is prone to inconsistency across reviewers, and leaves no auditable record of classification rationale.

This skill compresses that cycle to hours, applies classification logic consistently, flags uncertainty explicitly, and produces an output that a third-party verifier can follow.

---

## How to use this skill

1. Open Claude and share this file as context
2. Upload or paste your procurement or AP export (see input requirements below)
3. Ask Claude: *"Classify my supplier spend data using the Scope 3 Supplier Classification skill"*

You can run this on a full annual dataset or a representative sample for scoping purposes.

---

## Before you begin

Before running the classification, Claude should ask:

> *"Two quick questions before I start: (1) How familiar are you with GHG Protocol Scope 3 accounting and supplier spend classification — is this your first inventory cycle, or are you refreshing an existing one? (2) Would you like the full detailed classification output, or a higher-level summary suited for an internal update or leadership briefing?"*

Use the answers to calibrate how much explanatory context to add around GHG Protocol categories, confidence flags, and next steps — and to decide whether to lead with the detailed classification table or the summary sections.

---

## Inputs to provide

| Input | Description | Example |
|-------|-------------|---------|
| Spend export | Raw procurement, accounts payable (AP), General Ledger (GL), or Trial Balance (TB) data as CSV or pasted table | Columns: supplier name (AP) or spend/cost category (GL/TB), spend ($), cost centre, description |
| Data type | Which of the two accepted input types you are providing | Preferred: supplier-specific AP data · Accepted: GL or TB spend-category data |
| Reporting year | The fiscal or calendar year being classified | FY2025 |
| Spend currency | Currency of spend figures | USD |
| Company type | Industry context to guide classification logic | CPG — food and beverage |
| Known exclusions | Spend categories to exclude (e.g. payroll, taxes) | Employee benefits, bank charges |
| Emission factor source (optional) | Preferred source for spend-based emission factors | Open CEDA 2025 (default); US EEIO or Exiobase if specified |
| Prior classification (optional) | Existing category mapping from a previous cycle | Upload or paste |

**Minimum viable input:** Supplier name + annual spend figure (preferred), or GL/TB spend category + annual spend figure (accepted). Classification confidence improves significantly with cost centre codes or line-item descriptions.

**Working with GL or TB data:** Supplier-specific AP data is preferred — it supports supplier-level deduplication (Step 1) and produces a genuine Top 10 Suppliers list (Step 4). GL or TB data is accepted for companies without ready supplier-level access: it is organised by spend or cost category rather than supplier name, so Step 1 (deduplication) does not apply, and Step 4's prioritisation becomes a *category* prioritisation instead of a supplier one. When GL/TB data is provided, Claude should classify at the category level, note in the output that supplier-level detail was not available, and flag category lines where obtaining supplier-level detail would materially improve classification confidence.

---

## What Claude will build

### Step 1 — Supplier Deduplication
- Identifies and consolidates duplicate or variant supplier names (e.g. "Tetra Pak Inc", "TETRA PAK", "Tetra-Pak North America" → single entity)
- Flags high-confidence merges separately from low-confidence ones for human review
- Produces a cleaned supplier master list with original variants noted

*If working from GL/TB data rather than supplier-level AP data, this step does not apply — skip to Step 2 and classify at the spend-category level instead.*

### Step 2 — GHG Protocol Category Mapping
Maps each supplier or spend line to one of the 15 GHG Protocol Scope 3 categories. For CPG companies, the most frequently populated categories are:

| Category | Label | Typical CPG examples |
|----------|-------|---------------------|
| Cat 1 | Purchased goods and services | Ingredients, packaging, contract manufacturing |
| Cat 2 | Capital goods | Equipment, facilities spend |
| Cat 3 | Fuel and energy-related activities | Indirect energy not in Scope 1/2 |
| Cat 4 | Upstream transportation and distribution | Third-party freight, co-man logistics |
| Cat 5 | Waste generated in operations | Waste haulers, disposal contractors |
| Cat 6 | Business travel | Airlines, hotels, car rental |
| Cat 7 | Employee commuting | Commuter benefit providers |
| Cat 9 | Downstream transportation and distribution | Outbound freight, 3PL (third-party logistics) providers |
| Cat 12 | End-of-life treatment of sold products | Packaging recovery, recycling |

- Each line is assigned a primary category, a confidence level (High / Medium / Low), and a one-line classification rationale
- Lines that cannot be classified with reasonable confidence are flagged for manual review rather than silently assigned

### Step 3 — Spend-Based Emission Factor Assignment
- Assigns a spend-based emission factor (in kilograms of carbon dioxide equivalent per dollar, kgCO2e/$) to each classified line, drawn from **Open CEDA 2025** (by Watershed) by default — an open-source, annually updated dataset built on the US Environmentally Extended Input-Output (EEIO) model for US sectors and Exiobase for non-US and multi-regional spend
- Calculates estimated emissions per supplier line: spend × emission factor
- For suppliers with international sourcing (e.g. ocean freight, imported ingredients), applies the appropriate country- or region-level factor from Open CEDA's multi-regional layer
- Notes where more precise activity-based data would materially improve accuracy

### Step 4 — Summary and Gap Analysis
- Rolls up estimated emissions by GHG Protocol category
- Identifies the top 10 suppliers by estimated emissions footprint (your "high-priority" engagement list)
- Flags data quality gaps: missing spend, unclassified lines, suppliers where spend-based factors are a poor proxy
- Notes which categories are likely understated due to data limitations

---

## Output format

```
# Scope 3 Supplier Classification
**Company:** [name] | **Reporting year:** [year] | **Run date:** [date]
**Total spend classified:** $[X]M across [N] supplier lines

---

## 1. Supplier Deduplication Log
| Original variants | Consolidated name | Confidence | Action required? |
|-------------------|------------------|-----------|-----------------|
| [list] | [name] | High / Low | Yes / No |

*[N] duplicates identified. [N] require manual confirmation before finalising.*
*Omit this section if working from GL/TB data — no supplier-level deduplication applicable.*

---

## 2. Classified Spend Summary

| GHG Protocol Category | Supplier count | Total spend ($M) | Est. emissions (tCO2e) | Data quality |
|-----------------------|---------------|-----------------|----------------------|-------------|
| Cat 1 — Purchased goods & services | | | | |
| Cat 4 — Upstream transport | | | | |
| [etc.] | | | | |
| **Unclassified** | | | | Flag for review |

---

## 3. Full Classification Table (all lines)
| Supplier (consolidated) | Spend ($) | Category | Confidence | Rationale | Est. emissions (tCO2e) | EF source |
|------------------------|-----------|----------|-----------|-----------|----------------------|-----------|
| [supplier] | | | High/Med/Low | [one line] | | Open CEDA 2025 |

---

## 4. Top 10 Suppliers by Estimated Emissions
| Rank | Supplier | Category | Est. tCO2e | Priority action |
|------|----------|----------|-----------|----------------|
| 1 | | | | Engagement / Data request / Verify |

---

## 5. Gap Analysis and Data Quality Notes
- **Unclassified spend:** $[X]M ([X]%) — [reason and recommended next step]
- **Low-confidence classifications:** [N] lines — recommend manual review
- **Spend-based factor limitations:** [categories where activity data would improve accuracy]
- **Missing data:** [suppliers or spend categories with incomplete information]

---

## 6. Recommended Data Quality Next Steps
1. [Top priority — e.g. confirm [N] low-confidence supplier merges]
2. [Second priority — e.g. reclassify [N] unclassified or ambiguous spend lines]
3. [Third priority — e.g. obtain missing cost-centre codes or line-item detail for [N] low-confidence rows]

*This section is limited to fixes that improve the classification itself — deduplication, categorisation, and data gaps. It does not include supplier engagement or decarbonisation strategy recommendations; those belong in a separate strategy or engagement-planning exercise.*

---
*Classification logic follows GHG Protocol Corporate Value Chain (Scope 3) Standard.*
*Emission factors: Open CEDA 2025 (Watershed) | Built on US EEIO + Exiobase | Currency: [specified]*
*Unclassified lines and low-confidence assignments flagged for human review — do not auto-approve.*
*Built using PPWA Scope 3 Supplier Classification Skill | [date]*
```

---

## CPG worked example: Bright & Bold Foods

**Bright & Bold Foods** is a fictional mid-size CPG snack brand used as the reference scenario throughout this skill. A shareable dummy dataset — `BrightBoldFoods_FY2025_Procurement_DUMMY.csv` — is available alongside this skill file and is designed to let practitioners run the full workflow without using proprietary data.

The dummy dataset contains 74 procurement lines, $129M in annual spend across ingredients, packaging, contract manufacturing, logistics, waste, capital goods, travel, and indirect spend. It includes intentional supplier name variants, ambiguous category lines, and three unclassifiable rows to showcase every feature of the skill — including deduplication, confidence flagging, and gap analysis.

**What the dummy dataset illustrates:**
- 18 duplicate or variant supplier entries across 9 consolidated entities (e.g. Archer Daniels Midland appearing as "Archer Daniels Midland Co.", "ADM", and "Archer-Daniels-Midland" across three ingredient lines)
- Clear high-confidence Category 1 lines (ingredients, packaging, contract manufacturing) alongside genuinely ambiguous ones (MRO (maintenance, repair and operations) supplies, energy utilities with Scope 1/2 boundary questions)
- International freight lines where Open CEDA's multi-regional emission factors apply (ocean freight via Geodis, imported ingredients)
- Three fully unclassifiable rows — including a line with no supplier name on record — to test gap-flagging behaviour
- Category ambiguity built in: Amazon Freight (Category 9 vs. Category 1 service?), utilities lines that may belong to Scope 2 rather than Category 3

**To run the skill against this dataset**, upload `BrightBoldFoods_FY2025_Procurement_DUMMY.csv` alongside this skill file and prompt:
> *"Classify this supplier spend data using the Scope 3 Supplier Classification skill. The company is a CPG snack brand. Reporting year is FY2025. Use Open CEDA 2025 as the emission factor source."*

---

## Framework alignment

This skill applies the **GHG Protocol Corporate Value Chain (Scope 3) Accounting and Reporting Standard** (World Resources Institute / World Business Council for Sustainable Development, 2011), the definitive global standard for Scope 3 emissions accounting. It is compatible with:

- **CDP** supply chain and climate questionnaire disclosure
- **Science Based Targets initiative (SBTi)** Corporate Net-Zero Standard Scope 3 screening requirements
- **EU Corporate Sustainability Reporting Directive (CSRD)** / European Sustainability Reporting Standards (ESRS) E1 climate standard
- **Task Force on Climate-related Financial Disclosures (TCFD)** supply chain risk disclosure

Spend-based emission factors drawn from:
- **Open CEDA 2025** (Watershed, open licence CC BY-SA 4.0) — default. A harmonised, annually updated dataset that synthesises the US Environmentally Extended Input-Output (EEIO) model for US sectors and Exiobase for multi-regional and non-US spend into a single practitioner-ready resource, with currency and price-year adjustments applied. Attribution required: *"CEDA by Watershed."*
- **US EEIO model** (US Environmental Protection Agency) — US-only datasets or where CEDA is not specified
- **Exiobase** — multi-regional datasets or where direct Exiobase access is preferred
- **Supplier-provided primary data** — always preferred where available; this skill flags which suppliers are worth requesting it from

---

## Limitations and important notes

- **Spend-based emission factors are a screening tool, not a final answer.** They are appropriate for identifying hotspots and prioritising supplier engagement, but should be supplemented with activity-based or primary data for material categories before formal disclosure.
- **Classification confidence levels are explicit, not hidden.** Low-confidence assignments are surfaced for human review. Do not remove the confidence column from the output before sharing with auditors.
- **Deduplication is probabilistic at scale.** Claude will flag merges it is uncertain about. A human should review low-confidence merges before locking the supplier master list.
- **This skill does not replace a full Scope 3 inventory methodology.** It accelerates the classification phase. Boundary-setting, double-counting checks, and disclosure decisions require human judgment.
- For supplier-level emissions performance assessment (beyond spend classification), pair with the **Regenerative Supplier Assessment Skill** or a supplier-specific data request template.

---

## Skill tier: Tier 1 — Support

This skill is classified as **Tier 1 — Support** in the PPWA AI for Sustainability Skills framework: it compresses work a practitioner already knows how to do, taking a spend file from raw procurement data to a Greenhouse Gas (GHG) Protocol Category 1–15 breakdown in hours rather than weeks, without changing what the classification says. It is suitable for practitioners with a working knowledge of Scope 3 accounting and basic data literacy — no coding required. Outputs are designed to be handed directly to a sustainability reporting lead or third-party verifier. As with all Tier 1 skills, its impact depends on how the reclaimed time is reinvested — in data quality, supplier engagement, or reduction strategy.

| Tier | Description |
|------|-------------|
| **Tier 1 — Support** | Doing the same work faster. Practitioner-ready; requires domain knowledge, no technical setup. Runs in Claude.ai with file upload. |
| Tier 2 — Augment | Surfacing what wasn't visible before. Power-user; structured prompting chains, live web search or document-heavy inputs, structured outputs for governance or client deliverables. |
| Tier 3 — Discover | Enabling decisions that weren't previously possible. Technical; APIs, automation pipelines, or custom tooling. |

---

*This skill is part of the University of Vermont Sustainable Innovation MBA - Sustainability Skills Library.*

*University of Vermont (March.Rochelle@uvm.edu)*
