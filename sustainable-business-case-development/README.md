# Sustainability Business Case Builder — Introduction

**Skill file:** `SustainabilityBusinessCase-Builder-SKILL.md`
**Tier:** 3 — a discover skill with two modes: a file-based mode anyone can run, and an optional Python-scripted mode that produces finance-grade numbers
**Who it's for:** Sustainability, operations, or innovation teams — or consultants working for them — who know *what* they want to do and now need to win the internal budget fight to fund it

---

## What this skill does

You describe a sustainability initiative — a packaging conversion, an energy programme, a supplier investment — and this skill builds the funding case for it. It models value across four pathways (cost reduction, risk mitigation, revenue opportunity, and brand), stress-tests the assumptions the case depends on, and then writes the pitch in the language of the specific person who controls the budget: a Chief Financial Officer (CFO) hears payback and downside protection; a board hears strategy and risk; a commercial lead hears customer requirements.

Crucially, it builds the case as a **pipeline, not a one-off document**: the assumptions live in a register you update and re-run when an energy price moves or a regulation firms up — so next budget cycle takes half a day, not three weeks.

## Why it matters

The hardest thing in corporate sustainability isn't knowing what to do — it's building the internal case to fund it. Sustainability initiatives lose budget decisions for a structural reason: their value is scattered across four pathways owned by four different departments, so any case written from inside one function misses most of the picture. And cases padded with unsourced numbers ("consumers will pay 10% more") get taken apart in exactly the meetings that matter. This skill assembles the full value picture in one place and enforces a simple rule: **every number carries a tag** showing where it came from — your data, a named published source, or a stated assumption.

## Before you start: what you'll need

| What | In plain terms |
|------|----------------|
| Initiative description | What would be done, over what period, at roughly what cost |
| A named decision-maker | Who actually decides, through what gate — "the CFO at the March capital committee" works; "leadership" doesn't |
| Organization context | Sector, rough revenue, where you operate |
| Time horizon | Usually 3, 5, or 10 years |
| Internal figures (optional but powerful) | Energy costs, material spend, fee schedules — every real figure you provide replaces a guess |
| For Mode B only | Your organization's hurdle rate (ask finance), plus a computer that can run one Python script |

## What happens when you run it

1. **Initiative brief and decision-maker mapping** — locks down what's proposed, what happens if you do nothing, and what this specific decision-maker actually cares about.
2. **Cost reduction scan** — direct savings, fee and tax effects, and honest accounting of transition costs.
3. **Risk mitigation scan** — the losses the initiative protects against, expressed as probability × severity, never as adjectives.
4. **Revenue opportunity scan** — starting with revenue *protection* (customer requirements you'd otherwise fail), the strongest and most conservative revenue argument.
5. **Brand and intangible scan** — captured honestly as directional support; the financial case is built to stand without it.
6. **Assumption register and stress test** — every assumption in one table, ranked by how much it moves the result, with the two or three that could flip the decision named explicitly.

**Mode B (optional):** export the register as a spreadsheet, run the included Python script, and get finance-grade outputs — Net Present Value (NPV), payback period, and a Monte Carlo simulation that produces sentences like *"the initiative is NPV-positive in 87% of 10,000 simulated scenarios."*

## What you'll get back

An integrated value case with every number tagged by evidence quality; a pitch narrative calibrated to your decision-maker; an **objection pre-brief** — the five objections you'll actually face, with the strongest honest response and a fallback position for each; and (Mode B) the probability-weighted financials.

**Strongly recommended:** before the meeting, run the **adversarial review** in a brand-new Claude conversation — hand it the finished case and ask it to act as the skeptical CFO. It routinely catches double-counting and over-confident numbers that the build process can't see about itself.

## Good to know

- Mode A alone is complete and pitch-ready — don't wait for Mode B if you don't have scripting support.
- Risk value ("expected loss avoided") is real value but not cash — the skill labels it separately so a skeptic can't accuse you of mixing the two.
- If the case only works when the brand estimate is included, it isn't ready for a funding gate — the skill will tell you so.
- Keep the assumption register after the decision. If the case is declined, you log the objections, set a revisit trigger, and come back with "here's what changed" — the strongest re-submission opening there is.
- This is a decision-support tool, not financial advice — cases above a material threshold should be checked by a finance partner.

## How to run it

1. Open Claude and share `SustainabilityBusinessCase-Builder-SKILL.md` as context (use Claude Code if you want Mode B to run automatically in-session).
2. Answer the three calibration questions, then confirm the required inputs — the decision-maker map especially.
3. Work through Steps 1–6 in order, gathering the internal figures Claude requests along the way.
4. Generate the integrated case, the stakeholder narrative, and the objection pre-brief.
5. Mode B: export the assumptions CSV, run `business_case_model.py` (instructions in the skill file), and feed the results back in.
6. Before submitting: run the adversarial review in a fresh session.
