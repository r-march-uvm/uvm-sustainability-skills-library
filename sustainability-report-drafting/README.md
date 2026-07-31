# Sustainability Report Drafting — Introduction

**Skill file:** `SustainabilityReport-Drafting-SKILL.md`
**Tier:** 1 — supporting the work by doing it faster, no coding required, runs directly in Claude.ai with a file upload
**Who it's for:** Sustainability professionals drafting sections of an annual report, CDP (Carbon Disclosure Project) questionnaire, or climate disclosure for an investor or Environmental, Social and Governance (ESG) analyst audience

---

## What this skill does

You give Claude your performance data, targets, and (ideally) last year's report language, and it drafts a specific section of your sustainability report in polished, framework-aligned prose — while refusing to invent any number or claim you didn't give it.

## Why it matters

A single unsourced statistic or overstated claim in a sustainability report can trigger greenwashing allegations or fail assurance review. This skill is built around one rule: **Claude writes only from data you supply.** Where information is missing, it inserts a visible placeholder instead of filling the gap with a plausible-sounding guess. Those placeholders double as your to-do list — a complete record of what needs confirming before the section can go to review.

## Before you start: what you'll need

| What | In plain terms |
|------|----------------|
| Company name, sector, reporting year | Basic context |
| Which section(s) you want drafted | See the menu below — **you choose**; the skill doesn't decide this for you |
| Performance data | The actual numbers the section reports on (see "what counts as performance data" below) |
| Confirmed targets | Only ones your board has actually approved and published — not internal drafts or ambitions |
| Prior-year report text (recommended) | Helps Claude match your existing voice |

**What counts as "performance data"?** It's whatever numbers the section is about — for a climate section, that's your Greenhouse Gas (GHG) emissions by scope; for a workforce section, headcount or safety metrics. Just as important as the numbers themselves: the methodology behind them (what's included, what year, how it was calculated, whether it's been assured). If you upload only a bottom-line total with no methodology notes, the skill will flag that gap explicitly rather than draft around it.

## The section menu

The skill can draft: climate and environment performance, supply chain and Scope 3, social and workforce performance, governance and ethics, the materiality narrative, a CEO/leadership message, performance data tables, or forward-looking statements. **You tell Claude which of these to draft — it will not add sections you didn't ask for**, and it won't assume that drafting one section means the others aren't needed.

## What happens when you run it

Before drafting, Claude asks two quick questions — how familiar you are with the frameworks involved, and whether this draft is headed for external publication or is an internal working version — to calibrate how much it explains along the way. It then confirms the "no data, no claim" rule with you, drafts the section, and tags every quantitative claim with an inline source reference.

**Built-in guardrails you should know about:**
- **No claim without data.** Missing figures become `[DATA REQUIRED: ...]` placeholders, not filled-in estimates.
- **No unapproved next steps, anywhere in the draft.** If the data implies a logical next move (e.g. "next year we'll shift to primary supplier data"), Claude won't state it as decided — it flags it as a suggestion for you to confirm or reject.
- **Greenwashing checks throughout**, not just in the leadership section: no unearned superlatives, no directional claims ("emissions are declining") without a baseline to compare against, no product claims ("recyclable," "sustainably sourced") without a certification behind them, and no carbon credit claims that aren't benchmarked against a recognized standard.

## What you'll get back

The drafted section, a table of every data placeholder still needing to be filled in, a source register mapping each claim back to where it came from (handy to hand to an assurance provider), and a list of editorial flags — places Claude thinks language may need legal or leadership sign-off before publication.

## Good to know

- Claude can't verify your numbers are accurate — only that everything in the draft traces back to something you provided.
- Forward-looking statements should always get a legal and Investor Relations (IR) review regardless of how they were drafted.
- If you skip prior-year report text, the draft will be accurate but may not match your usual voice.

## How to run it

1. Open Claude and share `SustainabilityReport-Drafting-SKILL.md` as context.
2. Provide your inputs and tell Claude which section(s) you want.
3. Ask: *"Draft [section name] of our sustainability report using the Sustainability Report Drafting skill."*
4. Answer the calibration questions, confirm the no-data-no-claim rule, then review — resolve every placeholder and editorial flag before this goes anywhere near assurance or publication.

