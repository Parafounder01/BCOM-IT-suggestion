# B.Com (IT) 2026 — Career Guide Page

A single-file editorial landing page presenting the **B.Com IT 2026 career landscape** — built with the **Ferrari design system** (cinematic editorial aesthetic).

---

## Design System Overview

The page applies Ferrari's marketing design language — luxury-automotive editorial, not a typical career portal. Think full-bleed photography, sharp geometry, scarce red accent, and generous whitespace.

### Canvas & Color

| Token               | Value     | Usage                                            |
| ------------------- | --------- | ------------------------------------------------ |
| Canvas (page floor) | `#181818` | Near-black body background — never pure black    |
| Canvas Elevated     | `#303030` | Cards, panels, secondary surfaces                |
| Canvas Light        | `#ffffff` | White editorial bands (used sparingly)           |
| Rosso Corsa         | `#da291c` | Primary CTAs, key stat numbers, small highlights |
| Ink (text on dark)  | `#ffffff` | Headlines, body emphasis                         |
| Body (text on dark) | `#969696` | Running text                                     |
| Hairline            | `#303030` | 1px dividers, card borders                       |

- **No drop shadows.** Depth comes from brightness-step elevation (`#181818` → `#303030`) and hairlines.
- **Rosso Corsa is scarce.** It only appears on primary CTAs, the pre-footer band headline, stat numbers in the livery band, and a few small highlight elements.

### Typography

**Font:** Inter (Google Fonts) — substitute for the licensed FerrariSans.

| Role              | Size                            | Weight | Letter-Spacing     |
| ----------------- | ------------------------------- | ------ | ------------------ |
| Hero h1           | 80px / 56px / 32px (responsive) | 500    | -1.6px             |
| Section headings  | 36px                            | 500    | -0.36px            |
| Sub-section heads | 26px                            | 500    | 0.195px            |
| Body              | 14px                            | 400    | 0                  |
| CTA labels        | 14px                            | 700    | 1.4px (uppercase)  |
| Nav links         | 13px                            | 600    | 0.65px (uppercase) |
| Caption uppercase | 11px                            | 600    | 1.1px              |

- **Display weight stays at 500.** Never bold. The content and layout do the visual work.
- **CTA and nav labels are uppercase** with generous tracking — luxury-precision feel.
- **Negative letter-spacing on display sizes only** (`-1.6px` to `-0.36px`); body text stays at 0.

### Layout & Spacing

**8px spacing token ladder:**

```
xxxs: 4px  |  xxs: 8px  |  xs: 16px  |  sm: 24px  |  md: 32px
lg: 48px   |  xl: 64px  |  xxl: 96px |  super: 128px
```

- Max content width: **1280px** on editorial bands. Hero photography is full-bleed.
- Section padding: **96px** (`xxl`) for major bands, **128px** (`super`) for hero band depth.
- Generous editorial pacing — cinematic hero fills the viewport, then tighter editorial body sections beneath.

### Shapes

- **Sharp 0px corners (`border-radius: 0`)** on every CTA, card, and band — the brand's signature precision.
- Pill geometry (`border-radius: 9999px`) is reserved for badge labels only.
- Form inputs: `border-radius: 4px`.

### Elevation & Depth

No shadow tiers. Depth is created through:

1. **Brightness-step elevation** — card surfaces step up from `#181818` to `#303030`
2. **Hairlines** — 1px borders at `#303030` (on dark) or `#d2d2d2` (on light)
3. **Full-bleed imagery** — the hero and content sections use photographic depth

---

## Components

### 1. Top Navigation (`top-nav-on-dark`)

Fixed 64px nav with transparent-backdrop blur. Logo placeholder + 5 uppercase nav links (Models, F1, Lifestyle, Owners, Preowned — repurposed as section anchors). Switches to hamburger below 768px.

### 2. Cinema Hero Band (`hero-band-cinema`)

Full-bleed viewport section with a gradient-overlayed background. Headline in 80px display-mega type, supporting body text, and two CTAs — primary Rosso Corsa + outline white with 1px border. Both have 0px sharp corners.

### 3. Livery Band (`livery-band`)

Two full-width Rosso Corsa accent bands that act as visual dividers between major sections. One features a stat callout ("8× sectors available"), the other a percentage highlight ("40% higher starting"). Headline in 36px display-lg type, text white. 96px padding.

### 4. Hairline Tables

Three tables (Placements, Salary by Sector, Government Exams) styled with `1px` hairlines and no border-radius. Alternating row backgrounds on light bands. Company names, roles, CTC ranges, and status tags with small uppercase captions.

### 5. Feature Card Grids

Sharp 0px cards in responsive grids:

- **Hot Sectors** — 3-up card grid with company logos/salary data
- **Certifications** — 5-card row with cost/duration/impact level
- **Skills** — Display cards with large spec-number values (80px weight 700)

### 6. Pre-Footer CTA Band (`cta-band-dark`)

Dark canvas band with centered "Ready to Begin?" headline in 36px display type, single Rosso Corsa CTA. 96px padding.

### 7. Footer (`footer-dark`)

5-column link grid on dark canvas. 64px top padding, 48px bottom. Column headers in small uppercase, links in 13px body-sm. Bottom bar with copyright and Rosso Corsa brand mark.

---

## Responsive Behavior

| Breakpoint | Width       | Changes                                           |
| ---------- | ----------- | ------------------------------------------------- |
| Mobile     | < 640px     | Hero h1 32px, 1-up grids, tighter spacing         |
| Tablet     | 640-1024px  | Hero h1 56px, 2-up grids                          |
| Desktop    | 1024-1280px | Hero h1 80px, 3-up/4-up grids                     |
| Wide       | > 1280px    | Content caps at 1280px; hero full-bleed continues |

- Nav collapses to hamburger at ≤768px
- CTA buttons maintain minimum 48px height (WCAG AAA touch target)

---

## Content Sections

1. **Active Campus Placements** — TCS, Infosys, Wipro, Cognizant, Capgemini, HCLTech + Big 4
2. **Fresher Salary by Sector** — 8 sectors with CTC and monthly in-hand ranges
3. **Government Exams 2026** — SSC CGL, RBI Grade B, SBI PO, IBPS PO/Clerk/SO with status tags
4. **Hot Emerging Sectors** — Data Analytics, Fintech, E-commerce with company-specific CTC data
5. **Certifications** — Microsoft PL-300, Google Data Analytics, SQL, CompTIA Security+, CFI FPAP
6. **Skills That Matter** — SQL, Excel, Power BI, Python, GenAI with demand ratings
7. **Practical Roadmap** — 3-phase timeline (Immediate / Skill Building / Govt Exam Prep)

---

## Technical Notes

- **Single file.** All HTML, CSS, and JavaScript are inlined in `index.html`.
- **No external dependencies** except Google Fonts (Inter) and a placeholder image service.
- **Zero JavaScript libraries** — vanilla JS for hamburger toggle and smooth scrolling.
- **CSS custom properties** for every design token — color, spacing, typography, and layout values are centralized in `:root`.
- **Dark-first.** The default canvas is `#181818`; light bands are the exception, not the rule.
