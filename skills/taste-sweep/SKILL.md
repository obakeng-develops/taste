---
name: taste-sweep
description: Sweep a whole codebase for design and prose taste, not one screen. Use when the user says "taste sweep", "taste-sweep", "audit the codebase for taste", "audit the repo for design", "where's the jank", or "find taste debt". Produces a ranked report of what to fix across the front-end and user-facing text. Read-only — applies no fixes. For a single screen or passage, use /taste-audit instead.
---

# Taste — sweep

Audit a whole codebase for taste. Find the patterns, not one-off nits. Report only.

## Calibrate first
Read the taste library at `~/.claude/taste/references.md` (if it exists). Judge
against the user's taste, not a generic ideal. A finding that fights a saved
reference loses.

## Map the surface
Don't read every file. Find the surface, then sample what carries the most weight.
- **Design system:** tokens, theme, global CSS, the shared component library. Drift
  here multiplies everywhere — start here.
- **High-traffic screens:** entry points, the main flow, anything money- or auth-shaped.
- **User-facing text:** button labels, empty/error/success copy, headings, toasts,
  validation messages — grep the string surface.
Use Explore/Grep to locate; for a large repo, fan out with subagents (or a workflow
if the user opts in). Sample representative files; say what you sampled and skipped.

## What to look for — patterns, ranked by blast radius
1. **Systemic jank:** more than one typeface family; ad-hoc spacing/colors instead of
   tokens; inconsistent radius, shadow, or alignment; body text outside 15–25px /
   line-height 1.3–1.45 / 45–90 chars.
2. **Affordance rot:** wrong control for the job repeated across screens; conventions
   broken by accident; inconsistent interactive states (hover/focus/disabled).
3. **Story gaps:** missing empty/error/success states; hierarchy that buries the
   user's real question; flows with no arc.
4. **Prose clutter (Zinsser):** copy thick with dead words and qualifiers; passive
   voice and weak verbs in UI text; jargon; stiff, voiceless microcopy.

## Report
Open with a one-line verdict on the codebase's taste health. Then findings ranked by
blast radius — widest first — **one line each**: pattern, where it lives
(`file:line` or "across N components"), the fix. Group as:
- **Systemic jank / clutter** — fix first; one change, many screens.
- **Affordance / clarity rot**
- **Story / voice gaps**
- **Polish**
Close with the single highest-leverage change and a rough count of what you didn't sample.

## Rules
- Hunt repeated patterns; a one-screen nit belongs in /taste-audit, not here.
- Name the mechanism and the blast radius, not "feels off".
- No fixes applied. Skip empty buckets. Flag what you sampled vs skipped — silent
  truncation reads as "covered everything" when it didn't.
