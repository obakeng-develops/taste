# Taste

A Claude Code plugin for building with taste — in interfaces and in prose.

Taste is noticing what makes something feel great, then reproducing it on purpose.
You learn it by exposure, not birth. This plugin gives the model that lens and a
place to keep your own examples, so your front-ends and your writing get the same
deliberate eye.

It works in two domains at once:

- **Interfaces** — kill the jank (alignment, one typeface, real body-text sizes),
  honor affordances, then shape the story so the biggest type answers the user's
  real question.
- **Prose** — cut the clutter, plain words, active verbs, one thought per sentence,
  a warm human voice (William Zinsser, *On Writing Well*).

## The skills

| Skill | What it does |
|---|---|
| `/taste` | Build with taste. Auto-loads when you design, write front-end, or draft user-facing text. |
| `/taste-learn` | Capture a reference — a link, screenshot, product, or passage — as *what / why / steal*. |
| `/taste-audit` | Critique one screen, URL, component, or passage. Ranked findings, floor first, no fixes applied. |
| `/taste-sweep` | Sweep a whole codebase for taste patterns, ranked by blast radius. Read-only. |
| `/taste-help` | A one-card reference of the above. |

**The loop:** learn → build → audit → capture what the audit surfaced → repeat.

## The library

Your taste lives in `~/.claude/taste/references.md` — saved examples and the *why*
behind each. `/taste` reads it to build, `/taste-audit` judges against it, and
`/taste-learn` grows it. It's seeded from a template on first use, then it's yours
to grow. The *why* is the point; a bare link teaches nothing.

## Install

```
/plugin marketplace add obakeng-develops/taste
/plugin install taste@taste
```

Then start designing or writing — `/taste` loads on its own — or run any of the
commands above. (Adjust the marketplace path to wherever you host this repo.)

## Updating

Turn on auto-update once and Claude Code pulls new versions at startup:

```
/plugin
```

Go to **Marketplaces → taste → Enable auto-update**. When an update lands, Claude
Code prompts you to `/reload-plugins`.

To update by hand instead:

```
/plugin marketplace update taste
/reload-plugins
```

Your library at `~/.claude/taste/references.md` lives outside the plugin, so
updates never touch your saved references.

## Credits

The model stands on others' work:

- **PostHog — Good Taste & Great Products** — taste is learnable; affordances, jank,
  prototyping, feeding your taste.
- **Practical Typography (Matthew Butterick)** — body text is most of typography.
- **Ellen Lupton — Design is Storytelling** — flows as narrative arcs.
- **Don Norman — The Design of Everyday Things** — visceral, behavioral, reflective.
- **William Zinsser — On Writing Well** — clear writing is clear thinking.

## License

MIT — see [LICENSE](LICENSE).
