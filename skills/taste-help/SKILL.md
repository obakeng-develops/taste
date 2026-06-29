---
name: taste-help
description: List the taste skills and how they fit together. Use when the user says "taste help", "taste-help", "/taste-help", "what taste commands", or "how do I use taste". One-shot reference card.
---

# Taste — help

Output this card verbatim, then stop. No extra prose.

---

**Taste** — noticing what feels great, then reproducing it on purpose. Two domains:
interfaces and prose. Four skills, one shared library.

- **/taste** — build with taste. Auto-loads on design or writing work.
  The model: kill jank → affordances → story (interfaces); cut clutter → plain
  words → active verbs → voice (prose, per Zinsser).
- **/taste-learn** — capture a reference. Share a link, screenshot, product, or
  passage; it records *what / why / steal* into the library.
- **/taste-audit** — critique one screen, URL, component, or passage.
  Ranked findings, floor-first, no fixes applied.
- **/taste-sweep** — audit the whole codebase for taste patterns, ranked by blast
  radius. Read-only. Use /taste-audit for a single target instead.
- **/taste-help** — this card.

**The library:** `~/.claude/taste/references.md` — your saved examples and the
*why* behind each. /taste reads it to build; /taste-audit judges against it; /taste-learn
grows it. Seeded from the plugin's template on first use. The *why* is the point —
a bare link teaches nothing.

**The loop:** learn → build → audit → capture what the audit surfaced → repeat.
