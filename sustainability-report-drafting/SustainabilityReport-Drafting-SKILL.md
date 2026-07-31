---
name: sustainability-report-drafting
description: >
  Drafts section-level sustainability report content calibrated for investor and Environmental,
  Social and Governance (ESG) analyst audiences. Applies built-in citation discipline and
  hallucination guardrails: Claude only writes from data the user provides, flags every gap
  explicitly, and never generates unsourced quantitative claims. Covers narrative sections,
  performance data framing, and forward-looking statements. Aligned to Global Reporting
  Initiative (GRI), International Sustainability Standards Board (ISSB) / IFRS S1 and S2,
  Task Force on Climate-related Financial Disclosures (TCFD), Sustainability Accounting
  Standards Board (SASB), and EU Corporate Sustainability Reporting Directive (CSRD).
category: Reporting & Disclosure
framework_alignment: GRI | ISSB (IFRS S1/S2) | TCFD | SASB | CSRD/ESRS
Tier: Tier 1 - Support
claude_interface: Claude.ai (with file upload)
---

# Sustainability Report Drafting — Skill

**Description:** Drafts section-level sustainability report content for investor and ESG analyst audiences. Operates under strict citation and sourcing discipline — Claude writes only from data the user provides, flags missing data explicitly, and distinguishes confirmed performance from estimates and targets. Produces polished, framework-aligned prose that a sustainability reporting lead can take directly into editorial review.

**When to use:** When a sustainability team needs to move from raw performance data, internal notes, and prior-year report text to a first draft of a specific report section — without the risk of fabricated statistics or unsourced claims that would fail third-party assurance or investor scrutiny. Suitable for annual sustainability reports, integrated reports, CDP (Carbon Disclosure Project) questionnaire narrative sections, and TCFD or ISSB-aligned climate disclosures.

**Created by:** Rochelle March, University of Vermont (March.Rochelle@uvm.edu)

---

## Background: the problem this solves

Sustainability report drafting carries a failure mode unique among corporate communications: a single unsourced statistic, an inflated claim, or a forward-looking statement made without adequate basis can expose a company to greenwashing allegations, regulatory scrutiny, or assurance rejection. This risk is amplified when drafting with AI — models trained on broad data may confidently supply plausible-sounding numbers that are simply wrong for the specific company.

This skill is designed around that constraint. Claude's role here is **structured ghostwriter, not data source**. It shapes language, applies framework conventions, and flags gaps — but every number in the output must trace back to something the user supplied. Where data is missing, Claude writes a clearly marked placeholder rather than filling the gap.

The second challenge is audience calibration. A sustainability report section written for a general stakeholder audience reads very differently from one written for an ESG analyst at a major asset manager or a CDP reviewer. This skill is tuned for the latter: precise, data-forward, materiality-aware, and free of aspirational language that cannot be substantiated.

---

## How to use this skill

1. Open Claude and share this file as context
2. Provide your inputs (see below) — the more you supply, the tighter the first draft
3. Specify which section(s) you want drafted (see section types below) — **this is your responsibility, not the skill's.** Claude drafts only the sections you name; it does not infer or add sections you did not request, and does not attempt to determine on its own what a "complete" report should contain.
4. Ask Claude: *"Draft [section name] of our sustainability report using the Sustainability Report Drafting skill"*

You can draft one section at a time or provide a full data package and ask Claude to draft multiple sections, noting gaps as it goes. If you're unsure which sections a comprehensive report typically includes, ask Claude for an overview of the eight section types below before deciding — but the scope decision, and the inputs to support it, remain yours.

---

## Before you begin

Before drafting, Claude should ask:

> *"Two quick questions before we start: (1) How familiar are you with sustainability reporting frameworks and the section you'd like drafted — is this your team's first report, or are you building on prior years? (2) Is this draft headed for assurance or external publication, or is it an internal working draft for now? This helps me calibrate how much framework context to explain alongside the draft, and how much editorial caution to apply."*

Use the answers to calibrate explanatory context around framework terminology and citation conventions, and to decide how much editorial guidance to surface alongside the draft itself.

---

## The non-negotiable rule: no data, no claim

Before drafting, Claude will confirm:

> *"I will only include quantitative claims, performance figures, and forward-looking statements that you have explicitly provided. Where data is missing I will insert a clearly marked placeholder — [DATA REQUIRED: description] — rather than filling the gap. Please confirm this is understood before I begin."*

This confirmation step is built into the skill. Do not skip it.

**Placeholders look like this in the draft:**
- `[DATA REQUIRED: FY2025 total Scope 1 emissions in tCO2e]`
- `[DATA REQUIRED: % of suppliers covered by code of conduct as of report date]`
- `[DATA REQUIRED: target year for net-zero commitment — confirm board-approved language]`

Placeholders are features, not bugs. They are your gap register: a complete list of data you need to confirm before the section can go to assurance.

---

## Guardrail: no unapproved next steps

This applies across every section, not only the CEO/leadership message. When performance data implies a logical next step — narrowing a Scope 3 range with primary supplier data, moving from a near-term to a long-term target, expanding assurance scope — Claude will not present that next step as decided or already in motion unless the user has explicitly confirmed it is approved.

Language like *"the focus for FY2026 is..."* or *"we are transitioning to..."* implies an approved plan. Where the user has not confirmed a next step is approved, Claude will phrase it as a flagged option instead:

> *"Based on the data provided, a natural next step would be [X]. [DATA REQUIRED: confirm whether this is an approved priority and, if so, the target timeline] before including it as a stated direction."*

The user should review these flags and either confirm the language as approved, revise it, or remove it — Claude should not resolve this ambiguity on its own.

---

## Inputs to provide

### Always required
| Input | Description | Format |
|-------|-------------|--------|
| Company name and sector | Industry context to calibrate materiality framing | Text |
| Reporting year | Fiscal or calendar year | e.g. FY2025 |
| Target audience | Primary reader (ESG analyst, CDP reviewer, integrated report reader) | Text |
| Framework(s) in scope | Which standards apply to this section | e.g. GRI 305, ISSB S2, SASB FB-PF |
| Performance data | The actual numbers for this section — e.g. GHG emissions by scope, energy/water/waste figures, workforce metrics, or targets — along with the boundary and methodology behind them (what's included, what year, how it was calculated) | Table, spreadsheet, or pasted data, ideally with methodology notes or footnotes |
| Prior year comparators | FY-1 or multi-year trend data if available | Same format as above |
| Confirmed targets and commitments | Only board-approved, publicly committed targets | Exact wording, source document |

**If you're not sure what counts as "performance data":** it's the underlying numbers the section will report on — for a climate section, that's GHG emissions figures by scope; for a social section, workforce or safety metrics. Methodology context (boundary, calculation method, assurance status) matters as much as the numbers themselves — see the flag below.

**Missing methodology context is flagged, not assumed.** If the data you provide includes only top-line figures (e.g. total Scope 1/2/3 tonnes) without boundary, calculation methodology, or assurance status, Claude will insert a `[DATA REQUIRED: methodology and boundary information]` placeholder rather than drafting around the gap. Well-documented figures — with footnotes on standard, boundary, and assurance — draft faster and carry fewer placeholders.

### Strongly recommended
| Input | Description |
|-------|-------------|
| Prior-year report text | Existing language to maintain voice consistency and avoid restating dropped commitments |
| Assurance scope | Which data has been externally assured, and to what level (limited / reasonable) |
| Material topics list | The outcomes of the company's materiality or double materiality assessment |
| Internal data notes | Any caveats, restatements, or methodology changes the reporting team is aware of |
| Forward-looking guidance constraints | Any legal, Investor Relations (IR), or board guidance on what can and cannot be stated |

---

## Section types this skill covers

**Note:** This list is a menu, not a checklist Claude applies automatically. Only the sections you explicitly request will be drafted. If your report needs to cover additional topics, request them explicitly or ask Claude to confirm which of these eight types are relevant to your reporting scope.

### 1. Climate and environment performance
Covers greenhouse gas (GHG) emissions (Scope 1, 2, and 3), energy, water, and waste. Applies TCFD-aligned structure (governance, strategy, risk management, metrics and targets) or GRI/ISSB section conventions depending on the framework specified.

**Audience-specific calibrations:**
- ESG analyst / investor: leads with material metrics, quantifies year-on-year change, explains methodology and boundary clearly, notes assurance status
- CDP reviewer: follows CDP scoring criteria — specificity of targets, scenario analysis disclosure, transition plan progress
- Integrated report: connects climate performance to financial materiality and strategic risk narrative

### 2. Supply chain and Scope 3
Covers supplier engagement programmes, Scope 3 Category coverage, spend-based vs. primary data methodology, and supplier decarbonisation commitments. Pairs naturally with the Scope 3 Supplier Classification skill output.

### 3. Social and people performance
Covers workforce data (headcount, diversity, turnover, pay equity), health and safety, human rights in the supply chain, and community investment. Applies GRI 400-series or SASB sector standards as specified.

**Guardrail note for social data:** Demographic data and pay equity figures are particularly sensitive. Claude will not present workforce diversity figures without a clear statement of scope (which employee population, which geography, which definition of the categories used).

### 4. Governance and ethics
Covers board composition and oversight, ESG governance structure, ethics and anti-corruption policies, and whistleblowing disclosures. Written to satisfy ISSB S1 governance requirements and TCFD governance pillar.

### 5. Materiality narrative
Describes the process and outcomes of the company's materiality or double materiality assessment. Explains which topics are material, why, and to whom. Calibrated for ESRS (European Sustainability Reporting Standards) double materiality requirements or GRI single materiality depending on reporting boundary.

### 6. CEO / leadership message
An executive-voice narrative that frames the reporting year, acknowledges material risks and progress, and sets direction without making unsupported forward-looking claims. Written in the voice register the user specifies (measured and data-forward vs. values-led vs. strategic).

**Guardrail note for leadership messages:** This section carries the highest greenwashing risk. Claude will not include superlatives ("industry-leading," "best-in-class"), claims of progress without data, or target language without confirmed board-approved commitments. Any claim that cannot be footnoted will be flagged.

**Broader greenwashing checks (apply across all sections, not only leadership messages):**
- **Directional claims without baseline or trajectory data** — e.g. "emissions are declining" without a baseline year, comparator, or trend data — are flagged rather than included as stated.
- **Product-related sustainability claims without certification** — e.g. "recyclable," "biodegradable," "sustainably sourced" applied to a product or ingredient — are flagged unless the user has supplied a certification, standard, or verification source.
- **Carbon credit and offset claims** are checked against whether the user has supplied the underlying standard the credits are benchmarked against — e.g. the Voluntary Carbon Markets Integrity Initiative (VCMi) or the Science Based Targets initiative (SBTi). Unsupported claims of credit quality or "carbon neutral" status are flagged rather than stated.

### 7. Performance data tables
Structures raw performance data into a publication-ready table with unit labels, boundary notes, assurance indicators, and GRI/ISSB disclosure cross-references. Does not alter the numbers — presents and labels them correctly.

### 8. Forward-looking statements section
Describes targets, commitments, and strategic priorities. Applies a three-tier discipline:

| Tier | Label | What it requires |
|------|-------|-----------------|
| **Committed target** | Board-approved, publicly stated, with baseline and target year | Exact wording from the commitment document |
| **Ambition / aspiration** | Directional intent not yet formalised as a target | Explicitly labelled as such — not presented as a commitment |
| **Safe harbour statement** | Legal protective language for forward-looking content | Applied where required by IR or legal team guidance |

Claude will not upgrade an aspiration to a committed target, and will flag any language in the user's draft that does so inadvertently.

---

## Built-in citation discipline

Every quantitative claim in the drafted section is tagged with an inline source reference at first use, drawn from the inputs provided:

> *"In FY2025, Bright & Bold Foods reduced absolute Scope 1 and 2 emissions by 12% against a 2022 baseline, to 18,400 tCO2e (market-based) [Source: FY2025 GHG Inventory, assured by [Assurer], limited assurance]."*

Source tags follow this format: `[Source: document name, data table or page reference, assurance status if applicable]`

After the draft, Claude produces a **source register** — a table listing every claim in the section, its source, and its assurance status. This is designed to hand directly to the assurance provider.

---

## Output format

```
# [Section title] — Draft for Review
**Company:** [name] | **Reporting year:** [year] | **Framework(s):** [list]
**Draft status:** For internal review — not cleared for publication
**Prepared using:** PPWA Sustainability Report Drafting Skill

---

## [Section content]

[Drafted prose, structured to the specified framework convention]

[DATA REQUIRED: description of missing data] — inserted inline where gaps exist

---

## Data placeholders requiring completion
| # | Placeholder | Data needed | Suggested source |
|---|-------------|-------------|-----------------|
| 1 | [DATA REQUIRED: ...] | Description | e.g. GHG inventory, HR system |

*[N] placeholders in this section. Resolve before assurance review.*

---

## Source register
| Claim | Source document | Reference | Assurance status |
|-------|----------------|-----------|-----------------|
| [quoted claim or paraphrase] | [document name] | [page/table] | Assured / Unassured / N/A |

---

## Editorial flags
[Items Claude is flagging for human review — language that may overstate, unverified comparators,
forward-looking statements that need IR or legal sign-off, or year-on-year changes that warrant
an explanatory note]

---
*Draft produced under citation discipline protocol — all quantitative claims sourced from user-provided data.*
*Unsourced claims and gaps marked [DATA REQUIRED]. Do not remove placeholder tags before assurance review.*
*Built using PPWA Sustainability Report Drafting Skill | [date]*
```

---

## CPG worked example: Bright & Bold Foods — Climate Performance Section

**Scenario:** Bright & Bold Foods is preparing its second annual sustainability report. The sustainability team has a completed GHG inventory, a prior-year comparator, and one confirmed Science Based Targets initiative (SBTi)-validated near-term target. They do not yet have Scope 3 Category 1 primary data (the Scope 3 Supplier Classification skill is still in progress). Their assurer has provided limited assurance on Scope 1 and 2 only.

**What the user provides:**
- FY2025 GHG inventory table (Scope 1: 4,200 tCO2e; Scope 2 market-based: 14,200 tCO2e; Scope 2 location-based: 16,800 tCO2e; Scope 3 Category 1 estimated: 89,000–105,000 tCO2e spend-based)
- FY2022 baseline figures
- SBTi-validated target: 42% absolute reduction in Scope 1 and 2 by 2030 against a 2022 baseline
- Assurance letter confirming limited assurance on Scope 1 and 2

**What Claude produces:**

> *Bright & Bold Foods' combined Scope 1 and 2 (market-based) emissions in FY2025 totalled 18,400 tCO2e, a reduction of 12% against the FY2022 baseline of 20,900 tCO2e [Source: FY2025 GHG Inventory, limited assurance — [Assurer]]. This progress reflects continued investment in renewable energy procurement across our manufacturing operations and a transition to lower-emission refrigerants at two facilities completed in Q3 FY2025 [DATA REQUIRED: specific facility names and refrigerant type, if disclosable].*
>
> *Our near-term science-based target — a 42% absolute reduction in Scope 1 and 2 emissions by 2030 against a 2022 baseline — has been validated by the Science Based Targets initiative and is aligned with a 1.5°C pathway [Source: SBTi validation letter, [date]]. At current trajectory, we are [DATA REQUIRED: on track / ahead of / behind] this target, based on [DATA REQUIRED: interim milestone or trajectory model].*
>
> *Scope 3 emissions, which represent the majority of our value chain footprint, are estimated at 89,000–105,000 tCO2e for FY2025, based on a spend-based methodology applied to Category 1 purchased goods and services [Source: FY2025 Scope 3 screening, spend-based, unassured]. This range reflects data quality limitations in our current supplier dataset; we are investing in primary data collection from our highest-emitting suppliers as a priority for FY2026 reporting. [DATA REQUIRED: confirm whether any Category 1 primary data is available from key suppliers to narrow this range before publication.]*

**Placeholders generated:** 4 (facility names, trajectory confirmation, interim milestone, primary data availability)
**Source register entries:** 3 claims sourced, all traceable
**Editorial flags:** 1 — the phrase "continued investment" implies multi-year pattern; user should confirm this is accurate or replace with specific action

---

## Framework quick-reference

| Framework | Primarily applies to | Key section implications |
|-----------|---------------------|------------------------|
| **GRI Universal Standards + topic standards** | General-purpose stakeholder reporting | Disclosure-by-disclosure structure; requires management approach narrative alongside metrics |
| **ISSB IFRS S1 (General Requirements)** | Investor-facing financial reporting | Materiality defined as investor-relevant; integrated with financial statements |
| **ISSB IFRS S2 (Climate)** | Investor-facing climate disclosure | TCFD-aligned four-pillar structure; scenario analysis required for material climate risk |
| **TCFD** | Climate risk and opportunity disclosure | Four pillars: governance, strategy, risk management, metrics and targets |
| **SASB sector standards** | Sector-specific investor metrics | Defines which metrics are financially material by industry; CPG companies reference Food & Beverage Processing (FB-PF) |
| **CSRD / ESRS** | EU-regulated entities and large non-EU companies in scope | Double materiality (impact + financial); more prescriptive disclosure requirements than GRI or ISSB |
| **CDP Climate / Water / Forest** | Institutional investor and supply chain disclosure | Scored questionnaire; specificity of targets and governance matters for scoring |

---

## Limitations and important notes

- **This skill does not conduct materiality assessments.** It drafts from materiality outcomes you provide. If your materiality assessment is incomplete or has not been documented, the drafted sections will reflect that gap.
- **Claude cannot verify data accuracy.** Numbers in the draft reflect what you provided. The source register is a traceability tool, not an audit.
- **Forward-looking statements carry legal risk.** All content in the forward-looking statements section should be reviewed by legal counsel and Investor Relations before publication, regardless of how it was drafted.
- **Voice consistency requires prior-year text.** Without the previous year's report, Claude will produce technically correct but potentially stylistically inconsistent drafts. Providing 1–2 pages of prior prose significantly improves alignment.
- **Greenwashing guardrails are intentional friction.** If Claude flags language you believe is accurate, provide the supporting data and ask it to revise. Do not remove flags without resolving the underlying evidential question.

---

## Skill tier: Tier 1 — Support

This skill is classified as **Tier 1 — Support** in the PPWA AI for Sustainability Skills framework: practitioner-ready, no technical setup required, runs in Claude.ai with file upload. It compresses the drafting of section-level sustainability report content — applying the same citation discipline and narrative standards a practitioner would already use — into a fraction of the time. Its impact, as with all Tier 1 skills, depends on how that reclaimed time is spent.

| Tier | Description |
|------|-------------|
| **Tier 1 — Support** | Doing the same work faster. Practitioner-ready; requires domain knowledge, no technical setup. Runs in Claude.ai with file upload. |
| Tier 2 — Augment | Surfacing what wasn't visible before. Power-user; structured prompting chains, live web search or document-heavy inputs, structured outputs for governance or client deliverables. |
| Tier 3 — Discover | Enabling decisions that weren't previously possible. Technical; APIs, automation pipelines, or custom tooling. |

---

*This skill is part of the University of Vermont Sustainable Innovation MBA - Sustainability Skills Library.*

*University of Vermont (March.Rochelle@uvm.edu)*

