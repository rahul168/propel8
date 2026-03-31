# Propel8 SPA — Implementation Plan

## Context
Build a self-contained single-page application for Propel8, a technology consulting firm. All content, styles, and scripts live in one `index.html` file. Hosted via **GitHub Pages** — no build step required.

---

## Output Files

| File | Purpose |
|---|---|
| `index.html` | Entire SPA — HTML + `<style>` + `<script>` |
| `README.md` | Repo description + GitHub Pages deploy instructions |

---

## Implementation Steps

### Step 1 — Document Skeleton
- `<!DOCTYPE html>`, lang, charset, viewport meta
- Google Fonts `<link>`: **Syne** (display headings), **DM Sans** (body), **JetBrains Mono** (monospace accents)
- Empty `<style>` block in `<head>`; empty `<script defer>` at bottom of `<body>`
- CSS custom properties (design tokens) at `:root`

**Design Tokens:**
```css
--bg-primary: #080C14
--bg-secondary: #0D1421
--bg-card: #111827
--accent-primary: #00E5C3
--accent-secondary: #0EA5E9
--text-primary: #F0F4FF
--text-secondary: #8B9AB5
--border-subtle: #1E2D45
--gradient-hero: linear-gradient(135deg, #00E5C3 0%, #0EA5E9 100%)
```

---

### Step 2 — Navigation
- Sticky `<nav>` with `position: sticky; top: 0; z-index: 100`
- Logo: "Propel" + `<span>` "8" in `--accent-primary`
- Links: Services | Platforms | Solutions | About | Contact (anchor `href="#section-id"`)
- CTA button: "Start a Conversation" — pill-shaped, accent background
- On scroll >60px: JS adds `.scrolled` class → `backdrop-filter: blur(12px)` + subtle bottom border
- Mobile: hamburger icon (3 lines → X transition) → full-screen overlay nav slides in from right; closes on link click

---

### Step 3 — Hero Section
- Asymmetric 2-column CSS Grid: text left, SVG graphic right
- H1: "Accelerate Your / Data Future" — "Data Future" in gradient clip text
- Subheadline paragraph
- Two CTA buttons: primary filled + secondary outline
- Background: deep navy + radial glow (teal, 8% opacity top-left) + dot-grid overlay via `radial-gradient` repeating at 20px
- **Animated SVG** (inline): 8–12 circle nodes + connecting `<line>`/`<path>` elements
  - Node `@keyframes pulse`: opacity 0.3→1→0.3 with staggered `animation-delay`
  - Line `stroke-dasharray` + animated `stroke-dashoffset` for "data flowing" effect
  - Colors: `--accent-primary` and `--accent-secondary`

---

### Step 4 — Trust Bar
- Label: "Trusted technologies we implement" (small, muted, monospace)
- 10 pill badges in monospace font: Snowflake · Databricks · dbt · Apache Airflow · Apache Iceberg · DuckDB · Kafka · Spark · Python · Terraform
- Each badge: subtle border (`--border-subtle`), Unicode/emoji prefix symbol

---

### Step 5 — Services Section
- Section label: "WHAT WE DO" (small caps, accent color)
- Section headline: "End-to-End Data & AI Expertise"
- 6 cards in a responsive CSS Grid (`repeat(auto-fill, minmax(300px, 1fr))`)
- Cards: dark background, subtle border, geometric Unicode icon in accent badge, description, "→" arrow link
- Hover: `translateY(-4px)` + `box-shadow` accent glow

| # | Title | Icon |
|---|---|---|
| 1 | Data Platform Modernization | ◈ |
| 2 | Open-Source Data Pipelines | ⟁ |
| 3 | AI & ML Enablement | ⬡ |
| 4 | Analytics Engineering | ◇ |
| 5 | Data Strategy & Architecture | △ |
| 6 | DataOps & Platform Engineering | ⊕ |

---

### Step 6 — Platform Spotlight (Snowflake & Databricks)
- Section label: "PLATFORM EXPERTISE"
- Section headline: "Deep Expertise in the Platforms That Matter"
- 2 large side-by-side panels (stack on mobile)
- Each panel: gradient top border line, partner badge pill, headline, body paragraph, 5 feature bullets with teal checkmarks (✓)

---

### Step 7 — Open Source Solutions Section
- Section label: "COST-EFFICIENT BY DESIGN"
- Section headline: "Enterprise Power. Open-Source Economics."
- Intro paragraph
- 6 cards in 3-column grid (2 on tablet, 1 on mobile):
  1. Ingestion & Integration — Kafka, Airbyte, Singer
  2. Transformation & Modeling — dbt Core, SQLMesh
  3. Storage & Query — Iceberg, Delta Lake, DuckDB, Trino
  4. Orchestration — Airflow, Prefect, Dagster
  5. Observability — Great Expectations, Elementary, OpenMetadata
  6. Compute — Spark, Ray, Dask
- Each card: category tag, tool names, one-line description

---

### Step 8 — Stats Bar
- Full-width dark band, subtle top/bottom borders
- 4 stats in a horizontal row (2×2 on mobile):
  - **50+** Data Platform Implementations
  - **$4M+** Client Infrastructure Savings Delivered
  - **12** Open-Source Tools in Our Production Stack
  - **100%** Projects Delivered On Scope
- Large number in gradient text; label in muted text
- **Animated count-up**: `requestAnimationFrame` + ease-out, triggers once via `IntersectionObserver`

---

### Step 9 — Why Propel8 Section
- Section headline: "Why Teams Choose Propel8"
- 2×2 grid of 4 differentiator cards:
  1. Practitioners, Not PowerPoints
  2. Platform Agnostic, Cost Obsessed
  3. Speed to Value
  4. Embedded, Not Extractive

---

### Step 10 — Process Timeline
- Section label: "HOW WE WORK"
- Section headline: "A Clear Path from Problem to Platform"
- Horizontal 4-step timeline with connecting line between steps
- Each step: numbered circle badge, title, description
- On mobile: vertical layout or horizontal scroll

| Step | Title | Description |
|---|---|---|
| 1 | Discover | Assess current state, define goals, map data landscape |
| 2 | Design | Architecture blueprints, platform selection, roadmap |
| 3 | Build | Agile delivery sprints, embedded engineers, weekly demos |
| 4 | Scale | Handoff enablement, runbooks, ongoing support options |

---

### Step 11 — Contact / CTA Section
- Full-width section with dot-grid + strong radial glow background
- Headline: "Ready to Propel Your Data Forward?"
- Subheadline paragraph
- HTML contact form (`action="mailto:hello@propel8.io" method="POST" enctype="text/plain"`):
  - Name, Company, Email inputs
  - Textarea: "What are you looking to solve?" (4 rows)
  - Submit: "Start the Conversation →"
- Form inputs: dark background, subtle border, accent glow on `:focus`
- Below form — 3 contact alternatives: 📧 hello@propel8.io | 💼 LinkedIn | 📅 Book a call

---

### Step 12 — Footer
- Left: Logo + tagline "Accelerate Your Data Future"
- Center/right: 4-column link grid — Services | Platforms | Resources | Company
- Bottom bar: "© 2025 Propel8 Consulting LLC. All rights reserved." + Privacy Policy | Terms
- Subtle top border, `--bg-primary` background

---

### Step 13 — JavaScript Behaviors
- **Sticky nav scroll**: `window.addEventListener('scroll')` → adds `.scrolled` at 60px
- **Hamburger menu**: toggle `.open` on `<nav>`, overlay slides in; close on link click
- **IntersectionObserver — section reveals**: all sections start `opacity:0; transform:translateY(30px)`; observer adds `.visible` → `opacity:1; translateY(0)` with `transition: 0.6s cubic-bezier(0.16,1,0.3,1)`
- **IntersectionObserver — active nav**: highlights matching nav link as sections scroll into view
- **Counter animation**: parses `data-target` on stat elements, counts up over 1.5s using `requestAnimationFrame` + ease-out easing, triggers once

---

### Step 14 — Responsiveness & Accessibility Polish
- Verify all grids collapse correctly at 640 / 768 / 1024 / 1280px breakpoints
- Add `prefers-reduced-motion` media query to disable animations
- `aria-label` on nav, hamburger button, form fields
- `:focus-visible` ring styles for keyboard navigation
- Confirm color contrast ratios meet WCAG AA

---

### Step 15 — README & GitHub Pages Setup
- `README.md` with: project description, local preview instructions, GitHub Pages deploy steps
- Verify `index.html` works opened directly as `file://` in browser
- Push to GitHub repo; enable Settings → Pages → main / (root)

---

## Verification Checklist
- [ ] All 11 sections render correctly
- [ ] Hero SVG animation runs (nodes pulse, lines flow)
- [ ] Counter animation triggers once on scroll
- [ ] Section reveal animations work on scroll
- [ ] Nav scroll behavior (blur + border) works
- [ ] Hamburger menu opens/closes correctly on mobile (375px)
- [ ] All grids collapse at correct breakpoints
- [ ] Form submits to mailto action
- [ ] No broken layouts at any viewport width
- [ ] Keyboard navigation works (focus rings visible)
- [ ] GitHub Pages URL loads correctly
