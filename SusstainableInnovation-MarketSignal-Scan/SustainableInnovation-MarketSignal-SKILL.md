---
name: sustainable-innovation-market-signal-analysis
description: >
  A structured market signal scan for practitioners evaluating whether a new sustainable
  product, service, or business model is worth pursuing. Compresses weeks of desk research
  into a four-category signal analysis — regulatory and policy, competitor and market moves,
  investor and capital flows, and consumer and demand signals — culminating in modular
  outputs: a signal register, a go / no-go / pause verdict, and an optional investment brief.
  Designed for both corporate sustainability and innovation teams and sustainability consultants
  working with clients. Covers sustainable products, services, new business models, and
  internal process innovation.
category: Innovation & Market Analysis
framework_alignment: None required — framework-agnostic signal scanning method
audience_level: Power-user (Tier 2)
claude_interface: Claude.ai (with web search enabled) or Claude API with search tools
---

# Sustainable Innovation Prototyping and Market Signal Analysis — Skill

**Description:** Before committing resources to a new sustainable product, service, or business model, practitioners need a fast read on whether the market is ready. This skill runs a structured four-category signal scan — regulatory and policy tailwinds, competitor and market moves, investor and capital flows, and consumer and demand signals — to answer the question: *"Is this worth pursuing?"* It runs as a multi-step prompting chain and produces three modular outputs: a signal register, a go / pause / pass verdict with rationale, and an optional one-page investment brief suitable for presenting to leadership or an investment committee.

**When to use:** When a corporate sustainability team, innovation function, or sustainability consultant needs to assess market readiness for a new sustainable offering before resourcing a prototype, pilot, or business case. Most useful at the ideation-to-validation stage — after a concept has been defined but before significant capital or headcount is committed. Can be run in a day rather than the two to four weeks a traditional market scan typically requires.

**Created by:** Rochelle March, PPWA (rochelle@ppwa.io)

---

## Background: the problem this solves

Sustainable innovation fails at two points: too early and too late.

Too early: a team commits to prototyping a new bio-based material, circular service model, or low-carbon product line before the market conditions are right — and the innovation stalls because regulation hasn't caught up, capital hasn't arrived, or procurement teams aren't yet asking for it.

Too late: a team waits for certainty that never comes, while a competitor captures the nascent market, a new regulation makes the innovation mandatory rather than differentiating, or a wave of investor capital flows to a rival.

The window between "too early" and "too late" is narrow and moves fast. The signals that define that window — regulatory pipeline, competitor activity, investor flow, and demand-side shifts — are publicly available but scattered across policy documents, financial filings, procurement databases, industry press, and investor reports. Pulling them together manually takes weeks and often happens inside a single function rather than across all four signal categories simultaneously.

This skill compresses that scan. It uses a structured prompting chain to gather and synthesise signals across all four categories in parallel, applies a consistent analytical lens, and produces outputs calibrated to the decision at hand — whether that decision is a board-level innovation agenda item, a business unit go/no-go gate, or a client recommendation.

---

## How to use this skill

This is a **Tier 2 skill** — it runs as a structured prompting chain across multiple steps, not a single prompt. Each step builds on the last. Work through them in order.

1. Open Claude with web search enabled (Claude.ai with search, or the API with search tools)
2. Share this skill file as context at the start of the session
3. Complete the innovation brief (see inputs section below) — this is the foundation the whole chain builds on
4. Follow the five-step prompting chain
5. Choose how far to take the outputs — signal register only, add a verdict, or produce a full investment brief

**Time estimate:** 3–6 hours for a well-defined concept with a clear sector and geography. Longer if the concept spans multiple sectors or geographies, or if you need to resolve ambiguity in step one before scanning begins.

**What you need before you start:**
- A defined concept — at minimum, a one-paragraph description of the innovation, the problem it solves, and the customer or market it targets
- A geographic focus — the signal landscape differs significantly between markets
- A sense of the innovation type — product, service, business model, or internal process (see definitions below)

---

## Before you begin

Before starting Step 1, Claude should ask:

> *"Two quick questions before we scope the scan: (1) How familiar are you with reading market signal analysis — is this informing a decision you already understand well, or would it help if I explained what 'tailwind/headwind/watch' mean and how to weigh them as we go? (2) What's riding on this — a quick internal gut-check, or a formal investment committee decision? That shapes how much I lean on the full prompting chain versus a faster pass."*

Use the answers to calibrate explanatory depth and to decide whether to run the full five-step chain with the optional extensions, or a leaner version.

---

## Innovation types: definitions

| Type | Definition | Examples |
|------|-----------|---------|
| **Sustainable product** | A physical good with materially lower environmental impact than the incumbent alternative, or designed for circularity, bio-based inputs, or end-of-life recovery | Bio-based insulation panels; low-carbon structural steel; circular packaging |
| **Sustainable service** | A service offering that enables customers to reduce their environmental impact or meet sustainability obligations | Net-zero pathway advisory; Scope 3 data collection platform; green logistics optimisation |
| **New business model** | A model-level innovation that changes *how* value is created, delivered, or captured in a more sustainable way | Product-as-a-service (servitisation); circular leasing; outcome-based environmental contracts |
| **Internal process innovation** | An internal operational change that materially reduces a company's environmental footprint, with potential to commercialise the approach | On-site renewable energy system; supplier decarbonisation programme; regenerative procurement model |

---

## Inputs to provide

### Required

| Input | Description | Format |
|-------|-------------|--------|
| Innovation concept | One paragraph: what the innovation is, the problem it solves, and the target customer or market | Plain text |
| Innovation type | Select from the four types above | One of: Product / Service / Business model / Internal process |
| Sector | The primary sector the innovation operates in or targets | e.g. Built environment · Food and agriculture · Industrials · Financial services |
| Geography | Primary market(s) to scan | e.g. United Kingdom (UK) / European Union (EU) / United States (US) / Global |
| Decision context | What decision this scan is informing | e.g. "Board-level innovation agenda item" / "Business unit go/no-go gate" / "Client recommendation" |
| Time horizon | How quickly you need a market signal — is the question about the next 12 months or the next five years? | e.g. "Near-term (0–18 months)" / "Medium-term (2–5 years)" |

### Recommended

| Input | Description |
|-------|-------------|
| Known competitors or analogues | Any companies already operating in this space, even if only adjacent |
| Existing internal view | The team's current hypothesis — does it lean toward pursue or wait? |
| Investment or revenue threshold | What scale of market opportunity would make this worth pursuing for your organisation |
| Constraints | Anything that limits the scan — e.g. specific regulations you know are relevant, geographies to exclude |

---

## The five-step prompting chain

### Step 1 — Concept Definition and Scan Scoping

**Purpose:** Lock down the concept and signal scope before any scanning begins. Ambiguity here produces scattered results.

**Confirm required inputs before running this step.** The six required inputs (concept, innovation type, sector, geography, decision context, time horizon — see Inputs table above) directly change the verdict, not just the framing. If any are missing, Claude must ask for them rather than silently assuming a value — geography in particular has been shown to flip the final Go/Pause/Pass verdict. If the user doesn't want to answer, they may explicitly delegate the choice — e.g. *"use your best judgment / assume [X]"* — and Claude should proceed using a clearly stated default, flagged at the top of every subsequent output: *"Assumed inputs (not confirmed by user): [list]. Treat this analysis as directional; confirm these before acting on the verdict."* The distinction that matters is between an input the user actively delegated to Claude and one Claude silently filled in — only the former is acceptable without a flag.

**Prompt to use:**

> *"I am assessing market readiness for the following sustainable innovation: [paste concept description]. Innovation type: [type]. Sector: [sector]. Primary geography: [geography]. Decision context: [context]. Time horizon: [horizon]. Before we begin the signal scan, please: (a) confirm your understanding of the concept and flag any definitional ambiguity that would affect the scan — for example, if the concept spans more than one innovation type, or if the target market could be interpreted in more than one way; (b) identify the two or three adjacent markets or innovation categories most likely to generate relevant signals — the signal landscape for a new low-carbon building material, for example, overlaps with both the construction supply chain and the green finance market; (c) confirm the four signal categories we will scan: regulatory and policy, competitor and market moves, investor and capital, and consumer and demand; (d) suggest any sector-specific signal sources I should be aware of — trade associations, procurement frameworks, investor coalitions, or regulatory bodies that are particularly active in this space."*

**What Claude produces:** A scoping confirmation that defines the concept clearly, names adjacent markets, and identifies sector-specific sources. Review it before proceeding — if the concept is ambiguous, resolve it here.

---

### Data quality discipline: resolving contradictory sources

Signal scans routinely surface conflicting figures — market size estimates that vary by an order of magnitude, competing cost-parity timelines, or investor sentiment that reads differently depending on the source. When this happens, Claude must not silently select the most favorable or most recent figure. Instead, for any material contradiction: (a) report the range and the sources behind each end of it, not a single point estimate; (b) note what might explain the divergence — different methodology, different market boundary, different date; (c) flag which figure the verdict is most sensitive to. This applies across all four signal scans (Steps 2–5) and should carry through into the signal register and verdict.

---

### Step 2 — Signal Scan: Regulatory and Policy

**Purpose:** Identify the regulatory and policy signals most relevant to the innovation's market readiness — tailwinds that accelerate adoption and headwinds that create friction or risk.

**Prompt to use:**

> *"Run the regulatory and policy signal scan for [concept name]. For each signal: (a) describe the regulation, policy, or standard and its current status — proposed, enacted, in force, under review; (b) classify the signal direction — Tailwind (creates demand for or requirement to use this innovation) / Headwind (creates friction, compliance cost, or risk) / Watch (relevant but direction unclear); (c) describe the mechanism: how specifically does this regulation create or inhibit market conditions for the innovation?; (d) note the timeline — when does this come into force or reach a decision point?; (e) note the geographic scope. Cover: national and regional regulations; sector-specific standards and building codes; procurement mandates (public sector); voluntary-to-mandatory shifts (e.g. net-zero commitments becoming legal requirements); carbon pricing and incentive schemes; product labelling and certification requirements. Present as a structured table. Highlight the two or three signals with the highest near-term market impact."*

**Signal direction definitions Claude will apply:**

| Direction | Definition |
|-----------|-----------|
| **Tailwind** | Regulation or policy that directly or indirectly creates demand for, mandates, or incentivises the innovation |
| **Headwind** | Regulation or policy that increases friction, compliance cost, or risk for the innovation or its target customers |
| **Watch** | Regulation or policy in development, under consultation, or with an unclear outcome — monitoring required |

---

### Step 3 — Signal Scan: Competitor and Market Moves

**Purpose:** Map what similar or adjacent organisations are doing — launches, acquisitions, pilots, strategic announcements — and what that reveals about market trajectory.

**Prompt to use:**

> *"Run the competitor and market moves signal scan for [concept name]. Search for: (a) direct competitors — companies already commercialising the same or very similar innovation; note their stage (pilot, early commercial, at-scale), their target customer, and any public information on traction or revenue; (b) adjacent players — companies in related spaces whose moves indicate broader market direction; (c) recent M&A and partnership activity — acquisitions, joint ventures, or strategic partnerships in this space in the last 24 months; (d) corporate commitments that create demand — large company procurement pledges, net-zero targets, or supply chain requirements that would pull this innovation into the market; (e) notable exits or failures — where has this type of innovation failed, and why? For each finding, note: the organisation, what they did, the date, and the market signal it represents — what does this tell us about whether the market is moving toward readiness? Highlight the three findings with the strongest signal value."*

---

### Step 4 — Signal Scan: Investor and Capital

**Purpose:** Track where sustainability-focused capital is flowing — or not flowing — as a leading indicator of market confidence.

**Prompt to use:**

> *"Run the investor and capital signal scan for [concept name]. Cover: (a) recent funding rounds — venture capital (VC), private equity (PE), or corporate venture capital (CVC) investments in direct or adjacent companies in the last 18–24 months; note stage, size where public, and investor names; (b) impact and Environmental, Social and Governance (ESG) fund activity — are major impact funds or ESG-mandated investors allocating to this space? Any public statements of investment thesis or exclusions that are relevant?; (c) green and sustainability-linked debt — green bonds, sustainability-linked loans, or blended finance instruments being used in this space; (d) public market signals — if relevant companies are publicly listed, note any analyst coverage, price movements, or investor communications that signal confidence or concern; (e) capital gaps — where is funding visibly absent or withdrawn? Absence of capital is as informative as its presence. Summarise: is capital flowing toward this space, away from it, or waiting? What is the capital market's implied view on timing?"*

---

### Step 5 — Signal Scan: Consumer and Demand

**Purpose:** Assess demand-side readiness — willingness to pay, procurement behaviour, and signals from the customer base.

**Prompt to use:**

> *"Run the consumer and demand signal scan for [concept name]. Cover: (a) willingness-to-pay evidence — survey data, pricing studies, or revealed preference data showing whether target customers would pay a premium (or accept parity pricing) for this innovation; note the source and date; (b) B2B procurement shifts — are corporate buyers changing their procurement criteria in ways relevant to this innovation? Look for: supplier qualification requirements, sustainable procurement policies, Request for Proposal (RFP) specification changes, or procurement framework updates; (c) certification and standards demand — are customers asking for, or requiring, certifications relevant to this innovation (e.g. whole-life carbon assessments, circular economy certification, Environmental Product Declarations (EPDs))?; (d) customer commitments creating pull — net-zero targets, Science Based Targets initiative (SBTi) commitments, or supply chain decarbonisation pledges from potential customers that would require this innovation; (e) demand signals from adjacent markets — where has a similar innovation found early customer traction, and what does that tell us about this market's trajectory? Summarise: is demand leading supply (customers want it but supply is limited), lagging (supply exists but customers aren't buying), or matched (supply and demand are roughly aligned)?"*

---

### Optional scan additions

These extend the core four-category scan for concepts where deeper diligence is warranted before a Go/Pause/Pass decision. Run either or both between Step 5 and Output A.

**Technology readiness assessment**

**Prompt to use:**

> *"Assess the technology readiness of [concept name]. For any headwind or constraint already flagged in the signal scans (e.g. cost competitiveness, manufacturing scalability, supply of key inputs), explain the underlying technical reason — is it a fundamental physics or chemistry constraint, a manufacturing scale-up problem, a supply chain bottleneck, or a cost curve expected to improve with volume? Estimate, where evidence supports it, the technology readiness level and the primary technical milestone standing between current state and commercial viability."*

**Failure analysis**

**Prompt to use:**

> *"Research prior attempts at this or closely analogous innovations that did not succeed commercially. For each: what was attempted, by whom, and what specifically caused it to stall or fail — technical performance, cost, regulatory timing, contractor or customer risk aversion, capital availability, or something else? Assess whether [concept name] is exposed to the same failure mode, and if so, whether anything about this attempt addresses it differently."*

---

### Output A — Signal Register

**Purpose:** Consolidate all four signal scans into a structured, navigable register.

**Prompt to use:**

> *"Consolidate the four signal scans into a single signal register. For each signal: include category (Regulatory and Policy / Competitor and Market / Investor and Capital / Consumer and Demand), signal description, direction (Tailwind / Headwind / Watch), strength (Strong / Moderate / Weak — based on specificity, recency, and relevance to the concept), timeline, and source or basis. Sort by strength descending within each category. Then produce a signal summary: for each of the four categories, one paragraph describing the overall signal picture — is the category showing strong tailwinds, mixed signals, or headwinds? Conclude with a signal landscape summary of no more than three sentences: what does the combined signal picture tell us about market readiness for this innovation?"*

---

### Output B — Go / Pause / Pass Verdict

**Purpose:** Translate the signal register into a clear recommendation.

**Prompt to use:**

> *"Based on the signal register, produce a structured verdict. Apply the following framework: Go (pursue now — signal landscape is sufficiently positive across three or four categories to justify prototype or pilot investment); Pause (wait and monitor — the direction is promising but one or more critical signals are not yet resolved — specify which and what to watch for); Pass (do not pursue at this time — signals are predominantly negative or the timing is materially wrong — specify why and whether this could change). For the verdict: (a) state the verdict clearly; (b) provide a rationale in no more than three paragraphs — what are the two or three signals that drove the verdict most strongly?; (c) if Go or Pause, specify the key conditions that should be monitored — what would upgrade a Pause to a Go, or downgrade a Go to a Pause?; (d) if Pass, specify whether this is a permanent pass or a timing call — and if timing, what would need to change?; (e) note any asymmetric risks — scenarios where the downside of acting too early or too late is particularly severe."*

---

### Output C — Investment Brief (optional)

**Purpose:** Package the signal register and verdict into a one-to-two page brief suitable for a leadership team, investment committee, or board innovation agenda item.

**Prompt to use:**

> *"Produce a one-page investment brief for [concept name] suitable for presenting to [audience — e.g. innovation investment committee / board sustainability committee / client leadership team]. The brief should include: (a) concept summary — two sentences; (b) signal landscape summary — four bullet points, one per category, each no more than two lines; (c) verdict — one sentence with the Go / Pause / Pass classification and the primary rationale; (d) key conditions to monitor — three bullet points maximum; (e) suggested next step — one specific action (e.g. commission a customer discovery sprint, engage a regulatory specialist, monitor a named regulation or competitive development). Format: professional, direct, no jargon. Spell out all acronyms on first use. Suitable for a reader who has not seen the underlying signal analysis."*

---

### Output D — Adversarial Review (recommended)

**Purpose:** Stress-test the signal register and verdict before they inform a real decision. Run this in a new context window — a fresh session, without the scan's own framing in context — so the review isn't anchored to the original analysis.

**Prompt to use (new session):**

> *"I'm attaching a market signal analysis [and/or its verdict] for a sustainable innovation decision. Acting as a skeptical reviewer, poke holes in the assumptions and analysis. Specifically: (a) flag any figure that was selected from among conflicting sources without the contradiction being resolved or disclosed; (b) check whether the verdict assumes a differentiated market position that the signals don't actually support; (c) check whether any input (geography, time horizon, decision context) was assumed rather than confirmed, and whether the verdict is sensitive to that assumption; (d) identify where a demand signal from one market (e.g. B2C) is being used as a proxy for a different market (e.g. B2B) without justification; (e) note any finding that was likely underweighted relative to its significance. Be specific — cite the finding, not just the category."*

**What this produces:** A structured critique that should be reconciled with the original verdict before it is presented to a decision-maker. A verdict that survives adversarial review is materially more defensible than one that hasn't been tested.

---

## Output format

The signal register produced in Output A follows this structure:

```
# Market Signal Analysis — Signal Register
**Concept:** [name] | **Innovation type:** [type] | **Sector:** [sector]
**Geography:** [geography] | **Run date:** [date] | **Time horizon:** [horizon]

---

## Signal Register

### Regulatory and Policy

| # | Signal | Direction | Strength | Timeline | Basis |
|---|--------|-----------|----------|----------|-------|
| R1 | [e.g. UK Future Homes Standard — mandatory embodied carbon limits for new residential build from 2025] | Tailwind | Strong | 2025 (enacted) | Department for Energy Security and Net Zero (DESNZ) technical consultation confirmed |
| R2 | [next signal] | | | | |

### Competitor and Market Moves

| # | Signal | Direction | Strength | Timeline | Basis |
|---|--------|-----------|----------|----------|-------|
| C1 | | | | | |

### Investor and Capital

| # | Signal | Direction | Strength | Timeline | Basis |
|---|--------|-----------|----------|----------|-------|
| I1 | | | | | |

### Consumer and Demand

| # | Signal | Direction | Strength | Timeline | Basis |
|---|--------|-----------|----------|----------|-------|
| D1 | | | | | |

---

## Signal Summary

**Regulatory and Policy:** [one paragraph]
**Competitor and Market:** [one paragraph]
**Investor and Capital:** [one paragraph]
**Consumer and Demand:** [one paragraph]

**Signal landscape:** [two to three sentences: overall market readiness assessment]

---

## Verdict

**Classification:** Go / Pause / Pass

**Rationale:** [two to three paragraphs]

**Key conditions to monitor:**
- [condition 1]
- [condition 2]
- [condition 3]

**Asymmetric risks:** [one paragraph]

---

*Signal analysis produced using PPWA Sustainable Innovation and Market Signal Analysis Skill.*
*Signal directions: Tailwind / Headwind / Watch. Signal strength: Strong / Moderate / Weak.*
*Verdicts: Go (pursue now) / Pause (wait and monitor) / Pass (do not pursue at this time).*
*This analysis is a structured market intelligence tool, not investment advice.*
*Built using PPWA Sustainable Innovation and Market Signal Analysis Skill | [date]*
```

---

## Worked example: Veritas Structures

**Veritas Structures** is a fictional mid-sized UK structural engineering and construction products company. It is a realistic composite of companies facing the tension between sustainable product opportunity and uncertain market timing in the built environment sector.

**Company profile:**
- UK-headquartered structural engineering consultancy with a materials manufacturing subsidiary; revenue approximately £85 million; 420 employees
- Innovation concept: a low-embodied-carbon structural timber composite panel (a hybrid cross-laminated timber (CLT) and recycled steel system) designed as a direct substitute for conventional reinforced concrete frames in mid-rise residential and commercial construction
- Innovation type: Sustainable product
- Sector: Built environment — construction materials
- Geography: UK primary; EU secondary
- Decision context: Innovation investment committee go/no-go gate for a prototype programme (£2.1 million over 18 months)
- Time horizon: Near-term (0–18 months for prototype decision); medium-term (2–5 years for commercial launch)

---

### Step 1 output (scoping) — excerpt

> *"Concept confirmed: a structural hybrid CLT / recycled steel composite panel targeting mid-rise residential and commercial construction as a lower-embodied-carbon alternative to reinforced concrete. Adjacent markets most likely to generate relevant signals: (1) mass timber construction broadly — CLT, glulam, and timber frame sectors are the closest analogues and share the regulatory and investor signal environment; (2) low-carbon concrete and alternative binders — the competitor most likely to contest the same architectural specification decision; (3) green building certification systems — Building Research Establishment Environmental Assessment Method (BREEAM), LEED, and WELL ratings drive specifier and developer demand for embodied carbon reduction. Sector-specific sources to watch: UK Green Building Council (UKGBC) Whole Life Carbon roadmap; Royal Institute of British Architects (RIBA) 2030 Climate Challenge targets; Homes England procurement framework updates; Infrastructure and Projects Authority (IPA) green construction guidance.*"

---

### Step 2 output (regulatory) — selected findings

**Finding R1 — UK Future Homes Standard and Embodied Carbon**

| Field | Detail |
|-------|--------|
| Signal | The UK Future Homes Standard, phasing in from 2025, requires substantial uplift in operational energy performance for new residential build. A parallel embodied carbon consultation — the Built Environment Net Zero (BENZ) roadmap — is establishing the framework for mandatory whole-life carbon assessments in planning by 2027. |
| Direction | **Tailwind** |
| Strength | **Strong** |
| Mechanism | Mandatory whole-life carbon assessment at planning stage makes low-embodied-carbon structural systems a specification requirement rather than a voluntary premium. Veritas's panel would shift from a "nice to have" to a "must consider" in structural specification decisions for planning-permitted mid-rise builds. |
| Timeline | Operational energy: 2025 (enacted). Embodied carbon mandatory assessment: 2027 (consulted, not yet enacted — Watch upgrade to Tailwind on enactment) |

**Finding R2 — BREEAM New Construction Embodied Carbon Credit Uplift**

| Field | Detail |
|-------|--------|
| Signal | BREEAM New Construction 2018 and the forthcoming BREEAM 2026 revision increase the credits available for embodied carbon reduction, with the 2026 revision expected to require whole-life carbon assessment for Excellent and Outstanding ratings. |
| Direction | **Tailwind** |
| Strength | **Moderate** |
| Mechanism | Developer clients targeting BREEAM Excellent ratings — a common requirement in commercial development finance covenants — will face pressure to demonstrate embodied carbon performance. Structural frame selection is one of the highest-impact levers available to specifiers. |
| Timeline | BREEAM 2026 revision: anticipated Q2 2026 publication |

---

### Step 3 output (competitor) — selected findings

**Finding C1 — Stora Enso and Rubner Holzbau mass timber commercial scale**

| Field | Detail |
|-------|--------|
| Signal | Stora Enso (Finland) and Rubner Holzbau (Austria) have both scaled mass timber frame solutions to commercial mid-rise delivery in European markets and are actively targeting UK Tier 1 contractors. Stora Enso's Sylva business reported a 34% increase in UK project enquiries in 2024. |
| Direction | Tailwind (market validation) / Headwind (competitive) |
| Strength | **Strong** |
| Market signal | The European mass timber players are validating the market but also establishing incumbent relationships with the Tier 1 contractors Veritas would need as route-to-market. Veritas's hybrid composite system needs a differentiated value proposition — faster installation, lower cost, or superior structural performance in specific use cases — to displace or complement these systems. |

**Finding C2 — Notable failure: Accsys Technologies Accoya structural**

| Field | Detail |
|-------|--------|
| Signal | Accsys Technologies' attempt to position modified wood products as structural alternatives to concrete in mid-rise settings stalled in 2022–2023, with the company refocusing on cladding and decking. |
| Direction | **Watch** |
| Strength | **Moderate** |
| Market signal | Structural performance certification timelines and contractor risk aversion were cited as barriers. Veritas should assess whether its hybrid system addresses these specific objections — particularly the steel integration, which may ease structural engineer sign-off compared to pure timber systems. |

---

### Output B — Verdict (excerpt)

**Classification: Pause**

> *"The signal landscape for Veritas's structural hybrid panel is directionally positive but not yet fully resolved. The regulatory signal is the clearest: embodied carbon mandatory assessment is moving from voluntary to mandatory in UK planning, and the timeline — 2027 for full enactment — aligns well with a 2026 commercial launch if the prototype programme proceeds on schedule. The investor signal is also supportive: green infrastructure capital is actively seeking UK built environment plays, and the panel's CLT component qualifies it for forest-product-backed sustainability-linked financing.*
>
> *The pause classification is driven by two unresolved signals. First, competitor: the European mass timber players are faster-moving than anticipated and are establishing Tier 1 contractor relationships now. Veritas needs to validate whether its hybrid system's differentiation — structural performance in spans above 12 metres, where CLT alone underperforms — is sufficient to command a distinct market position, or whether it will be absorbed into a subcontracting role. Second, demand: willingness-to-pay evidence for the hybrid composite vs. CLT remains thin. Developer clients will pay a premium for certified embodied carbon performance, but the hybrid system's Environmental Product Declaration (EPD) is not yet published, making specification impossible in the near term.*
>
> *Recommended: proceed with the prototype programme but front-load two activities: a competitive differentiation validation exercise with three to five Tier 1 contractors before month three, and EPD preparation as a parallel workstream rather than a post-prototype step. These two actions convert the Pause to a conditional Go within six months."*

---

## Tier 2 mechanics: what makes this a power-user skill

This skill is classified as **Tier 2** because it requires:

**Structured prompting chain with web search:** The skill requires Claude to search for current signals — regulatory pipeline, recent funding rounds, competitor announcements, procurement framework updates. It will not produce reliable results from training data alone for a fast-moving signal landscape. Use Claude with web search enabled.

**Concept definition discipline:** The quality of the scan depends entirely on the precision of the concept definition in Step 1. A vague concept produces scattered signals. If the concept is not yet well-defined — if the team is still debating whether it is a product or a service, or who the target customer is — resolve that first. The skill will flag definitional ambiguity in Step 1; do not bypass that step.

**Cross-category synthesis:** The most valuable insights come from the intersection of signal categories — for example, a regulatory tailwind that has not yet produced investor capital inflow may indicate the market is early; strong investor capital combined with weak consumer demand may indicate a supply-push dynamic. The signal summary and verdict steps are where this synthesis happens; they should not be skipped in favour of reading individual category outputs in isolation.

**Human judgment at the verdict stage:** Output B (the go / pause / pass verdict) is a structured analytical output, not a decision. The practitioner retains the decision. Factors that Claude cannot fully account for — internal capability, risk appetite, relationship capital with specific customers or channels, proprietary technology advantages — belong in the human layer above the verdict.

---

## Adapting the skill across innovation types

The four signal categories are constant across all innovation types, but the weight and interpretation of each category shifts depending on what is being assessed:

| Innovation type | Highest-signal category | Key watch points |
|----------------|------------------------|-----------------|
| **Sustainable product** | Regulatory and policy | Certification timelines; EPD requirements; product standards |
| **Sustainable service** | Investor and capital | Platform funding rounds; B2B contract announcements; corporate venture activity |
| **New business model** | Consumer and demand | Willingness-to-pay evidence; procurement model flexibility; risk-sharing appetite |
| **Internal process innovation** | Competitor and market | Are peers disclosing this practice? Is it becoming a procurement qualifier? |

---

## Limitations and important notes

- **This skill does not constitute investment advice or market research.** The signal register is a structured intelligence tool to inform internal decision-making. It draws on publicly available information, not proprietary market data. For decisions above a material investment threshold, commission primary research or specialist market analysis alongside this scan.
- **Signal recency matters.** The built environment, clean technology, and sustainability policy landscapes move quickly. Run this scan as close to the decision date as possible, and treat any signals older than 18 months as background context rather than live intelligence. Claude's training data has a knowledge cutoff; always run with web search enabled to capture recent regulatory announcements, funding rounds, and competitor moves.
- **The verdict is a structured output, not a decision.** Go / Pause / Pass is a classification based on the signal landscape. Internal factors — organisational risk appetite, capability gaps, competitive positioning, existing customer relationships — are not captured in the scan and must be weighed by the practitioner.
- **Geography materially affects the signal landscape.** A concept that is a Go in the EU (where policy tailwinds are strongest) may be a Pause in the US (where federal policy is less supportive) or vice versa. If the concept is being evaluated for multiple geographies, run the signal scan separately for each primary market before attempting a combined verdict.
- **Concept definition is a prerequisite.** This skill cannot reliably scan for an ill-defined concept. If the concept is still in flux, use the skill to scan two or three concept variants and compare signal landscapes — this is a legitimate use of the skill but should be treated as concept refinement work, not a market readiness assessment.

---

## Skill tier: Tier 2 — Augment

This skill is classified as **Tier 2 — Augment** in the PPWA AI for Sustainability Skills framework — power-user, requiring sustainability domain knowledge, structured prompting discipline, and active web search capability. Its value sits in surfacing market-readiness patterns scattered across regulatory filings, competitor moves, capital flows, and demand signals — the kind of cross-category read no single analyst has time to assemble alone.

| Tier | Description |
|------|-------------|
| Tier 1 — Support | Doing the same work faster. Practitioner-ready; requires domain knowledge, no technical setup. Runs in Claude.ai with file upload. |
| **Tier 2 — Augment** | Surfacing what wasn't visible before. Power-user; involves structured prompting chains, web search for live signals, and structured outputs designed for internal governance or client deliverable integration. |
| Tier 3 — Discover | Enabling decisions that weren't previously possible. Technical; involves application programming interfaces (APIs), automation pipelines, or custom tooling. |

---

*This skill is part of the PPWA AI × Sustainability Skills series. Related skills: AI-Sustainability Weekly Scan (Section 3.x) · Regulatory Gap Analysis (Section 3.3) · [forthcoming: Double Materiality Assessment Facilitator · Transition Plan Builder]*

*PPWA (rochelle@ppwa.io) | UVM Thought Leadership Paper, Section 3.4*
