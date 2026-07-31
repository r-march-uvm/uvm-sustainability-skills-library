---
name: regulatory-gap-analysis
description: >
  Maps a company's existing sustainability disclosures against the requirements of
  Corporate Sustainability Reporting Directive (CSRD) / European Sustainability
  Reporting Standards (ESRS), International Sustainability Standards Board (ISSB)
  IFRS S1 and S2, California's Climate Corporate Data Accountability Act (SB 253)
  and Climate-Related Financial Risk Act (SB 261), and — in preparation for eventual
  enforcement — the U.S. Securities and Exchange Commission (SEC) Climate Rules.
  Also incorporates the Taskforce on Nature-related Financial Disclosures (TNFD) as
  a voluntary-but-converging framework — identifying compliance gaps and producing
  a prioritised remediation register. Designed for corporate Environmental, Social
  and Governance (ESG) teams managing multi-framework compliance simultaneously.
  Built as a structured prompting chain that processes existing disclosure documents
  and outputs a structured gap register ready for internal governance review or a
  Governance, Risk, and Compliance (GRC) tool import.
category: Regulatory Compliance
framework_alignment: CSRD / ESRS | ISSB (IFRS S1/S2) | California SB 253/261 | TNFD | SEC Climate Rules (preparatory) | GRI | TCFD | SASB
tier: Tier 2 - Augment
claude_interface: Claude.ai (with file upload) + optional spreadsheet integration
---

# Regulatory Gap Analysis — Skill

**Description:** Maps existing sustainability disclosures against the requirements of CSRD/ESRS, ISSB IFRS S1/S2, SEC Climate Rules, and incumbent frameworks (Global Reporting Initiative (GRI), Task Force on Climate-related Financial Disclosures (TCFD), Sustainability Accounting Standards Board (SASB)). Runs as a structured, multi-step prompting chain. Outputs a prioritised gap register — a structured table identifying every requirement gap, its severity, and recommended remediation action — suitable for board reporting, legal review, or import into a GRC tool.

**When to use:** When an ESG or legal team needs a systematic, defensible audit of where current disclosures comply with, partially comply with, or are silent against each new regulatory framework — before an external consultant runs the same exercise at ten times the cost. Particularly suited to companies navigating two or more of the major frameworks simultaneously, or preparing for a first-time CSRD or ISSB filing.

**Created by:** Rochelle March, University of Vermont (March.Rochelle@uvm.edu)

---

## Background: the problem this solves

Regulatory convergence in sustainability reporting has created a genuinely new compliance burden. A large company operating in the US with EU operations may simultaneously face: CSRD/ESRS (mandatory for EU entities above certain thresholds, phased 2024–2028); ISSB IFRS S1 and S2 (adopted or in adoption across 20+ jurisdictions); California's SB 253 and SB 261 (mandatory GHG emissions and climate-risk disclosure for companies doing business in California above revenue thresholds, phasing in from 2026); and SEC Climate Rules (applicable to US registrants, currently under litigation — treat as a preparatory exercise rather than an active filing deadline; see framework quick-reference below). Meanwhile, existing GRI, TCFD, TNFD, and SASB disclosures — developed under voluntary frameworks — provide a base that partially satisfies new requirements but was not designed with mandatory compliance in mind.

The challenge is not just knowing what each framework requires. It is mapping what you already have against what each framework requires — at the disclosure level, not just the topic level — and then answering three questions:

1. **Where are we already compliant** (existing disclosure satisfies the requirement)?
2. **Where are we partially compliant** (disclosure exists but is insufficient in scope, specificity, or methodology)?
3. **Where are we silent** (no current disclosure; new data collection, governance process, or methodology required)?

For a company with three years of GRI reporting and a TCFD-aligned climate section, this mapping exercise involves hundreds of disclosure points across three or four frameworks. Done manually, it is 6–12 weeks of consultant time. Done poorly, it leaves material gaps that surface at audit, in assurance review, or — for CSRD — in regulator enforcement.

This skill compresses the gap analysis phase to days, applies consistent logic across all frameworks in scope, and produces an auditable register that a legal or compliance team can stand behind.

---

## How to use this skill

This is a **Tier 2 skill** — it runs as a structured prompting chain across multiple steps, not a single prompt. Each step builds on the last. Work through them in order; do not skip ahead.

1. Open Claude and share this skill file as context
2. Upload your existing disclosure documents (see input requirements below)
3. Confirm which frameworks are in scope for your company
4. Follow the five-step prompting chain below
5. Receive the gap register as a structured output — export as needed

**Time estimate:** 2–4 hours for a company with 2–3 years of existing disclosure documents. Longer if documents are fragmented across multiple reports.

---

## Before you begin

Before starting Step 1, Claude should ask:

> *"Two quick questions before we begin: (1) How familiar is your team with CSRD/ESRS, ISSB, and the other frameworks in scope — has your team scoped these before, or is this a first pass? (2) Is this gap register headed for legal or board review, or is it an internal working document for now? This helps me calibrate how much I explain about each framework alongside the findings, and how prominently to surface the legal caveats."*

Use the answers to calibrate explanatory depth around framework requirements and to decide how prominently to surface the legal disclaimers throughout the chain.

---

## Inputs to provide

### Required
| Input | Description | Format |
|-------|-------------|--------|
| Existing disclosure documents | Annual sustainability report(s), TCFD report, CDP submission, 10-K climate section, proxy statement ESG disclosures | PDF upload or pasted text |
| Company profile | Legal structure, listing status, EU operational presence, employee headcount, revenue | 1 paragraph of text |
| Frameworks in scope | Which target frameworks apply to your company | Select from: CSRD/ESRS · ISSB IFRS S1/S2 · California SB 253/261 · TNFD · SEC Climate Rules (preparatory) · any combination |
| Reporting year | The year your existing disclosures cover | e.g. FY2024 |
| First compliance deadline | When mandatory reporting begins under each applicable framework | e.g. CSRD FY2025 first report; ISSB adopted by local regulator FY2026 |

### Strongly recommended
| Input | Description |
|-------|-------------|
| Double materiality assessment (DMA) | Outcomes of your DMA if completed — material topics and impact/financial materiality classification |
| Prior gap analysis | Any existing consultant or internal gap assessment, even if high-level |
| Legal entity list | Which entities are in CSRD scope (EU subsidiaries above threshold) vs. consolidated group |
| GRC tool format | If you intend to import the gap register into a tool (e.g. Workiva, Archer, ServiceNow GRC), specify the column structure you need |

---

## The five-step prompting chain

### Step 1 — Company Profile and Framework Scoping

**Purpose:** Establish which requirements apply before mapping anything.

**Prompt to use:**

> *"I am preparing a regulatory gap analysis for [Company Name]. Here is our company profile: [paste profile]. Our existing disclosures are attached. We need to assess our compliance position against: [list frameworks]. Our first mandatory reporting deadline is [date/year]. Before we begin the gap mapping, please confirm: (a) which ESRS standards are in scope based on our company profile, (b) whether we are a large accelerated filer, accelerated filer, or non-accelerated filer under SEC rules, and (c) confirm which ISSB standards have been adopted in our primary listing jurisdiction. Flag any ambiguity in our scoping — I would rather resolve a scoping question now than discover it in the gap register."*

**What Claude produces:** A scoping confirmation — which specific standards, disclosure requirements, and filing timelines apply to your company. This is the foundation the rest of the chain builds on. Review it carefully before proceeding.

---

### Step 2 — Existing Disclosure Inventory

**Purpose:** Catalogue what you currently disclose, by topic, before assessing it against new requirements.

**Confirm inputs first.** Before running the inventory, Claude should list the documents it has received and ask the user to confirm the list is complete: *"Before I build the disclosure inventory, here is what I have received: [list documents]. Can you confirm this is the complete set of relevant disclosure documents, or are there others — e.g. a CDP submission, proxy statement, or an internal report — that should be included? The gap register in later steps will only reflect what I can see in these documents."* Findings in Steps 3–5 are only as reliable as this document set; an incomplete set will understate the gap register rather than flag itself as incomplete.

**Prompt to use:**

> *"Now read the attached disclosure documents and build an inventory of our existing sustainability disclosures. For each topic below, note: (a) whether we currently disclose it, (b) the document and section where the disclosure appears, and (c) a brief characterisation of the disclosure's depth (quantitative with methodology / qualitative narrative / mentioned only / not disclosed). Topics to cover: [paste list from Step 1 scoping output, or use the default list below]. Flag any disclosures that appear to be incomplete or that use language suggesting a commitment without supporting data."*

**Default topic list (edit to match your scoping output):**
- Governance: board oversight of sustainability risks, management roles and responsibilities
- Climate risk: physical and transition risk identification, scenario analysis
- Strategy: integration of sustainability risks and opportunities into business strategy
- Targets and metrics: GHG emissions (Scope 1, 2, 3), intensity metrics, climate targets
- Transition plan: decarbonisation pathway, capital allocation, policy engagement
- Nature and biodiversity: material nature-related dependencies and impacts
- Social: workforce metrics, supply chain human rights, community impacts
- Remuneration: link between executive pay and sustainability performance

**What Claude produces:** A structured inventory table — your current disclosure baseline. Do not skip this step; without it, the gap mapping in Step 3 has nothing to compare against.

---

### Step 3 — Framework-by-Framework Gap Mapping

**Purpose:** The core analytical step. Claude maps your existing disclosure inventory against each framework's requirements, requirement by requirement.

**Run this step once per framework in scope.** Use the same prompt structure for each.

**Prompt to use (repeat for each framework):**

> *"Now map our existing disclosure inventory against [FRAMEWORK NAME] requirements. For each requirement: (a) assess our compliance status — Compliant / Partially Compliant / Gap; (b) if Partially Compliant or Gap, describe specifically what is missing; (c) indicate the effort level to close the gap — Data collection required / Methodology development required / Narrative drafting only / Governance process required; (d) note any dependency on outputs from other teams (e.g. finance, legal, procurement). Present this as a structured table. Do not compress or summarise requirements — I need one row per disclosure point, not one row per topic."*

**Status definitions Claude will apply:**

| Status | Definition |
|--------|-----------|
| **Compliant** | Existing disclosure satisfies the requirement in scope, specificity, and methodology. No action needed for this requirement. |
| **Partially Compliant** | A disclosure exists and is relevant, but falls short — typically in quantitative specificity, methodology documentation, assurance coverage, or scope boundary. |
| **Gap** | No current disclosure. Closing this gap requires new data collection, a new governance process, a new methodology, or a combination of all three. |
| **Not applicable** | The requirement does not apply given the company's scoping profile (confirmed in Step 1). |

**CSRD / ESRS requirement coverage:**
Claude will map against the mandatory ESRS set: ESRS 1 (General Requirements), ESRS 2 (General Disclosures), ESRS E1 (Climate), ESRS E2 (Pollution), ESRS E3 (Water), ESRS E4 (Biodiversity), ESRS E5 (Resource Use), ESRS S1 (Own Workforce), ESRS S2 (Workers in the Value Chain), ESRS S3 (Affected Communities), ESRS S4 (Consumers), ESRS G1 (Business Conduct) — filtered to those material under your DMA or flagged as presumed material where no DMA is available.

**ISSB IFRS S1/S2 requirement coverage:**
Claude will map against IFRS S1 (general sustainability-related financial disclosures: governance, strategy, risk management, metrics and targets) and IFRS S2 (climate-specific: physical and transition risk, scenario analysis, Scope 1/2/3 emissions, cross-industry and industry-based metrics).

**SEC Climate Rules requirement coverage (preparatory):**
The SEC Climate Rules remain subject to a litigation-related stay, and their final form and enforcement timeline are uncertain. Claude will map against the rules as published March 2024 and treat this mapping as **preparatory scoping, not an active compliance deadline** — useful for readiness planning, but findings in this section should generally be weighted lower in the priority matrix (Step 4) than CSRD, ISSB, or California findings, unless the company's legal counsel advises otherwise. Key areas: material climate risk disclosure, governance, scenario analysis (where material), GHG emissions (Scope 1 and 2; Scope 3 if material or targeted), financial statement effects, and attestation requirements.

**California SB 253 / SB 261 requirement coverage:**
Claude will map against California's Climate Corporate Data Accountability Act (SB 253 — mandatory Scope 1, 2, and 3 GHG emissions disclosure, third-party assurance required, phasing in from reporting year 2026) and the Climate-Related Financial Risk Act (SB 261 — biennial climate-related financial risk disclosure aligned to TCFD recommendations, first reports due 2026). These apply to companies doing business in California above the relevant revenue thresholds, regardless of where the company is headquartered — a company outside CSRD and SEC scope may still be in scope here.

**TNFD requirement coverage:**
Claude will map against the Taskforce on Nature-related Financial Disclosures (TNFD) recommendations — governance, strategy, risk and impact management, and metrics and targets for nature-related dependencies, impacts, risks, and opportunities. TNFD is voluntary, but is treated here as a converging framework: it is the primary methodology referenced for ESRS E4 (Biodiversity) implementation, much as TCFD served as the de facto methodology for ISSB S2 and ESRS E1. Include TNFD in scope if nature-related impacts are material to the company's sector, or if ESRS E4 is in scope.

**GRI / TCFD / SASB as baseline:**
Where your existing disclosure is GRI- or TCFD-aligned, Claude will note the degree to which each GRI disclosure or TCFD recommendation satisfies (or partially satisfies) the corresponding mandatory requirement. This is the most common source of Partially Compliant findings: a TCFD-aligned climate section often satisfies the qualitative requirements of ISSB S2 but lacks the quantitative specificity (scenario analysis inputs, transition plan capital allocation, Scope 3 methodology documentation) required for mandatory compliance.

---

### Step 4 — Consolidated Gap Register

**Purpose:** Merge the framework-by-framework mapping into a single prioritised register.

**Prompt to use:**

> *"Now consolidate the three framework gap maps into a single gap register. For each gap or partial compliance finding: (a) note which frameworks it affects (a single gap may affect all three); (b) assign a priority tier based on the matrix below; (c) assign a lead function (ESG team, Finance, Legal, Procurement, etc.); (d) estimate remediation effort (Low: <1 week; Medium: 1–4 weeks; High: >1 month; Complex: requires new process or system); (e) note the dependency chain — which gaps must be resolved before others can be closed. Present as a structured table. Then provide a short executive summary — no more than one paragraph — describing the overall compliance posture and the top three remediation priorities."*

**Priority matrix Claude will apply:**

| Priority | Criteria |
|----------|---------|
| **P1 — Critical** | Required by mandatory framework; no current disclosure; first filing deadline within 12 months |
| **P2 — High** | Required by mandatory framework; partial disclosure exists but material gap remains; or required within 24 months |
| **P3 — Medium** | Required by mandatory framework; partial disclosure exists and gap is primarily one of specificity or documentation, not data collection |
| **P4 — Low** | Voluntary framework enhancement; not yet in mandatory scope; or gap exists only in frameworks not adopted in primary jurisdiction |

---

### Step 5 — Remediation Roadmap

**Purpose:** Sequence the remediation work into a realistic programme of action.

**Prompt to use:**

> *"Using the consolidated gap register, build a phased remediation roadmap. Phase the work by: (a) immediate actions (0–3 months): what must start now to meet the first filing deadline; (b) short-term (3–12 months): data collection, methodology development, and governance process work; (c) medium-term (12–24 months): enhancements and system changes; (d) ongoing: recurring processes and monitoring. For each phase, list the specific actions, the lead function, and the dependency on other actions. Flag any actions that require board or audit committee approval. Flag any actions that require third-party support (assurance provider, legal counsel, data vendor)."*

**What Claude produces:** A phased action plan formatted for presentation to a programme steering group. Not a Gantt chart — Claude produces a structured action list that a project manager can translate into whichever tool the team uses.

---

## Output format

The consolidated gap register produced in Step 4 follows this structure:

```
# Regulatory Gap Analysis — Gap Register
**Company:** [name] | **Reporting year:** [year] | **Run date:** [date]
**Frameworks in scope:** CSRD/ESRS · ISSB IFRS S1/S2 · SEC Climate Rules
**Existing disclosure baseline:** [documents reviewed]
**First mandatory filing deadline:** [date]

---

## Executive Summary
[One paragraph: overall compliance posture, top 3 priorities, estimated remediation complexity]

---

## Gap Register

| # | Requirement | Framework(s) | Existing disclosure | Status | What is missing | Priority | Lead function | Effort | Dependencies |
|---|-------------|-------------|---------------------|--------|----------------|----------|--------------|--------|-------------|
| 1 | [e.g. ESRS E1-6: Gross Scope 1, 2, 3 GHG emissions by source] | CSRD / ISSB S2 / SEC | GHG inventory table in Sustainability Report p.34 | Partially Compliant | Scope 3 Category breakdown by source not disclosed; market-based vs. location-based Scope 2 not separated; methodology documentation not included | P2 | ESG + Finance | Medium | Scope 3 methodology development (Gap #7) |
| 2 | [next requirement] | | | | | | | | |

---

## Framework Coverage Summary

| Framework | Total requirements reviewed | Compliant | Partially Compliant | Gap | Not Applicable |
|-----------|---------------------------|-----------|---------------------|-----|---------------|
| CSRD / ESRS | | | | | |
| ISSB IFRS S1/S2 | | | | | |
| SEC Climate Rules | | | | | |

---

## Remediation Roadmap

### Phase 1: Immediate (0–3 months)
| Action | Gap # | Lead | Dependencies | Board approval needed? |
|--------|-------|------|-------------|----------------------|

### Phase 2: Short-term (3–12 months)
[same structure]

### Phase 3: Medium-term (12–24 months)
[same structure]

### Phase 4: Ongoing
[same structure]

---

*Gap register produced using PPWA Regulatory Gap Analysis Skill.*
*Status definitions: Compliant / Partially Compliant / Gap / Not Applicable.*
*Priority tiers: P1 Critical · P2 High · P3 Medium · P4 Low.*
*This register is an internal compliance management tool. It does not constitute legal advice.*
*Built using PPWA Regulatory Gap Analysis Skill | [date]*
```

---

## Worked example: Meridian Materials Group

**Meridian Materials Group** is a fictional global specialty chemicals and advanced materials manufacturer used as the reference scenario for this skill. It is a realistic composite of the type of company facing the most acute multi-framework compliance pressure: large, globally listed, with significant EU manufacturing operations.

**Company profile:**
- Large-cap specialty chemicals and materials company listed on the New York Stock Exchange (NYSE)
- EU operations: manufacturing subsidiaries in Germany, Netherlands, and Belgium employing ~4,800 people; aggregate EU revenue exceeds €150M — firmly in CSRD scope from FY2025 (Wave 2 large undertakings)
- US parent: large accelerated filer under SEC rules, with SEC Climate Rule attestation obligations phasing in
- Existing disclosures: three years of GRI-referenced sustainability report; TCFD-aligned climate section published as a standalone document; SASB Chemicals industry standard metrics table; CDP Climate A-list respondent

**Why this scenario is instructive:**
Meridian has strong existing disclosure — CDP A-list, TCFD-aligned, SASB table — that a naive assessment might call "close to compliant." The gap analysis reveals a more nuanced picture: their qualitative disclosure is strong; their quantitative and methodological depth is not.

---

### Step 1 output (scoping confirmation) — excerpt

> *"Based on the company profile provided: (a) ESRS scope — Meridian's EU subsidiaries are large undertakings under the CSRD definition; mandatory ESRS reporting applies from FY2025 with first report due in 2026. Presumed material ESRS standards given Chemicals sector: ESRS E1 (Climate), ESRS E2 (Pollution — high relevance for specialty chemicals), ESRS E3 (Water), ESRS S1 (Own Workforce), ESRS G1 (Business Conduct). DMA required before E4 (Biodiversity) scope is finalised. (b) SEC filer category — large accelerated filer; Scope 1 and 2 GHG disclosure required from FY2026; limited assurance on Scope 1 and 2 from FY2026; reasonable assurance from FY2033 (or revised timeline pending litigation outcome). (c) ISSB adoption — IFRS S1/S2 not yet mandated by SEC; however, Meridian's European institutional investors are applying ISSB-aligned expectations via stewardship policy. Recommend treating ISSB S2 as in-scope for investor relations (IR) purposes even ahead of mandatory adoption."*

---

### Step 3 output (gap mapping) — selected findings

**Finding 1 — Scenario Analysis (ESRS E1-3 / ISSB S2-10 / SEC)**

| Field | Detail |
|-------|--------|
| Existing disclosure | "We have assessed our business against 1.5°C and 3°C scenarios in line with TCFD recommendations" — two paragraphs, qualitative only |
| Status | **Partially Compliant** |
| What is missing | Quantitative financial impact of identified risks not disclosed; scenario inputs and assumptions not documented; no time horizon distinction between short-, medium-, and long-term physical risks; transition risk assessment does not include policy scenario for EU Carbon Border Adjustment Mechanism (CBAM) — material given export volumes |
| Priority | **P1 Critical** — required by both ESRS E1-3 and ISSB S2; first CSRD filing FY2025 |
| Lead | ESG + Finance + Legal |
| Effort | **High** — quantitative scenario modelling requires external support or significant internal build |

**Finding 2 — Transition Plan (ESRS E1-4 / ISSB S2-14)**

| Field | Detail |
|-------|--------|
| Existing disclosure | Net-zero commitment by 2045; Science Based Targets initiative (SBTi) near-term target validated; capital expenditure (CapEx) in low-carbon R&D referenced in annual report |
| Status | **Partially Compliant** |
| What is missing | Transition plan as a standalone, structured document with phased CapEx and operating expenditure (OpEx) allocation not published; policy engagement positions not disclosed (required under ESRS G1); locked-in emissions from existing assets not quantified |
| Priority | **P2 High** |
| Lead | ESG + Finance + Strategy |
| Effort | **Complex** — requires cross-functional alignment on capital allocation disclosure |

**Finding 3 — Pollution Disclosures (ESRS E2)**

| Field | Detail |
|-------|--------|
| Existing disclosure | Regulatory compliance statements; no emissions-to-air, water, or soil data in current sustainability report |
| Status | **Gap** |
| What is missing | ESRS E2 requires disclosure of material pollutants by medium (air, water, soil), substance, and site — not present in any current document; data likely exists in environmental compliance records but has not been prepared for public disclosure |
| Priority | **P1 Critical** — Chemicals sector; ESRS E2 likely material; no current disclosure |
| Lead | Environmental Health and Safety (EHS) + ESG + Legal |
| Effort | **High** — data exists in regulatory systems but requires extraction, consolidation, materiality scoping, and legal review before disclosure |

---

### Step 4 output — executive summary excerpt

> *"Meridian's existing disclosure programme provides a strong qualitative foundation — particularly governance, risk identification narrative, and targets — that satisfies a meaningful proportion of TCFD-derived requirements within ISSB S2 and ESRS E1. However, three structural gaps are material: (1) quantitative scenario analysis with documented inputs and financial impact quantification is absent across all three frameworks; (2) ESRS E2 pollution disclosures represent a full gap requiring new data extraction and legal scoping; (3) Scope 3 Category 1 and 11 (use of sold products) disclosures lack the methodological documentation and boundary clarity required for assurance. These three gaps account for the majority of P1 and P2 findings and should anchor the remediation programme. Remaining gaps are primarily ones of specificity and documentation — closable within the existing disclosure programme with targeted effort."*

---

## Tier 2 mechanics: what makes this a power-user skill

This skill is classified as **Tier 2** because it requires:

**Structured prompting chain:** The five steps are not interchangeable. Each step produces an output that the next step requires. Running Step 3 without a completed Step 2 inventory produces unreliable results — Claude will map requirements against general knowledge of typical disclosures rather than your specific documents.

**Document processing at volume:** The skill is designed for companies with multiple existing disclosure documents — often totalling 200–400 pages across a sustainability report, TCFD report, CDP submission, and proxy statement. Claude processes these via file upload; users should upload all relevant documents at the start of the session and keep the session open across all five steps.

**Spreadsheet / GRC integration:** The gap register output is designed to be exported as a structured table. To import into a GRC tool:
- Copy the gap register table from Claude's output
- Paste into Excel or Google Sheets; the column structure maps directly to most GRC tool import templates
- Add your internal control reference numbers, owner assignments, and target completion dates before import
- If using Workiva, the gap register structure aligns with the Wdesk framework mapping feature

**Human judgment requirements:** Unlike Tier 1 skills, this one has several points where human judgment is essential before proceeding — particularly in Step 1 (scoping confirmation) and Step 3 (ESRS materiality gating via DMA). Claude will flag these decision points explicitly; do not bypass them.

---

## Framework quick-reference

| Framework | Jurisdiction | Mandatory for whom | Phase-in (as of mid-2025) | Key new requirements vs. GRI/TCFD |
|-----------|-------------|-------------------|--------------------------|------------------------------------|
| **CSRD / ESRS** | EU | Large EU undertakings + listed SMEs + non-EU companies with EU revenue >€150M | Wave 1: FY2024 (PIEs >500 employees); Wave 2: FY2025 (large undertakings); Wave 3: FY2026 (listed SMEs) | Double materiality; pollution (E2); biodiversity (E4); full value chain social standards; assurance required |
| **ISSB IFRS S1/S2** | Global (jurisdiction adoption varies) | Entities in jurisdictions that have adopted ISSB standards | Adopted by 20+ jurisdictions; EU interoperability confirmed; US adoption pending | Financial materiality lens; industry-based metrics (S2 Appendix B); cross-industry climate metrics |
| **SEC Climate Rules (preparatory)** | US | US registrants (phased by filer category) | Large accelerated filers: FY2026 — but subject to an ongoing litigation-related stay; timeline and final form uncertain | Scope 1/2 (if material); Scope 3 if material or targeted; financial statement footnotes; attestation |
| **California SB 253 / SB 261** | US (California) | Companies "doing business in California" above revenue thresholds ($1B for SB 253 Scope 1/2/3; $500M for SB 261), regardless of headquarters location | SB 253: Scope 1/2 reporting from 2026, Scope 3 from 2027; SB 261: first climate risk report 2026 | Mandatory Scope 1/2/3 GHG disclosure with third-party assurance; TCFD-aligned climate risk reporting; applies independent of the federal SEC outcome |
| **TNFD** | Voluntary (global) | Any organisation choosing to report on nature-related issues; increasingly referenced for ESRS E4 | Recommendations published 2023; adoption growing, not yet mandatory anywhere | Nature/biodiversity-specific version of the TCFD four-pillar structure; primary methodology reference for ESRS E4 |
| **GRI** | Voluntary (global) | Any organisation choosing to report | Universal Standards updated 2021; sector standards rolling out 2022–2026 | Commonly used as baseline; GRI 1–3 + topic standards partially satisfy ESRS qualitative requirements |
| **TCFD** | Voluntary (now absorbed into ISSB S2) | Superseded by ISSB S2; many regulators still reference | ISSB S2 is the successor framework | Four-pillar structure (governance, strategy, risk, metrics/targets) is preserved in ISSB S2 |
| **SASB** | Voluntary (US origin, global use) | Sector-specific investor metrics | Integrated into ISSB S2 Appendix B industry guidance | SASB metrics satisfy industry-based disclosure requirements under ISSB S2 |

*Note: CBAM = Carbon Border Adjustment Mechanism. PIE = Public Interest Entity. SME = Small and Medium-sized Enterprise.*

---

## Limitations and important notes

- **This skill does not constitute legal advice.** The gap register is a compliance management tool, not a legal opinion. Requirements under CSRD, SEC, California, and ISSB involve interpretive questions that require qualified legal counsel, particularly for scoping (which entities are in scope), materiality gating (which ESRS standards are material), and forward-looking statement risk.
- **Findings only reflect the documents provided.** If a relevant disclosure document is missing from the upload, the gap register will understate compliance rather than flag the omission. Confirm the complete document set at Step 2 before treating the register as a reliable baseline.
- **Regulatory positions change.** The SEC Climate Rules were subject to a litigation-related stay as of mid-2025; CSRD implementation details continue to evolve via European Financial Reporting Advisory Group (EFRAG) guidance; ISSB jurisdiction adoption is ongoing. Claude's knowledge reflects the regulatory position at its training cutoff; users should verify current regulatory status before relying on the gap register for filing decisions.
- **DMA gating is essential for CSRD.** Without a completed Double Materiality Assessment (DMA), Claude will flag ESRS standards as presumed material based on sector. This is a conservative but imprecise default — it will over-scope rather than under-scope. Complete the DMA before finalising the gap register.
- **Assurance scope affects the register.** Gap findings related to data quality and methodology documentation take on different weight depending on whether limited or reasonable assurance is required. Note your assurance requirements in the company profile so Claude can calibrate.
- **Session continuity matters.** This skill is designed to run across a single Claude session, keeping all five step outputs in context. If the session is interrupted between steps, re-upload the skill file and the previous step outputs before continuing.

---

## Skill tier: Tier 2 — Augment

This skill is classified as **Tier 2 — Augment** in the PPWA AI for Sustainability Skills framework — power-user, requiring sustainability and regulatory domain knowledge, structured prompting discipline, and comfort working across multiple documents. Its value sits in surfacing what a manual review would struggle to catch: the disclosure gaps scattered across five overlapping regulations, read consistently and in full by a reviewer that flags what it cannot verify rather than guessing.

| Tier | Description |
|------|-------------|
| Tier 1 — Support | Doing the same work faster. Practitioner-ready; requires domain knowledge, no technical setup. Runs in Claude.ai with file upload. |
| **Tier 2 — Augment** | Surfacing what wasn't visible before. Power-user; involves structured prompting chains, document-heavy inputs, and structured outputs designed for integration with GRC (Governance, Risk, and Compliance) tools or internal governance processes. |
| Tier 3 — Discover | Enabling decisions that weren't previously possible. Technical; involves application programming interfaces (APIs), automation pipelines, or custom tooling. |

---

*This skill is part of the University of Vermont Sustainable Innovation MBA - Sustainability Skills Library.*

*University of Vermont (March.Rochelle@uvm.edu)*
