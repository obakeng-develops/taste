---
name: taste-learn
description: Capture a new taste reference into the taste library. Use when the user says "learn this", "add to my taste refs", "taste-learn", or shares a link, screenshot, product, or piece of writing they want remembered. Works for interfaces and prose. Extracts the *why* and the reusable move, then appends an entry to the taste library at ~/.claude/taste/references.md.
---

# Taste — learn

Capture one reference. The point is the **why**, not the link.

## Input (args or this message)
- A **URL** → WebFetch it. Judge the design or the writing, not the page chrome.
- A **screenshot or image** in chat → read it.
- A **piece of writing** (copy, doc, name, message) → read it as prose.
- A **product or feature named in prose** → use what the user says plus what you know.
- Nothing clear → ask one line: "What am I learning, and what works or fails?"

## Do
1. Find the single sharpest thing that works or fails. Name the mechanism in taste
   terms — alignment, hierarchy, affordance, the arc, restraint; or for prose,
   clutter cut, plain words, active verbs, voice. Anti-patterns count too.
2. Distill the move worth stealing.
3. Append to the library at `~/.claude/taste/references.md` in its format:
   What / Why it works or fails / Steal. One tight line each. If the library
   doesn't exist yet, create `~/.claude/taste/` and seed it from
   `references.template.md` in the `taste` skill's directory first.
4. Put new entries above the `<!-- Append new references below. -->` marker.
5. Confirm what you added in one line. Don't lecture.

## Rules
- One reference per call, unless the user lists several.
- A link with no *why* is not a reference. Derive the why or ask.
- Match the brevity of the entries already there.
