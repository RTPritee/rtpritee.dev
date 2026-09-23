# Pritee Profile Design System v2 — "Build Log"

A text-first design language, built to read like an engineering journal rather than a landing page. No hero banner, no wall of badge icons — structure and typography carry the identity instead of decoration.

## 1. Concept

The organizing idea: **show the work as a log, not a gallery.** Repos are grouped and *collapsed by default* (the reader chooses what to open), the intro is a `whoami` code block instead of a centered tagline, and the stack is typed out as inline code instead of rendered as logo badges. This keeps the page scannable in one screen and puts emphasis on what's currently being built, not on decoration.

## 2. Color tokens

Rose (identity) + slate (structure) — deliberately different from typical blue/violet dev-profile palettes so stat cards still feel distinct even though badges are gone.

| Token | Light mode | Dark mode | Used for |
|---|---|---|---|
| `color-primary` | `#9F1239` | `#FB7185` | Stat-card titles, link hover accents |
| `color-accent` | `#334155` | `#94A3B8` | Stat-card icons, secondary text |
| `color-text` | `#1F2328` | `#E6EDF3` | Body text on generated cards |
| `color-bg` | transparent | transparent | Card backgrounds (inherits GitHub's own) |
| `color-success` | `#15803D` | `#4ADE80` | "shipping now" markers |

## 3. Typography & voice

| Token | Value | Usage |
|---|---|---|
| `type-code-intro` | fenced ` ```text ` block | Opening identity block, key: value pairs, lowercase keys |
| `type-h3-section` | `### lowercase heading` | Section headings — lowercase, no emoji-per-heading (one optional emoji max, in `<summary>` only) |
| `type-body` | Sentence case, terse | "now" section: present-tense, one clause per bullet |
| `type-chip` | inline code `` `Like This` `` | Stack/tech listed as typed tokens, not logo images |

Voice: first person, present tense, no marketing adjectives ("robust", "cutting-edge"). State what the project does, not how impressive it is.

## 4. Structure (fixed order — this is what differs most from a typical profile README)

1. **`whoami` block** — plain fenced code, not a centered `<h1>`
2. **`now`** — 2–3 bullets, only what's actively being worked on
3. **repo groups as `<details>`** — collapsed by default, one `<details>` per theme, opened by the reader
4. **`stack`** — inline code chips, grouped by line (languages / frameworks / data & tools), no images
5. **`activity`** — stat cards (only visual/graphic element on the page)
6. **`reach me`** — one line of plain markdown links, no badge images

Never use a centered hero, never render skills as logo-badge rows — those are the two things that make profile READMEs look interchangeable. Collapsing repo groups behind `<details>` is the signature structural move: content density stays high without a wall of tables on first paint.

## 5. Components

**`whoami` block**
```text
$ whoami
name     <Full Name>
based_in <Location>
build    <one-line personal thesis>
online   <primary links, space-dot-separated>
```

**Repo group**
```html
<details>
<summary><strong>emoji + lowercase group name</strong></summary>

- **[Repo Name](url)** — `Tag` `Tag` — one clause, lowercase start, no trailing period.
</details>
```

**Stack line** — one line per category, space-separated inline code, no icons:
```
`Python` `Java` `C++`
```

## 6. Applying elsewhere

```css
:root { --color-primary: #9F1239; --color-accent: #334155; --color-text: #1F2328; }
@media (prefers-color-scheme: dark) {
  :root { --color-primary: #FB7185; --color-accent: #94A3B8; --color-text: #E6EDF3; }
}
```
