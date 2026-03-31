# Claude Code Prompt: Propel8 Technology Consulting SPA

## Project Overview

Build a **single-page application (SPA) website** for **Propel8**, a modern technology consulting firm
specializing in data, analytics, and AI solutions. The brand name "Propel8" evokes forward momentum and
acceleration — the "8" suggests infinity, speed, and scale.

---

## Business Context

**Company Name:** Propel8
**Tagline:** *Accelerate Your Data Future*
**Core Focus Areas:**
1. Data Platform Modernization (Snowflake, Databricks)
2. Open-source, cost-efficient data aggregation & pipeline solutions
3. AI & Machine Learning enablement
4. Advanced Analytics & Business Intelligence

**Target Clients:** Mid-market to enterprise companies looking to modernize their data infrastructure,
reduce costs, and unlock AI-driven insights.

**Brand Voice:** Confident, expert, forward-thinking, approachable — not corporate-stiff, not startup-casual.

---

## Design Direction

**Aesthetic:** Refined dark-mode editorial — think "precision instrument meets creative agency." Deep navy
and near-black backgrounds with electric accent colors (a vivid teal or electric blue-green). Not purple
gradients. Not generic SaaS blue. Sharp, geometric, technical-yet-human.

**Typography:**
- Display/Headings: A geometric, bold sans-serif with strong personality (e.g., "Syne", "Cabinet
  Grotesk", "Neue Machina", or "Clash Display" — load from Google Fonts or Bunny Fonts)
- Body: A refined, highly readable sans (e.g., "DM Sans", "Plus Jakarta Sans", or "Instrument Sans")
- Monospace accents: Use a monospace font (e.g., "JetBrains Mono") for technical labels, data callouts,
  and code-style elements

**Color Palette (CSS variables):**
```
--bg-primary: #080C14        /* near-black navy */
--bg-secondary: #0D1421      /* slightly lighter navy */
--bg-card: #111827           /* card backgrounds */
--accent-primary: #00E5C3    /* electric teal */
--accent-secondary: #0EA5E9  /* sky blue */
--text-primary: #F0F4FF      /* off-white */
--text-secondary: #8B9AB5    /* muted blue-gray */
--border-subtle: #1E2D45     /* subtle border */
--gradient-hero: linear-gradient(135deg, #00E5C3 0%, #0EA5E9 100%)
```

**Motion & Animation:**
- Smooth fade-up-stagger on page load for hero elements (CSS keyframes with animation-delay)
- Intersection Observer for scroll-triggered reveals on each section
- Subtle parallax depth on hero background elements
- Hover states on cards: slight lift (translateY -4px), border glow using accent color box-shadow
- Animated counter numbers (count up from 0) for stats section when scrolled into view
- Smooth scroll behavior for nav anchor links

**Layout:**
- Full-width sections with generous padding
- Asymmetric hero: text left, animated visual/graphic right
- Cards in a responsive CSS Grid (auto-fill, minmax)
- One dramatic "breaking" layout element — e.g., a full-bleed angled divider between sections
  (`clip-path: polygon(0 0, 100% 5%, 100% 100%, 0 95%)`)

---

## Technical Requirements

**Stack:** Vanilla HTML5 + CSS3 + JavaScript (ES6+) — single `index.html` file, no build tools required.
All fonts loaded via `<link>` from Google Fonts / Bunny Fonts. No external JS frameworks. No jQuery.

**File output:** One self-contained `index.html` with all CSS in a `<style>` block and all JS in a
`<script>` block at the bottom.

**Performance:**
- Use `loading="lazy"` on any images
- CSS custom properties for all design tokens
- No unused CSS — write only what's needed
- Smooth 60fps animations (use `transform` and `opacity` only — never animate `top/left/width/height`)

**Accessibility:**
- Semantic HTML (`<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`)
- ARIA labels on interactive elements
- Focus-visible ring styles for keyboard navigation
- Sufficient color contrast ratios

**Responsiveness:** Fully responsive. Mobile-first breakpoints at 640px, 768px, 1024px, 1280px.
Hamburger menu on mobile that slides in a nav drawer.

---

## Page Structure & Content

### 1. Navigation (sticky, blurs on scroll)
- Logo: "Propel8" wordmark — the "8" in a distinct accent color or weight
- Nav links: Services | Platforms | Solutions | About | Contact
- CTA button: "Start a Conversation" (accent-colored, pill shape)
- On scroll past 60px: adds `backdrop-filter: blur(12px)` and a subtle border-bottom
- Mobile: hamburger → full-screen overlay nav

---

### 2. Hero Section
**Headline (H1):** "Accelerate Your  
Data Future"
*(line break between "Your" and "Data" — "Data Future" renders in gradient text)*

**Subheadline:** "Propel8 partners with ambitious organizations to design, build, and scale modern data
platforms — from Snowflake and Databricks implementations to cost-efficient open-source pipelines that
deliver real AI-ready infrastructure."

**CTA Buttons:**
- Primary: "Explore Our Services"
- Secondary (outline): "View Case Studies"

**Hero Visual (right side):** An animated SVG or CSS-drawn abstract — a geometric "data flow" graphic.
Render this as interconnected nodes and flowing lines using CSS/SVG animation. Nodes pulse softly.
Lines animate along a `stroke-dasharray` path. Use accent colors. This replaces any placeholder image.

**Background:** Deep navy with a very subtle radial gradient glow at the top-left (teal, 8% opacity) and
a fine dot-grid pattern overlay (CSS `radial-gradient` repeating at 20px).

---

### 3. Trust Bar / Logos Section
**Label:** "Trusted technologies we implement"
Display pill-shaped badges (not actual logos — use styled text badges since we have no real logo assets):
`Snowflake` · `Databricks` · `dbt` · `Apache Airflow` · `Apache Iceberg` · `DuckDB` · `Kafka` ·
`Spark` · `Python` · `Terraform`

Style as monospace-font pill badges with subtle border and icon-like emoji or Unicode symbol prefix.

---

### 4. Services Section
**Section Label (small caps, accent color):** "What We Do"
**Section Headline:** "End-to-End Data & AI Expertise"

**Six service cards in a 3-column grid (2 on tablet, 1 on mobile):**

1. **Data Platform Modernization**
   Icon: ◈ (or a geometric SVG icon)
   Description: "Architect and migrate to cloud-native data platforms. We specialize in Snowflake and
   Databricks implementations that scale with your business and cut infrastructure costs."

2. **Open-Source Data Pipelines**
   Icon: ⟁
   Description: "Build cost-efficient, production-grade data pipelines using best-in-class open-source
   tools — dbt, Airflow, Kafka, Iceberg, and DuckDB — without enterprise licensing overhead."

3. **AI & ML Enablement**
   Icon: ⬡
   Description: "Transform your data platform into an AI-ready foundation. From feature stores and model
   serving to LLM integration and RAG architectures, we make AI practical."

4. **Analytics Engineering**
   Icon: ◇
   Description: "Design semantic layers, data models, and self-service BI that give business teams
   trusted, governed access to insights without bottlenecking your data engineers."

5. **Data Strategy & Architecture**
   Icon: △
   Description: "Cut through the noise. We assess your current state, map your goals, and deliver a
   pragmatic roadmap — buy vs. build decisions, platform selection, and migration planning."

6. **DataOps & Platform Engineering**
   Icon: ⊕
   Description: "Bring DevOps discipline to your data stack. CI/CD for dbt, infrastructure-as-code with
   Terraform, observability with Monte Carlo or Great Expectations, and automated testing."

**Card style:** Dark card background, subtle border, accent-colored icon in a small geometric shape badge,
hover lifts and glows. Include a small "→" arrow link at the bottom of each card.

---

### 5. Platform Spotlight Section (Snowflake & Databricks)
**Section Label:** "Platform Expertise"
**Section Headline:** "Deep Expertise in the Platforms That Matter"

Two large feature panels side-by-side (stack on mobile):

**Panel A — Snowflake**
- Badge: "SNOWFLAKE PARTNER"
- Headline: "The Data Cloud, Fully Realized"
- Body: "From initial setup and data migration to performance tuning, cost governance, and Snowpark-based
  ML — we've delivered Snowflake implementations across retail, finance, and healthcare that reduced
  query costs by up to 60% and onboarding time for new data products from weeks to days."
- Feature bullets (with checkmark icons):
  - Zero-copy cloning & time travel for dev/test
  - Dynamic Data Masking & column-level security
  - Snowpark ML and Python UDFs
  - Cost monitoring with resource monitors & query tagging
  - Data sharing and Marketplace integration

**Panel B — Databricks**
- Badge: "DATABRICKS PARTNER"
- Headline: "Unified Analytics at Lakehouse Scale"
- Body: "We architect Unity Catalog governance layers, build Delta Lake pipelines, and operationalize
  ML workflows with MLflow — turning Databricks from a raw tool into a governed, production-grade
  lakehouse that your whole organization trusts."
- Feature bullets:
  - Unity Catalog for fine-grained data governance
  - Delta Live Tables for declarative pipeline engineering
  - MLflow experiment tracking and model registry
  - Photon-accelerated query optimization
  - Structured Streaming for real-time use cases

**Panel style:** Slightly larger cards with a top accent border (gradient line), partner badge as a
small pill, feature bullets with teal checkmarks.

---

### 6. Open Source Solutions Section
**Section Label:** "Cost-Efficient by Design"
**Section Headline:** "Enterprise Power. Open-Source Economics."

**Intro paragraph:** "Not every problem requires an expensive SaaS license. Propel8 designs and builds
production-grade data infrastructure using the modern open-source data stack — giving you full control,
no vendor lock-in, and dramatically lower total cost of ownership."

**Three-column highlight grid:**

1. **Ingestion & Integration** — Apache Kafka, Airbyte, Singer, Fivetran alternatives
2. **Transformation & Modeling** — dbt Core, SQLMesh, data contracts
3. **Storage & Query** — Apache Iceberg, Delta Lake, DuckDB, Trino
4. **Orchestration** — Apache Airflow, Prefect, Dagster
5. **Observability** — Great Expectations, Elementary, OpenMetadata
6. **Compute** — Apache Spark, Ray, Dask

Display as a 3-column grid of minimal cards with tool name, one-line description, and category tag.

---

### 7. Stats / Social Proof Bar
Four stats in a horizontal row (stack 2x2 on mobile), animated count-up on scroll:

- **50+** — Data Platform Implementations
- **$4M+** — Client Infrastructure Savings Delivered
- **12** — Open-Source Tools in Our Production Stack
- **100%** — Projects Delivered On Scope

Style: Large animated number in gradient text, label below in muted text. Full-width dark band with
subtle top/bottom borders.

---

### 8. Why Propel8 Section
**Section Headline:** "Why Teams Choose Propel8"

**Four differentiator cards in a 2x2 grid:**

1. **Practitioners, Not PowerPoints** — "Our consultants have built production data platforms, not just
   advised on them. Every recommendation comes from hands-on experience."

2. **Platform Agnostic, Cost Obsessed** — "We're not paid to push any vendor. We find the right tool —
   commercial or open-source — for your specific constraints and goals."

3. **Speed to Value** — "We use proven accelerators, templates, and patterns to compress implementation
   timelines. Faster time to insight without cutting corners."

4. **Embedded, Not Extractive** — "We build your team's capabilities alongside the platform. When we
   leave, your team can own it."

---

### 9. Process Section
**Section Label:** "How We Work"
**Section Headline:** "A Clear Path from Problem to Platform"

Horizontal timeline (scrollable on mobile) with 4 steps connected by a line:

1. **Discover** — Assess current state, define goals, map data landscape
2. **Design** — Architecture blueprints, platform selection, roadmap
3. **Build** — Agile delivery sprints, embedded engineers, weekly demos
4. **Scale** — Handoff enablement, runbooks, ongoing support options

Each step: number badge, title, description, connecting line/arrow between steps.

---

### 10. CTA / Contact Section
**Full-width section with a dramatic background** — use a mesh gradient or the dot-grid with a strong
radial glow at center.

**Headline:** "Ready to Propel Your Data Forward?"
**Subheadline:** "Whether you're modernizing a legacy warehouse, evaluating Snowflake vs. Databricks,
or building your first AI-ready data platform — let's talk."

**Contact form (functional HTML form — no backend needed, use `mailto:` action or Formspree):**
- Name (text input)
- Company (text input)
- Email (email input)
- What are you looking to solve? (textarea, 4 rows)
- Submit button: "Start the Conversation →"

**Form style:** Dark inputs with subtle border, focus state glows with accent color, full-width on mobile.

**Below form:** Three contact alternatives in a row:
- 📧 admin@propel8.com
- 💼 LinkedIn (https://www.linkedin.com/in/link2rahul/)
- 📅 "Book a 30-min intro call" (https://calendar.app.google/vEFuXKgP6ySzAuXi8)

---

### 11. Footer
- Logo + tagline left
- Four-column link grid: Services | Platforms | Resources | Company
- Bottom bar: "© 2025 Propel8 Consulting. All rights reserved." + Privacy Policy | Terms links
- Subtle top border, same dark background

---

## Additional Technical Details

**Smooth Scroll:** `scroll-behavior: smooth` on `html` element. All nav links use `href="#section-id"`.

**Active Nav State:** Use IntersectionObserver to highlight the active nav link as user scrolls.

**Hamburger Menu (mobile):**
- Three-line icon transforms to X on open (CSS transition)
- Full-screen nav overlay slides in from right
- Closes on nav link click

**Animated Hero Nodes (SVG):**
Generate an inline SVG with 8–12 circles (nodes) and connecting lines. Animate node opacity with
`@keyframes pulse` (staggered delays). Animate line `stroke-dashoffset` to create a "data flowing
through" effect. Use `--accent-primary` and `--accent-secondary` for colors.

**Intersection Observer Animations:**
All sections start with `opacity: 0; transform: translateY(30px)` and transition to
`opacity: 1; transform: translateY(0)` with `transition: all 0.6s cubic-bezier(0.16, 1, 0.3, 1)`
when they enter the viewport (add `.visible` class via JS).

**Counter Animation:**
For the stats section, animate numbers from 0 to their target value over 1.5s using
`requestAnimationFrame` and an easing function when the section becomes visible.

---

## Quality Bar

The final output must feel like it was designed by a senior product designer and built by a senior
frontend engineer. It should be immediately credible to a Fortune 500 CTO evaluating a consulting
partner. Zero placeholder copy — all content is final as specified above. Zero broken layouts at any
viewport width. The hero data-flow SVG animation must be present and working.

Do not use stock photo placeholders (`<img>` with no src). All visuals must be CSS or SVG generated.