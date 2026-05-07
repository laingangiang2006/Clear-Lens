# Clear Lens — News Bias Detector

## Project Overview
ClearLens is a high-fidelity media literacy tool built for **Next Byte Hacks V2**. It empowers readers to "see past the spin" by identifying political framing, loaded language, and missing perspectives in news articles through real-time URL analysis.

## Core Features
- **Smart Bias Analysis Engine:** A local, research-backed analysis engine that profiles 50+ major news sources (BBC, Guardian, Reuters, Fox News, NYT, Breitbart, etc.) with pre-calibrated bias scores and credibility ratings — no API key required.
- **Interactive Bias Spectrum:** An animated visual scale that positions an article's political lean from "Strongly Progressive" to "Strongly Conservative" with a sliding marker.
- **URL Keyword Detection:** Scans article URL paths for politically-loaded keywords (e.g. `climate-crisis`, `border-security`, `woke-agenda`) to dynamically adjust bias scores beyond the source's baseline.
- **Loaded Language Detection:** Identifies rhetorical terms with per-term explanations of why each phrase carries political weight, categorised by left, right, and neutral lean.
- **Missing Perspectives:** Automatically surfaces viewpoints absent from the article's framing, matched to the source's editorial stance.
- **Framing Strategy Analysis:** Describes the structural narrative approach used by the article (e.g. systemic framing, individual liberty framing, false equivalence).
- **Live News Suggestions:** Fetches real headlines from BBC News, The Guardian, and Reuters via RSS — shuffled on every refresh so suggestions are always current.
- **Complete User Flow:** Includes a searchable, filterable **Analysis Archive**, a full **Methodology** breakdown, an **About** page, and a complete **Authentication Suite** (Sign In / Sign Up / Google).
- **Per-User Data Persistence:** All analyses are saved to `localStorage` per user account. Guest analyses are stored separately. Sessions persist across page reloads.

## Technical Implementation
ClearLens is a single-file application (`index.html`) built with **Vanilla HTML, CSS, and JavaScript**, styled with **Tailwind CSS**.

### Analysis Engine
The bias engine operates entirely client-side with no external API dependencies:

- **Source Profile Database:** 50+ outlets mapped to bias scores (−100 to +100) and credibility ratings derived from established media bias research (e.g. Ad Fontes Media, AllSides).
- **URL Path Signal Detection:** Left and right keyword lists are cross-referenced against the article's URL path to apply directional adjustments to the base source score.
- **Loaded Terms Pool:** Curated pools of politically-loaded phrases for left-lean, right-lean, and neutral coverage, each with explanatory context.
- **Variance Simulation:** Small randomised variance is applied per analysis to reflect genuine article-level differences within a source.

### News Feed Integration
Live headlines are fetched from three RSS feeds via the [AllOrigins](https://allorigins.win/) CORS proxy:
- BBC News — `feeds.bbci.co.uk/news/rss.xml`
- The Guardian — `theguardian.com/world/rss`
- Reuters — `feeds.reuters.com/reuters/topNews`

Falls back gracefully to a curated static pool if feeds are unavailable.

### Authentication & Storage
- Sign Up / Sign In with email and password (passwords stored as Base64 in `localStorage` — suitable for demo/hackathon use).
- Google Sign-In simulated for demo purposes.
- All user data, analyses, and sessions are stored in a single `clearlens_data` key in `localStorage`.
- Archive supports search by title/source, filter by bias direction (Left / Center / Right), and sort by date or confidence score.

### Local Setup
1. Clone this repository.
2. Open `index.html` in any modern web browser.
3. No API key or build step required — the app runs entirely in the browser.

## Design System
- **Typography:** Work Sans (Headlines, 700/600 weight), Inter (Body & Labels, 400/600 weight).
- **Palette:** Deep Navy `#091426` (primary), Amber `#fe932c` (accent/secondary), Neutral Greys for surfaces.
- **Aesthetic:** "Precision Instrument" — flat, editorial, high-contrast. No heavy shadows; depth via 1px borders and tonal layering.
- **Components:** Cards with `rounded-xl`, bias spectrum gradient bar, uppercase label-sm tracking, amber focus states on inputs.

## Pages
- **Analysis** — URL input, live analysis result panel, news suggestions, and recent history.
- **Archive** — Full searchable and filterable grid of all past analyses.
- **Methodology** — Explainer covering linguistic deviation, systemic bias detection, framing analysis, and the three-stage processing pipeline.
- **About** — Manifesto, mission statement, feature pillars, team section, and CTA.
- **Sign In** — Email/password login with a Google sign-in option.
- **Sign Up** — Account creation with a split branding and form layout.

## Project Status
Developed for **Next Byte Hacks V2**.
**Deadline:** May 31, 2026.
