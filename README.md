# The Sustainability Skills Library

**An open-source collection of AI-assisted workflows for sustainability practitioners.**

Maintained by the University of Vermont (UVM) Sustainable Innovation Master of Business Administration (MBA) program, in partnership with People Places Words Actions (PPWA).

## About this repository

This repository holds a growing library of "skills" — free, open, plain-text working methods that let an AI assistant like Claude carry out real sustainability workflows: classifying emissions data, drafting disclosure sections, mapping regulatory gaps, assessing suppliers, scanning markets for readiness signals, modeling climate risk, and building the internal business case for sustainability initiatives, among others.

Every skill is designed to be downloaded, run against your own data, inspected, and improved. Nothing in the core library requires a purchase, a subscription, or an application programming interface (API) key.

## The report behind this library

This library is the companion resource to *From Compliance to Catalyst: How AI Is Enabling Positive Sustainability Impact*, a report produced through the PPWA × UVM Sustainable Innovation MBA collaboration. The report argues that artificial intelligence's (AI's) most consequential role in sustainability work is not simply speeding up compliance, but freeing practitioner time and judgment for the work that changes outcomes: deciding where to focus, building the case for action, and directing resources toward measurable results. Read the full report for the reasoning, the research behind it, and practitioner perspectives from across the field. This README focuses on the library itself.

## What a skill is

A skill is a markdown file that encodes a complete working method for an AI assistant: the background knowledge it needs, the sequence of steps it follows, the questions it asks the user, the evidence rules it enforces, and the exact output format it produces. Skills in this library follow the Agent Skills open standard, so the same file works across Claude.ai, Claude Code, and other compatible environments. A skill is not software in the traditional sense, it has no server and no subscription, and anyone can open the file and read exactly what it does.

Each skill ships with a plain-language companion guide written for non-technical practitioners, covering what the skill does, why it matters, what to prepare before running it, and what comes back.

## A framework for evaluating impact

Every skill in this library is tagged against a simple three-tier framework for what AI actually changes:

**Tier 1 — Support.** Compresses work you already do: same output, less time.

**Tier 2 — Augment.** Surfaces patterns and exposures that weren't visible before — a second analyst that reads everything and flags what it can't verify.

**Tier 3 — Discover.** Enables analysis and decisions that weren't previously possible at all, because the underlying research would otherwise take weeks or an enterprise budget.

The tier describes the depth of impact, not a difficulty rating — some Tier 1 skills matter enormously to a small team, and the tiers are cumulative rather than a hierarchy of value.

## Getting started

To run a skill: open Claude, attach the relevant skill file as context, upload or paste your data, and ask Claude to run it. Most skills begin by asking a few calibration questions — your familiarity with the topic, and whether the output is headed for internal use or external review — so the depth of the result matches your needs. For any output headed toward a decision-maker, auditor, or regulator, running a second, independent session to critique the first session's result is good practice.

Individual skills and their companion guides are organized within this repository; start with whichever workflow matches the problem in front of you.

## Why open source

Publishing openly serves three purposes. It makes the method auditable — sustainability outputs increasingly face verifiers and regulators, and a method that can't be inspected can't be defended. It allows adaptation — every organization's data, sector, and materiality profile differs, and an open file can be forked and adjusted in ways a closed product cannot. And it supports learning — reading a skill is itself a lesson in how to structure a rigorous AI-assisted workflow.

## Responsible use

AI in sustainability work is only useful if its outputs can survive scrutiny. Skills in this library are built around a small set of non-negotiable principles: no unsourced numbers or filled-in data gaps, every claim tagged to its evidence source, low-confidence outputs flagged rather than smoothed over, and the consequential judgment calls — materiality, prioritization, final disclosure language — left with the human practitioner. See the full report for the complete responsible-use discussion, including data privacy and AI's own environmental footprint.

## Contributing and institutional home

This library is designed to grow. The University of Vermont Sustainable Innovation MBA hosts it as an ongoing, community-built resource: students test and extend skills as coursework, practitioners contribute workflows from real engagements, and the program curates for quality and coherence over time.

There are three ways to contribute a skill:

1. **Submit a pull request.** Fork this repository, add or edit a skill following the existing file conventions (a skill file plus a plain-language companion guide), and open a pull request for review.  
2. **Add a skill directly**, if you have contributor access to this repository — commit it to the relevant location and flag it for review.  
3. **Email a skill for review.** Send the skill file, a short description of the problem it solves, and any supporting materials to [march.rochelle@uvm.edu](mailto:march.rochelle@uvm.edu), and it will be reviewed for inclusion.

However you contribute, please include the same information every skill in this library carries: what problem it solves, what inputs it needs, what evidence rules it enforces, and what tier of impact it delivers. Thank you!

## Attribution and contact

Developed by Rochelle March, PPWA and University of Vermont Sustainable Innovation MBA.

Questions or contributions: [march.rochelle@uvm.edu](mailto:march.rochelle@uvm.edu)  
