# Assets

Custom, hand-authored SVG illustrations for the profile README. Every illustration
ships in **both** a dark and a light variant; the README selects between them
automatically with the HTML `<picture>` element and
`prefers-color-scheme` media queries.

| File | Purpose | Theme |
| :--- | :--- | :--- |
| `hero-dark.svg` / `hero-light.svg` | Hero banner (name, headline, location, avatar monogram, animated background) | dark / light |
| `terminal-dark.svg` / `terminal-light.svg` | Animated `whoami` terminal (sequential reveal + blinking cursor) | dark / light |
| `education-dark.svg` / `education-light.svg` | Education card (John Bryce – Tel Aviv) | dark / light |

## Design notes

- **No JavaScript.** All motion is native SVG SMIL (`<animate>`, `<animateTransform>`),
  which renders inside GitHub's `<img>` sandbox.
- **Palette**
  - Dark: bg `#0B1220` / panel `#0F172A` / text `#F8FAFC` / muted `#94A3B8`,
    accent `#7C3AED → #22D3EE → #10B981`.
  - Light: bg `#FFFFFF`/`#F8FAFC` / text `#0F172A` / muted `#475569`,
    accent `#2563EB → #06B6D4 → #10B981`.
- **Accessibility.** Each SVG has `role="img"` and a descriptive `aria-label`; the
  README `<img>` tags carry equivalent `alt` text.
- **Responsive.** SVGs use a `viewBox` and are embedded at `width="100%"`, so they
  scale crisply from mobile to desktop.

## Live data (not stored here)

Statistics (stars, streak, top languages, contribution graph) are **not** committed
as files — they are rendered live from the GitHub API by external widgets, so the
numbers are always current and never hardcoded. The contribution **snake** is the
one generated asset: it is produced by `.github/workflows/snake.yml` and published
to the `output` branch on a schedule.
