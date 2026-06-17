---
name: generate-brand-assets
description: Generate logos, favicons, and brand icons using AI image generation. Use when creating or updating brand assets, logos, favicons, app icons, or visual identity for a project.
---

# Generate Brand Assets

## When to use

Apply when the user asks to create, regenerate, or rebrand logos, favicons, or icon sets.

## Style extraction

Before generating, read existing brand assets in `assets/` to extract:

- Color palette (note hex values)
- Shape language (rounded, flat, sticker effect, etc.)
- Icon motif and composition

## Generation workflow

1. **Read reference assets** — load current favicon/logo PNGs for style matching.
2. **Logo icon** (`assets/favicon-adjusted.png`) — header/nav icon at ~32–64px. Same sticker style as reference; update motif to match new brand name theme. No long text (too small at display size).
3. **Favicon** (`assets/favicon.png`) — browser tab icon. Must be **visually distinct** from the logo icon (different motif or simplified mark) while keeping the same palette and flat sticker aesthetic.
4. **Full logo (optional)** — horizontal lockup with brand name text when user requests text in the logo file itself.

## Brand palette (Hired Sphere)

| Role | Hex |
|------|-----|
| Background | `#F8DB8C` pale yellow |
| Foreground | `#1C1E2E` navy |
| Sticker border | white offset shadow |

## Generation prompt template

```
Minimalist flat vector app icon, sticker style. Pale yellow (#F8DB8C) rounded square background with white offset drop shadow border. Navy blue (#1C1E2E) [MOTIF DESCRIPTION]. Clean modern professional recruitment brand. No gradients. Rounded geometry.
```

## After generation

1. Save outputs to `assets/favicon-adjusted.png` and `assets/favicon.png`.
2. Update HTML `<link rel="icon">` and `<img class="brand-logo">` references if filenames change.
3. Replace brand name strings across all HTML files and `package.json`.

## Quality checks

- Logo and favicon must not be identical
- Icons readable at 16×16 and 32×32
- Alt text and aria-labels match new brand name
