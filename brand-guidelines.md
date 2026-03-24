# Exchange Brand Guidelines

> **Source:** Exchange Brand Playbook — Figma Slides  
> https://www.figma.com/slides/Oyb9M17fbUWZl4C7ZTO3jQ/Exchange-Brand-Playbook  
>
> This document summarises the brand principles as extracted from the Figma Brand Playbook
> and cross-referenced with the XDS design system tokens.  
> For the full visual presentation including imagery, illustrations, and layout examples,
> open the Figma Slides file directly.

---

## 1. Brand Identity

**Product name:** Exchange (by Crypto.com)  
**Full context:** crypto.com/exchange  
**Audience:** Active traders — from retail to professional  
**Tone:** Precise, confident, performance-first

---

## 2. Colour

The Exchange brand is **dark-first**. All surfaces, UI, and marketing visuals use the dark palette as the canonical expression of the brand.

### Primary Brand Colour
| Swatch | Hex | Token | Use |
|---|---|---|---|
| Brand Blue 500 | `#026AB8` | `--xds-color-brand` | Primary CTAs, links, interactive elements |
| Brand Blue 200 | `#92D1FF` | `--xds-color-brand-light` | Dark-mode text highlights, accent fills |
| Brand Blue 900 | `#0B1B26` | `--xds-color-blue-900` | Tinted accent backgrounds |

### Semantic Colours
| Role | Hex | Token |
|---|---|---|
| Success / Positive / Gain | `#00DC82` | `--xds-text-success` |
| Success bg | `#09B870` | `--xds-bg-success` |
| Error / Negative / Loss | `#FE4A6B` | `--xds-text-destructive` |
| Error bg | `#FC3055` | `--xds-bg-destructive` |
| Warning | `#F7B721` | `--xds-text-warning` |
| Warning bg | `#BE8004` | `--xds-bg-warning` |

### Dark Theme Surface Palette
| Layer | Hex | Token | Description |
|---|---|---|---|
| Page | `#09090A` | `--xds-bg-primary` | Deepest background (Slate/950) |
| Panel / Card | `#141416` | `--xds-bg-widgets` | Cards, menus, sheets (Slate/900) |
| Section | `#1B1B1F` | `--xds-bg-muted` | Subtle grouping (Slate/850) |
| Secondary | `#28292E` | `--xds-bg-secondary` | Inputs, chips, pills (Slate/800) |
| Tooltip | `#464853` | `--xds-bg-tooltip` | Tooltips (Slate/700) |

### Text
| Role | Hex | Token |
|---|---|---|
| Primary | `#FFFFFF` | `--xds-text-primary` |
| Secondary | `#9597A8` | `--xds-text-secondary` |
| Muted | `#7B7D8E` | `--xds-text-muted` |
| Accent / Link | `#92D1FF` | `--xds-text-accent` |

---

## 3. Typography

### Primary Typeface
**Inter Variable** — Used for all UI text, headings, and marketing copy.

- Download: [rsms.me/inter](https://rsms.me/inter)
- Google Fonts: [fonts.google.com/specimen/Inter](https://fonts.google.com/specimen/Inter)
- CSS import:
  ```html
  <link href="https://fonts.googleapis.com/css2?family=Inter:ital,opsz,wght@0,14..32,100..900;1,14..32,100..900&display=swap" rel="stylesheet">
  ```

### Monospace (for data/numbers)
**SF Mono** (macOS) → **Fira Code** (cross-platform fallback)
Used for: prices, volumes, trade quantities, wallet addresses.

### Type Scale (from Figma)
| Style | Size | Weight | Line Height | Use |
|---|---|---|---|---|
| Heading 1 | 32px | 400 | 52px | Page titles |
| Heading 2 | 24px | 400 | 40px | Section headers |
| Heading 3 | 18px | 400 | 28px | Sub-section headers |
| Body 1 | 14px | 400 | 20px | Primary body text |
| Body 2 | 12px | 400 | 16px | Secondary body, captions |
| Body 3 | 10px | 400 | 14px | Micro-text, timestamps |
| Label 1 | 14px | 500 | 20px | Form labels, button text |
| Label 2 | 12px | 500 | 16px | Tags, badges, meta |
| Link 1 | 14px | 500 | 20px | Inline links |
| Link 2 | 12px | 500 | 16px | Small inline links |

---

## 4. Brand Principles

### Dark-First Design
- Never use white/light backgrounds on Exchange product surfaces
- The dark palette (`#09090A` → `#141416`) creates the immersive trading environment
- Avoid light mode unless explicitly building a light theme variant

### Data Clarity
- Numbers are always **white** (`#FFFFFF`) or monochrome — never coloured unless indicating P&L direction
- Positive values → `#00DC82` (green)
- Negative values → `#FE4A6B` (red)
- Use monospace font for all price/quantity fields

### Colour Meaning — Strictly Enforced
| Colour | Semantic Use | Never Use For |
|---|---|---|
| Blue `#026AB8` | CTAs, links, primary interactions | Status indicators, P&L |
| Green `#00DC82` | Gains, success, long positions | General highlights |
| Red `#FE4A6B` | Losses, errors, short positions, danger actions | Warnings |
| Yellow `#F7B721` | Warnings, pending states, VIP | Primary actions |
| Light Blue `#92D1FF` | Accent text, highlights on dark bg | Background fills |

### Hierarchy
1. One primary CTA per view (`.xds-btn-primary` with blue)
2. Secondary actions use ghost or outlined style
3. Destructive actions (deactivate, delete) always use `.xds-btn-danger`

---

## 5. Iconography

- Use the **XDS Global Icon v2** icon set (Figma page: `↳ icons - Global Icon v2`)
- Icon sizes: 16px, 20px, 24px (standard), 32px
- Icons always match the text colour context (`--xds-text-primary`, `--xds-text-secondary`, etc.)
- Never apply brand blue to icons as a fill unless it is an interactive state

---

## 6. Spacing & Layout

Always use the 8-point grid system via tokens:

```
4px  (--xds-space-2)   ← Tight spacing between inline elements
8px  (--xds-space-4)   ← Default gap within components
12px (--xds-space-6)   ← Gap between related items
16px (--xds-space-8)   ← Standard padding inside cards/panels
24px (--xds-space-12)  ← Section gap
32px (--xds-space-16)  ← Large section gap
48px (--xds-space-24)  ← Page section separation
```

---

## 7. Border & Elevation

### Borders
- Default border: `1px solid var(--xds-border)` → `#28292E`
- Input/interactive border: `1px solid var(--xds-border-input)` → `#5D606F`
- Focus ring: `var(--xds-ring)` → `#B1B2BF`
- Border radius: prefer `--xds-radius-sm` (4px) for inputs, `--xds-radius-xl` (12px) for cards

### Shadows (from Figma effect styles)
| Level | Value | Use |
|---|---|---|
| xs | `0 1px 3px rgba(0,0,0,0.40)` | Subtle lift |
| sm | `0 2px 8px rgba(0,0,0,0.50)` | Default card shadow |
| md | `0 4px 16px rgba(0,0,0,0.60)` | Popovers |
| lg | `0 8px 32px rgba(0,0,0,0.70)` | Menus, dropdowns |
| xl | `0 16px 48px rgba(0,0,0,0.80)` | Bottom sheets, modals |

---

## 8. Component Rules

### Buttons
- Radius: `4px` (`--xds-radius-sm`)
- Height: `32px` (sm) / `40px` (md, default) / `48px` (lg)
- Font weight: 600 (semibold)
- Primary bg: `#026AB8` → hover: `#1F86D1`

### Cards
- Background: `#141416` (`--xds-bg-widgets`)
- Border: `1px solid #28292E`
- Radius: `12px` (`--xds-radius-xl`)
- Padding: `32px` (`--xds-space-16`)

### Status Badges (Campaign Lifecycle)
| Status | Background | Text | Border |
|---|---|---|---|
| Draft | `rgba(123,125,142,0.16)` | `#9597A8` | `#28292E` |
| Scheduled | `rgba(146,209,255,0.16)` | `#92D1FF` | `rgba(146,209,255,0.30)` |
| Active | `rgba(9,184,112,0.16)` | `#00DC82` | `rgba(9,184,112,0.30)` |
| Ended | `rgba(247,183,33,0.16)` | `#F7B721` | `rgba(247,183,33,0.30)` |
| Deactivated | `rgba(252,48,85,0.16)` | `#FE4A6B` | `rgba(252,48,85,0.30)` |

---

## 9. Accessing the Full Brand Playbook

The complete Exchange Brand Playbook (Figma Slides) contains:
- Logo usage rules and clearspace
- Brand photography and illustration guidelines
- Motion and animation principles
- Marketing layout templates
- Co-branding rules

👉 **Open in Figma:** https://www.figma.com/slides/Oyb9M17fbUWZl4C7ZTO3jQ/Exchange-Brand-Playbook

> Note: Access requires membership in the Crypto.com Figma organisation.

---

## 10. Quick Reference — Key Hex Values

```css
/* Core brand */
--exchange-brand:        #026AB8;
--exchange-brand-accent: #92D1FF;

/* Surfaces */
--exchange-bg:           #09090A;
--exchange-panel:        #141416;
--exchange-surface:      #28292E;

/* Text */
--exchange-text:         #FFFFFF;
--exchange-text-dim:     #9597A8;
--exchange-text-muted:   #7B7D8E;

/* Status */
--exchange-green:        #00DC82;
--exchange-red:          #FE4A6B;
--exchange-yellow:       #F7B721;
```
