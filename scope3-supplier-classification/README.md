# Scope 3 Supplier Classification — Introduction

**Skill file:** `Scope3-Supplier-Classification-SKILL.md`
**Tier:** 1 — no coding required, runs directly in Claude.ai with a file upload
**Who it's for:** Sustainability or procurement professionals with basic familiarity with Scope 3 accounting who need to turn a spend list into a Greenhouse Gas (GHG) Protocol category breakdown

---

## What this skill does

You upload a list of what your company spent money on — suppliers, categories, amounts — and this skill sorts it into the 15 official Scope 3 categories defined by the GHG Protocol (the global standard for corporate emissions accounting), estimates the emissions behind each line, and flags anything it isn't confident about rather than guessing silently.

## Why it matters

For most mid-to-large companies, Scope 3 Category 1 (purchased goods and services) is 60–80% of total emissions — the single biggest number in the inventory. Sorting a spend file into categories by hand typically takes a sustainability analyst 2–4 weeks per reporting cycle and produces inconsistent results between reviewers. This skill compresses that to hours and keeps a documented rationale for every classification decision, which matters if a third party later verifies your numbers.

## Before you start: what you'll need

| What | In plain terms |
|------|----------------|
| A spend file | Either a list of supplier names with dollar amounts (an **accounts payable**, or **AP**, export — preferred), or a **General Ledger (GL)** or **Trial Balance (TB)** export organized by spend category rather than supplier name (also accepted — see note below) |
| Reporting year | The fiscal or calendar year the spend covers |
| Company type | A short description of your industry — this skill is tuned for Consumer Packaged Goods (CPG) companies but can be adapted |
| Anything to exclude | Categories that shouldn't count, e.g. payroll or bank fees |

**If you only have a General Ledger or Trial Balance (not supplier-level detail):** that's fine. It's a lower-precision starting point — the skill can't deduplicate supplier names or build a true "top suppliers" list from it — but it still produces a category-level emissions estimate, and it flags where getting supplier-level detail later would sharpen the picture.

You don't need a perfectly clean file. Messy, duplicated supplier names and ambiguous line items are expected — the skill is built to handle and flag that, not to require pristine data first.

## What happens when you run it

The skill works through four stages:

1. **Cleans up supplier names** — merges obvious duplicates (e.g. "Tetra Pak Inc" and "TETRA PAK" become one entity), and separately flags the merges it isn't sure about for you to confirm.
2. **Sorts each line into a GHG Protocol category** — ingredients, packaging, freight, waste, travel, and so on — with a confidence rating (High/Medium/Low) and a one-line reason for each call.
3. **Estimates emissions** — applies a standard, publicly documented emissions factor to each spend line to produce a tonnes-of-CO2-equivalent estimate.
4. **Rolls everything up and flags gaps** — summarizes totals by category, ranks your highest-emitting suppliers, and lists exactly what's unclassified or low-confidence.

Before it starts, the skill will ask you two quick questions — how familiar you are with this topic, and whether you want the full detailed output or a higher-level summary. Answer honestly; it changes how much explanation gets built into the result.

## What you'll get back

A structured report with: a log of the supplier name cleanup, a category-by-category spend and emissions summary, the full line-by-line classification table, your top 10 highest-emitting suppliers, a list of data gaps and low-confidence items, and a short list of **data quality** next steps (confirming uncertain merges, reclassifying ambiguous lines, chasing down missing detail).

**Note:** that last section is deliberately limited to fixing the classification itself. It won't tell you what to do strategically about your top emitters — that's a separate conversation, informed by this output but not part of it.

## Good to know

- This is a screening tool, not a final answer. It's built to identify hotspots and prioritize where to focus — for anything going to a verifier or investor, material categories should eventually be backed by more precise data.
- Low-confidence flags are there on purpose. Don't strip them out before sharing the output with a colleague or auditor.
- It doesn't replace a full Scope 3 inventory methodology — it accelerates the classification step within one.

## How to run it

1. Open Claude and share `Scope3-Supplier-Classification-SKILL.md` as context.
2. Upload your spend file.
3. Ask: *"Classify my supplier spend data using the Scope 3 Supplier Classification skill."*
4. Answer the two calibration questions Claude asks, then review the output — pay closest attention to anything flagged Low confidence.

A ready-to-use practice file (`BrightBoldFoods_FY2025_Procurement_DUMMY.csv`) is included alongside the skill if you want to try it before using real company data.
