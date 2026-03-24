# Exchange Design System — Prototype Kit

The shared CSS foundation for all Exchange back-office and internal prototypes.  
Every new prototype built in Cursor **must** start from this kit.

---

## Figma Sources

| File | Purpose | Link |
|---|---|---|
| XDS — Exchange Design System | Components, tokens, patterns | [Open in Figma](https://www.figma.com/design/S5vzHnfEkTU1uETKnVOl7x/XDS---Exchange-Design-System) |
| Exchange Brand Playbook | Colours, typography, tone of voice | [Open in Figma](https://www.figma.com/slides/Oyb9M17fbUWZl4C7ZTO3jQ/Exchange-Brand-Playbook) |

> When building a new prototype, **always open both Figma files first** before writing any CSS.

---

## Repository Structure

```
exchange-design-system/
├── tokens.css              ← All design tokens as CSS custom properties (--xds-*)
├── components.css          ← Base component classes built on top of tokens
├── starter-template.html   ← Copy-paste starting point for every new prototype
├── README.md               ← This file
└── .cursor/
    └── rules/
        └── exchange-design-system.mdc   ← Cursor rule (auto-applied to all HTML/CSS)
```

---

## Quick Start — New Prototype

1. **Copy `starter-template.html`** into your project folder and rename it
2. The template already imports `tokens.css` and `components.css`
3. Start building — Cursor will automatically enforce design system rules

```html
<!-- At the top of every prototype -->
<link rel="stylesheet" href="path/to/exchange-design-system/tokens.css">
<link rel="stylesheet" href="path/to/exchange-design-system/components.css">
```

---

## Token Reference

### Colours — Brand

| Token | Hex | Use |
|---|---|---|
| `--xds-color-brand-blue` | `#1C6EF2` | Primary CTA, interactive |
| `--xds-color-brand-cyan` | `#00D2FF` | Charts, accents |
| `--xds-color-brand-gold` | `#F0B90B` | VIP, rewards |
| `--xds-color-brand-green` | `#0ECB81` | Gains, success, positive |
| `--xds-color-brand-red` | `#F6465D` | Losses, errors, destructive |

### Colours — Surfaces (Dark Theme)

| Token | Hex | Use |
|---|---|---|
| `--xds-surface-page` | `#0D0D1C` | Page root |
| `--xds-surface-elevated` | `#12122A` | Cards, panels |
| `--xds-surface-overlay` | `#1A1A36` | Modals, dropdowns |
| `--xds-surface-border` | `#2A2A4A` | Dividers, input borders |
| `--xds-surface-hover` | `#1E1E3C` | Hover states |

### Colours — Text

| Token | Use |
|---|---|
| `--xds-text-primary` | Main body text (`#FFFFFF`) |
| `--xds-text-secondary` | Supporting text (`#B0B0C8`) |
| `--xds-text-tertiary` | Captions, placeholders (`#6E6E8A`) |
| `--xds-text-positive` | Gains / success |
| `--xds-text-negative` | Losses / errors |

### Spacing Scale

`--xds-space-{n}` where n maps to: `2→4px`, `4→8px`, `6→12px`, `8→16px`, `10→20px`, `12→24px`, `16→32px`, `20→40px`, `24→48px`

### Typography

| Token | Value |
|---|---|
| `--xds-font-family-base` | Inter, system-ui |
| `--xds-font-size-sm` | 12px |
| `--xds-font-size-base` | 14px |
| `--xds-font-size-md` | 16px |
| `--xds-font-size-lg` | 18px |
| `--xds-font-size-xl` | 20px |
| `--xds-font-size-2xl` | 24px |

---

## Component Classes

### Buttons
```html
<button class="xds-btn xds-btn-primary">Primary</button>
<button class="xds-btn xds-btn-secondary">Secondary</button>
<button class="xds-btn xds-btn-ghost">Ghost</button>
<button class="xds-btn xds-btn-danger">Danger</button>
<button class="xds-btn xds-btn-primary xds-btn-sm">Small</button>
<button class="xds-btn xds-btn-primary xds-btn-lg">Large</button>
```

### Status Badges
```html
<span class="xds-badge xds-badge-active">Active</span>
<span class="xds-badge xds-badge-scheduled">Scheduled</span>
<span class="xds-badge xds-badge-draft">Draft</span>
<span class="xds-badge xds-badge-ended">Ended</span>
<span class="xds-badge xds-badge-deactivated">Deactivated</span>
```

### Cards
```html
<div class="xds-card">
  <h3 class="xds-card-title">Card Title</h3>
  <p class="xds-body xds-text-secondary">Content here.</p>
</div>
```

### Form Inputs
```html
<label class="xds-label-field">Field Name <span class="xds-required">*</span></label>
<input class="xds-input" type="text" placeholder="Enter value">
<select class="xds-select"><option>Option</option></select>
<textarea class="xds-textarea" rows="4"></textarea>
<span class="xds-error-msg">Error message here</span>
```

### Info Blocks
```html
<div class="xds-info-block">Blue info message</div>
<div class="xds-info-block success">Green success message</div>
<div class="xds-info-block warning">Amber warning message</div>
<div class="xds-info-block error">Red error message</div>
<div class="xds-info-block purple">Purple contextual note</div>
```

### Navigation
```html
<nav class="xds-nav">
  <div class="xds-nav-brand">
    <div class="xds-nav-brand-icon">⬡</div>
    EXCHANGE
  </div>
</nav>
```

### Tabs
```html
<div class="xds-tabs">
  <div class="xds-tab active">Tab One</div>
  <div class="xds-tab">Tab Two</div>
  <div class="xds-tab">Tab Three</div>
</div>
```

---

## Updating Tokens from Figma

When the Figma XDS file is updated, sync the tokens as follows:

### Prerequisites
1. Install the **Figma desktop app** (not the browser version)
2. Ensure the Figma MCP plugin is enabled in Cursor settings
3. Open the [XDS Figma file](https://www.figma.com/design/S5vzHnfEkTU1uETKnVOl7x/XDS---Exchange-Design-System) in the desktop app

### Steps
1. In Figma desktop, click on a component or colour swatch to select it
2. In Cursor, ask: *"Extract design tokens from the selected Figma layer and update tokens.css"*
3. Cursor will call `get_variable_defs` and `get_design_context` via the Figma MCP
4. Review the diff, then commit:

```bash
git add tokens.css components.css
git commit -m "Sync design tokens from Figma XDS — [date]"
git push origin main
```

> **Note:** View-seat accounts are limited to 6 Figma MCP calls/month. Full/Dev seat on Org plan gets 200/day.

---

## Cursor Integration

The `.cursor/rules/exchange-design-system.mdc` file is automatically applied by Cursor to all `.html` and `.css` files in any project that references this repo. It enforces:

- Always importing `tokens.css` and `components.css`
- Using `var(--xds-*)` tokens — no hardcoded values
- Dark theme by default
- Correct semantic colour usage
- XDS component classes before custom CSS

To use in a new project, copy `.cursor/rules/exchange-design-system.mdc` into your project's `.cursor/rules/` folder.

---



*Add your prototype here when you publish it.*
