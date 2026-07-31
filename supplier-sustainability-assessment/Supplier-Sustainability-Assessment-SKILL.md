---
name: supplier-sustainability-assessment
description: >
  Evaluates and scores suppliers on sustainability maturity for any sector — not
  limited to agriculture. Runs as a structured, multi-step sequence: first
  establishes the supplier's sector and primary input type, then generates a
  tiered question framework (standard asks, stretch asks, forward-looking asks)
  adapted to that context, then scores suppliers across six weighted dimensions
  covering environmental and operational practice maturity, input and cost
  resilience, environmental resource performance, emissions and Environmental,
  Social and Governance (ESG) data transparency, social/human rights/governance
  maturity, and transition readiness. Produces a structured supplier scorecard
  suitable for sourcing strategy, supplier engagement, or Request for Proposal
  (RFP) evaluation. Use when a client needs to assess supplier sustainability
  maturity in manufacturing, apparel and textiles, food and agriculture,
  technology and electronics, professional services, or any other sector.
category: Procurement & Supply Chain
framework_alignment: GHG Protocol | GRI | CDP | UN Guiding Principles on Business and Human Rights (UNGPs) | General
audience_level: Power-user (Tier 2)
claude_interface: Claude.ai (with file upload optional)
---

# Supplier Sustainability Assessment — Skill

**Description:** Evaluates and scores suppliers, across any sector, on their sustainability maturity. Uses a tiered question framework that distinguishes standard asks, stretch asks, and forward-looking asks, so assessments reflect both current practice and credible intent. The framework adapts to the supplier's sector and primary input type, then covers environmental and operational practice maturity, input and cost resilience, environmental resource performance, emissions transparency, social/human rights/governance maturity, and transition readiness. Produces a structured supplier scorecard for Environmental, Social and Governance (ESG) reporting, sourcing strategy, or Request for Proposal (RFP) purposes.

**When to use:** When a client is evaluating or onboarding suppliers in any sector and needs to assess sustainability practice maturity — across both environmental and social/human rights/governance dimensions — for sourcing strategy, supplier engagement, or sustainability reporting. This is a sector-general version of the practice-specific supplier assessment skills in the PPWA RegenAg Toolkit — use this one when suppliers sit outside agriculture (manufacturing, apparel, technology, professional services, and so on), or when comparing suppliers across different sectors within the same procurement category.

**Created by:** Rochelle March, University of Vermont (March.Rochelle@uvm.edu)

---

## How this skill works

This is a four-step sequence. Each step builds on the last, so run them in order rather than skipping ahead:

1. **Sector & sourcing context** — Claude asks a short set of calibration questions to establish the supplier's sector, primary input type, and which sustainability dimensions — environmental and social/governance alike — are most material to that category.
2. **Tiered framework generation** — using the Dimension Adaptation Guide below, Claude generates a sector-adapted set of Tier 1, Tier 2, and Tier 3 questions specific to the supplier's category.
3. **Input collection** — the user provides available supplier information against the generated framework (RFP responses, sustainability reports, human rights or labor policy documents, interview notes, and so on).
4. **Scoring & output** — Claude scores the supplier across the six weighted dimensions and produces the structured scorecard.

---

## How to use this skill

1. Open Claude and share this file as context.
2. Answer the Step 1 calibration questions (see below) so Claude can adapt the framework to your sector.
3. Review the generated tiered question set and provide available supplier information against it — pasted from RFP responses, sustainability reports, human rights or labor audit summaries, or interview notes.
4. Ask Claude: *"Assess this supplier using the Supplier Sustainability Assessment skill."*

You can run this for a single supplier or a comparison across multiple suppliers simultaneously, provided they sit in the same or comparable sectors (see **Multi-supplier comparison** below).

---

## Step 1: Sector & sourcing context

Before generating the question framework, Claude will ask:

- What sector or industry does this supplier operate in (e.g., food and agriculture, manufacturing and industrial, apparel and textiles, technology and electronics, professional and knowledge services, or another category)?
- What is the primary input, material, or service being supplied?
- Are there sector-specific certifications, standards, or regulations already relevant to this supplier (e.g., Fair Trade, Responsible Business Alliance (RBA), Global Organic Textile Standard (GOTS), EcoVadis, ISO 14001, SA8000, Worldwide Responsible Accredited Production (WRAP))?
- Are there known labor, human rights, or governance risk factors for this sector, geography, or supply tier (e.g., migrant or seasonal labor, sub-tier/subcontractor visibility gaps, high-risk sourcing geographies, elevated corruption risk)?
- Is there a reason to weight one dimension more heavily than the default weighting below (e.g., water performance is likely immaterial for a professional services supplier but central for a beverage ingredient supplier; social/human rights maturity is typically far more material for apparel or seasonal agricultural labor than for a professional services firm)?

Claude will propose adjusted dimension weights where materiality clearly differs from the default, but will confirm with the user before applying them.

---

## How questions are tiered

Questions are organised into three tiers that reflect what is realistic to expect from suppliers at different stages of sustainability practice, regardless of sector.

| Tier | Label | What to expect |
|------|-------|----------------|
| **Tier 1** | Standard ask | Most suppliers can answer these; commonly included in sustainability-forward RFPs and supplier questionnaires |
| **Tier 2** | Stretch ask | Useful if available; indicates a more advanced supplier — but absence is not automatically penalised |
| **Tier 3** | Forward-looking ask | Signals intent and direction of travel; a credible plan scores positively even without current data |

**Scoring note:** A "not yet tracked" response is treated differently from "not doing this." Where a supplier acknowledges a gap and describes a plan to address it, this is captured under Tier 3 and factored into the Transition Readiness score. The same logic applies to social and governance gaps — a supplier without a formal human rights policy but with a credible remediation timeline is scored differently than one with no awareness of the issue at all.

---

## Dimension Adaptation Guide

This table shows how each of the six scoring dimensions translates across sectors. Use it as a reference when Claude generates the sector-specific question set in Step 2 — the underlying dimension stays the same, but what counts as evidence changes by sector. These sector rows are illustrative starting points, not an exhaustive list; adapt further for sectors not shown here using the same logic (what material practice, resource, labor/governance, and transparency signals apply to this category?).

| Dimension | Food & Agriculture | Manufacturing & Industrial | Apparel & Textiles | Technology & Electronics | Professional & Knowledge Services |
|---|---|---|---|---|---|
| **Environmental & operational practice maturity** | Tillage approach, cover cropping, regenerative or conservation certifications | Energy efficiency measures, renewable energy use, waste reduction and circularity practices | Fiber sourcing (organic, recycled, certified), factory environmental management systems | Responsible mineral sourcing, e-waste and take-back programs, energy efficiency in manufacturing | Renewable energy procurement, remote/digital-first operating practices, sustainable procurement policy |
| **Input & cost resilience** | Fertiliser, fuel, and crop protection cost exposure; supply shortfall history | Raw material and energy price exposure; supplier diversification strategy | Raw fiber and dye cost exposure; sourcing concentration risk | Critical mineral and component price exposure; single-source dependency | Vendor concentration risk; exposure to energy and travel cost volatility |
| **Environmental resource performance** | Irrigation practices, drought/flood exposure, water infiltration | Water use in processing, energy intensity, waste-to-landfill rate | Water and chemical use in dyeing and finishing, discharge management | Water and energy use in component manufacturing | Office and data center energy sourcing, business travel footprint |
| **Emissions & ESG data transparency** | On-farm Scope 1/2/3 tracking, sequestration measurement | Facility-level Scope 1/2/3 tracking, third-party verification | Scope 3 tracking across tiered supply chain, chemical disclosure | Scope 3 tracking across component and assembly tiers | Scope 2/3 tracking for offices, travel, and cloud/data center usage |
| **Social, human rights & governance maturity** | Farmworker wages, housing, and health & safety; freedom of association; child/forced labor risk screening for seasonal or migrant labor; grievance mechanisms; certifications such as Fair Trade or the Fair Food Program; land rights and community relations | Factory worker health & safety; freedom of association and collective bargaining; wage compliance vs. living wage benchmarks; anti-corruption/bribery policy; sub-tier/subcontractor visibility; workforce diversity, equity and inclusion (DEI) data | Factory labor conditions and certifications (WRAP, Fair Labor Association, SA8000); sub-tier (mills, cut-make-trim) labor risk visibility; freedom of association; grievance and remediation mechanisms; gender equity given majority-female garment workforces; living wage progress | Human rights linkage in mineral sourcing (conflict minerals, artisanal mining labor conditions); RBA Code of Conduct compliance in assembly; overtime/forced labor risk; data governance and privacy ethics; anti-corruption policy | Firm-level DEI metrics (workforce diversity, pay equity); business ethics and anti-corruption policy; human rights policy commitments in client engagements; governance oversight of sustainability (board or leadership structure); treatment of subcontracted or gig labor where relevant |
| **Transition readiness** | Years in transition, formal regenerative targets | Decarbonisation roadmap, capital investment plans | Sustainable fiber transition targets, factory improvement plans | Supply chain decarbonisation targets, circular design roadmap | Net-zero commitments, sustainable procurement targets |

---

## Inputs to provide

Provide as much of the following as is available. Claude will flag gaps and note where data is missing or where "not yet tracked" responses indicate future potential.

### Supplier basics *(Tier 1 — Standard ask)*
- Supplier name, sector, and primary input/material/service supplied
- Geography of primary operations
- Annual volume or spend supplied or proposed

### Sector-adapted question set
Once Step 1 and Step 2 are complete, Claude will present a Tier 1/Tier 2/Tier 3 question set specific to your sector, following the same structure as the Dimension Adaptation Guide above (environmental and operational practice maturity, input and cost resilience, environmental resource performance, emissions transparency, social/human rights/governance maturity, transition status).

---

## Scoring framework

Claude scores each supplier across six dimensions on a 1–5 scale. Scores are based on available evidence across all three tiers. Gaps are scored conservatively, but "not yet tracked + credible plan" responses are differentiated from "not applicable / no awareness."

| Dimension | What it measures | Default weight |
|-----------|-----------------|--------|
| Environmental & operational practice maturity | Depth and verification of the environmental and operational sustainability practices most material to this sector | 25% |
| Input & cost resilience | Structural exposure to volatility in the supplier's key input costs | 15% |
| Environmental resource performance | Management of the resource pressures (water, energy, waste, materials) most material to this sector | 15% |
| Emissions & ESG data transparency | Quality and credibility of operational emissions data or plans | 15% |
| Social, human rights & governance maturity | Depth and verification of labor rights, human rights due diligence, business ethics/governance, and DEI practices most material to this sector | 20% |
| Transition readiness | Stage of transition, direction of travel, and credibility of commitments | 10% |

Default weights rebalance the original RegenAg Supplier Assessment weighting to give explicit, visible weight to social/human rights/governance rather than folding it into practice maturity. Adjust per the Step 1 materiality discussion where a dimension is clearly more or less relevant to the sector in question — social/human rights/governance weight in particular should typically be set higher (often 25–30%+) for sectors with elevated labor risk, such as apparel/textiles or food and agriculture with seasonal or migrant labor, and can be set lower for sectors with limited direct labor exposure, though it should rarely be reduced to zero given governance and ethics considerations apply broadly.

**Score guide:**

| Score | Label | What it looks like |
|-------|-------|-------------------|
| **5** | Leading | Strong evidence across Tier 1–2; third-party verified; multi-year data |
| **4** | Progressing | Credible Tier 1–2 responses; some verification or program participation |
| **3** | Emerging | Tier 1 practices in place; Tier 2 data limited but Tier 3 intent credible |
| **2** | Early stage | Awareness of sustainability goals; limited practice adoption; Tier 3 plans forming |
| **1** | Conventional | No documented practices, commitments, or plans across any tier |

**Important:** A supplier scoring 2–3 with strong Tier 3 responses may be a higher-value *develop* candidate than a supplier scoring 3–4 with no forward-looking commitments. This distinction should be captured in the Sourcing Recommendation. The same logic applies to the Social, Human Rights & Governance dimension: a supplier with an emerging score but a credible, resourced remediation plan for a known labor risk should not automatically be treated as lower-priority than a supplier with no known risk simply because it has not looked for one.

---

## Output format

```
# Supplier Sustainability Assessment
**Supplier:** [name] | **Sector:** [sector] | **Primary input:** [material/service] | **Assessed:** [date]

## Summary Scorecard
| Dimension | Score (1–5) | Weight | Tier evidence available | Key gaps |
|-----------|-------------|--------|-------------------------|----------|
| Environmental & operational practice maturity | | | | |
| Input & cost resilience | | | | |
| Environmental resource performance | | | | |
| Emissions & ESG data transparency | | | | |
| Social, human rights & governance maturity | | | | |
| Transition readiness | | | | |

## Overall Score: [X / 5] — [Leading / Progressing / Emerging / Early stage / Conventional]

## Dimension Summaries

### Environmental & Operational Practice Maturity
[2–3 sentences: what practices are in place, what tier of evidence was provided, what is missing]

### Input & Cost Resilience
[2–3 sentences: directional signals on input cost trajectory, volatility management, and reduction intent]

### Environmental Resource Performance
[2–3 sentences: practices in place, any resilience evidence, forward-looking plans]

### Emissions & ESG Data Transparency
[2–3 sentences: current tracking status, any verified data, plans to improve]

### Social, Human Rights & Governance Maturity
[2–3 sentences: labor rights and working conditions evidence, human rights due diligence and grievance mechanisms, governance/business ethics posture, DEI data where available, and any known risk factors with or without a credible remediation plan]

### Transition Readiness
[2–3 sentences: how long into transition, direction of travel, strength of commitment signals]

## Key Strengths
- [Bullet 1]
- [Bullet 2]
- [Bullet 3 if applicable]

## Key Gaps & Recommended Follow-up Questions
- [Tier 2 or Tier 3 question that would most improve the assessment]
- [Second priority gap]
- [Third if applicable]

## Sourcing Recommendation
[One of: Prioritise / Develop / Monitor / Deprioritise]

[2–3 sentences of plain-language rationale, noting whether the recommendation is based on current evidence, forward-looking signals, or both. Flag if strong Tier 3 responses elevate a lower-scoring supplier to Develop status, and flag separately if a known social/human rights risk without a credible remediation plan should cap the recommendation regardless of environmental performance.]

---
*Assessment based on information provided. Scores reflect available evidence only.*
*"Not yet tracked" responses are distinguished from "not applicable" in scoring.*
*Built using PPWA Supplier Sustainability Assessment Skill | July 2026*
```

---

## Multi-supplier comparison

To compare multiple suppliers, provide inputs for each and ask Claude to produce a combined comparison table followed by individual assessments. The comparison table will rank suppliers by overall score, flag which dimensions drive the differences, and note where Tier 3 responses suggest a lower-scoring supplier may warrant higher engagement priority.

**Cross-sector comparisons:** If suppliers span different sectors (for example, comparing a packaging supplier against an ingredient supplier), Claude will run Step 1 and Step 2 separately for each and flag that dimension weights and evidence expectations differ before presenting a combined table — direct score comparison across dissimilar sectors should be read as directional, not exact. This applies with particular force to the Social, Human Rights & Governance dimension, where materiality and baseline risk vary widely by sector and geography.

---

## Important notes

- **Scores reflect the quality of available evidence, not necessarily the quality of a supplier's practices.** A supplier with strong practices but poor documentation will score lower — that gap is itself a procurement signal and an engagement agenda item.
- **"Not yet tracked" is not the same as "not doing this."** The tiered framework is designed to capture direction of travel, not just current state.
- **This assessment does not replace on-site verification, third-party social audit (e.g., SMETA, SA8000, WRAP), or a formal human rights impact assessment.** Use it to prioritise suppliers for deeper engagement, not as a final compliance check — this applies to both environmental claims and social/human rights/governance claims.
- **A high environmental score does not offset a known, unaddressed social or human rights risk.** Where a supplier has a known labor or human rights risk factor with no credible remediation plan, this should be flagged prominently in the Sourcing Recommendation regardless of strength elsewhere.
- **Sector adaptation is a starting point, not a fixed taxonomy.** If a supplier's sector doesn't map cleanly to the five illustrative examples in the Dimension Adaptation Guide, ask Claude to reason from the same underlying dimensions rather than forcing a mismatched fit.
- For financial modelling of sourcing value specific to regenerative agriculture, pair with the **RegenAg Sourcing ROI (Return on Investment) Model Skill** in the PPWA RegenAg Toolkit.
- For spend-based Scope 3 estimation across a full supplier base, pair with the **Scope 3 Supplier Classification Skill**.
- For portfolio-level prioritisation once individual supplier assessments are complete, pair with the **Sustainable Supply Chain Strategy Skill**.

---

## Skill tier: Tier 2 — Augment

This skill is classified as **Tier 2 — Augment** in the PPWA AI for Sustainability Skills framework — power-user, requiring sustainability domain knowledge, structured prompting discipline, and comfort adapting a tiered question framework across sectors. Its value sits in surfacing what a standard supplier questionnaire would miss: the gap between a supplier's marketing language and its actual evidence quality, read consistently across environmental, social, and governance dimensions and flagged rather than guessed at.

| Tier | Description |
|------|-------------|
| Tier 1 — Support | Doing the same work faster. Practitioner-ready; requires domain knowledge, no technical setup. Runs in Claude.ai with file upload. |
| **Tier 2 — Augment** | Surfacing what wasn't visible before. Power-user; involves structured prompting chains, document-heavy inputs, and structured outputs designed for sourcing strategy or RFP (Request for Proposal) evaluation. |
| Tier 3 — Discover | Enabling decisions that weren't previously possible. Technical; involves application programming interfaces (APIs), automation pipelines, or custom tooling. |

---

*This skill is part of the University of Vermont Sustainable Innovation MBA - Sustainability Skills Library.*

*University of Vermont (March.Rochelle@uvm.edu)*
