# Supplier Sustainability Assessment — Introduction

**Skill file:** `Supplier-Sustainability-Assessment-SKILL.md`
**Tier:** 2 — Augment. It runs as a structured, multi-step sequence rather than one single request, and works best with someone who already knows roughly what sector and category the supplier sits in
**Who it's for:** Procurement, sourcing, or Environmental, Social and Governance (ESG) professionals who need to assess supplier sustainability maturity in any sector — not just agriculture

---

## What this skill does

You tell Claude what sector and input category a supplier operates in, and it generates a tailored set of sustainability questions for that context — then scores the supplier across six weighted dimensions using whatever evidence you provide (Request for Proposal (RFP) responses, sustainability reports, human rights or labor policy documents, interview notes). It produces a structured scorecard with an overall rating, a sourcing recommendation, and a prioritised list of follow-up questions.

This is a sector-general counterpart to the RegenAg Supplier Assessment skill in the PPWA RegenAg Toolkit. Use this one for manufacturing, apparel, technology, professional services, or any category outside agriculture — or when comparing suppliers across different sectors within the same procurement decision.

## Why it matters

Supplier sustainability questionnaires are usually built from scratch per category, or borrowed from a template that doesn't fit the sector well — leading to irrelevant questions, inconsistent scoring between reviewers, and suppliers penalised for gaps that were never realistic to expect from them. This skill fixes the scoring logic once (six dimensions, three evidence tiers) and adapts only the questions and weighting to the sector, so results stay comparable across a mixed supplier base while still reflecting what's actually material to each one.

A dedicated **Social, Human Rights & Governance Maturity** dimension carries an explicit, visible weight (20% by default, adjustable by sector) rather than sitting implicitly inside a general "practice" score — labor rights, human rights due diligence, business ethics/governance, and diversity, equity and inclusion (DEI) practices are assessed on the same footing as environmental performance, not as an afterthought to it.

## Before you start: what you'll need

| What | In plain terms |
|------|----------------|
| Supplier sector and primary input | A short description — e.g., "apparel manufacturer, cut-and-sew" or "professional services, IT consulting" |
| Available supplier information | RFP responses, sustainability reports, certifications, human rights or labor policy documents, or interview notes — as much or as little as you have |
| A sense of what's material to this category | Not required, but helpful — Claude will propose dimension weight adjustments in Step 1 and confirm with you, including for known labor, human rights, or governance risk factors |

## What happens when you run it

This is a four-step sequence, and the steps build on each other in order:

1. **Sector & sourcing context** — Claude asks what sector the supplier is in, what they supply, any relevant certifications, known labor/human rights/governance risk factors, and whether default dimension weights need adjusting for materiality.
2. **Tiered framework generation** — Claude generates a sector-adapted question set (standard asks, stretch asks, forward-looking asks) using the Dimension Adaptation Guide in the skill file.
3. **Input collection** — you provide available supplier information against that generated framework.
4. **Scoring & output** — Claude scores the supplier across six dimensions and produces the structured scorecard.

**Plan for 30–60 minutes** for a single supplier with reasonably complete information; longer if you're assembling a multi-supplier comparison.

## What you'll get back

A summary scorecard (six dimensions, scores, weights, evidence tier, key gaps), an overall rating (Leading / Progressing / Emerging / Early stage / Conventional), dimension-by-dimension narrative summaries — including a dedicated Social, Human Rights & Governance Maturity summary — key strengths, prioritised follow-up questions, and a sourcing recommendation (Prioritise / Develop / Monitor / Deprioritise).

## Good to know

- **Scores reflect evidence quality, not just practice quality.** A supplier with strong practices but weak documentation will still score lower — treat that gap as a procurement follow-up item, not a final judgment.
- **This does not replace on-site verification, third-party social audit (e.g., SMETA, SA8000, WRAP), or a formal human rights impact assessment.** Use it to prioritise suppliers for deeper engagement.
- **A high environmental score does not offset a known, unaddressed social or human rights risk.** A known labor or human rights risk with no credible remediation plan should be flagged prominently in the Sourcing Recommendation regardless of how strong the supplier looks elsewhere.
- **Cross-sector comparisons are directional.** If you're comparing suppliers from different sectors, Claude runs Steps 1–2 separately for each and flags that weighting and evidence expectations differ before presenting a combined table — this matters especially for the Social, Human Rights & Governance dimension, where baseline risk varies widely by sector and geography.
- **If a supplier's sector doesn't map cleanly to the illustrative examples in the Dimension Adaptation Guide**, ask Claude to reason from the same six underlying dimensions rather than forcing a mismatched fit.

## How to run it

1. Open Claude and share `Supplier-Sustainability-Assessment-SKILL.md` as context.
2. Answer the Step 1 calibration questions about sector, input category, known certifications, and any known labor/human rights/governance risk factors.
3. Provide available supplier information against the generated framework.
4. Ask: *"Assess this supplier using the Supplier Sustainability Assessment skill."*
5. For multiple suppliers, provide inputs for each and ask for a combined comparison table.
