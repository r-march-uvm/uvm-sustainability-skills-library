---
name: sustainability-business-case-builder
description: >
  Builds the internal funding case for a proposed sustainability initiative by modeling
  four value pathways in parallel — cost reduction, risk mitigation, revenue opportunity,
  and brand and intangible value — stress-testing the assumptions behind each, and
  producing stakeholder-specific narratives calibrated to the decision-maker's priorities.
  Runs in two modes: Mode A (file-based) produces a directional, evidence-tagged business
  case suitable for internal pitching; Mode B (scripted) adds a finance-grade model with
  Net Present Value (NPV), payback period, and Monte Carlo sensitivity analysis. Structures
  the business case as a repeatable pipeline — an assumption register that is refreshed and
  re-run as conditions change — not a one-off document.
category: Strategy & Advisory
framework_alignment: None required — framework-agnostic value modeling method; compatible with TCFD / ISSB S2 risk quantification and standard internal capital allocation processes
audience_level: Technical (Tier 3)
claude_interface: Claude.ai (with file upload) + Python scripting (optional, Mode B)
---

# Sustainability Business Case Builder — Skill

**Description:** The hardest problem in corporate sustainability is rarely knowing what to do — it is building the internal case to fund it. This skill models the value of a proposed sustainability initiative across four pathways at once (cost reduction, risk mitigation, revenue opportunity, brand and intangible value), forces every number to carry an evidence tag, stress-tests the assumptions the case depends on, and renders the result as a narrative calibrated to the specific decision-maker who controls the budget. At its most powerful, it runs a finance-grade Monte Carlo model over the assumption register; it also runs in a file-only mode for teams without scripting support.

**When to use:** When a sustainability, operations, or innovation team has a defined initiative — a packaging conversion, an energy efficiency programme, a supplier engagement investment, a product line change — and needs to win a capital allocation or budget decision against competing internal priorities. Most useful after the "what" is settled and before the funding gate: investment committee, annual budget cycle, board sustainability committee, or a skeptical Chief Financial Officer (CFO). Also suited to consultants building funding cases on behalf of clients.

**Created by:** Rochelle March, PPWA (rochelle@ppwa.io)

---

## Background: the problem this solves

Sustainability initiatives lose internal funding decisions for a structural reason, not an evidential one: their value is scattered across four pathways that no single corporate function owns. The cost savings sit with operations, the risk reduction sits with legal and audit, the revenue effect sits with sales, and the brand effect sits with marketing. A business case written from inside one function makes most of the value invisible — and the initiative ends up competing for capital against projects whose value sits in one familiar line item.

A second failure mode is fragility. Most sustainability business cases are one-off documents built for a single meeting. The moment an energy price moves, a regulation timeline slips, or a competitor announces something, the document is stale — and rebuilding it from scratch costs weeks. The case never compounds; every budget cycle starts over.

A third failure mode is credibility. Cases padded with unsourced figures — "consumers will pay 10% more," "this meaningfully reduces risk" — get taken apart in exactly the meetings that matter most. A smaller number with a visible source outperforms a larger number without one.

This skill addresses all three. It models the four pathways in parallel so the full value picture is assembled in one place. It structures the case around a living assumption register, so a change in one input triggers a re-run, not a rewrite. And it enforces evidence discipline: every quantitative claim is tagged by provenance, contradictions between sources are disclosed rather than resolved silently, and the assumptions the verdict actually depends on are named and stress-tested before a decision-maker ever sees the case.

**Mode A — File-based:** The user supplies the initiative description, whatever internal figures are available (energy costs, material spend, fee schedules), and the decision context. Claude runs the full prompting chain, producing directional value ranges with evidence tags, an assumption register with qualitative sensitivity flags, stakeholder-calibrated narratives, and an objection pre-brief. **Mode A is complete and pitch-ready** on its own — appropriate for internal championing, budget-cycle submissions, and any decision gate that accepts directional ranges with disclosed provenance. Run it first, without waiting for finance-grade inputs.

**Mode B — Finance-grade (full Tier 3):** The Mode A assumption register is exported as a structured file and run through a Python model that computes Net Present Value (NPV), Internal Rate of Return (IRR), and payback period, then runs a Monte Carlo simulation across the assumption ranges to produce probability-weighted outcomes (for example, "there is an 87% probability the initiative is NPV-positive") and a tornado ranking of which assumptions move the result the most. **Mode B makes the case defensible in front of a finance function** — it speaks the language of the capital allocation process the initiative is competing in, and it turns "the numbers are uncertain" from a weakness into a quantified, transparent property of the model.

---

## How to use this skill

This is a **Tier 3 skill**: the full workflow involves structured prompting plus optional Python scripting. Mode A requires no technical setup.

1. Open Claude (Claude.ai with file upload, or Claude Code for Mode B automation) and share this skill file as context.
2. Decide which mode you are running: **Mode A** (file-based, directional) or **Mode A followed by Mode B** (finance-grade).
3. Complete the initiative brief (see Inputs section) — the decision-maker map in particular shapes everything downstream.
4. Work through the prompting chain in order: Steps 1–5 build the value model, Step 6 stress-tests it, the Outputs render it.
5. If running Mode B: export the assumption register as a CSV after Step 6, run the included script, and feed the results back into Outputs A and B.

**Time estimate:**
- Mode A: 3–5 hours of active time for a well-defined initiative — most of it spent gathering the internal figures that upgrade assumptions to user-provided data, and reviewing pathway outputs between steps.
- Mode B: 1–2 additional hours once Mode A is complete — populating the assumptions CSV, running the script, and interpreting the results. Script setup is a one-time cost of under 30 minutes (two Python packages).

**What you need before you start:**
- A defined initiative: what would be done, over what period, at roughly what cost.
- A named decision-maker or decision gate — "the CFO at the March capital committee" is workable; "leadership" is not.
- Whatever internal figures exist, even partial. The skill works without them, but every real figure supplied replaces an assumption.

---

## Before you begin

Before starting Step 1, Claude should ask:

> *"Three quick questions before we build the case: (1) Who actually decides — a named role, committee, or gate — and do you know what that decision-maker has funded or rejected recently? (2) What does a winning case look like in your organization — is there a standard capital request template, a hurdle rate, a payback ceiling? (3) How much finance support do you have — none, a friendly analyst, or a full finance business partner? That determines whether we target Mode A or push through to Mode B."*

Use the answers to calibrate the depth of financial modeling, the format of Output B, and whether Mode B is worth the setup.

---

## The four value pathways: definitions

| Pathway | Definition | Typical value mechanisms | Natural internal owner |
|---------|-----------|--------------------------|------------------------|
| **Cost reduction** | Direct and avoided operating costs attributable to the initiative | Energy and material efficiency; waste and disposal fees; Extended Producer Responsibility (EPR) fee modulation; tax and levy avoidance; logistics optimization | Operations / Finance |
| **Risk mitigation** | Reduction in the probability or severity of losses the organization is exposed to | Regulatory non-compliance penalties and market-access restrictions; supply disruption; asset stranding; litigation; insurance premiums; customer delisting | Legal / Risk / Audit |
| **Revenue opportunity** | Sales the initiative enables, protects, or grows | Retailer and business-to-business (B2B) procurement scorecard eligibility; contract qualification requirements; price premiums where evidenced; new segment access; tender scoring uplift | Sales / Commercial |
| **Brand and intangible value** | Effects on reputation, talent, and license to operate | Consumer perception; employer brand and retention; investor and rating signals; community and regulator goodwill | Marketing / Human Resources (HR) / Investor Relations (IR) |

Two disciplines apply across all four pathways. First, **the pathways are scanned in declining order of evidential hardness** — cost figures are usually verifiable, brand effects rarely are — and no output may present soft-pathway estimates with the same confidence as hard-pathway figures. Second, **avoided cost is not revenue**: risk-mitigation value is expressed as expected loss reduction (probability × severity), clearly labeled, and never silently combined with cost savings as if it were equally certain cash.

---

## Evidence discipline: every number carries a tag

This skill inherits the citation and hallucination guardrails used across the PPWA skills library. Every quantitative claim in every output must carry one of three tags:

| Tag | Meaning | Example |
|-----|---------|---------|
| **[USER]** | Figure provided by the user from internal data | "[USER] Current annual flexible packaging material spend: €6.2M" |
| **[BENCHMARK]** | Figure from a named, published external source, with source and date stated | "[BENCHMARK] Mono-material polyethylene film lightweighting typically yields 8–15% material weight reduction (Ellen MacArthur Foundation, 2023)" |
| **[ASSUMPTION]** | A stated estimate with a rationale, expressed as a range, flagged for validation | "[ASSUMPTION] EPR eco-modulation discount of 10–25% for recyclable format — mid-point of announced ranges across EU member states; validate against your compliance scheme's published fee schedule" |

Three rules follow:

1. **No naked numbers.** A figure without a tag does not appear in any output. If Claude cannot source or reasonably bound a figure, it writes "no defensible estimate available" and logs the gap — a disclosed gap is more credible in a funding meeting than a soft number.
2. **Ranges, not points.** [BENCHMARK] and [ASSUMPTION] figures are expressed as ranges. Where published benchmarks contradict each other, Claude reports the range and the sources behind each end, notes what might explain the divergence, and flags which end the case is sensitive to — never silently selecting the favorable figure.
3. **Tags survive aggregation.** When pathway values are combined in Output A, the summary must state what proportion of total modeled value rests on each tag class. A case where 70% of the value is [USER]-tagged is a different case from one where 70% is [ASSUMPTION]-tagged, even if the headline number is identical.

---

## Inputs to provide

### Required (both modes)

| Input | Description | Format |
|-------|-------------|--------|
| Initiative description | What would be done, over what period, at what approximate cost (capital and operating) | One or two paragraphs |
| Decision-maker map | Who decides, through what gate, on what timeline — and anything known about their evaluation criteria or recent funding decisions | Plain text |
| Organization context | Sector, approximate revenue, geography of operations | Plain text |
| Time horizon | The period over which value is modeled — typically 3, 5, or 10 years | Years |
| Decision context | What the output will be used for — capital committee submission, budget cycle, board paper, client recommendation | Plain text |

### Recommended (upgrades assumptions to [USER] data)

| Input | Why it matters |
|-------|----------------|
| Internal cost figures | Energy tariffs, material spend, waste and disposal fees, current EPR / compliance fees — each replaces a benchmark with a verifiable figure |
| Standard capital request template or hurdle rate | Lets Output B mirror the format the decision gate already uses |
| Known objections | Anything the decision-maker or their function has said about sustainability spend before — feeds Output C directly |
| Prior rejected or funded cases | The single best predictor of what this gate rewards |
| Related analyses | A market signal scan, a Scope 3 classification, or a climate resiliency assessment — pathway scans reuse their findings rather than re-deriving them |

### Mode B additional inputs

| Input | Description |
|-------|-------------|
| Discount rate | The organization's hurdle rate or weighted average cost of capital (WACC) — ask finance; do not guess. If unavailable, run at 8%, 10%, and 12% and present all three |
| Assumption register CSV | Exported from Step 6, in the schema defined in the Mode B section below |
| Python environment | Python 3.9+, with `numpy` and `numpy-financial` installed |

---

## The prompting chain

### Step 1 — Initiative Brief and Decision-Maker Mapping

**Purpose:** Lock down what is being proposed and — equally important — who it must persuade. A business case is an argument aimed at a specific audience; building it before the audience is defined produces a generic document that persuades no one.

**Confirm required inputs before running this step.** If the decision-maker map is vague ("leadership," "the business"), Claude must push back and help the user identify the actual gate: who has budget authority at this scale, what committee does the request route through, and what does that gate's standard evaluation look like. If the user cannot answer, Claude proceeds with a clearly labeled assumed decision profile, flagged at the top of every subsequent output: *"Assumed decision context (not confirmed by user): [profile]. Validate before submission."*

**Prompt to use:**

> *"I am building the internal funding case for the following sustainability initiative: [paste initiative description]. Organization context: [sector, revenue, geography]. Decision-maker map: [who decides, through what gate, on what timeline]. Time horizon: [years]. Decision context: [what the output is for]. Before we model value, please: (a) confirm your understanding of the initiative and flag any scope ambiguity that would change the value model — for example, whether this is a pilot or a full rollout, and what the counterfactual is (what happens if we do nothing?); (b) profile the decision-maker: based on the role and gate described, what are the two or three criteria this decision will actually turn on, and what evidence format does this audience find credible?; (c) assess which of the four value pathways (cost reduction, risk mitigation, revenue opportunity, brand and intangible) are likely to be material for this initiative, and in what order of evidential strength; (d) list the internal figures that would most upgrade this case from assumption-based to data-based, so I can request them before we continue."*

**What Claude produces:** A confirmed initiative brief, a decision-maker profile, a pathway materiality ranking, and a data request list. **The counterfactual defined here — the do-nothing baseline — is the reference point for every value estimate in Steps 2–5.** Pause here and gather whatever items from the data request list are obtainable; each one materially strengthens the case.

---

### Step 2 — Value Pathway Scan: Cost Reduction

**Purpose:** Model direct and avoided operating costs — the hardest-evidence pathway and the anchor of credibility for the whole case.

**Prompt to use:**

> *"Run the cost reduction pathway scan for [initiative name] against the do-nothing counterfactual defined in Step 1. Cover: (a) direct input savings — energy, materials, water, or other consumption the initiative reduces; quantify using my provided figures where available [paste any internal figures], published benchmarks where not; (b) fee and levy effects — waste and disposal costs, Extended Producer Responsibility (EPR) fee modulation, plastic or carbon taxes, and any announced fee schedules the initiative changes our position under; (c) operational efficiencies — maintenance, logistics, downtime, or labour effects, including any transition costs or temporary inefficiencies during implementation (count these as negative value, do not omit them); (d) capital cost interactions — whether the initiative displaces, defers, or adds to already-planned capital expenditure. For each item: annual value as a range, the years in which it applies, evidence tag ([USER] / [BENCHMARK] / [ASSUMPTION]), and the source or rationale. Where benchmark sources conflict, show the range and the sources behind each end. Present as a structured table, then summarize: total annual cost-pathway value range, and the two items the range is most sensitive to."*

---

### Step 3 — Value Pathway Scan: Risk Mitigation

**Purpose:** Express risk reduction as expected loss avoided — probability × severity against the counterfactual — rather than as adjectives.

**Prompt to use:**

> *"Run the risk mitigation pathway scan for [initiative name]. Identify the specific loss events the initiative reduces exposure to, in these categories: (a) regulatory — non-compliance penalties, market-access restrictions, or mandatory remediation under current and announced regulation; name the regulation, its status (proposed / adopted / in force), and the compliance deadline; (b) commercial — customer or retailer delisting, contract loss, or tender exclusion tied to sustainability requirements; (c) operational — supply disruption, input price volatility, or asset stranding the initiative hedges; (d) legal and reputational — litigation exposure and incident-driven reputational loss, only where a concrete mechanism exists. For each risk: describe the loss event; estimate severity as a range (what would it cost if it happened?); estimate likelihood over the modeling horizon as a range, with the basis for the estimate; state how much the initiative reduces probability or severity, and why; compute expected loss avoided (probability reduction × severity) as an annual range with evidence tags. Label all risk-pathway value clearly as expected-loss reduction, not cash savings. Flag any risk where the honest answer is 'material but not quantifiable' — these are presented qualitatively in the case, never forced into numbers."*

---

### Step 4 — Value Pathway Scan: Revenue Opportunity

**Purpose:** Identify revenue the initiative enables, protects, or grows — with the discipline that revenue claims face the most skepticism in funding meetings and therefore need the most conservative treatment.

**Prompt to use:**

> *"Run the revenue opportunity pathway scan for [initiative name]. Cover: (a) revenue protection — existing revenue at risk without the initiative: customer sustainability requirements, retailer scorecards, procurement qualification criteria, or tender thresholds we currently meet only marginally or will fail as requirements tighten; this is usually the strongest revenue argument and should be scanned first; (b) qualification and access — contracts, customers, or segments the initiative newly qualifies us for; distinguish 'eligible to compete' from 'will win' and model accordingly with an explicit win-rate assumption; (c) price effects — premium or preferential pricing, only where willingness-to-pay evidence exists for our market (business-to-business (B2B) and business-to-consumer (B2C) evidence are not interchangeable — do not use one as a proxy for the other); (d) tender and scorecard scoring — where sustainability criteria carry explicit weighting in customer or public procurement scoring, estimate the effect on win probability. For each item: annual value range, timing, evidence tag, source. Apply the most conservative defensible framing — a revenue-protection claim grounded in a named customer's published requirements outlives a growth projection in every funding meeting. Summarize: total annual revenue-pathway range and the confidence gradient across items."*

---

### Step 5 — Value Pathway Scan: Brand and Intangible Value

**Purpose:** Capture the softest pathway honestly — as directional evidence and strategic argument, not manufactured numbers.

**Prompt to use:**

> *"Run the brand and intangible value pathway scan for [initiative name]. Cover: (a) consumer and customer perception — published category-level evidence on sustainability perception effects in our market, clearly labelled as category-level, not initiative-specific; (b) talent — evidence on recruitment and retention effects where the initiative is visible to employees; include only if a plausible mechanism exists at our scale; (c) investor and rating signals — whether the initiative affects positions in ratings, indices, or investor screens that matter to our organization (name which ones and why they matter to us specifically); (d) license to operate — community, regulator, or media goodwill, qualitative only. Default treatment: this pathway is presented as directional support with evidence tags, NOT as a quantified annual value added to the model. Only quantify an intangible item if a specific, defensible mechanism exists (e.g. a documented cost-per-hire reduction) — and even then, present the case total both with and without it. State explicitly in the summary: 'The brand pathway strengthens the strategic argument; the financial case above stands without it.' A case that needs its brand estimate to clear the hurdle rate is not ready for a funding gate."*

---

### Step 6 — Assumption Register and Stress Test

**Purpose:** Consolidate every assumption the four pathway scans rest on, identify which ones the verdict actually depends on, and stress-test them — before a skeptical reviewer does it for you.

**Prompt to use:**

> *"Consolidate all assumptions from Steps 2–5 into a single assumption register. For each assumption: unique ID; description; the pathway(s) it affects; the low / base / high range used; evidence tag and source; and the validation route (who inside or outside the organization could confirm or tighten this figure, and how quickly). Then run the stress test: (a) for each assumption, estimate the effect on total case value of moving it from base to its low end; (b) rank assumptions by that impact — identify the two or three verdict-critical assumptions where the low end materially changes the funding decision; (c) for each verdict-critical assumption, state the strongest available evidence for the base value, the most credible reason it could sit at the low end, and what near-term action would resolve the uncertainty; (d) construct an explicit downside case using the low end of every verdict-critical assumption simultaneously — state whether the initiative still clears the decision-maker's threshold in that case, because a case that survives its own downside scenario is the strongest possible position in a funding meeting; (e) flag any assumption pair that is correlated (e.g. an energy price assumption that drives both a cost saving and a risk estimate) so value is not double-counted."*

**What Claude produces:** The assumption register — **the living core of the pipeline**. In Mode A, the stress test is qualitative-analytical (one-at-a-time swings and a combined downside case). In Mode B, this register is exported as a CSV and the stress test becomes a probabilistic simulation. Either way, the register is the artefact you maintain and re-run in future cycles; the documents are just renderings of it.

---

## Mode B — the finance-grade model

Mode B converts the assumption register into a probabilistic financial model. It answers the three questions a finance function will actually ask: What is the Net Present Value (NPV) and payback period? How confident are you? And which assumptions should we argue about?

### The assumptions CSV schema

Export the Step 6 register into a CSV with one row per value stream, using these columns:

| Column | Description | Example |
|--------|-------------|---------|
| `id` | Unique assumption ID from the register | `C1` |
| `name` | Short description | `Material lightweighting saving` |
| `pathway` | `cost` / `risk` / `revenue` / `brand` / `capex` | `cost` |
| `low` | Annual value, low end (negative for costs/capex) | `310000` |
| `base` | Annual value, base case | `470000` |
| `high` | Annual value, high end | `640000` |
| `year_start` | First year the stream applies (1 = first year) | `2` |
| `year_end` | Last year the stream applies | `10` |
| `tag` | `USER` / `BENCHMARK` / `ASSUMPTION` | `BENCHMARK` |

Conventions: capital expenditure and transition costs are entered as **negative** values in the years they occur (for a cost row, low = the most expensive outcome). Risk-pathway rows contain the *expected loss avoided* range from Step 3. Brand rows are normally excluded (see Step 5); if included, run the model with and without them.

### The script

Save as `business_case_model.py`. Requires `pip install numpy numpy-financial`.

```python
"""
business_case_model.py — Mode B finance-grade model
PPWA Sustainability Business Case Builder skill (Section 3.7)

Usage:
    python business_case_model.py assumptions.csv --rate 0.10 --years 10 --sims 10000
"""
import argparse
import csv

import numpy as np
import numpy_financial as npf

RNG = np.random.default_rng(42)  # fixed seed: results are reproducible across runs


def load_assumptions(path):
    rows = []
    with open(path, newline="", encoding="utf-8-sig") as f:
        for r in csv.DictReader(f):
            rows.append({
                "id": r["id"].strip(),
                "name": r["name"].strip(),
                "pathway": r["pathway"].strip().lower(),
                "low": float(r["low"]),
                "base": float(r["base"]),
                "high": float(r["high"]),
                "year_start": int(r["year_start"]),
                "year_end": int(r["year_end"]),
                "tag": r["tag"].strip().upper(),
            })
    return rows


def cash_flows(rows, years, values):
    """Annual net cash flow vector (index 0 = year 1) for given per-row annual values."""
    cf = np.zeros(years)
    for row, v in zip(rows, values):
        y0, y1 = row["year_start"] - 1, min(row["year_end"], years)
        cf[y0:y1] += v
    return cf


def npv(rate, cf):
    return float(sum(c / (1 + rate) ** (i + 1) for i, c in enumerate(cf)))


def payback_year(cf):
    cum = np.cumsum(cf)
    hit = np.argmax(cum > 0)
    return int(hit) + 1 if cum[hit] > 0 else None


def sample_triangular(rows, sims):
    """Per-row annual value draws. Triangular(low, base, high); degenerate ranges collapse to base."""
    draws = np.empty((sims, len(rows)))
    for j, r in enumerate(rows):
        lo, md, hi = sorted([r["low"], r["base"], r["high"]])
        draws[:, j] = md if lo == hi else RNG.triangular(lo, md, hi, size=sims)
    return draws


def main():
    p = argparse.ArgumentParser()
    p.add_argument("csv_path")
    p.add_argument("--rate", type=float, default=0.10, help="discount rate (e.g. 0.10)")
    p.add_argument("--years", type=int, default=10, help="modeling horizon in years")
    p.add_argument("--sims", type=int, default=10000, help="Monte Carlo iterations")
    args = p.parse_args()

    rows = load_assumptions(args.csv_path)

    # --- Base case ---
    base_vals = [r["base"] for r in rows]
    base_cf = cash_flows(rows, args.years, base_vals)
    base_npv = npv(args.rate, base_cf)
    irr = npf.irr(np.concatenate([[0.0], base_cf]))
    pb = payback_year(base_cf)

    print(f"\n=== Base case ({args.years}y horizon, {args.rate:.0%} discount rate) ===")
    print(f"NPV:            {base_npv:,.0f}")
    print(f"IRR:            {irr:.1%}" if irr is not None and not np.isnan(irr) else "IRR:            n/a")
    print(f"Payback:        {'year ' + str(pb) if pb else 'not within horizon'}")

    # --- Monte Carlo ---
    draws = sample_triangular(rows, args.sims)
    npvs = np.array([npv(args.rate, cash_flows(rows, args.years, draws[i]))
                     for i in range(args.sims)])
    p10, p50, p90 = np.percentile(npvs, [10, 50, 90])
    print(f"\n=== Monte Carlo ({args.sims:,} iterations, triangular distributions) ===")
    print(f"NPV P10 / P50 / P90:   {p10:,.0f} / {p50:,.0f} / {p90:,.0f}")
    print(f"Probability NPV > 0:   {np.mean(npvs > 0):.0%}")

    # --- Tornado: one-at-a-time low/high swings around base ---
    print("\n=== Tornado (NPV swing, low vs high, one assumption at a time) ===")
    swings = []
    for j, r in enumerate(rows):
        for bound in ("low", "high"):
            vals = list(base_vals)
            vals[j] = r[bound]
            swing_npv = npv(args.rate, cash_flows(rows, args.years, vals))
            swings.append((r, bound, swing_npv))
    by_row = {}
    for r, bound, v in swings:
        by_row.setdefault(r["id"], {"row": r})[bound] = v
    ranked = sorted(by_row.values(), key=lambda d: abs(d["high"] - d["low"]), reverse=True)
    for d in ranked:
        r = d["row"]
        print(f"  {r['id']:>4}  [{r['tag']:<10}] {r['name'][:44]:<44} "
              f"NPV {d['low']:>14,.0f} .. {d['high']:>14,.0f}")
    flips = [d for d in ranked if (d["low"] > 0) != (d["high"] > 0)]
    if flips:
        print("\n  Verdict-critical (NPV sign flips within assumption range): "
              + ", ".join(d["row"]["id"] for d in flips))
    else:
        print("\n  No single assumption flips the NPV sign within its range.")


if __name__ == "__main__":
    main()
```

### Interpreting Mode B outputs

- **NPV P10 / P50 / P90** — the 10th, 50th, and 90th percentile NPVs across the simulation. Present all three, not just the mid-point; a case presented as a distribution signals analytical maturity to a finance audience.
- **Probability NPV > 0** — the single most useful sentence Mode B produces: *"Across 10,000 simulated scenarios spanning the full range of our stated assumptions, the initiative is NPV-positive in X% of cases."*
- **Tornado ranking** — which assumptions move the result most, with their evidence tags visible. If the top of the tornado is [ASSUMPTION]-tagged, the highest-value next step is validating that figure, not polishing the document. If a "verdict-critical" flag appears, that assumption's validation route (from the Step 6 register) belongs in the funding request itself.
- **Feed the results back:** paste the script output into the session and re-run Outputs A and B so the narrative reflects the simulation — e.g. replacing "the case is robust to assumption variation" with the actual probability figure.

---

### Output A — Integrated Value Case

**Purpose:** Consolidate the four pathway scans and the stress test into a single structured case document.

**Prompt to use:**

> *"Consolidate Steps 2–6 [and the Mode B simulation results, if run] into an integrated value case. Include: (a) initiative summary and do-nothing counterfactual — three sentences; (b) value summary table — the four pathways with annual value ranges, evidence-tag composition, and timing; brand presented as directional support unless a defensible quantification exists; (c) total case value — as a range, with the proportion of value resting on [USER] vs [BENCHMARK] vs [ASSUMPTION] tags stated explicitly [Mode B: plus NPV P10/P50/P90, IRR, payback, and probability NPV-positive]; (d) the downside case — combined low-end scenario and whether the case still clears the threshold; (e) verdict-critical assumptions — the two or three the decision turns on, each with its validation route; (f) implementation outline — phasing, decision points, and what a staged approval (pilot gate before full commitment) would look like if the full ask is likely to fail. Spell out all acronyms on first use. This is the master document; Output B renders it for a specific audience."*

---

### Output B — Stakeholder-Calibrated Narrative

**Purpose:** Render the same case for the specific decision-maker profiled in Step 1. The facts do not change between versions; the ordering, emphasis, and language do.

**Calibration table Claude will apply:**

| Decision-maker | Leads with | Language register | Treats with caution |
|----------------|-----------|-------------------|---------------------|
| Chief Financial Officer (CFO) / capital committee | Payback, NPV, downside case, capital phasing | Financial — mirrors the standard capital request format | Brand claims; any unvalidated [ASSUMPTION] in the headline |
| Chief Executive Officer (CEO) / board | Strategic positioning, risk mitigation, competitor moves | Concise, decision-oriented, one page | Operational detail |
| Chief Operating Officer (COO) | Operational continuity, transition plan, efficiency gains | Practical — implementation risk addressed head-on | Revenue projections outside their control |
| Chief Risk Officer (CRO) / General Counsel | Regulatory timeline, expected loss reduction, compliance deadlines | Precise — named regulations, dates, penalty mechanisms | Soft benefits of any kind |
| Chief Marketing Officer (CMO) / Commercial lead | Revenue protection, customer requirements, scorecard positions | Customer-evidence-led | Cost detail |

**Prompt to use:**

> *"Render the integrated value case as a funding narrative for [decision-maker profile from Step 1], using the calibration table. Structure: (a) opening — the single sentence this decision-maker most needs to hear, in their language; (b) the ask — amount, phasing, and decision requested; (c) the case — three to five points ordered by this audience's priorities, each carrying its evidence tags; (d) the downside — what we lose by not acting, and what the combined low-end scenario looks like (never omit this: pre-empting it reads as confidence, hiding it reads as salesmanship); (e) the risks of proceeding and how they are managed; (f) next step — the specific approval requested. Length and format: [match the organization's standard template if provided; otherwise one to two pages]. Every number retains its tag. If a second audience must also be persuaded, produce a second rendering — do not average two audiences into one document that persuades neither."*

---

### Output C — Objection Pre-Brief

**Purpose:** Arm the person presenting the case with the objections it will actually face, and the strongest honest response to each.

**Prompt to use:**

> *"Produce an objection pre-brief for [initiative name] presented to [decision-maker profile]. Identify the five objections this case is most likely to face — drawing on the decision context, any known objections I provided, and the standard failure modes of sustainability funding requests ('payback is too long', 'the benefits are soft', 'we have higher-priority capital demands', 'why now — the regulation isn't in force yet', 'can't we do a cheaper version'). For each objection: (a) state it in the blunt form it will actually be raised in; (b) assess it honestly — is it partially valid? Conceding the valid part first is the strongest rhetorical position; (c) give the strongest evidence-tagged response from the case; (d) identify the fallback position if the objection prevails — e.g. staged approval, pilot scope, or a defined revisit trigger. Close with the one objection the case is genuinely weakest against, and what could be done before the meeting to shore it up."*

---

### Output D — Adversarial Review (strongly recommended)

**Purpose:** Stress-test the case the way the toughest person in the room will — before the meeting, not during it. Run this in a **new session**, without the build conversation in context, so the review is not anchored to the original analysis.

**Prompt to use (new session):**

> *"I'm attaching an internal business case for a sustainability initiative. Act as the skeptical CFO reviewing it for a capital committee. Specifically: (a) hunt for untagged or weakly-sourced numbers presented with more confidence than their evidence supports; (b) check whether risk-pathway value (expected loss avoided) has been added to cost savings as if it were equally certain cash; (c) check for double-counting across pathways — the same customer revenue appearing as both 'protection' and 'growth', or one energy assumption driving two value streams without the correlation being flagged; (d) test whether the case survives its own downside scenario, and whether the downside scenario is honestly constructed (all verdict-critical assumptions at their low end simultaneously); (e) identify the strongest objection NOT covered in the objection pre-brief; (f) state whether you would fund it, fund a staged version, or decline — and what single change would most improve its chances. Be specific: cite the figure or claim, not just the category."*

**What this produces:** A structured critique to reconcile before submission. A case that has survived adversarial review carries visibly more confidence into the room — and the review regularly catches double-counting and confidence inflation that the build process itself cannot see.

---

## A pipeline, not a document: running the case across budget cycles

The deliverables above are renderings; the **assumption register and its CSV are the asset**. Maintain them, and the case compounds instead of going stale:

| Trigger | Action | Effort |
|---------|--------|--------|
| A [USER] figure changes (energy tariff, fee schedule, material price) | Update the register row, re-run the Mode B script, regenerate Output A | Minutes |
| A regulation advances (proposed → adopted → in force) | Update the affected Step 3 risk rows — probability typically rises, and the risk pathway hardens | Under an hour |
| A verdict-critical [ASSUMPTION] gets validated | Retag it, tighten the range, re-run — the probability-NPV-positive figure usually improves, which is itself news worth sending the decision-maker | Under an hour |
| The case was declined | Log the actual objections into Output C's input, set the revisit trigger named in the fallback position, and diarise it | Under an hour |
| New budget cycle | Re-run Steps 2–3 for changed externals, refresh the register, re-render Output B for this cycle's gate | Half a day, not the weeks a rebuild costs |

Version the register (a date-stamped CSV per run is sufficient) so the case's history is auditable — being able to show a decision-maker *"here is what changed since you last saw this"* is one of the strongest re-submission openings available.

---

## Output format

The integrated value case produced in Output A follows this structure:

```
# Sustainability Business Case — [Initiative name]
**Organization:** [name] | **Prepared for:** [decision gate] | **Run date:** [date]
**Mode:** A (directional) / B (finance-grade) | **Horizon:** [years] | **Discount rate:** [rate, Mode B]
**Counterfactual:** [one-sentence do-nothing baseline]

---

## The Ask
[Amount, phasing, decision requested — two sentences]

## Value Summary

| Pathway | Annual value range | Years | Evidence mix | Basis |
|---------|-------------------|-------|--------------|-------|
| Cost reduction | [range] | [y–y] | [e.g. 60% USER / 40% BENCHMARK] | [one line] |
| Risk mitigation (expected loss avoided) | [range] | [y–y] | [mix] | [one line] |
| Revenue opportunity | [range] | [y–y] | [mix] | [one line] |
| Brand and intangible | Directional — not included in totals | — | [tags] | [one line] |

**Total modeled value:** [range] | **Evidence composition:** [X% USER / Y% BENCHMARK / Z% ASSUMPTION]
**Mode B:** NPV P10 / P50 / P90: [values] | IRR: [%] | Payback: year [n] | Probability NPV > 0: [%]

## Downside Case
[Combined low-end scenario; does the case still clear the threshold?]

## Verdict-Critical Assumptions

| ID | Assumption | Range | Tag | Validation route |
|----|-----------|-------|-----|------------------|

## Implementation Outline
[Phasing, decision points, staged-approval option]

---

*Produced using the PPWA Sustainability Business Case Builder Skill.*
*Evidence tags: [USER] internal figure / [BENCHMARK] published source / [ASSUMPTION] stated estimate.*
*Risk-pathway value is expected loss reduction, not cash savings. Brand pathway is directional unless separately stated.*
*This is a structured internal decision-support tool, not financial advice.*
```

---

## Worked example: Alderline Foods

**Alderline Foods** is a fictional mid-sized European food manufacturer — a realistic composite of consumer goods companies facing packaging regulation and retailer sustainability pressure simultaneously.

**Company profile:**
- Netherlands-headquartered ambient and chilled food manufacturer; revenue approximately €420 million; 1,100 employees; sells to major European Union (EU) and United Kingdom (UK) grocery retailers, roughly 40% under retailer private label.
- Initiative: convert the flexible packaging portfolio (snack and dried-goods lines) from non-recyclable multi-material laminate film to recyclable mono-material polyethylene film, across three production lines.
- The ask: €3.8 million (€3.1M capital — line modification and tooling; €0.7M transition costs — trials, requalification, temporary line-speed loss) over 24 months.
- Decision gate: quarterly capital committee, chaired by the CFO; hurdle rate 10%; strong preference for payback inside five years.
- Time horizon: 10 years | Mode: A then B.

---

### Step 1 output (decision-maker mapping) — excerpt

> *"Decision profile: a CFO-chaired capital committee with a 10% hurdle rate and a five-year payback preference. Two of the last three sustainability-framed requests at Alderline were declined — both, notably, presented brand value as the lead argument. This decision will turn on: (1) payback inside five years under conservative assumptions; (2) whether the regulatory risk is dated and specific rather than atmospheric; (3) competing demand — a warehouse automation proposal is in the same committee cycle. Recommended pathway emphasis: cost and risk lead, revenue protection second, brand as one closing line at most. Highest-value data requests: current film procurement cost per tonne [USER]; current Extended Producer Responsibility (EPR) fee schedule and the announced eco-modulation rates for your compliance schemes; the two retailer scorecards with published packaging recyclability thresholds."*

---

### Step 2 output (cost pathway) — selected rows

| Item | Annual value | Years | Tag | Basis |
|------|-------------|-------|-----|-------|
| Material cost delta — mono-PE film vs laminate | −€120k to +€180k | 2–10 | [USER] price quotes + [BENCHMARK] resin spread | Mono-material film is currently cost-comparable; range reflects resin price spread volatility. Sources conflict: converter quotes suggest parity, trade data suggests a 3–5% premium at current volumes — range shown, not averaged |
| Lightweighting (8–15% film weight reduction) | €340k – €640k | 2–10 | [BENCHMARK] | Published mono-material lightweighting range applied to [USER] €6.2M annual film spend |
| EPR eco-modulation discount — recyclable format | €210k – €520k | 3–10 | [ASSUMPTION] | Announced modulation ranges across Alderline's four largest EU markets; schedules not yet final in two of them. **Flagged verdict-critical** |
| Transition costs — trials, requalification, line-speed loss | −€700k total | 1–2 | [USER] | Engineering estimate; counted against the case |

---

### Step 3 output (risk pathway) — selected row

**Risk R2 — EU Packaging and Packaging Waste Regulation (PPWR) recyclability requirement**

| Field | Detail |
|-------|--------|
| Loss event | Packaging that fails recyclability grading faces escalating EPR penalties and, by 2030, restricted market access in the EU. Alderline's laminate portfolio would not meet the announced grading threshold |
| Severity | €1.2M – €2.6M per year (forced accelerated conversion at premium cost, plus penalty-tier EPR fees) [BENCHMARK on fee tiers + USER on affected volume] |
| Likelihood without initiative | 70–90% over the horizon — regulation is adopted, not proposed; implementing acts pending [BENCHMARK] |
| Expected loss avoided | €900k – €2.1M per year from 2030 (probability × severity, less residual risk) — labeled as expected-loss reduction throughout |

---

### Step 6 + Mode B output — excerpt

> *"Register: 14 assumptions. Tornado top three: (1) EPR eco-modulation discount [ASSUMPTION] — NPV swing €1.9M; (2) resin price spread [BENCHMARK] — swing €1.4M; (3) PPWR implementing-act timing [BENCHMARK] — swing €1.1M. One verdict-critical flag: at the low end of the eco-modulation range combined with the high end of resin spread, payback moves from year 4 to year 6 — past the committee's preference. Validation route: both compliance schemes publish final modulation schedules in Q1; a two-week wait converts the case's largest [ASSUMPTION] to a [BENCHMARK] before the committee date.*
>
> *Mode B (10 years, 10% discount rate, 10,000 iterations): NPV P10 / P50 / P90 = €0.4M / €2.8M / €5.6M. IRR (base): 19%. Payback (base): year 4. Probability NPV-positive: 87%. Downside case (all verdict-critical assumptions at low end): NPV −€0.3M, payback year 6 — the case does NOT fully survive its own downside, which argues for the staged approval: commit line 1 now (€1.4M), gate lines 2–3 on the Q1 modulation schedules."*

---

### Output B (CFO rendering) — opening excerpt

> *"This is a €3.8M conversion with a base-case payback in year 4 and an 87% probability of positive Net Present Value across the full range of our stated assumptions — and the do-nothing case is not neutral: from 2030, our current laminate portfolio sits in the penalty tier of an adopted EU regulation, at an expected cost of €0.9M–€2.1M per year. We are asking the committee to approve line 1 (€1.4M) now, with lines 2 and 3 gated on the final eco-modulation fee schedules publishing in Q1 — the single assumption our downside case turns on."*

Note what the calibration did: the brand pathway — genuinely relevant for a consumer-facing food brand — appears nowhere in the opening. It survives as one line in the closing paragraph. The two previously declined requests at Alderline led with it.

---

## What makes this Tier 3

- **Scripted probabilistic modeling:** Mode B requires running a Python script, managing a structured assumptions CSV, and interpreting simulation outputs (percentile NPVs, tornado rankings). Non-technical practitioners can run Mode A alone — it is complete and pitch-ready — but the full capability needs basic scripting comfort or a data-literate colleague.
- **Financial model design judgment:** Discount rate selection, horizon choice, correlation between assumptions, and the treatment of expected-loss value all involve decisions that must be made deliberately and documented — the skill supplies defaults, but a case headed to a capital committee should have its parameters confirmed with a finance partner.
- **Cross-functional data integration:** A strong case pulls figures from procurement, operations, compliance, and sales systems — four functions with different owners, formats, and update cycles. The assumption register is the reconciliation layer.
- **Pipeline maintenance:** The re-run discipline (versioned registers, refresh triggers, re-submission cycles) is what separates this from a document generator — and it assumes someone owns the register between cycles.

---

## Running this skill in Claude Code

In Claude.ai (browser), Mode B is a manual loop: export the register CSV, run the script locally, paste results back. In Claude Code, the loop closes: Claude writes the register CSV directly, executes `business_case_model.py`, reads the results, and regenerates Outputs A and B in one session. Re-runs become a single request — *"the final eco-modulation schedule published at 18%, update the case"* — with Claude editing the register row, re-running the simulation, and producing a change note against the prior version.

The prompting chain is unchanged between interfaces; only the Mode B mechanics differ.

---

## Limitations and important notes

- **This skill is a decision-support tool, not financial advice.** It structures an internal argument; it does not replace the organization's own financial governance, and cases above a material threshold should be reviewed by a finance partner before submission.
- **The model is only as honest as its register.** Evidence tags are a discipline, not a guarantee — a [USER] figure can still be wrong, and a [BENCHMARK] can be misapplied. The adversarial review (Output D) exists because the build process cannot audit itself; do not skip it for cases that matter.
- **Expected-loss value invites misreading.** Probability-weighted risk value is analytically sound but rhetorically fragile — a skeptic can always say "so it might not happen." That is why it is labeled separately, why the downside case exists, and why risk value should never be silently pooled with cost savings.
- **Willingness-to-pay evidence is market-specific.** Consumer survey premiums do not transfer to business-to-business procurement, and category-level brand evidence does not transfer to a specific initiative. The revenue and brand scans enforce this, but pressure to inflate these pathways is exactly how sustainability cases lose credibility — resist it.
- **The decision-maker profile is a hypothesis.** Step 1's calibration is inference from role and context. Where possible, validate it against someone who has actually presented to that gate — one conversation with a previous presenter is worth more than any archetype table.
- **Regulatory figures go stale.** Fee schedules, modulation rates, and compliance timelines move. Any case older than one quarter should have its Step 3 rows and regulatory [BENCHMARK] tags re-verified before reuse — with web search enabled, this is a minutes-long check.

---

## Skill tier: Tier 3 — Discover

This skill is classified as **Tier 3 — Discover** in the PPWA AI for Sustainability Skills framework: technical, involving structured financial modeling, Python scripting, and multi-source internal data integration. Mode A (file-based) allows the core workflow without technical setup; Mode B unlocks the full capability — a finance-grade business case with Monte Carlo sensitivity analysis that a two-person sustainability team could not otherwise produce without a dedicated financial planning and analysis (FP&A) resource.

| Tier | Description |
|------|-------------|
| Tier 1 — Support | Doing the same work faster. Practitioner-ready; requires domain knowledge, no technical setup. Runs in Claude.ai with file upload. |
| Tier 2 — Augment | Surfacing what wasn't visible before. Power-user; structured prompting chains, document-heavy inputs, outputs designed for internal governance or client deliverable integration. |
| **Tier 3 — Discover** | Enabling decisions that weren't previously possible. Technical; involves scripting, automation pipelines, and multi-source data integration. Designed for teams with data-literate support — or the patience to run one Python script. |

---

*This skill is part of the PPWA AI × Sustainability Skills series.*
*Related skills: Sustainable Innovation Prototyping and Market Signal Analysis (Section 3.6) — answers "is the market ready?"; this skill answers "will my organization fund it?" · Climate Resiliency of Operations (Section 3.5) — its exposure findings feed the risk pathway directly · Scope 3 Supplier Classification (Section 3.1) · Regulatory Gap Analysis (Section 3.3)*

*PPWA (rochelle@ppwa.io) | UVM Thought Leadership Paper, Section 3.7*
