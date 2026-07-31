# Sustainable Innovation & Market Signal Analysis — Introduction

**Skill file:** `SustainableInnovation-MarketSignal-SKILL.md`
**Tier:** 2 — Augment skill that runs as a structured sequence with live web search, not a single request
**Who it's for:** Innovation or sustainability teams, or consultants, deciding whether a new sustainable product, service, or business model idea is worth investing in — before committing real budget to it

---

## What this skill does

You describe an innovation concept — a new material, service, or business model — and this skill scans four areas of the outside world (regulation, competitors, investors, and customer demand) to answer one question: **is the market ready for this, right now?** It produces a structured signal register and a clear Go / Pause / Pass recommendation with reasoning.

## Why it matters

Sustainable innovation tends to fail two ways: moving too early, before regulation or capital or demand catches up, or moving too late, after a competitor or a new mandatory rule has already claimed the opening. The signals that tell you which situation you're in are public, but scattered across policy documents, funding announcements, and industry press — pulling them together by hand takes two to four weeks. This skill does it in closer to a day.

## Before you start: what you'll need

| What | In plain terms |
|------|----------------|
| Concept description | One paragraph: what the innovation is, the problem it solves, and who it's for |
| Innovation type | Is this a physical product, a service, a new business model, or an internal process change? |
| Sector and geography | What industry, and which market (a concept can be a "Go" in one region and a "Pause" in another) |
| Decision context | What this analysis will actually be used for — a board discussion, a formal investment committee gate, a client recommendation |
| Time horizon | Are you asking about the next 12–18 months, or the next 2–5 years? |

**Important:** all five of these genuinely change the answer — geography especially. Before running the scan, Claude will ask you to confirm each one rather than guessing. If you'd rather not answer everything up front, you can explicitly tell Claude to use its own judgment — it will proceed, but will clearly label which inputs it assumed, so you know the result is directional rather than fully confirmed.

## What happens when you run it

Five steps, run in sequence:

1. **Scoping** — locks down the concept and identifies adjacent markets worth watching.
2. **Regulatory and policy scan** — is regulation pushing this forward (a tailwind), creating friction (a headwind), or still unresolved (a watch item)?
3. **Competitor and market moves scan** — who else is already doing this, and what does their activity signal?
4. **Investor and capital scan** — is funding flowing toward this space, or conspicuously absent?
5. **Consumer and demand scan** — do customers actually want this, and are they willing to pay for it?

Along the way, if sources disagree — for example, five different reports citing wildly different market size figures — the skill won't quietly pick the most flattering number. It will show you the range and explain why sources might disagree.

Two optional add-ons are available if you want more depth before a big decision: a **technology readiness** check (why exactly is a flagged headwind, like cost, actually true?) and a **failure analysis** (why have similar ideas failed before, and are you exposed to the same problem?).

## What you'll get back

A signal register organized by category, a plain-language summary of each category, and a final verdict — **Go** (pursue now), **Pause** (promising, but something specific needs to resolve first), or **Pass** (not now, and here's why) — along with what would need to change to flip that verdict.

**Strongly recommended:** once you have a verdict, run the optional **adversarial review** in a brand-new Claude conversation. Hand it the finished analysis and ask it to actively try to poke holes in it. This step has already surfaced real issues in testing — like a verdict that quietly assumed a favorable geography, or a headline figure picked from conflicting sources without disclosing the disagreement. A verdict that survives this review is much more trustworthy than one that hasn't been challenged.

## Good to know

- This is a structured intelligence tool, not investment advice or formal market research — for large capital decisions, pair it with primary research.
- The verdict doesn't account for things only you know: your organization's risk appetite, internal capability, or existing customer relationships. Weigh those in yourself.
- Run this close to your actual decision date — the regulatory and funding landscape in this space moves quickly, and older scans go stale.

## How to run it

1. Open Claude **with web search enabled** and share `SustainableInnovation-MarketSignal-SKILL.md` as context.
2. Answer the calibration questions and confirm your five required inputs (or explicitly hand judgment calls to Claude).
3. Work through the five-step scan in order.
4. Review the signal register and verdict.
5. Before acting on it, run the adversarial review in a new session — it's optional, but worth the extra 15 minutes.
