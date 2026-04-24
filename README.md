# Niamh St John Lynch — Personal Research Website

Personal academic and consulting overview for Niamh St John Lynch, PhD Researcher at Dundalk Institute of Technology (DkIT), registered under Dublin City University (DCU), as part of the DkIT/UCD Collaborative Project on Trustworthy AI-enabled Medical Devices "RegFrAIMs" and funded by Research Ireland.

---

## Live Site 

Deploy `index.html` to any static hosting platform (see [Deployment](#deployment) below).

---

## About

The site provides a professional online presence covering:

- **Doctoral research** at the intersection of regulatory science and AI-enabled medical device quality management, conducted as part of the DkIT/UCD Collaborative Project on Trustworthy AI-enabled Medical Devices
- **Publications** — all 9 items linked directly to the [DkIT STÓR institutional repository](https://eprints.dkit.ie/view/creators/St_John_Lynch=3ANiamh=3A=3A.html)
- **Standards development** — 10+ IEC TC62 committee roles including Sub-Team Lead for AI requirements of IEC 62304 Ed.2, Chair of NSAI/ETC/TC10, CEN-CENELEC AI Task Groups 1 & 2
- **Contact** — live form powered by Formspree, direct email links

---

## Pages

| Page | Description |
|------|-------------|
| **Home** | Hero section, research focus overview, featured publications, standards summary |
| **Research** | Full publication list (9 items, grouped by year), doctoral thesis description, two research figures from published papers, active projects |
| **Standards** | Full IEC TC62 committee listing (10+ groups), CEN-CENELEC AI TG1/TG2, NSAI/ETC/TC10 chair role, key standards reference grid |
| **Contact** | Email links, institutional affiliations, education history, Formspree contact form |

---

## Technical Overview

| Item | Detail |
|------|--------|
| **Format** | Single-file HTML5 (`index.html`) |
| **CSS** | Inline `<style>` block — CSS custom properties, CSS Grid, Flexbox |
| **JavaScript** | Inline `<script>` block — vanilla JS, no frameworks or build tools |
| **Fonts** | Google Fonts: Cormorant Garamond + DM Sans |
| **Form handler** | [Formspree](https://formspree.io) (form ID: `xlgabrqj`) |
| **Dependencies** | None (beyond Google Fonts CDN and Formspree API) |
| **Build process** | None — edit `index.html` directly |

---

## Accessibility

The site targets **WCAG 2.1 Level AA**. Key features:

- **Skip link** — "Skip to main content" visible on keyboard focus
- **Keyboard navigation** — all interactive elements operable via Tab, Enter, Space
- **Screen reader support** — `aria-hidden` on inactive pages, `aria-current="page"` on active nav, `role="region"` with labels on all page sections
- **Live regions** — form success/error messages announced via `aria-live`
- **Colour contrast** — all text meets AA contrast ratios against their backgrounds
- **Reduced motion** — `prefers-reduced-motion` disables all animations and transitions
- **Focus indicators** — visible `:focus-visible` rings on all interactive elements
- **Semantic landmarks** — `<nav>`, `<main>`, `<footer>` with appropriate ARIA labels

See `Website_Design_Document_NiamhStJohnLynch.docx` for the full WCAG compliance table.

---

## Responsive Design

Built mobile-first. No media query frameworks — layout uses CSS Grid `auto-fit` / `minmax` throughout.

| Viewport | Behaviour |
|----------|-----------|
| **Mobile** (`< 768px`) | Single column, hero affiliations card hidden, hamburger menu replaces nav links |
| **Tablet** (`≥ 768px`) | Two-column grids, hero two-column layout, contact side-by-side |
| **Desktop** (`≥ 1100px`) | Three-column card grids, 1100px max-width centred content |

The `<meta viewport>` tag does **not** restrict user zoom (`maximum-scale` is not set).

---

## Mobile Navigation

On viewports ≤ 768px the horizontal nav links are replaced by a hamburger menu (☰ icon). Tapping it opens a full-width dropdown with each page link on its own row. The menu closes automatically when:

- A navigation link is tapped
- The user taps anywhere outside the nav bar
- The `Escape` key is pressed

The toggle button uses `aria-expanded`, `aria-controls`, and `aria-label` so screen readers announce the open/closed state correctly.

---

## Research Figures

The Research page includes two inline SVG figures drawn from published papers:

| Figure | Source |
|--------|--------|
| **AIeMD Standards Landscape** — four-layer diagram (Regulatory Framework → International AI Standards → Medical Device Technical Standards → Development & Quality Processes) | St John Lynch et al. (2024) *AI-Enabled Medical Device Standards: A Multidisciplinary Literature Review.* EuroSPI'24 |


Figure carries full citations with links to DkIT STÓR, and have `role="img"` with `aria-label` descriptions for screen reader users.

---

## Stats Strip

A full-width stats strip sits between the hero and the Research Focus section on the Home page, displaying five key figures:

| Stat | Value |
|------|-------|
| Years in Medical Devices | 25+ |
| Publications | 10+ |
| Standards Committees | 10+ |
| Postgraduate Degrees | 5 |
| National Committee Chair | 1 |

---

## Education

Displayed on the Contact page alongside professional affiliations:

- BSc (Hons) Cognitive Science — University of Hertfordshire
- MSc Neuropharmacology — NUI Galway
- MSc Software Engineering & Database Technologies — NUI Galway & Regis University (US)
- MSc Work & Organisational Psychology — University of Limerick
- Postgraduate Diploma in TechInnovate — NUI Galway

---

## Deployment

The site is a single file — no server, no build step required.

### GitHub Pages

```bash
# In your repository root
cp index.html docs/index.html   # or use root
# Enable Pages in repository Settings → Pages → Deploy from branch
```
---

## Updating Content

### Adding a Publication

1. Open `index.html` and locate the Research page section (`id="page-research"`).
2. Find the relevant year group (`<div class="pub-year-header">YEAR</div>`), or add a new one.
3. Copy an existing `.pub-item` block and update:
   - `.pub-type` — e.g. `Journal Article`
   - `.pub-status` badge class — `status-press`, `status-submitted`, or `status-published`
   - `.pub-title` `<a href="...">` — link to DkIT STÓR record
   - `.pub-authors` — author list
   - `.pub-venue` — journal/conference, year, DOI if available

### Updating a Standards Role

Locate the relevant `.std-item` block in the Standards page section (`id="page-standards"`) and edit the `.std-title`, `.std-desc`, and `.std-role` spans directly.

### Updating the Contact Form

The Formspree form ID (`xlgabrqj`) appears in two places in `index.html`:

```html
<!-- Hidden input (line ~636) -->
<input type="hidden" name="_formspree_id" value="xlgabrqj" />

<!-- JavaScript constant (line ~663) -->
const FORMSPREE_ID = 'xlgabrqj';
```

Replace both values if the form ID changes.

---

## Contact

| | |
|-|--|
| **Email** | [niamh@stjohnlynch.com](mailto:niamh@stjohnlynch.com) |
| **Email (DkIT)** | [niamh.stjohnlynch@dkit.ie](mailto:niamh.stjohnlynch@dkit.ie) |
| **Publications** | [DkIT STÓR Repository](https://eprints.dkit.ie/view/creators/St_John_Lynch=3ANiamh=3A=3A.html) |

---

## Licence

All site content © Niamh St John Lynch. All rights reserved.
