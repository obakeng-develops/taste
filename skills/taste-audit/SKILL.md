---
name: taste-audit
description: Audit an interface or a piece of writing against the taste model and the user's reference library. Use when the user says "taste audit", "taste-audit", "is this any good", "critique this", "what's wrong with this UI", "edit this copy", or shares a screen, URL, component, or text for a taste pass. One-shot report ranked by severity; applies no fixes (use /taste to build, /taste-learn to capture).
---

# Taste — audit

Critique one target against the taste model. Report only — no edits.

## Target (args or this message)
- **Screenshot or image** → read it.
- **URL** → WebFetch and judge the rendered result.
- **Front-end code / component / CSS** → read it, infer how it renders.
- **Writing** (copy, doc, message, name) → judge it as prose.
- Nothing → ask one line what to audit.

## Calibrate first
Read the taste library at `~/.claude/taste/references.md` (if it exists). Judge
against the user's taste, not a generic ideal. If a finding fights a saved
reference, the reference wins.

## What to check

**For interfaces — three layers, in order:**
1. **Jank:** alignment/grid, typeface count, body text (15–25px, line-height
   1.3–1.45, 45–90 chars/line), spacing rhythm, drift.
2. **Affordances:** does each element show how it works? Right control for the job?
   Broken conventions — on purpose or by accident?
3. **Story:** does the flow have an arc? Does hierarchy answer the real question
   first? Are empty, error, and success states there? Restraint or clutter?

**For writing — Zinsser:**
- **Clutter:** dead words, "in order to", "the fact that", empty qualifiers,
  adverbs that repeat the verb.
- **Plain words:** fancy where simple would do; jargon.
- **Verbs and voice:** passive where active is stronger; weak verbs.
- **One thought per sentence; warm, human voice.**
- Read it aloud in your head — flag what stumbles.

## Report
Open with a one-line verdict. Then findings in severity order, **one line each**,
location plus the specific fix:
- **Jank / Clutter** — floor problems; cheap and high-leverage, fix first.
- **Affordance / Clarity gaps** — confusing controls, or unclear sentences.
- **Story / Voice misses** — weak arc or missing states; flat or stiff prose.
- **Polish** — optional.
Close with the single highest-leverage change.

## Rules
- Be specific. Name the mechanism, not "feels off".
- Praise only what teaches — and suggest /taste-learn to capture it.
- No fixes applied. This is diagnosis. Skip empty buckets; don't pad.
