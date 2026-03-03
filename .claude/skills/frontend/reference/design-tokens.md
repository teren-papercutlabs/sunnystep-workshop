# Sunnystep Design Tokens

## Primary Colors

| Token | Hex | Usage |
|-------|-----|-------|
| `--ss-orange` | `#f56a19` | Primary brand color, CTAs, headlines, logo |
| `--ss-black` | `#141210` | Body text, dark backgrounds |
| `--ss-white` | `#ffffff` | Light text on dark, backgrounds |

## Secondary Color Palette

### Teal family
| Token | Hex |
|-------|-----|
| `--ss-teal-dark` | `#1f5b65` |
| `--ss-teal-light` | `#d2dee0` |

### Yellow family
| Token | Hex |
|-------|-----|
| `--ss-yellow` | `#fffd9d` |
| `--ss-yellow-light` | `#ffffeb` |

### Purple family
| Token | Hex |
|-------|-----|
| `--ss-purple` | `#4944b2` |
| `--ss-purple-light` | `#dbdaf0` |
| `--ss-lavender` | `#bc8ad6` |
| `--ss-lavender-light` | `#f2e8f7` |

### Green family
| Token | Hex |
|-------|-----|
| `--ss-green` | `#0eb272` |
| `--ss-green-light` | `#cff0e3` |

### Blue family
| Token | Hex |
|-------|-----|
| `--ss-blue` | `#a1ddff` |
| `--ss-blue-light` | `#ecf8ff` |

### Orange tint family
| Token | Hex |
|-------|-----|
| `--ss-orange-dark` | `#f78847` |
| `--ss-orange-mid` | `#f8985e` |
| `--ss-peach` | `#f9a675` |
| `--ss-peach-light` | `#fab48c` |
| `--ss-peach-lighter` | `#fbc3a3` |
| `--ss-peach-lightest` | `#fcd2ba` |

### Warm neutrals (backgrounds)
| Token | Hex |
|-------|-----|
| `--ss-cream` | `#fde1d1` |
| `--ss-cream-light` | `#fef1e8` |
| `--ss-bg-warm` | `#fef8f3` |

## Gradients

- **Orange Gradient**: peach (#f9a675) → light blue (#a1ddff) — warm, uplifting feel
- **Yellow Gradient**: yellow (#fffd9d) → light blue (#a1ddff) — bright, energetic feel

Use gradients for hero backgrounds, product shots, and feature sections. Both gradients feel like sunshine and sky.

## Typography

- **Brand font:** Matter SQ (weights: Light, Regular, Medium, Medium Italic)
- **Fallback:** Arial, sans-serif
- **Web alternative:** If Matter SQ is unavailable, use `Inter` or `DM Sans` from Google Fonts as closest matches

### Font Scale (recommended for web)

| Element | Size | Weight |
|---------|------|--------|
| Hero headline | 48-64px | Medium (500) |
| Section heading | 28-32px | Medium (500) |
| Card title | 18-20px | Medium (500) |
| Body text | 16px | Regular (400) |
| Small text / labels | 13-14px | Regular (400) |
| Badges / tags | 11-12px | Medium (500) |

## Spacing & Radius

- **Border radius:** 16px for cards, 50px for pill buttons/badges, 12px for icons
- **Card shadow:** `0 24px 64px rgba(20, 18, 16, 0.08)`
- **Button shadow:** `0 8px 24px rgba(0, 0, 0, 0.12)`

## Iconography

- All icons on a 32px grid with 2px strokes
- Line-art style, not filled
- Black (`#141210`) on light backgrounds

## Background Pattern

- Primary page background: warm off-white (`#fef8f3` or `#fef1e8`)
- Section dividers: use brand-color full-bleed blocks (orange, purple, teal, green, blue)
- The overall feel is warm, bright, and airy — never cold or clinical

## CSS Variables (copy-paste ready)

```css
:root {
  /* Primary */
  --ss-orange: #f56a19;
  --ss-black: #141210;
  --ss-white: #ffffff;

  /* Teal */
  --ss-teal-dark: #1f5b65;
  --ss-teal-light: #d2dee0;

  /* Yellow */
  --ss-yellow: #fffd9d;
  --ss-yellow-light: #ffffeb;

  /* Purple */
  --ss-purple: #4944b2;
  --ss-purple-light: #dbdaf0;
  --ss-lavender: #bc8ad6;
  --ss-lavender-light: #f2e8f7;

  /* Green */
  --ss-green: #0eb272;
  --ss-green-light: #cff0e3;

  /* Blue */
  --ss-blue: #a1ddff;
  --ss-blue-light: #ecf8ff;

  /* Orange tints */
  --ss-orange-dark: #f78847;
  --ss-orange-mid: #f8985e;
  --ss-peach: #f9a675;
  --ss-peach-light: #fab48c;
  --ss-peach-lighter: #fbc3a3;
  --ss-peach-lightest: #fcd2ba;

  /* Warm neutrals */
  --ss-cream: #fde1d1;
  --ss-cream-light: #fef1e8;
  --ss-bg-warm: #fef8f3;

  /* Gradients */
  --ss-gradient-orange: linear-gradient(135deg, #f9a675, #a1ddff);
  --ss-gradient-yellow: linear-gradient(135deg, #fffd9d, #a1ddff);

  /* Radius */
  --ss-radius-card: 16px;
  --ss-radius-pill: 50px;
  --ss-radius-icon: 12px;

  /* Shadows */
  --ss-shadow-card: 0 24px 64px rgba(20, 18, 16, 0.08);
  --ss-shadow-button: 0 8px 24px rgba(0, 0, 0, 0.12);
}
```

## Logo Rules

- Only use official logo formats (icon, wordmark, wordmark + tagline)
- Logo colors: Sunnystep Orange (`#f56a19`), Black (`#141210`), or White (`#ffffff`) only
- Never stretch, distort, crop, or modify the logo
- Place on clean, low-clutter backgrounds
